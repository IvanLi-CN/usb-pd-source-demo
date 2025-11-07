# NCEP3065QU Datasheet Summary

> Source: [docs/datasheets/source/NCEP3065QU.pdf](../source/NCEP3065QU.pdf)

## Device Overview

- N-channel Super Trench I MOSFET in `DFN3.3×3.3-8L` package
- `VDS = 30 V`, continuous `ID = 65 A` (25 °C), `ID = 45.5 A` @ 100 °C
- Typical `RDS(on)`:
  - 1.9 mΩ @ `VGS = 10 V`, `ID = 20 A`
  - 3.0 mΩ @ `VGS = 4.5 V`, `ID = 20 A`
- Optimised for high-frequency switching and synchronous rectification
- 100% UIS / ΔVDS tested, Pb-free lead finish

## Absolute Maximum Ratings (TC = 25 °C)

| Parameter | Symbol | Limit | Unit |
| --- | --- | --- | --- |
| Drain-source voltage | `VDS` | 30 | V |
| Gate-source voltage | `VGS` | ±20 | V |
| Continuous drain current (25 °C) | `ID` | 65 | A |
| Continuous drain current (100 °C) | `ID(100°C)` | 45.5 | A |
| Pulsed drain current | `IDM` | 260 | A |
| Power dissipation | `PD` | 55 | W |
| Derating factor | — | 0.44 | W/°C |
| Single pulse avalanche energy | `EAS` | 500 | mJ |
| Operating junction/storage temp. | `TJ`, `TSTG` | -55 to 150 | °C |

## Thermal Resistance

| Parameter | Symbol | Typ. | Unit |
| --- | --- | --- | --- |
| Junction-to-case | `RθJC` | 2.3 | °C/W |

## Electrical Characteristics (TC = 25 °C)

| Parameter | Symbol | Test Conditions | Min | Typ | Max | Unit |
| --- | --- | --- | --- | --- | --- | --- |
| Drain-source breakdown | `BVDSS` | `VGS = 0 V`, `ID = 250 µA` | 30 | – | – | V |
| Zero-gate drain current | `IDSS` | `VDS = 30 V`, `VGS = 0 V` | – | – | 1 | µA |
| Gate-body leakage | `IGSS` | `VGS = ±5 V/±20 V`, `VDS = 0 V` | – | – | ±80/±100 | nA |
| Gate threshold voltage | `VGS(th)` | `VDS = VGS`, `ID = 250 µA` | 1.0 | 1.5 | 2.0 | V |
| On-state resistance | `RDS(on)` | `VGS = 10 V`, `ID = 20 A` | – | 1.9 | 2.3 | mΩ |
|  |  | `VGS = 4.5 V`, `ID = 20 A` | – | 3.0 | 3.6 | mΩ |
| Forward transconductance | `gFS` | `VDS = 5 V`, `ID = 20 A` | 60 | – | – | S |
| Input capacitance | `Ciss` | `VDS = 15 V`, `VGS = 0 V`, `f = 1 MHz` | – | 5100 | – | pF |
| Output capacitance | `Coss` | Same as above | – | 1360 | – | pF |
| Reverse transfer capacitance | `Crss` | Same as above | – | 220 | – | pF |
| Total gate charge | `Qg` | `VDS = 15 V`, `ID = 45 A`, `VGS = 10 V` | – | 54 | – | nC |
| Gate-to-drain charge | `Qgd` | Same conditions | – | 16 | – | nC |
| Gate-to-source charge | `Qgs` | Same conditions | – | 10 | – | nC |

## Package Marking

- Device marking: `NCEP3065QU`
- Reel: Ø180 mm, 5000 pcs per reel

## Typical Performance Notes

- Very low `RDS(on)` with good charge figure of merit supports SW2303 charge pump drive.
- High avalanche energy (500 mJ) supports hot-plug and surge events when paired with SW2303 OVP.
