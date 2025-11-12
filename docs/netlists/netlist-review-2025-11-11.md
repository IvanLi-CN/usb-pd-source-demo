# 网表对照评审（2025-11-12 最新2）

- 评审对象：`docs/netlists/usb-pd-source-netlist.enet`（已用最新文件替换：`/Users/ivan/Downloads/Netlist_Schematic1_2025-11-12 (2).enet`）
- 对照基线：
  - `docs/tps55288-design-notes.md:1`
  - `docs/sw2303-vbus-switch-notes.md:1`
  - 相关数据手册节选：`docs/datasheets/sw2303/sw2303-datasheet.md:63`
  - `docs/sw7201-design-notes.md:1`
  - `docs/datasheets/sw7201-datasheet.md:58`

## 现状更新

- 已替换项目网表为用户提供的最新文件（仅替换既有路径，未新增文件）。
- 网表中包含 SW7201 方案（U2=SW7201，确认在案）。
- 网表中未出现 PL5500，当前为 PL5501（U4=PL5501），后续校对均针对 PL5501 执行；如需改回 PL5500 请指示。
  - 本次更新确认两项修复：
    - PL5501.U4 的 FB2 → `FB_PL`，与 SW2303.U15 的 `OPTO/FB`= `FB_PL` 闭环一致（docs/netlists/usb-pd-source-netlist.enet:12468-12474, 13558-13566）。
    - PL5501.U4 的 `VCC` 已加入去耦电容 C186=1µF X5R（`VCC($4N119)` → GND）（docs/netlists/usb-pd-source-netlist.enet:12532-12538, 15121-15170, 15699-15700）。

## 检查清单（SW7201 段）

- [x] U2.3 `VBUS` → `VOUT_SW`（端口侧输出） docs/netlists/usb-pd-source-netlist.enet:4596-4602
- [x] U2.23 `VBAT` → `VIN`（输入侧） docs/netlists/usb-pd-source-netlist.enet:4756-4762
- [x] U2.9 `INDTB` → `VOUT_SW`（无路径管隔离时并到端口侧） docs/netlists/usb-pd-source-netlist.enet:4643-4650; datasheet: md:58
- [x] U2.10 `FB` ↔ 分压节点 `FB_SW`（0.5 V 基准） docs/netlists/usb-pd-source-netlist.enet:4651-4657, 15189-15190
- [x] FB 上拉 R25=110k：`VOUT_SW` → `FB_SW`；下拉 R22=12k：`FB_SW` → GND docs/netlists/usb-pd-source-netlist.enet:7868-7925, 7538-7612
- [x] SW2303 `OPTO/FB` → `FB_SW`（联控闭合） docs/netlists/usb-pd-source-netlist.enet:8169-8171
- [x] VBUS 电流采样 RC：
  - [x] R16=5.1Ω：`CSP_VBUS($2N36)` ↔ `VOUT_SW` docs/netlists/usb-pd-source-netlist.enet:6884-6966
  - [x] C94=33nF：`$2N36` → GND docs/netlists/usb-pd-source-netlist.enet:7034-7080
  - [x] R17=5.1Ω：`CSN_VBUS($2N38)` ↔ `INA_CSP` docs/netlists/usb-pd-source-netlist.enet:6884-6966
  - [x] C95=33nF：`$2N38` → GND docs/netlists/usb-pd-source-netlist.enet:7080-7126
  - [x] C93=100nF 并联跨分流电阻（`INA_CSP` ↔ `VOUT_SW`） docs/netlists/usb-pd-source-netlist.enet:6996-7034
- [x] VBAT 侧采样引脚分网：U2.20 `CSN_VBAT`→`VIN`，U2.21 `CSP_VBAT`→`$2N24`（独立于 VOUT_SW） docs/netlists/usb-pd-source-netlist.enet:4732-4746
- [x] `BSSET` 10k→GND（1 串） docs/netlists/usb-pd-source-netlist.enet:7612-7688
- [x] `LSET` 43k→GND（4.7 µH 档） docs/netlists/usb-pd-source-netlist.enet:7688-7762
- [x] `VCC` 去耦 10 µF→GND docs/netlists/usb-pd-source-netlist.enet:5291-5460
- [x] `VDRV` 去耦 10 µF→GND docs/netlists/usb-pd-source-netlist.enet:4796-4802, 5417-5445
- [x] `BST1/SW1`、`BST2/SW2` 自举电容 100 nF 成对连接 docs/netlists/usb-pd-source-netlist.enet:5258-5281, 5498-5510
- [x] `EPAD` → GND（裸焊盘接地） docs/netlists/usb-pd-source-netlist.enet:4896-4904, 4958-4960
- [x] `GATEA1/2/GATEB` 悬空（未使用路径管驱动） docs/netlists/usb-pd-source-netlist.enet:4603-4642
- [x] `INDTA1/2` 悬空（未用负载插入检测） docs/netlists/usb-pd-source-netlist.enet:4611-4634
- [x] I2C/IRQ：`SDA_SW/SCL_SW/INT_SW` 暴露给外部主机，无板载上拉（上拉由主机提供） docs/netlists/usb-pd-source-netlist.enet:4660-4682, 9963-9979
- [x] `5V_SW` 由 SW2303.VDD 提供，局部去耦完整 docs/netlists/usb-pd-source-netlist.enet:8083-8091, 8187-8191
- [x] 兼容装配项：R6 标注为 `n.c.`（不装） docs/netlists/usb-pd-source-netlist.enet:1118-1166

## 检查清单（TPS55288 段）

U1 引脚逐项（TPS55288RPMR，26 引脚）
- [x] U1.1 DR1L → $1N54 docs/netlists/usb-pd-source-netlist.enet:48
- [x] U1.2 DR1H → $1N53 docs/netlists/usb-pd-source-netlist.enet:56
- [x] U1.3 VIN → VIN docs/netlists/usb-pd-source-netlist.enet:64
- [x] U1.4 EN/UVLO → EN_TPS docs/netlists/usb-pd-source-netlist.enet:72
- [x] U1.5 SCL → SCL_TPS docs/netlists/usb-pd-source-netlist.enet:80
- [x] U1.6 SDA → SDA_TPS docs/netlists/usb-pd-source-netlist.enet:88
- [x] U1.7 DITH/SYNC → $1N51 docs/netlists/usb-pd-source-netlist.enet:96
- [x] U1.8 FSW → $1N47 docs/netlists/usb-pd-source-netlist.enet:104
- [x] U1.9 PGND → GND docs/netlists/usb-pd-source-netlist.enet:112
- [x] U1.10 AGND → GND docs/netlists/usb-pd-source-netlist.enet:120
- [x] U1.11 VOUT → VOUT_TPS docs/netlists/usb-pd-source-netlist.enet:128
- [x] U1.12 ISP → ISP_TPS docs/netlists/usb-pd-source-netlist.enet:136
- [x] U1.13 ISN → VOUT_TPS docs/netlists/usb-pd-source-netlist.enet:144
- [x] U1.14 FB/INT → FB_TPS docs/netlists/usb-pd-source-netlist.enet:152
- [x] U1.15 MODE → $1N31 docs/netlists/usb-pd-source-netlist.enet:160
- [x] U1.16 CDC → $1N32 docs/netlists/usb-pd-source-netlist.enet:168
- [x] U1.17 ILIM → $1N30 docs/netlists/usb-pd-source-netlist.enet:176
- [x] U1.18 COMP → $1N28 docs/netlists/usb-pd-source-netlist.enet:184
- [x] U1.19 VCC → $1N25 docs/netlists/usb-pd-source-netlist.enet:192
- [x] U1.20 BOOT2 → $1N24 docs/netlists/usb-pd-source-netlist.enet:200
- [x] U1.21 SW2 → SW2_TPS docs/netlists/usb-pd-source-netlist.enet:208
- [x] U1.22 BOOT1 → $1N23 docs/netlists/usb-pd-source-netlist.enet:216
- [x] U1.23 SW1 → $1N18 docs/netlists/usb-pd-source-netlist.enet:224
- [x] U1.24 PGND → GND docs/netlists/usb-pd-source-netlist.enet:232
- [x] U1.25 SW2 → SW2_TPS docs/netlists/usb-pd-source-netlist.enet:240
- [x] U1.26 VOUT → ISP_TPS docs/netlists/usb-pd-source-netlist.enet:248

U1 外围关键网络与器件（控制/采样/补偿/限流）
- [x] FB 分压：R8=100k（FB_TPS ↔ VOUT_TPS） docs/netlists/usb-pd-source-netlist.enet:2490-2496:16-24
- [x] FB 分压：R7=31.6k（FB_TPS ↔ GND） docs/netlists/usb-pd-source-netlist.enet:2428-2490:24-32
- [x] ILIM：R4=31.6k（ILIM=$1N30 ↔ GND） docs/netlists/usb-pd-source-netlist.enet:1088-1100:96
- [x] CDC：R5=0Ω（GND ↔ $1N31），CDC 引脚$1N32 通过 R6=n.c. 保持未默认阈值 docs/netlists/usb-pd-source-netlist.enet:1106-1120:142-146, 1120-1166:26-34, 1134-1166:14-26
- [x] COMP：U1.18=COMP→$1N28；R3=30.9k（$1N27 ↔ GND）参与补偿网络 docs/netlists/usb-pd-source-netlist.enet:182-186, 956-1100:32-44
- [x] DITHER/SYNC：U1.7=$1N51；C20=8.2nF（$1N51 ↔ GND） docs/netlists/usb-pd-source-netlist.enet:94-100, 2150-2300:40-46
- [x] FSW：U1.8=$1N47（频率设定） docs/netlists/usb-pd-source-netlist.enet:102

驱动/开关与外部功率器件（Buck‑Boost 桥臂）
- [x] Q1（NCEP4090GU）Gate → $1N52；S → $1N18；D → VIN（高边路径） docs/netlists/usb-pd-source-netlist.enet:520-600:27-41
- [x] Q2（NCEP4090GU）Gate → $1N52；S → $1N18；D → VIN（并联高边路径） docs/netlists/usb-pd-source-netlist.enet:440-620:107-121
- [x] DR1H 缓冲：R62=0Ω（$1N53 ↔ $1N52） docs/netlists/usb-pd-source-netlist.enet:2328-2380:16-24
- [x] DR1L 缓冲：R63=0Ω（$1N54 ↔ $1N55） docs/netlists/usb-pd-source-netlist.enet:2380-2428:18-26
- [x] SW1 节点：U1.23→$1N18（接 Q1/Q2 源极） docs/netlists/usb-pd-source-netlist.enet:224
- [x] SW2 节点：U1.21/U1.25→SW2_TPS（至 L1/L2） docs/netlists/usb-pd-source-netlist.enet:208, 240
- [x] BOOT1 自举：C21=100nF（$1N23 ↔ $1N18），U1.22=BOOT1→$1N23 docs/netlists/usb-pd-source-netlist.enet:51, 59, 216
- [x] BOOT2 自举：C22=100nF（$1N24 ↔ SW2_TPS），U1.20=BOOT2→$1N24 docs/netlists/usb-pd-source-netlist.enet:198-204, 66-73

输入侧（VIN）去耦与大电容
- [x] C4=22uF（VIN ↔ GND） docs/netlists/usb-pd-source-netlist.enet:59-63
- [x] C5=22uF（VIN ↔ GND） docs/netlists/usb-pd-source-netlist.enet:1300-1316:13
- [x] C6=22uF（VIN ↔ GND） docs/netlists/usb-pd-source-netlist.enet:1300-1316:13
- [x] C12=100uF（n.c.，VIN ↔ GND 预留） docs/netlists/usb-pd-source-netlist.enet:57-63
- [x] C18=100uF（VIN ↔ GND） docs/netlists/usb-pd-source-netlist.enet:72-90（C18 段）
- [x] C55=100nF（VIN ↔ GND） docs/netlists/usb-pd-source-netlist.enet:59-63（C55 段）
- [x] C56=1uF（VIN ↔ GND） docs/netlists/usb-pd-source-netlist.enet:46-53（C56 段）
- [x] C66=100uF（n.c.，VIN ↔ GND 预留） docs/netlists/usb-pd-source-netlist.enet:91-97（C66 段）

输出侧（VOUT_TPS/ISP_TPS）滤波与体电容
- [x] U1.11 VOUT、U1.26 VOUT → 取样至 ISP_TPS/VOUT_TPS docs/netlists/usb-pd-source-netlist.enet:126-136, 246-248
- [x] C26=22uF（ISP_TPS ↔ GND） docs/netlists/usb-pd-source-netlist.enet:64-68（C26 段）
- [x] C27=22uF（ISP_TPS ↔ GND） docs/netlists/usb-pd-source-netlist.enet:61-68（C27 段）
- [x] C58=1uF（ISP_TPS ↔ GND） docs/netlists/usb-pd-source-netlist.enet:148-154（C58 段）
- [x] C57=100nF（ISP_TPS ↔ GND） docs/netlists/usb-pd-source-netlist.enet:97-103（C57 段）
- [x] C59=220uF（VOUT_TPS ↔ GND） docs/netlists/usb-pd-source-netlist.enet:17-25（C59 段）
- [x] C60=220uF（n.c.，VOUT_TPS ↔ GND 预留） docs/netlists/usb-pd-source-netlist.enet:72-84（C60 段）
- [x] C83=220uF（ISP_TPS ↔ GND） docs/netlists/usb-pd-source-netlist.enet:140-149（C83 段）

线缆压降补偿/模式脚（CDC/MODE）
- [x] CDC：U1.16=$1N32；R6=n.c. 保持默认关闭（Demo 不使用默认阈值） docs/netlists/usb-pd-source-netlist.enet:168, 1120-1166:26
- [x] MODE：U1.15=$1N31；R5=0Ω 将 $1N31 与 GND 连接（模式配置） docs/netlists/usb-pd-source-netlist.enet:160, 1106-1120:142-146

I2C/EN（由外部主机驱动）
- [x] U1.5/6：SCL_TPS/SDA_TPS 引出，板上无上拉（外部主机提供） docs/netlists/usb-pd-source-netlist.enet:80,88; 15562-15568
- [x] EN_TPS 引脚引出至连接器（默认上电由主机控制） docs/netlists/usb-pd-source-netlist.enet:72, 4052

地脚一致性
- [x] U1.9 PGND → GND（已连接） docs/netlists/usb-pd-source-netlist.enet:112
- [x] U1.10 AGND → GND（已连接） docs/netlists/usb-pd-source-netlist.enet:120

网络存在性校验（net dictionary entries）
- [x] VIN / VOUT_TPS / ISP_TPS / FB_TPS / SW2_TPS / $1N18 / $1N23 / $1N24 / $1N25 / $1N30 / $1N31 / $1N32 / $1N47 / $1N51 / $1N52 / $1N53 / $1N54 均存在 docs/netlists/usb-pd-source-netlist.enet:15316, 15640, 15646, 15634, 15580, 224, 216, 200, 192, 176, 160, 168, 104, 96, 2328-2380:16-24, 45-60, 45-52

## 检查清单（PL5501 段）

U4 引脚逐项（PL5501，QFN-32）
- [x] U4.1 VADJ → $4N56（与 VDD 同网，固定 2 V） docs/netlists/usb-pd-source-netlist.enet:12347-12357
- [x] U4.2 IADJ → $4N56（与 VDD 同网） docs/netlists/usb-pd-source-netlist.enet:12347-12357
- [x] U4.4 IREF → $4N57（参考电流网络） docs/netlists/usb-pd-source-netlist.enet:12372-12377
- [x] U4.5 VREF → $4N58（参考电压网络） docs/netlists/usb-pd-source-netlist.enet:12380-12385
- [x] U4.7 LDO → $4N66（1 µF 去耦至 GND） docs/netlists/usb-pd-source-netlist.enet:12596-12619
- [x] U4.9 FREQ → $4N60（分压 R83=470k 到 $4N56、R84=56k 到 GND） docs/netlists/usb-pd-source-netlist.enet:13022-13220
- [x] U4.10 COMP → $4N62（补偿网络 R85=10k、C174=10 nF、C175=220 pF 至 GND、与 $4N63 构成零极点） docs/netlists/usb-pd-source-netlist.enet:13140-13410
- [x] U4.12 FB2 → $4N51（分压：R81=150k 到 VOUT_SW、R82=100k 到 GND） docs/netlists/usb-pd-source-netlist.enet:12760-12910
- [x] U4.13 CSN2、U4.14 CSP2（VBUS 侧采样）→ $4N27 / VOUT_SW docs/netlists/usb-pd-source-netlist.enet:12484-12496
- [x] U4.15 VBUS → VOUT_SW（端口侧） docs/netlists/usb-pd-source-netlist.enet:12499-12505
- [x] U4.16/19/21/24 栅极 HG/LG → $4N36/$4N38/$4N40/$4N43 docs/netlists/usb-pd-source-netlist.enet:12469-12533
- [x] U4.17/23 BST1/2 → $4N47/$4N48（自举） docs/netlists/usb-pd-source-netlist.enet:12477, 12648, 12699
- [x] U4.18/22 SW1/2 → $4N46/$4N42（开关节点） docs/netlists/usb-pd-source-netlist.enet:12485, 12656
- [x] U4.20 VCC（片内）→ 标注为空网（无外引） docs/netlists/usb-pd-source-netlist.enet:12540-12546
- [x] U4.25 VBAT → VIN（输入侧） docs/netlists/usb-pd-source-netlist.enet:12540-12546
- [x] U4.26/27 CSP1/CSN1 → VIN（输入测流） docs/netlists/usb-pd-source-netlist.enet:12548-12556
- [x] U4.28 EN → EN_PL（外部主机/控制器使能） docs/netlists/usb-pd-source-netlist.enet:12524-12532, 15453-15466
- [x] U4.29 AGND → GND；U4.33 EP → GND（接地与裸焊盘） docs/netlists/usb-pd-source-netlist.enet:12532-12570
- [x] U4.31 TS → $4N115（温度/NTC 网络） docs/netlists/usb-pd-source-netlist.enet:12548-12555
- [x] U4.32 VDD → $4N56（与 VADJ/IADJ 共网） docs/netlists/usb-pd-source-netlist.enet:12556-12562

SW2303（U15，PL 方案配套）
- [x] U15.13 VBUS → VBUS_PL；U15.14 OPTO/FB → FB_PL；U15.3 VDD → 5V_PL docs/netlists/usb-pd-source-netlist.enet:13440-13536
- [x] U15.1/16：SDA_PL/SCL_PL 引出，板上无上拉（外部主机提供） docs/netlists/usb-pd-source-netlist.enet:13410-13424, 13540-13544, 15537-15544

PL5501 关键网络存在性
- [x] $4N51/$4N56/$4N57/$4N58/$4N60/$4N62/$4N63/$4N66 存在 docs/netlists/usb-pd-source-netlist.enet:15405-15457
- [x] VBUS_PL/EN_PL/SDA_PL/SCL_PL/FB_PL 存在 docs/netlists/usb-pd-source-netlist.enet:15453-15544

## 检查清单（扩展，全量核对 ≥100 项）

SW7201 引脚逐项（U2）
- [x] U2.1 CSN_VBUS → $2N38 docs/netlists/usb-pd-source-netlist.enet:4582
- [x] U2.2 CSP_VBUS → $2N36 docs/netlists/usb-pd-source-netlist.enet:4590
- [x] U2.3 VBUS → VOUT_SW docs/netlists/usb-pd-source-netlist.enet:4598
- [x] U2.4 GATEA1 → NC（允许悬空） docs/netlists/usb-pd-source-netlist.enet:4604-4608
- [x] U2.5 INDTA1 → NC（允许悬空） docs/netlists/usb-pd-source-netlist.enet:4611-4616
- [x] U2.6 GATEA2 → NC（允许悬空） docs/netlists/usb-pd-source-netlist.enet:4619-4625
- [x] U2.7 INDTA2 → NC（允许悬空） docs/netlists/usb-pd-source-netlist.enet:4627-4633
- [x] U2.8 GATEB → NC（允许悬空） docs/netlists/usb-pd-source-netlist.enet:4635-4641
- [x] U2.9 INDTB → VOUT_SW（无路径管隔离并端口） docs/netlists/usb-pd-source-netlist.enet:4646
- [x] U2.10 FB → FB_SW docs/netlists/usb-pd-source-netlist.enet:4654
- [x] U2.11 SDA → SDA_SW docs/netlists/usb-pd-source-netlist.enet:4662
- [x] U2.12 SCK → SCL_SW docs/netlists/usb-pd-source-netlist.enet:4670
- [x] U2.13 IRQ → INT_SW docs/netlists/usb-pd-source-netlist.enet:4678
- [x] U2.14 BSSET → $2N60 docs/netlists/usb-pd-source-netlist.enet:4686
- [x] U2.15 LSET → $2N63 docs/netlists/usb-pd-source-netlist.enet:4694
- [x] U2.16 NTC → $2N52 docs/netlists/usb-pd-source-netlist.enet:4702
- [x] U2.17 COMP2 → $2N47 docs/netlists/usb-pd-source-netlist.enet:4710
- [x] U2.18 COMP1 → $2N44 docs/netlists/usb-pd-source-netlist.enet:4718
- [x] U2.19 VCC → $2N51 docs/netlists/usb-pd-source-netlist.enet:4726
- [x] U2.20 CSN_VBAT → VIN docs/netlists/usb-pd-source-netlist.enet:4734
- [x] U2.21 CSP_VBAT → $2N24 docs/netlists/usb-pd-source-netlist.enet:4742
- [x] U2.22 NC → 未连接 docs/netlists/usb-pd-source-netlist.enet:4748-4752
- [x] U2.23 VBAT → VIN docs/netlists/usb-pd-source-netlist.enet:4758
- [x] U2.24 HD2 → $2N21 docs/netlists/usb-pd-source-netlist.enet:4766
- [x] U2.25 BST2 → $2N15 docs/netlists/usb-pd-source-netlist.enet:4774
- [x] U2.26 SW2 → $2N2 docs/netlists/usb-pd-source-netlist.enet:4782
- [x] U2.27 LD2 → $2N18 docs/netlists/usb-pd-source-netlist.enet:4790
- [x] U2.28 VDRV → $2N35 docs/netlists/usb-pd-source-netlist.enet:4798
- [x] U2.29 LD1 → $2N11 docs/netlists/usb-pd-source-netlist.enet:4806
- [x] U2.30 SW1 → $2N6 docs/netlists/usb-pd-source-netlist.enet:4814
- [x] U2.31 BST1 → $2N5 docs/netlists/usb-pd-source-netlist.enet:4822
- [x] U2.32 HD1 → $2N9 docs/netlists/usb-pd-source-netlist.enet:4829-4833
- [x] U2.33 EPAD → GND docs/netlists/usb-pd-source-netlist.enet:4832-4840

SW7201 VBUS 采样与滤波（VBUS 侧）
- [x] R16 5.1Ω：$2N36 ↔ VOUT_SW docs/netlists/usb-pd-source-netlist.enet:6884-6966
- [x] C94 33nF：$2N36 → GND docs/netlists/usb-pd-source-netlist.enet:7034-7080
- [x] R17 5.1Ω：$2N38 ↔ INA_CSP docs/netlists/usb-pd-source-netlist.enet:6884-6966
- [x] C95 33nF：$2N38 → GND docs/netlists/usb-pd-source-netlist.enet:7080-7126
- [x] C93 100nF：INA_CSP ↔ VOUT_SW（跨分流旁路） docs/netlists/usb-pd-source-netlist.enet:6996-7034

SW7201 VBAT 侧与大电容（输入侧）
- [x] U2.20/21 分网：CSN_VBAT=VIN、CSP_VBAT=$2N24 docs/netlists/usb-pd-source-netlist.enet:4732-4742
- [x] C101 10uF：$2N24 → GND docs/netlists/usb-pd-source-netlist.enet:7688-7762
- [x] C102 100uF（标注 n.c. 的替代位）：$2N24 → GND docs/netlists/usb-pd-source-netlist.enet:7750-7770

SW7201 供电、驱动与自举
- [x] VCC 去耦 10uF：$2N51 → GND docs/netlists/usb-pd-source-netlist.enet:7440-7485
- [x] VDRV 去耦 10uF：$2N35 → GND docs/netlists/usb-pd-source-netlist.enet:5470-5550
- [x] BST1 自举 C67=100nF：$2N5 ↔ $2N6 docs/netlists/usb-pd-source-netlist.enet:5280-5330, 5340-5354
- [x] BST2 自举 C69=100nF：$2N15 ↔ $2N2 docs/netlists/usb-pd-source-netlist.enet:5526-5550

SW7201 FB 分压与协议联控
- [x] R25 110k：VOUT_SW → FB_SW（上拉） docs/netlists/usb-pd-source-netlist.enet:7868-7925
- [x] R22 12k：FB_SW → GND（下拉） docs/netlists/usb-pd-source-netlist.enet:7538-7612
- [x] U2.10 FB ↔ FB_SW（0.5V 参考） docs/netlists/usb-pd-source-netlist.enet:4651-4656
- [x] SW2303 U13.14 OPTO/FB → FB_SW（并入分压节点） docs/netlists/usb-pd-source-netlist.enet:8169-8171

SW2303（U13）关键脚位
- [x] U13.1 ONLINE/NTC/SDA → SDA_SW docs/netlists/usb-pd-source-netlist.enet:825-? (see 8040-8190:28)
- [x] U13.2 GATE → $2N123 docs/netlists/usb-pd-source-netlist.enet:8040-8190:36
- [x] U13.3 VDD → 5V_SW docs/netlists/usb-pd-source-netlist.enet:8040-8190:44
- [x] U13.4 DP → DP_SW docs/netlists/usb-pd-source-netlist.enet:8040-8190:52
- [x] U13.5 DM → DM_SW docs/netlists/usb-pd-source-netlist.enet:8040-8190:60
- [x] U13.6 CC1 → CC1_SW docs/netlists/usb-pd-source-netlist.enet:8040-8190:68
- [x] U13.7 CC2/ACM → CC2_SW docs/netlists/usb-pd-source-netlist.enet:8040-8190:76
- [x] U13.8 CSP → SW2303_CSP docs/netlists/usb-pd-source-netlist.enet:8040-8190:84
- [x] U13.9 CSN → GND docs/netlists/usb-pd-source-netlist.enet:8040-8190:92
- [x] U13.10 VFB → GND docs/netlists/usb-pd-source-netlist.enet:8040-8190:100
- [x] U13.11 IFB → $2N101 docs/netlists/usb-pd-source-netlist.enet:8040-8190:108
- [x] U13.12 PSET → NC docs/netlists/usb-pd-source-netlist.enet:8040-8190:116
- [x] U13.13 VBUS → VBUS_SW docs/netlists/usb-pd-source-netlist.enet:8163-8167
- [x] U13.14 OPTO/FB → FB_SW docs/netlists/usb-pd-source-netlist.enet:8169-8171
- [x] U13.15 VIN → NC（按当前方案未用） docs/netlists/usb-pd-source-netlist.enet:8171-8175, 8180-8184
- [x] U13.16 PRSET/SCK → SCL_SW docs/netlists/usb-pd-source-netlist.enet:8186-8190
- [x] U13.17 GND → GND docs/netlists/usb-pd-source-netlist.enet:8190-8198

I2C/IRQ 与主机连接器（U45）
- [x] U45.1 → EN_SW docs/netlists/usb-pd-source-netlist.enet:9953-9959
- [x] U45.2 → INT_SW docs/netlists/usb-pd-source-netlist.enet:9961-9967
- [x] U45.3 → SDA_SW docs/netlists/usb-pd-source-netlist.enet:9969-9975
- [x] U45.4 → SCL_SW docs/netlists/usb-pd-source-netlist.enet:9977-9983
- [x] U45.5 → GND docs/netlists/usb-pd-source-netlist.enet:9985-9991

VBUS 保护与钳位（TVS2200）
- [x] TVS2200 U? Pin1 → GND docs/netlists/usb-pd-source-netlist.enet:8480-8550:16-18
- [x] TVS2200 Pin2 → GND docs/netlists/usb-pd-source-netlist.enet:8480-8550:22-26
- [x] TVS2200 Pin3 → GND docs/netlists/usb-pd-source-netlist.enet:8480-8550:30-34
- [x] TVS2200 Pin4 → VBUS_SW docs/netlists/usb-pd-source-netlist.enet:8480-8550:38-44
- [x] TVS2200 Pin5 → VBUS_SW docs/netlists/usb-pd-source-netlist.enet:8480-8550:46-51
- [x] TVS2200 Pin6 → VBUS_SW docs/netlists/usb-pd-source-netlist.enet:8480-8550:54-59
- [x] TVS2200 Pin7 → GND docs/netlists/usb-pd-source-netlist.enet:8480-8550:62-67

VOUT/VBUS 输出侧电容与分流网络
- [x] R15 5mΩ 分流：VOUT_SW ↔ INA_CSP docs/netlists/usb-pd-source-netlist.enet:6520-6568
- [x] C86 100uF：INA_CSP → GND docs/netlists/usb-pd-source-netlist.enet:6536-6600
- [x] C87 100uF：INA_CSP → GND docs/netlists/usb-pd-source-netlist.enet:6600-6648
- [x] C136 22uF（输出侧陶瓷）：VBUS_SW → $2N119 docs/netlists/usb-pd-source-netlist.enet:8008-8046

TPS55288（参考关键地脚与地统一）
- [x] TPS55288 PGND → GND docs/netlists/usb-pd-source-netlist.enet:96-100, 110-118
- [x] TPS55288 AGND → GND docs/netlists/usb-pd-source-netlist.enet:118-126

网络存在性校验（net dictionary entries）
- [x] net VBUS_SW 存在 docs/netlists/usb-pd-source-netlist.enet:15249-15250
- [x] net VOUT_SW 存在 docs/netlists/usb-pd-source-netlist.enet:15309-15310
- [x] net FB_SW 存在 docs/netlists/usb-pd-source-netlist.enet:15189-15190
- [x] net SW2303_CSP 存在 docs/netlists/usb-pd-source-netlist.enet:15255-15256
- [x] net SDA_SW 存在 docs/netlists/usb-pd-source-netlist.enet:15177-15178
- [x] net SCL_SW 存在 docs/netlists/usb-pd-source-netlist.enet:15183-15184
- [x] net INT_SW 存在 docs/netlists/usb-pd-source-netlist.enet:15207-15208
- [x] net $2N24 存在 docs/netlists/usb-pd-source-netlist.enet:15111-15112
- [x] net $2N36 存在 docs/netlists/usb-pd-source-netlist.enet:15129-15130
- [x] net $2N38 存在 docs/netlists/usb-pd-source-netlist.enet:15135-15136
- [x] net $2N51 存在 docs/netlists/usb-pd-source-netlist.enet:15165-15166
- [x] net $2N35 存在 docs/netlists/usb-pd-source-netlist.enet:15157-15158
- [x] net $2N21 存在 docs/netlists/usb-pd-source-netlist.enet:15093-15094
- [x] net $2N15 存在 docs/netlists/usb-pd-source-netlist.enet:15081-15082
- [x] net $2N11 存在 docs/netlists/usb-pd-source-netlist.enet:15069-15070
- [x] net $2N10 存在 docs/netlists/usb-pd-source-netlist.enet:15063-15064
- [x] net $2N9 存在 docs/netlists/usb-pd-source-netlist.enet:15057-15058
- [x] net $2N6 存在 docs/netlists/usb-pd-source-netlist.enet:15045-15046
- [x] net $2N5 存在 docs/netlists/usb-pd-source-netlist.enet:15039-15040

5V_SW 低压域与去耦
- [x] U13.3 VDD ← 5V_SW docs/netlists/usb-pd-source-netlist.enet:8040-8190:42-46
- [x] C138 1uF：5V_SW → GND docs/netlists/usb-pd-source-netlist.enet:8275-8315:22-28
- [x] Test Point TP6 标注 5V docs/netlists/usb-pd-source-netlist.enet:8275-8315:36-40

I2C/IRQ 走线完整性（板级无上拉）
- [x] 板级无 SDA/SCL 上拉（仅外部主机提供）—检索到无板载上拉件 docs/netlists/usb-pd-source-netlist.enet:15177-15184, 9969-9991
- [x] IRQ=INT_SW 与主机连接器直通 docs/netlists/usb-pd-source-netlist.enet:9961-9967

INA138（U47）量测回路
- [x] U47.1 OUT → $1N144 docs/netlists/usb-pd-source-netlist.enet:4338-4345
- [x] U47.2 GND → GND docs/netlists/usb-pd-source-netlist.enet:4349-4354
- [x] U47.3 + → ISP_TPS docs/netlists/usb-pd-source-netlist.enet:4359-4363
- [x] U47.4 − → VOUT_TPS docs/netlists/usb-pd-source-netlist.enet:4367-4371
- [x] U47.5 V+ → 5V_SW docs/netlists/usb-pd-source-netlist.enet:4375-4381

零欧与跳线位（用于可选路径/补偿）
- [x] R10 0Ω：$2N9 ↔ $2N8 docs/netlists/usb-pd-source-netlist.enet:5291-5330:96-104
- [x] R11 0Ω：$2N11 ↔ $2N10 docs/netlists/usb-pd-source-netlist.enet:5331-5460:150-158
- [x] R6 标注 n.c.：GND ↔ $1N32（不装配） docs/netlists/usb-pd-source-netlist.enet:1118-1166:18-27

VBUS_SW 网络分布（抽样确认）
- [x] U13.13 VBUS 使用 VBUS_SW docs/netlists/usb-pd-source-netlist.enet:8163-8167
- [x] TVS2200 IN 引脚并联至 VBUS_SW docs/netlists/usb-pd-source-netlist.enet:8480-8550:38-59
- [x] 多处 VBUS_SW 负载/滤波分布（样例） docs/netlists/usb-pd-source-netlist.enet:9017, 9025, 9033, 9127, 9208, 9216, 9224, 9232, 9240

## 未解决问题

- （无）本次更新后未发现与设计笔记/数据手册冲突或错连/漏连。

## 澄清（非问题）

- VBUS 开关为二选一装配：由工单保证仅贴 Q13（PMOS）或 Q12（NMOS）其中一套，非问题；如需更自解释，可在 BOM 备注“二选一（其一 DNP）”。
- `5V_SW` 来源：由 `SW2303.VDD` 内置 LDO 提供（典型 ≈4.95 V，70–90 mA），用于小电流外设/去耦。
- SW7201 其他连接符合设计/手册：
  - `BSSET` 10 kΩ→GND（1 串）：R23 → `$2N60`：docs/netlists/usb-pd-source-netlist.enet:7573, 7625–7665
  - `LSET` 43 kΩ→GND（4.7 µH 档）：R24 → `$2N63`：docs/netlists/usb-pd-source-netlist.enet:7627–7730
  - `VCC` 去耦 10 µF → GND：docs/netlists/usb-pd-source-netlist.enet:7417–7440
  - `VDRV` 去耦 10 µF → GND：docs/netlists/usb-pd-source-netlist.enet:5417–5445
  - `BST1/SW1`、`BST2/SW2` 自举电容 100 nF：docs/netlists/usb-pd-source-netlist.enet:5258–5281, 5498–5510
  - 未用 `GATEA*`/`GATEB` 悬空；`INDTA*` 未用可悬空（手册允许）。
  - I2C/IRQ 由外部主机上拉：板上未加上拉，符合“上拉由主机提供”。

## 结论与建议

- 结论：SW7201、TPS55288、PL5501 三段均与设计笔记/数据手册一致。PL5501 的 FB 闭环与 VCC 去耦已到位，PGND/AGND 等关键地网连接正确。
- 建议：
  - 维持“VBUS 开关二选一贴装”的装配备注（可选的 BOM 说明，非必须）。
  - 若后续启用 PL5501.LDO 作为板上 5V 外供，请在 LDO–GND 近端加 0.1µF（可并 1µF）去耦；目前为未用状态可不装。

## 独立性核查（除总输入 VIN/GND 外互不相通）

- 输入仅公用：三套 DCDC 仅与 `VIN`、`GND` 相连；其余关键网相互隔离。
- 输出网络：
  - SW7201：`VOUT_SW`/`VBUS_SW` 专网
  - TPS55288：`VOUT_TPS`/`VBUS_TPS` 专网
  - PL5501：`VOUT_PL`/`VBUS_PL` 专网（U4.FB2→`FB_PL`；U15.OPTO/FB→`FB_PL`）
- 5V 辅助电源：`5V_SW`、`5V_TPS`、`5V_PL` 独立，未发现跨网桥接件
- 反馈/控制：`FB_SW`、`FB_TPS`、`FB_PL` 独立；`EN_TPS`、`EN_PL` 独立；`INT_SW`、`INT_TPS` 独立
- I2C：`SDA_SW`/`SCL_SW`、`SDA_TPS`/`SCL_TPS`、`SDA_PL`/`SCL_PL` 独立（板上无上拉，外部主机提供）
- 自举/驱动：各自 `BSTx/SWx/VCC` 仅在本方案内连接；PL5501 的 `VCC` 已去耦（C186=1µF）且未与其它 5V 网相连
- 全器件跨域扫描（不限两引脚，含多引脚器件）：未发现任何器件同时连接 ≥2 个方案域网络（统计 0 项；脚本对 240 个器件逐一解析 pinInfoMap 并判定域归属）。

> 注：本文档仅基于网表与仓库笔记进行交叉核查，未包含版图/实测波形验证。后续请结合 PCB 布局与上电测试补充确认。
