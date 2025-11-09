# NCEP4045GU Datasheet (Mineru Extract)

> Source: [docs/datasheets/source/NCEP4045GU-datasheet.pdf](../source/NCEP4045GU-datasheet.pdf)

## Overview
- 40 V / 45 A DFN5x6-8L N-channel MOSFET，面向同步整流与开关降压。
- 典型 RDS(on) 6.0 mΩ@VGS=10 V、8.5 mΩ@VGS=4.5 V，兼顾低导通损耗与中等电流能力。
- 150 °C 额定结温，Pb-free，100% UIS / ΔVDS 量产测试。

## 主要特性
| 指标 | 数值 |
| --- | --- |
| 封装 | DFN5x6-8L |
| VDS | 40 V |
| ID (Tc=25 °C / 100 °C) | 45 A / 31.8 A |
| IDM | 125 A |
| RDS(on) (typ) | 6.0 mΩ @10 V / 8.5 mΩ @4.5 V |
| 功耗 PD | 28 W (Tc=25 °C) |
| RθJC | 4.5 °C/W |
| 单脉冲雪崩能量 | 115 mJ |
| VGS(max) | ±20 V |

## 应用
- DC/DC Converter 高频同步整流
- 中功率负载开关、半桥下管

## 绝对额定值 (Tc=25 °C，除非另有说明)
| 参数 | 符号 | 极限 | 单位 |
| --- | --- | --- | --- |
| 漏源电压 | VDS | 40 | V |
| 栅源电压 | VGS | ±20 | V |
| 连续漏电流 | ID | 45 | A |
| 连续漏电流 (Tc=100 °C) | ID(100 °C) | 31.8 | A |
| 脉冲漏电流 | IDM | 125 | A |
| 功率耗散 | PD | 28 | W |
| 雪崩能量 | EAS | 115 | mJ |
| 结温/储存温度 | TJ, TSTG | -55 ~ 150 | °C |

## 备注
- 完整电气特性（阈值电压、栅电荷、输出电容等）请参考上方源 PDF；本文仅保留关键额定值以便元件选型。
