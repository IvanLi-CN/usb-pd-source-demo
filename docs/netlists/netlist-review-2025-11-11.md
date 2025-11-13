# 网表评审（当前网表）

- 评审对象：`docs/netlists/usb-pd-source-netlist.enet`
- 对照基线：
  - `docs/tps55288-design-notes.md`
  - `docs/sw2303-vbus-switch-notes.md`
  - `docs/sw7201-design-notes.md`
- 相关数据手册节选：`docs/datasheets/sw2303/sw2303-datasheet.md`

> 本文针对当前评审对象进行全面评审，移除过时增量记录与行号引用，仅呈现当前状态与结论。

## 澄清与设计约定（本版）

- SW2303 的 PSET 悬空策略（正确）
  - 设计采用 I2C 模式：`PRSET/SCK` 作 `SCK`，`PSET` 为 X/不关心；功率由 I2C 配置，不依赖 PSET 分压。
  - 运行策略：外部主机上电后以 I2C 配置为“最大功率”（不降额）。

- TPS55288 默认输出电压 5 V（已确认）
  - 默认使用内部反馈（FB=0）+ 默认参考电压（282 mV）+ 默认内部反馈比（0.0564），VOUT ≈ 5.0 V。
  - 外部分压（如 R3/R5）用于“外部反馈模式”，需软件切换后生效；上电默认仍为 5 V。

- I2C 上拉由外部主机提供
  - 板上不装 I2C 上拉，SDA/SCL 通过调试排针与外部主机相连并上拉。

## 本次检查确认

- R4 反馈直通风险已消除（不装）
  - 现状：`R4` 定义为 `FB_TPS ↔ INT_TPS`，默认 `n.c.`（DNI），避免反馈回路外引噪声/失稳风险；不影响 PCB 焊盘保留与验证装配灵活性。

- SW 域 SW2303（U7）CSP/CSN RC 滤波已就位
  - U7.8（CSP）节点配置 R35=510 Ω（至 `PGND_SW`）与 C76=1 µF（至 `GND`）；U7.9（CSN）接地。满足“510 Ω + 1 µF”建议，抑制采样噪声。

- USB‑C 三端口 ESD 保护（本次变更）
  - 三端口统一采用 TPD4E05U06，ESD 回流分别就地闭合到端口地 `PGND_n`：
    - TPS 域：D5（DP/DM/CC1/CC2 ↔ `PGND_TPS`）
    - SW 域：D13（DP/DM/CC1/CC2 ↔ `PGND_SW`）
    - PL 域：D21（DP/DM/CC1/CC2 ↔ `PGND_PL`）
  - 评价：就地回流降低 ESD 脉冲注入系统地/采样地风险，符合端口域隔离设计意图。

## 检查清单（TPS55288 段）

- [x] U1.3 VIN → VIN；U1.4 EN → EN_TPS
- [x] U1.5/6 → SCL_TPS/SDA_TPS（I2C 到外部主机）
- [x] U1.9 PGND → GND；U1.10 AGND → AGND_TPS；U1.24 PGND → GND（地网分配一致）
- [x] U1.13 VOUT_TPS；U1.14 FB_TPS（默认内部反馈 5 V）
- [x] U1.21/25 → SW2_TPS；U1.11/12/26 → ISP_TPS（引脚簇一致）
- [x] F1=10 mΩ：ISP_TPS ↔ VOUT_TPS（电流检测/线缆补偿基准）
- [x] USB1：A4B9/B4A9 → VBUS_TPS；A5/B5 → CC1_TPS/CC2_TPS；A6/B6 → DP_TPS；A7/B7 → DM_TPS；12/13/14/15 与 A1B12/B1A12 → PGND_TPS
- [x] USB1：A8/B8（SBU）未用保持 NC，符合当前不走音频/ALT 模式的约束
- [x] D5=TPD4E05U06（DP/DM/CC ↔ PGND_TPS）
- [x] VBUS 保护：D6=TVS2200（VBUS_TPS ↔ PGND_TPS）
- [x] VBUS 开关栅极网络：
  - [x] U3.2 GATE → Q6.4（N-MOS 高边）；串 R12=1 k；钳位 D4=18 V（GATE↔VBUS_TPS）
  - [x] Q5（P-MOS）门极经 R12 与同一钳位网络关联（防止 |VGS| 超额）
- [x] 端口地与系统地：R13=5 mΩ（GND ↔ PGND_TPS）
- [x] SW2303（U3）模式：U3.10 VFB → GND（FB 模式），U3.14 OPTO/FB → FB_TPS，U3.13 → VBUS_TPS，U3.3 → 5V_TPS（去耦已布）
- [x] VIN 去耦与电容阵列：VIN ↔ GND 大小电容并联（C5/C6/C7/等）
- [x] Buck 外置功率级周边：驱动脚经 0 Ω 跳线与钳位二极管网络（R1/R2 + D1/D2）与 MOS 栅极连接，符合驱动/EMI 抑制布置
- [x] FSW/配置脚绑值：R6=43k（FSW）→ AGND_TPS；其余绑值电阻（R9/R10/R7/R8）到位（与笔记/手册对应）
- [x] 调试排针：U2 暴露 EN_TPS/INT_TPS/SDA_TPS/SCL_TPS/GND（I2C 由外部主机上拉）
- [x] 测试点：TP1=5V_TPS、TP2=FB_TPS 已提供
- [x] VIN 大电容/小电容：C3/C5/C6/C7（≥35 V）、C9/C10/C60/C86（50 V）与若干 n.c. 位保留（与装配策略一致）

## 检查清单（SW7201 段）

- [x] U5：VOUT_SW 引脚（3/9）→ VOUT_SW；U5.10 → FB_SW；U5.11/12/13 → SDA_SW/SCL_SW/INT_SW
- [x] U5.20/23 → VIN；EPAD → GND；VCC/VDRV 去耦、BST1/2 自举电容存在
- [x] U7（SW2303）：1/16 → SDA_SW/SCL_SW；4/5 → DP_SW/DM_SW；6/7 → CC1_SW/CC2_SW；13 → VBUS_SW；14 → FB_SW；15 → VOUT_SW
- [x] U8=INA138：3 → INA_CSP；4 → VOUT_SW；5 → 5V_SW（高边电流检测就位）
- [x] U7.8/9（CSP/CSN）RC：R35=510 Ω、C76=1 µF；CSN 接地（抑制采样噪声）
- [x] USB2：VBUS_SW/CCx_SW/DP_SW/DM_SW/PGND_SW 归属正确
- [x] USB2：A8/B8（SBU）未用保持 NC
- [x] D13=TPD4E05U06（DP/DM/CC ↔ PGND_SW）；D14=TVS2200（VBUS_SW ↔ PGND_SW）
- [x] VBUS 开关栅极网络：
  - [x] U7.2 GATE → Q16.4（N-MOS 高边）；串 R33=1 k；钳位 D12=18 V（GATE↔VBUS_SW）
  - [x] Q15（P-MOS）门极经 R33 与同一钳位网络关联
- [x] 端口地与系统地：R34=5 mΩ（GND ↔ PGND_SW）
- [x] SW2303（U7）模式：U7.10 VFB → GND（FB 模式），U7.14 → FB_SW，U7.13 → VBUS_SW，U7.3 → 5V_SW（去耦已布）
- [x] SW2303 VBUS 采样与系统监测：INA138 高边检测链路完整（VOUT_SW/INA_CSP/5V_SW）
- [x] SW7201 参数脚：R27=10k（BSSET）→GND、R28=43k（LSET）→GND、R29=NTC 10k（至 GND），与笔记设定一致
- [x] 测试点：TP3=5V_SW、TP4=FB_SW 已提供

## 检查清单（PL5501 段）

- [x] U9（PL5501）：25/26/27 → VIN；14/15 → VOUT_PL；12 → FB_PL；29/33 → GND
- [x] U11（SW2303）：1/16 → SDA_PL/SCL_PL；4/5 → DP_PL/DM_PL；6/7 → CC1_PL/CC2_PL；13 → VBUS_PL；14 → FB_PL；15 → VOUT_PL
- [x] USB3：VBUS_PL/CCx_PL/DP_PL/DM_PL/PGND_PL 归属正确
- [x] USB3：A8/B8（SBU）未用保持 NC
- [x] D21=TPD4E05U06（DP/DM/CC ↔ PGND_PL）；D22=TVS2200（VBUS_PL ↔ PGND_PL）
- [x] VBUS 开关栅极网络：
  - [x] U11.2 GATE → Q26.4（N-MOS 高边）；串 R51=1 k；钳位 D20=18 V（GATE↔VBUS_PL）
  - [x] Q25（P-MOS）门极经 R51 与同一钳位网络关联
- [x] 端口地与系统地：R52=5 mΩ（GND ↔ PGND_PL）
- [x] SW2303（U11）模式：U11.10 VFB → GND（FB 模式），U11.14 → FB_PL，U11.13 → VBUS_PL，U11.3 → 5V_PL（去耦已布）
- [x] 测试点：TP5=5V_PL、TP6=FB_PL 已提供
- [x] SW2303（U11）模式：U11.10 VFB → GND（FB 模式），U11.14 → FB_PL，U11.13 → VBUS_PL，U11.3 → 5V_PL（去耦已布）

## 当前连线一致性结论（精简）

- 架构：三域独立（TPS55288/TPS、SW7201/SW、PL5501/PL），各自 Type‑C 连接器与 ESD/TVS/`PGND_n` 归属正确。
- TPS55288 接地：U1.9 PGND→`GND`、U1.24 PGND→`GND`、U1.10 AGND→`AGND_TPS`；满足模拟/端口/系统地分隔意图。
- VBUS 保护：三域均配置 TVS2200（VBUS ↔ PGND_n）；TPS 域含齐纳监测位（D4）。
- SW 域电流检测：INA138 高边检测就位；SW2303 CSP/CSN 侧 RC 滤波落实（510 Ω + 1 µF）。
- 外设与接口：I2C 由外部主机上拉；SW2303 PSET 悬空（I2C 配置最大功率）。
- 验证板差异：R4 设为 `n.c.`（DNI），不影响 PCB；可按需求临时装配以进行调试。

## 附注（装配与约定）

- R4 标记 n.c./DNI（不装），仅供验证时临时装配；不影响 PCB。
- SW2303 PSET 悬空（I2C 模式），由外部主机配置功率；I2C 上拉由外部主机提供。

## 结论

- 基于当前网表，未发现与设计笔记/数据手册冲突、不匹配或明显连接错误；此前阻断性问题均已关闭（ESD 回流归属、SW 域 CSP/CSN RC、FB 外引风险）。
- 建议保持：ESD 贴近 Type‑C、`PGND_n` 就地回流、关键采样走线最短/对称；在设计说明中明确 I2C 上拉由外部主机提供。
