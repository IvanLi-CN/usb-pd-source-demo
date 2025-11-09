# NCEP4090GU Datasheet (Mineru Extract)

> Source: [docs/datasheets/source/NCEP4090GU-datasheet.pdf](../source/NCEP4090GU-datasheet.pdf)

## Overview
- 40 V / 90 A (25 °C) DFN5x6-8L N-channel super trench MOSFET，针对高频同步整流优化。
- 典型 RDS(on) 2.2 mΩ@VGS=10 V、3.3 mΩ@VGS=4.5 V，Qg 与导通电阻组合优异，适合高效率 DC/DC。
- 150 °C 额定结温，Pb-free 工艺，100% UIS 与 ΔVDS 测试覆盖。

## 主要特性
| 指标 | 数值 |
| --- | --- |
| 封装 | DFN5x6-8L |
| VDS | 40 V |
| ID (Tc=25 °C) | 90 A |
| ID (Tc=100 °C) | 63.6 A |
| IDM | 360 A |
| RDS(on) (typ) | 2.2 mΩ @10 V / 3.3 mΩ @4.5 V |
| 功耗 PD | 85 W @25 °C / 34 W @100 °C |
| RθJC | 1.47 °C/W |
| 单脉冲雪崩能量 | 500 mJ |
| VGS(max) | ±20 V |

## 应用
- 高效率 DC/DC 转换器
- 高频同步整流级或负载开关

## 绝对额定值 (Tc=25 °C，除非另有说明)
| 参数 | 符号 | 极限 | 单位 |
| --- | --- | --- | --- |
| 漏源电压 | VDS | 40 | V |
| 栅源电压 | VGS | ±20 | V |
| 连续漏电流 (Tc=25 °C / 100 °C) | ID | 90 / 63.6 | A |
| 脉冲漏电流 | IDM | 360 | A |
| 功率耗散 (Tc=25 °C / 100 °C) | PD | 85 / 34 | W |
| 雪崩能量 (单脉冲) | EAS | 500 | mJ |
| 结温/储存温度 | TJ, TSTG | -55 ~ 150 | °C |

## 备注
- 典型特性与完整电气表格请参阅源 PDF；本文档仅保留项目选型所需的关键额定值，方便与仓库内其它 DFN5x6 MOSFET 做对比。
