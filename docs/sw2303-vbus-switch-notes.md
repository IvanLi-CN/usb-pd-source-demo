# SW2303 VBUS 开关设计笔记

## 1. 目标与边界条件

- 输出协议：`SW2303` 内建 PD3.0/PPS，最高 `20 V / 5 A`，APDO 覆盖 `3.3–21 V`，需满足 100 W 等级 USB-PD 源端能力。`SW2303` 将根据协商结果主动驱动外部 VBUS 开关。[`docs/datasheets/sw2303/sw2303-datasheet.md:802`](docs/datasheets/sw2303/sw2303-datasheet.md:802)
- 工作电压：输入/输出设计范围 `3.0–25 V`，VBUS 侧 OVP/UVP 控制窗口 ±2 V 内置完成，外部 MOS 需额外提供耐压裕度与快速关断能力。[`docs/datasheets/sw2303/sw2303-datasheet.md:24`](docs/datasheets/sw2303/sw2303-datasheet.md:24) [`docs/datasheets/sw2303/sw2303-datasheet.md:674`](docs/datasheets/sw2303/sw2303-datasheet.md:674)
- 开关类型：`SW2303` 自动识别外接 `PMOS` 或 `NMOS`，并切换驱动模式；单颗 MOSFET 需兼顾 5 A 连续电流、USB 插拔热冲击、ESD。[`docs/datasheets/sw2303/sw2303-datasheet.md:804`](docs/datasheets/sw2303/sw2303-datasheet.md:804)
- 驱动限制：NMOS 模式采用内置电荷泵，驱动能力有限；要求所选 NMOS 的栅漏电 `IGSS ≤ 100 nA`，并尽量控制门极电荷。PMOS 模式需要外置上拉与栅极限流/钳位网络。[`docs/datasheets/sw2303/sw2303-schematic-guide.md:51`](docs/datasheets/sw2303/sw2303-schematic-guide.md:51)

### 1.1 资料索引

- `SW2303` 数据手册（英文抽取版）：`docs/datasheets/sw2303/sw2303-datasheet.md`
- `SW2303` 原理图设计指南：`docs/datasheets/sw2303/sw2303-schematic-guide.md`
- `SW2303` PCB 设计指南：`docs/datasheets/sw2303/sw2303-pcb-guide.md`
- MOSFET 数据：
  - `NCE30P30G`（DFN5×6 P 沟道）：`docs/datasheets/mosfets/nce30p30g.md`
  - `NCE30P50G`（DFN5×6 P 沟道，增强型）：`docs/datasheets/mosfets/nce30p50g.md`
  - `NCE20P70G`（DFN5×6 P 沟道，20 V 级）：`docs/datasheets/mosfets/nce20p70g.md`
  - `NCE3025Q`（DFN3.3×3.3 P 沟道，30 V）：`docs/datasheets/mosfets/nce3025q.md`
  - `NCE3035Q`（DFN3.3×3.3 P 沟道，35 A）：`docs/datasheets/mosfets/nce3035q.md`
  - `NCEP4090GU`（DFN5×6 N 沟道）：`docs/datasheets/ncep4090gu-datasheet.md`
  - `NCEP40T13GU`（DFN5×6 N 沟道，高电流）：`docs/datasheets/ncep40t13gu-datasheet.md`
  - `NCEP3045GU`（DFN5×6 N 沟道，30 V / 45 A）：`docs/datasheets/mosfets/ncep3045gu.md`
  - `NCEP40T14G`（DFN5×6 N 沟道，40 V / 140 A）：`docs/datasheets/mosfets/ncep40t14g.md`
  - `NCEP3040Q`（DFN3.3×3.3 N 沟道）：`docs/datasheets/mosfets/ncep3040q.md`
  - `DMP3013SFV`（PowerDI3333-8 P 沟道）：`docs/datasheets/mosfets/dmp3013sfv.md`
  - `NCE30P28Q`（DFN3.3×3.3 P 沟道，低压版）：`docs/datasheets/mosfets/nce30p28q.md`
  - `NCEP01ND35AG`（DFN5×6 N 沟道，100 V）：`docs/datasheets/mosfets/ncep01nd35ag.md`
  - `NCEP035N85GU`（DFN5×6 N 沟道，高电流）：`docs/datasheets/mosfets/ncep035n85gu.md`
  - `NCEP3090GU`（DFN5×6 N 沟道，30 V 级）：`docs/datasheets/mosfets/ncep3090gu.md`
  - `NCEP6080AG`（DFN5×6 N 沟道，60 V 级）：`docs/datasheets/mosfets/ncep6080ag.md`
  - `NCEP6090AGU`（DFN5×6 N 沟道，AEC-Q101）：`docs/datasheets/mosfets/ncep6090agu.md`
  - `NCE01P30K`（TO-252 P 沟道，高耐压）：`docs/datasheets/mosfets/nce01p30k.md`
  - `SiS454DN`（PowerPAK1212-8 N 沟道，20 V）：`docs/datasheets/mosfets/sis454dn.md`

## 2. 通用设计要点

### 2.1 负载工况与热平衡

- 5 A 满载下单颗 MOSFET 导通损耗可估算为 `P ≈ I²·RDS(on)`；以 7.6 mΩ（AON6405 @ -4.5 V）计，约 0.19 W，需配合 ≥2 oz 铜、完整散热铜皮以及过孔导热。
- PPS 场景下 21 V APDO 会把 PMOS 的 `VGS` 拉到 -21 V 左右，应选 `VGS(MAX) ≥ ±20 V` 且考虑钳位齐纳冗余，避免长期靠近极限。

### 2.2 驱动网络

- **PMOS 模式**：GATE 输出需串 1 kΩ 限流后连接到 MOSFET 栅极；同时从栅极到 VOUT 上拉 30 kΩ 并并联 15 V TVS/Zener，实现快速关断与 VGS 钳位。该网络可防止插拔瞬间因 VBUS 电压高于 15 V 导致 VGS 超额。[`docs/datasheets/sw2303/sw2303-schematic-guide.md:53`](docs/datasheets/sw2303/sw2303-schematic-guide.md:53)
- **NMOS 模式**：GATE 与栅极直接连接，依赖内置电荷泵。需确认 MOSFET 栅漏电流 ≤100 nA，以免泵电荷流失导致 VGS 降幅。必要时可加 1–2 Ω 栅电阻抑制振铃。

### 2.3 保护与布局

- VBUS 端建议放置 20 V 级 TVS 贴近连接器，并保证 VBUS/VIN 快速放电路径（SW2303 内置）。[`docs/datasheets/sw2303/sw2303-datasheet.md:27`](docs/datasheets/sw2303/sw2303-datasheet.md:27)
- 电流采样电阻需靠近 SW2303 CSP/CSN，避免高 dI/dt 共模噪声耦合。[`docs/datasheets/sw2303/sw2303-schematic-guide.md:55`](docs/datasheets/sw2303/sw2303-schematic-guide.md:55)
- PCB 指南建议 VBUS 主铜皮≥2 mm 宽、栅极走线远离高 dv/dt 区域，同时多点接地减少环路面积。`docs/datasheets/sw2303/sw2303-pcb-guide.md`

### 2.4 推荐方案（单 USB 口）

1. **优选 PMOS（DFN5×6 单管：NCE30P50G）**  
   - MOSFET：`NCE30P50G`。  
   - 配件：`1 kΩ` 栅串阻、`30 kΩ` 上拉、`15 V` SOD-123 TVS（如 SMF15A）跨栅源；VBUS 端 `SMAJ20A/SMBJ20A`；`5 mΩ` 取样电阻采用 Kelvin 布线。  
   - 用途：100 W 单口输出的主力方案，导通损耗最低。

2. **次优 PMOS（DFN5×6 单管：NCE30P30G）**  
   - MOSFET：`NCE30P30G`。  
   - 配件：与优选 PMOS 相同，TVS 与串阻不可省；需保证 MOSFET 下方≥2 oz 铜皮与过孔。  
   - 用途：在成本或供应受限但仍需 100 W 的情况下替代。

3. **优选 NMOS（DFN5×6 单管：NCEP4090GU）**  
   - MOSFET：`NCEP4090GU`。  
   - 配件：GATE 串 `1 Ω` 阻尼；栅源并 `18 V` TVS（SMAJ18A）；VBUS 端 `SMAJ24A`；漏到源各加 `100 kΩ` 泄放确保关断；取样线路保持 Kelvin。  
   - 用途：需要高侧 NMOS 拓扑且希望在 100 W 下保持极低 `RDS(on)`。

4. **次优 NMOS（DFN5×6 背靠背：NCEP40T14G ×2）**  
   - 结构：两颗 `NCEP40T14G` 源端相连、漏端分别朝上/下游，形成双向阻断。  
   - 配件：每颗栅串 `2 Ω`，栅源并 `18 V` TVS；两栅之间增设 `100 kΩ` 均压；背靠背节点加 `1 nF` 缓冲；VBUS 侧 `SMAJ24A`。  
   - 用途：对浪涌、反插、防回灌要求严苛的 USB-PD 场景。

> 紧凑方案（DFN3.3×3.3，如 `NCE3035Q`、`NCEP3065QU`）仅在散热确认后使用：PMOS 栅极 `1 kΩ` 串阻 + `15 V` TVS，NMOS 栅极 `1 Ω` 串阻 + `18 V` TVS，VBUS 端必须配置 `SMAJ20~24A`，并在 PCB 上提供 ≥1 cm² 铜皮与 ≥6 颗热过孔。


## 3. DFN5×6 PMOS 方案

## 3. DFN5×6 PMOS 方案

适用于 100 W 级单口 VBUS。优先保证低导通阻和合理门极电荷，以匹配 SW2303 保守驱动能力。

| 器件 | 封装 | 关键指标 | 估算损耗 (5 A) | 优势 | 关注点 | 淘宝价格 |
| --- | --- | --- | --- | --- | --- | --- |
| `NCE30P30G` | DFN5×6 | `RDS(on)=7.4 mΩ@-10 V / 11 mΩ@-4.5 V`；`Qg(typ)=24 nC`；`ID=-30 A`。[`docs/datasheets/mosfets/nce30p30g.md:7`](docs/datasheets/mosfets/nce30p30g.md#L7) | ≈0.19 W | 低栅电荷 + 中阻值，便于 SW2303 直接驱动；1.56 °C/W 的良好热阻利于单颗 5 A 使用 | 典型 `Qg=24 nC`，仍建议串 1 kΩ 栅阻并评估关断速度；`VGS(max)=±20 V`，必须布置齐纳钳位 | [￥0.93（1+）](https://item.taobao.com/item.htm?id=811984370950) |
| `NCE30P50G` | DFN5×6 | `RDS(on)=4.4 mΩ@-10 V`（max 7 mΩ）；`Qg(typ)=84 nC`；`ID=-50 A`。[`docs/datasheets/mosfets/nce30p50g.md:7`](docs/datasheets/mosfets/nce30p50g.md#L7) | ≈0.11 W | 更低导通阻、50 A 级额定电流，适合 5 A 主路留足余量；FOM 较低便于控制热损 | 84 nC 栅电荷对 SW2303 电荷泵为上限，建议测试断电时间并配置 1~2 Ω 栅阻与 15 V 齐纳 | [￥1.50（1+）](https://item.taobao.com/item.htm?id=811858719180) |
| `NCE20P70G` | DFN5×6 | `RDS(on)=3 mΩ@-4.5 V (typ)`；`Qg≈100 nC`；`VDS=-20 V`。[`docs/datasheets/mosfets/nce20p70g.md:7`](docs/datasheets/mosfets/nce20p70g.md#L7) [`docs/datasheets/mosfets/nce20p70g.md:41`](docs/datasheets/mosfets/nce20p70g.md#L41) | ≈0.075 W | 超低导通阻、对 -4.5 V 驱动友好，适合 12 V 场景或需要极低导通损的策略 | 耐压仅 20 V，若输出到 20 V/PD 档位需改用更高耐压器件；`Qg≈100 nC` 需验证驱动能力并配置齐纳钳位 | [￥1.90](https://item.taobao.com/item.htm?id=812226000203) |

**建议**

1. 单口 VBUS 推荐 `NCE30P50G` 作为首选，以更低 `RDS(on)` 降低发热；成本敏感场景可采 `NCE30P30G` 并适当放宽铜面积。
2. PMOS 栅极上拉与齐纳务必靠近器件摆放，保持回路最小化；建议使用 15 V/0.5 W 级 SOD-123 钳位吸收负向尖峰。
3. 评估插拔热冲击：VBUS 空载到 20 V 负载切换时，监测 VGS 是否超过 -18 V；若门极电荷偏大可增设栅串阻或 RC 缓冲。

## 4. DFN5×6 NMOS 方案

适合单 NMOS 高侧开关或背靠背配置（需额外一颗实现反灌保护）。

| 器件 | 封装 | 关键指标 | 估算损耗 (5 A) | 优势 | 关注点 | 淘宝价格 |
| --- | --- | --- | --- | --- | --- | --- |
| `NCEP4090GU` | DFN5×6 | `RDS(on)=2.2 mΩ@10 V / 3.3 mΩ@4.5 V`；`Qg≈40 nC`；`IGSS±100 nA`。[`docs/datasheets/ncep4090gu-datasheet.md:47`](docs/datasheets/ncep4090gu-datasheet.md:47) | ≈0.08 W | 超低导通阻 + 40 V 耐压，适合同一 USB 口的 5 A 场景；封装兼容常规 DFN5×6 焊盘 | 门极电荷 40 nC 接近驱动上限，建议使用 1~2 Ω 栅阻并验证关断时间与温升 | [￥1.10](https://item.taobao.com/item.htm?id=812122094056) |
| `NCEP40T13GU` | DFN5×6 | `RDS(on)=2.3 mΩ@10 V`，`Qg≈70 nC`，`ID=130 A`。[`docs/datasheets/ncep40t13gu-datasheet.md:47`](docs/datasheets/ncep40t13gu-datasheet.md:47) | ≈0.09 W | 130 A 额定，浪涌能力强；适用于 5×6 双 NMOS 背靠背方案 | `Qg` 更高，需要确认充泵能力；若关断时间延长需增设驱动缓冲或退回 PMOS 方案 | [￥1.30](https://item.taobao.com/item.htm?id=814185136443) |
| `NCEP01ND35AG` | DFN5×6 | `RDS(on)=24 mΩ(typ)@10 V / 27 mΩ(typ)@4.5 V`；`Qg≈26 nC`；`VDS=100 V`。[`docs/datasheets/mosfets/ncep01nd35ag.md:43`](docs/datasheets/mosfets/ncep01nd35ag.md:43) | ≈0.70 W | 100 V 耐压提供高输入余量，可作为车载或双 NMOS 背靠背的高压侧器件 | 导通阻较高导致 5 A 发热显著，更适合并联或特定隔离场景，布局需预留散热铜皮 | [￥2.20](https://item.taobao.com/item.htm?id=812086710883) |
| `NCEP035N85GU` | DFN5×6 | `RDS(on)=2.7 mΩ@10 V`；`Qg≈64.5 nC`；`ID=130 A`。[`docs/datasheets/mosfets/ncep035n85gu.md:48`](docs/datasheets/mosfets/ncep035n85gu.md:48) | ≈0.08 W | 85 V/130 A 等级，单颗即可覆盖高浪涌主路；低阻确保 5 A 温升可控 | 64 nC 栅电荷偏大，需确认 SW2303 驱动冗余并配置 1–2 Ω 栅阻；成本较高 | [￥3.00](https://item.taobao.com/item.htm?id=811964011974) |
| `NCEP3045GU` | DFN5×6 | `RDS(on)=5.8 mΩ@10 V / 8 mΩ@4.5 V`；`Qg≈15 nC`；`ID=45 A`。[`docs/datasheets/mosfets/ncep3045gu.md:12`](docs/datasheets/mosfets/ncep3045gu.md#L12) | ≈0.15 W | 30 V/45 A 规格 + 极低 Qg，便于 SW2303 电荷泵驱动；适合 5 A 主路或双 NMOS 组合 | 30 V 耐压仅有 10 V 裕量，需搭配 TVS/齐纳抑制 20 V 主路尖峰；热设计需保证 5×6 器件下方有足够铜皮/过孔 | [￥1.15](https://item.taobao.com/item.htm?id=812115690286) |
| `NCEP40T14G` | DFN5×6 | `RDS(on)=1.6 mΩ@10 V / 2.3 mΩ@4.5 V`；`Qg≈90 nC`；`ID=140 A`。[`docs/datasheets/mosfets/ncep40t14g.md:12`](docs/datasheets/mosfets/ncep40t14g.md#L12) | ≈0.04 W | 40 V/140 A 旗舰规格，提供超大浪涌余量及 133 W 散热能力 | Qg 高达 90 nC，SW2303 充泵裕度紧张；务必串 >2 Ω 栅阻并验证关断时间，必要时改用外部驱动 | [￥2.20](https://item.taobao.com/item.htm?id=811993983238) |

**设计提示**

- SW2303 驱动 NMOS 时会将栅电压拉高到 VBUS+ΔV。确保 MOSFET `VGS(max)` ≥ ±20 V，并在 GATE 与源之间预留 18–22 V 齐纳钳位（选配）。
- 若需反向阻断（防止外部电源回灌上游），建议使用两颗 DFN5×6 N-MOS 背靠背，并将中间节点反馈到 SW2303 VBUS 端以保证监测准确。

## 5. DFN3.3×3.3 PMOS 方案

面向尺寸受限、散热资源有限的场景。

| 器件 | 封装 | 关键指标 | 估算损耗 (5 A) | 优势 | 关注点 | 淘宝价格 |
| --- | --- | --- | --- | --- | --- | --- |
| `NCE20P45Q` | DFN3.3×3.3 | `RDS(on)=7 mΩ@-4.5 V / 12 mΩ@-1.8 V`；`ID=-45 A`。[`docs/datasheets/mosfets/nce20p45q.md:18`](docs/datasheets/mosfets/nce20p45q.md#L18) | ≈0.45 W | 20 V 等级提供 45 A 峰值，适合多颗并联扩展；低阈值支持 SW2303 PMOS 驱动 | 需要确保 `VGS(max)=±10 V`，齐纳钳位必须贴近栅源；PowerDI3333 散热有限 | [￥0.89（1+）](https://item.taobao.com/item.htm?id=813357243438) |
| `NCE40P20Q` | DFN3.3×3.3 | `RDS(on)=18 mΩ@-10 V / <28 mΩ@-4.5 V`；`ID=-40 A`。[`docs/datasheets/mosfets/nce40p20q.md:18`](docs/datasheets/mosfets/nce40p20q.md#L18) | ≈0.34 W | 40 V 耐压可覆盖 28 V 浪涌，适合在紧凑布局中承担高压余量 | 栅电荷较高，建议串 1 kΩ 栅阻；全功率运行需在底层铺铜导热 | [￥0.85（1+）](https://item.taobao.com/item.htm?id=813531926445) |
| `NCE30P28Q` | DFN3.3×3.3 | `RDS(on)=6.7 mΩ(typ)@-10 V / 9.5 mΩ(typ)@-4.5 V`；`Qg≈45 nC`；`ID=-28 A`。[`docs/datasheets/mosfets/nce30p28q.md:42`](docs/datasheets/mosfets/nce30p28q.md:42) | ≈0.23 W | 30 V 等级配合 3×3 封装仍保持低阻，适合空间受限的 VBUS 开关 | 栅电荷 45 nC，需验证 SW2303 PMOS 驱动速度并配 1 kΩ 栅阻、齐纳钳位 | [￥0.83](https://item.taobao.com/item.htm?id=811850463141) |
| `NCE3025Q` | DFN3.3×3.3 | `RDS(on)=10 mΩ@-10 V / 14 mΩ@-4.5 V`；`Qg≈15 nC`；`ID=-25 A`。[`docs/datasheets/mosfets/nce3025q.md:9`](docs/datasheets/mosfets/nce3025q.md#L9) | ≈0.25 W | 栅电荷仅 15 nC，SW2303 易于驱动；25 A 额定 + 7 mm² 占板适合紧凑或背靠背 PMOS | DFN3.3×3.3 散热有限，5 A 连续工作需 2 oz 铜+底层导热；30 V 器件必须配合齐纳钳位 | [￥0.78](https://item.taobao.com/item.htm?id=813675385660) |
| `NCE3035Q` | DFN3.3×3.3 | `RDS(on)=7 mΩ@-10 V / 11 mΩ@-4.5 V`；`Qg≈45 nC`；`ID=-35 A`。[`docs/datasheets/mosfets/nce3035q.md:10`](docs/datasheets/mosfets/nce3035q.md#L10) | ≈0.18 W | 更低导通阻、35 A 峰值，适合中电流方案；150 mJ 单脉冲浪涌能力好 | `Qg≈45 nC` 逼近 PMOS 驱动极限，需严格验证 VGS 波形并配置 1 kΩ 栅阻 + 15 V 齐纳 | [￥0.63](https://item.taobao.com/item.htm?id=813775396551) |

**设计提示**

- 由于 RDS(on) 较高，建议在 100 W 系统中按设计热约束使用，并结合热仿真确认余量。
- 栅极网络同 5×6 PMOS；需格外注意齐纳位置，避免 3.3×3.3 裸露焊盘造成回流困难。

## 6. DFN3.3×3.3 NMOS 方案

适合紧凑布局或背靠背防反灌等高效低损耗开关场景。

| 器件 | 封装 | 关键指标 | 估算损耗 (5 A) | 优势 | 关注点 | 淘宝价格 |
| --- | --- | --- | --- | --- | --- | --- |
| `NCEP3040Q` | DFN3.3×3.3 | `RDS(on)=6.8 mΩ@10 V / 9.5 mΩ@4.5 V`；`ID=40 A`。[`docs/datasheets/mosfets/ncep3040q.md:9`](docs/datasheets/mosfets/ncep3040q.md#L9) | ≈0.24 W | 30 V 器件，低栅漏电可稳定配合 SW2303 电荷泵；FOM 适中，易于布线 | 建议串 1 Ω 栅阻抑制振铃，并在功率闭环中核算热耗散余量 | [￥0.62（1+）](https://item.taobao.com/item.htm?id=812367836579) |
| `NCEP3065QU` | DFN3.3×3.3 | `RDS(on)=1.9 mΩ@10 V / 3.0 mΩ@4.5 V`；`ID=65 A`。[`docs/datasheets/mosfets/ncep3065qu.md:7`](docs/datasheets/mosfets/ncep3065qu.md#L7) | ≈0.07 W | 极低导通阻和 500 mJ 单脉冲能量，适合高功率防反灌配置或反灌保护双 NMOS | 栅电荷 54 nC，建议验证 SW2303 驱动充电速度；布线需留足散热铜皮 | [￥1.85（1+）](https://item.taobao.com/item.htm?id=814077881714) |

**设计提示**

- 3×3 封装散热能力有限，建议搭配大面积接地铜皮与底层曝光铜。
- 若与 EPR 240 W 方案搭配，需下调目标电流或选择 5×6 封装。

## 7. 验证与后续工作

1. **原理图实现**：按照 `SW2303` 原理图指南添加 PMOS/NMOS 对应外设网络，并在仿真中检查 VGS 波形，确保开关时间 < 1 ms、VGS 不越界。
2. **热仿真 / 实测**：对最小封装（3.3×3.3）方案进行 5 A 连续老化测试，测量焊盘温升；若升温 >40 ℃，考虑并联或回退到 5×6 封装。
3. **保护策略**：评估是否需要在 VBUS 侧增加慢熔丝/电子保险，避免 MOSFET 短路失效导致的过流；同时验证 SW2303 OVP 与外部 TVS 的协同动作。
4. **库存与备选**：`AON6405` 已列为停产，量产阶段应提前锁定供应商或替换为 `AONS20485`/其他同等参数器件。

> 备注：所有功耗估算基于室温 `I = 5 A` 持续导通场景，未考虑温度漂移。实际应用需在热平衡后重新评估 RDS(on) 与温升。
