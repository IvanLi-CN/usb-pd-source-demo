# TPS55288 方案设计笔记（DC‑DC 段）

## 1. 需求描述（完善）
- 输入范围：`12–24 VDC`（上电/掉电斜率受控；来自受限母线而非汽车级，允许常规EMI抑制与浪涌/尖峰吸收）。
- 输出范围与能力：`最高 20 V / 5 A（100 W）`；支持 USB‑PD 固定电压 5/9/15/20 V，后续可评估 PPS 步进（20 mV）。
- 控制模式：初期以协议芯片（如 `SW2303`）通过 `FB` 实现调压；若具备 I2C/AVS/PPS 能力，优先与 TPS55288 I2C 联控（获得线缆压降补偿、限流与斜率可编程）。
- 效率/热目标：20 V 5 A 满载效率≥94%（自然风/轻风冷）；关键器件结温 < 125 ℃（环境 25–40 ℃）。
- EMC：满足常规开关电源 EMI 要求；支持固定频率/展频/同步功能以避让干扰；开关频率初设 `400–800 kHz`，综合效率/体积/EMI 折衷。
- 保护：过压、限流、短路打嗝、过温；源端 PD 广告电流与硬件 OCP 一致；5 A 输出需 E‑Marker 线缆。

## 2. 参考资料（本仓库 Markdown 摘要）
- 输入范围 2.7–36 V：`docs/datasheets/tps55288-datasheet.md:38`
- 集成 Buck 侧门极驱动（DR1H/DR1L 1 A 源/1.8 A 灌；Boost 模式 Buck 上管常导通）：`docs/datasheets/tps55288-datasheet.md:194`–`200`
- 电缆压降补偿（CDC 寄存器/外部）：`docs/datasheets/tps55288-datasheet.md:402`–`405`
- PPS 支持与步进：`docs/datasheets/tps55288-datasheet.md:671`，`923`
- 官方能力陈述（“12 V 输入可达 100 W”）：`docs/datasheets/tps55288-datasheet.md:708`

> 注：更多寄存器与环路补偿细节见上述 Markdown 摘要与原始 PDF。

## 3. 关键工况与简要初算
以两端典型工况快速估算 Buck 两只外置 MOSFET 的应力与损耗：
- Boost 工况（12 V → 20 V / 5 A，η≈95%）：
  - 输入电流约 `IIN ≈ 20*5/(12*0.95) ≈ 8.8 A`。
  - Buck 侧：上管（DR1H）“常导通”，下管（DR1L）关断；因此 Buck 上管相当于串联通态电阻，损耗近似 `P ≈ IIN² · RDS(on)`。
- Buck 工况（24 V → 20 V / 5 A，η≈95%）：
  - 占空比 `D ≈ Vout/Vin ≈ 0.833`，电感电流近似 5 A。
  - 高边/低边均在开关，导通损耗：`PHS ≈ I²·RDS(on)·D`，`PLS ≈ I²·RDS(on)·(1-D)`；高边还承担主要开关损耗 `Psw ≈ 0.5·Vin·I·(tr+tf)·fs` 及 Coss/Qrr 相关损耗。

由此可见：
- 100 W 场景下，Boost 工况对 Buck 高边 MOSFET 的导通电阻极为敏感；Buck 工况下，高边 MOS 兼顾导通与开关损耗，低边 MOS 更侧重体二极管/Qrr 与 Coss。

## 4. Buck 两只外置 MOSFET 的选型要点
> 结合数据手册与同步 Buck 常规选型原则，对 Buck 高边（DR1H）与低边（DR1L）分别给出要点。

### 4.1 通用要求（两只 MOS 共性）
- 电压等级 `VDS`：输入上限 24 V，考虑尖峰/谐振和安规裕量，建议选 `40 V` 器件；若应用存在更高浪涌（如车规 24 V 母线），需评估 `60 V` 器件与TVS/RC吸收搭配。
- 栅极驱动与阈值：TPS55288 的 Buck 驱动为栅极约 5 V 级（VCC/BOOT1 供电，见 `docs/datasheets/tps55288-datasheet.md:200`），优选 `Logic‑Level` 器件，`RDS(on)` 在 `VGS=4.5/5 V` 有明确指标；`VGS(max) ≥ ±20 V`。
- 热与封装：优先 `LFPAK/PowerPAK/TDSON‑8 5×6` 等低寄生、低热阻封装；要求大铜皮、密集过孔导热与 Kelvin 源（若可用）以降低环流与 EMI。
- 开关频率与门极电荷：门极损耗近似 `Pgate ≈ Qg · Vdrive · fs`。以 `Qg=30 nC, Vdrive=5 V, fs=600 kHz` 估算，单管门极损耗约 `0.09 W`，两管合计约 `0.18 W`；`Qg` 过大将显著抬升驱动损耗与开关损耗。
- 布局：缩短 `VIN–HS–LS–PGND–输入电容` 高频环路（见 `docs/datasheets/tps55288-datasheet.md:42`–`46`），必要时加 2–10 Ω 栅电阻折中 dV/dt 与 EMI。

### 4.2 高边 MOSFET（Buck 上管，DR1H）
- 角色特点：
  - Boost 工况下“常导通”，承受约 9 A 直流电流（12→20 V 满载）；
  - Buck 工况下为主要开关器件（24→20 V）。
- 选型侧重：
  - 低 `RDS(on)` 优先（Boost 工况直流损耗最敏感）。为将导通损耗压至 ≲0.5 W，建议目标 `RDS(on)@4.5/5 V ≤ 5 mΩ`（9 A 场景导通损耗约 `0.41 W`；若 3 mΩ 则约 `0.24 W`）。
  - 适度控制 `Qg/Qgd`：在满足低电阻的前提下，尽量选择较低 `Qg、Qgd` 的器件以降低 `Pgate` 与 `Psw`。过大的 `Qgd` 会拉长上升/下降沿，抬高 `0.5·Vin·I·(tr+tf)·fs` 项。
  - 低 `Coss`（特别是高压段）有助于降低充放电损耗与谐振尖峰。
- 校核项：
  - `SOA/雪崩/Avalanche` 能力与 `UIS` 等级（吸收尖峰或异常短路瞬态）。
  - 温度系数：按 `Tj=100–125 ℃` 的 `RDS(on)` 再次核算损耗与热平衡。

### 4.3 低边 MOSFET（Buck 下管，DR1L）
- 角色特点：
  - Boost 工况长期关断（损耗主要为结到环境的泄露与耦合微小损失）。
  - Buck 工况下与高边同步整流，承受约 `(1-D)` 比例导通（24→20 V 时约 17% 占空）。
- 选型侧重：
  - `Qrr` 低、体二极管软恢复：减小高边开启瞬间的反向恢复损耗与尖峰电流；降低 EMI。
  - 低 `Coss`/`Coss(Er)`：减小节点换向与硬开关损耗，改善过冲。
  - 合理 `RDS(on)`：在占空较小（24→20 V）情况下，导通损耗相对次要，但仍建议 `≤ 5–8 mΩ@4.5/5 V` 量级以压低峰值温升。
- 校核项：
  - 与高边同封装/同热条件下的温升均衡；必要时可略选更低 `Qg` 的下管以降低驱动损耗与 EMI。

## 5. 小结与器件筛选建议
- 电压等级：优先 `40 V` 同步 Buck 优化型 MOSFET；若系统浪涌/环境不明，评估 `60 V` 档并加 TVS/RC。
- 高边 MOS：以低 `RDS(on)` 为首要，兼顾较低 `Qg/Qgd/Coss`；目标 `≤ 5 mΩ@4.5/5 V`。
- 低边 MOS：优先低 `Qrr`、低 `Coss`，并兼顾 `≤ 5–8 mΩ` 的导通阻抗。
- 频率与驱动：`400–800 kHz` 区间内先做样机 A/B 测试，结合 `Pgate` 与 `Psw` 收支、EMI 与热，确定最终 `fs` 与栅电阻取值。
- 版图：严格按数据手册所列 Buck/Boost 高频环路布置与 AGND/PGND 分区（参见 `docs/datasheets/tps55288-datasheet.md:42`–`50`）。

> 附注：
> - TPS55288 Buck 驱动能力：源 1 A / 灌 1.8 A（`docs/datasheets/tps55288-datasheet.md:196`）。
> - 12 V 输入可达 100 W（`docs/datasheets/tps55288-datasheet.md:708`）；PPS、线缆压降补偿、限流等寄存器支持见 `docs/datasheets/tps55288-datasheet.md:306`、`402`、`923`。

## 6. Buck MOSFET 备选对比（NCEP4090GU / NCEP40T13GU / NCEP4045GU）

> 数据来源：`docs/datasheets/ncep4090gu-datasheet.md`、`docs/datasheets/ncep40t13gu-datasheet.md`、`docs/datasheets/ncep4045gu-datasheet.md`。

| 器件 | RDS(on)@10 V (typ/max) | RDS(on)@4.5 V (typ/max) | Qg typ (nC) | Qgs/Qgd (nC) | Ciss / Coss / Crss (pF) | Qrr / trr | R<sub>θJC</sub> (°C/W) | I<sub>D</sub> (25 °C) | 亮点/风险 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| NCEP4090GU | 2.2 / 2.75 mΩ | 3.3 / 4.0 mΩ | 40 | 5.8 / 7.2 | 2300 / 740 / 38 | 21 nC / 14 ns | 1.47 | 90 A | 阻抗与门极电荷平衡，SOA/热参数充裕 |
| NCEP40T13GU | 1.8 / 2.3 mΩ | 2.8 / 3.6 mΩ | 49 (max 70) | 9.4 / 5.0 | 3334 / 650 / 57 | 67 nC / 23 ns | 1.56 | 130 A | 阻抗最低但 Qg、Qrr 偏大，对驱动/EMI 更苛刻 |
| NCEP4045GU | 6.0 / 6.6 mΩ | 8.5 / 10 mΩ | 17.6 | 3.5 / 3.1 | 831 / 318 / 24 | 19 nC / 11 ns | 4.5 | 45 A | 门极/恢复指标理想但 RDS(on) 偏高、热阻大 |

### 6.1 高边（DR1H）适配性
- **导通损耗**（Boost 12→20 V，I≈9 A）：
  - NCEP4090GU：≈0.27–0.32 W，满足“≤5 mΩ@4.5 V”目标 (`docs/tps55288-design-notes.md:47`)。
  - NCEP40T13GU：≈0.23–0.29 W，进一步压低导通损耗。
  - NCEP4045GU：≈0.69–0.81 W，明显超出热预算，不宜使用。
- **驱动与开关损耗**（假设 5 V 栅驱、600 kHz）：
  - NCEP4090GU：P<sub>gate</sub>≈0.12 W，可落在 TPS55288 1 A|1.8 A 驱动余量内 (`docs/tps55288-design-notes.md:72`)。
  - NCEP40T13GU：P<sub>gate</sub>≈0.15–0.21 W，需重点验证驱动温升与 EMI，对栅电阻和布局约束更严。
  - NCEP4045GU：P<sub>gate</sub>≈0.05 W，但导通损耗过高，无法弥补。
**结论**：高边推荐 **NCEP4090GU** 作为默认选型；在追求更低导通损耗、并能接受更大门极能耗/EMI 调试成本时，可评估 **NCEP40T13GU** 做对照样机。

### 6.2 低边（DR1L）适配性
- 低边在 Buck 24→20 V 时仅 17% 占空 (`docs/tps55288-design-notes.md:58`)，导通损耗主要由 `RDS(on)` 与 `Qrr` 决定整流效率。
  - NCEP4090GU：导通损耗 ≈0.05 W；Qrr 21 nC，表现稳健。
  - NCEP40T13GU：导通损耗 ≈0.04 W，但 Qrr 67 nC，反向恢复尖峰与高频振铃压力最大。
  - NCEP4045GU：导通损耗 ≈0.035–0.04 W（占空比低），Qrr 19 nC、Qg 17.6 nC，有利于减轻 dv/dt 与驱动功耗，需关注其 45 A 电流额定与 4.5 °C/W 热阻，确保 PCB 铜箔和散热设计能妥善导热。
**结论**：低边首选 **NCEP4045GU**（若能满足热设计与库存），其次为 **NCEP4090GU**；避免使用 Qrr 较大的 NCEP40T13GU 作为低边整流管。

### 6.3 组合建议与验证要点
1. **基线方案**：NCEP4090GU (高边) + NCEP4045GU (低边)。若 NCEP4045GU 供货或热阻不满足，则双用 NCEP4090GU。
2. **效率强化对照**：高边切换 NCEP40T13GU，对比导通下降与驱动热的取舍，低边保持 NCEP4045GU。
3. **实验关注点**：
   - 频率先落在 500–600 kHz，视驱动温升与波形调整栅电阻（2–5 Ω 初始）。
   - 重点记录 SW 节点的 dv/dt、振铃幅度与整流反向恢复尖峰，必要时叠加 RC Snubber。
   - 满载条件下复核高边 MOS 结温（Boost & Buck 工况各 30 min），并以红外热像确认低边热分布。
   - 验证 45 A 额定的 NCEP4045GU 是否满足长期可靠性（包含浪涌、短时过流与线缆插拔应力）。

> 若后续需与国际品牌低压 MOSFET 做效率或 EMI 对比，可在同封装范畴内引入 AOS/Infineon/Vishay 等器件作为 Benchmark，建立栅驱能耗与 Qrr 性能的量化对照。
