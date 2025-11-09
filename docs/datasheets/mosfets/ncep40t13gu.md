# NCEP40T13GU Datasheet (Mineru Extract)

> Source: [docs/datasheets/source/NCEP40T13GU-datasheet.pdf](../source/NCEP40T13GU-datasheet.pdf)

## Overview
- 40 V / 130 A（硅片限制）DFN5x6-8L N-channel 超级沟槽 MOSFET，面向大电流同步整流与低压母线。
- 典型 RDS(on) 1.8 mΩ@VGS=10 V、2.8 mΩ@VGS=4.5 V，兼具极低导通损耗与优异 FOM。
- 额定结温 150 °C，单脉冲雪崩能量 600 mJ，100% UIS / ΔVDS 测试。

## 主要特性
| 指标 | 数值 |
| --- | --- |
| 封装 | DFN5x6-8L |
| VDS | 40 V |
| ID (silicon limit / Tc=100 °C) | 130 A / 100 A |
| IDM (package limit) | 400 A |
| RDS(on) (typ) | 1.8 mΩ @10 V / 2.8 mΩ @4.5 V |
| 功耗 PD | 80 W |
| RθJC | 1.56 °C/W |
| 单脉冲雪崩能量 | 600 mJ |
| VGS(max) | ±20 V |

## 应用
- 大电流 DC/DC 同步整流级
- 低压母线 OR-ing、热插拔 / 负载开关

## 绝对额定值 (Tc=25 °C，除非另有说明)
| 参数 | 符号 | 极限 | 单位 |
| --- | --- | --- | --- |
| 漏源电压 | VDS | 40 | V |
| 栅源电压 | VGS | ±20 | V |
| 连续漏电流 (Si 限制 / Tc=100 °C) | ID | 130 / 100 | A |
| 脉冲漏电流 | IDM | 400 | A |
| 功率耗散 | PD | 80 | W |
| 雪崩能量 | EAS | 600 | mJ |
| 结温/储存温度 | TJ, TSTG | -55 ~ 150 | °C |

## 备注
- 更详细的电气特性（阈值、Qg、输出电容、SOA 等）可参考源 PDF，以便进行热设计与驱动器匹配。
