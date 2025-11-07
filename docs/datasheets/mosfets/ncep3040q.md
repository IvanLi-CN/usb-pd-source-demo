# NCEP3040Q Datasheet (Mineru Extract)

> Source: [docs/datasheets/source/NCEP3040Q.pdf](../source/NCEP3040Q.pdf)

## Device Overview

- N-channel Super Trench MOSFET, DFN3.3x3.3-8L package
- `VDS = 30 V`, `ID = 40 A` (25 degC)
- Typical `RDS(on)`:
  - 6.8 mOhm @ `VGS = 10 V`, `ID = 20 A`
  - 9.5 mOhm @ `VGS = 4.5 V`, `ID = 20 A`
- Optimized for synchronous rectification and high-frequency DC/DC conversion

![](../assets/mosfets/ncep3040q/80c1e7285e1a9eb4bb6b02dafb08dfbf1d19e375d342bd036ab75b23a091336d.jpg)

## Absolute Maximum Ratings (25 degC)

| Parameter | Symbol | Limit | Unit |
| --- | --- | --- | --- |
| Drain-source voltage | `VDS` | 30 | V |
| Gate-source voltage | `VGS` | +/-20 | V |
| Continuous drain current | `ID` | 40 | A |
| Continuous drain current @100 degC | `ID(100C)` | 28.3 | A |
| Pulsed drain current | `IDM` | 125 | A |
| Power dissipation | `PD` | 25 | W |
| Junction/storage temp. | `TJ, TSTG` | -55 to 150 | degC |

## Thermal Characteristics

| Parameter | Symbol | Typ. | Unit |
| --- | --- | --- | --- |
| Junction-to-case thermal resistance | `RthJC` | 5 | degC/W |

## Electrical Characteristics (25 degC)

| Parameter | Symbol | Test Conditions | Min | Typ | Max | Unit |
| --- | --- | --- | --- | --- | --- | --- |
| Drain-source breakdown | `BVDSS` | `VGS = 0 V`, `ID = 250 uA` | 30 | - | - | V |
| Zero-gate drain current | `IDSS` | `VDS = 30 V`, `VGS = 0 V` | - | - | 1 | uA |
| Gate-body leakage | `IGSS` | `VGS = +/-20 V`, `VDS = 0 V` | - | - | +/-100 | nA |
| Gate threshold voltage | `VGS(th)` | `VDS = VGS`, `ID = 250 uA` | 1.0 | 1.5 | 2.0 | V |
| `RDS(on)` | `RDS(on)` | `VGS = 10 V`, `ID = 20 A` | - | 6.8 | 7.1 | mOhm |
| `RDS(on)` | `RDS(on)` | `VGS = 4.5 V`, `ID = 20 A` | - | 9.5 | 11 | mOhm |
| Forward transconductance | `gfs` | `VDS = 5 V`, `ID = 20 A` | - | 30 | - | S |
| Input capacitance | `Ciss` | `VDS = 15 V`, `VGS = 0`, `f = 1 MHz` | - | 822 | - | pF |
| Output capacitance | `Coss` | same | - | 344 | - | pF |
| Reverse transfer capacitance | `Crss` | same | - | 15.3 | - | pF |
| Total gate charge | `Qg` | `VDS = 15 V`, `ID = 20 A`, `VGS = 10 V` | - | 15 | - | nC |
| Gate-source charge | `Qgs` | same | - | 2.9 | - | nC |
| Gate-drain charge | `Qgd` | same | - | 2.1 | - | nC |
| Turn-on delay | `td(on)` | `VDD = 15 V`, `ID = 20 A`, `RG = 1.6 ohm`, `VGS = 10 V` | - | 6.5 | - | ns |
| Rise time | `tr` | same | - | 2.5 | - | ns |
| Turn-off delay | `td(off)` | same | - | 17 | - | ns |
| Fall time | `tf` | same | - | 2.5 | - | ns |
| Body diode forward voltage | `VSD` | `VGS = 0`, `ID = 20 A` | - | 0.85 | 1.2 | V |
| Reverse recovery time | `trr` | `IF = 20 A`, `di/dt = 100 A/us`, `TJ = 25 degC` | - | 11 | - | ns |
| Reverse recovery charge | `Qrr` | same | - | 19 | - | nC |

![](../assets/mosfets/ncep3040q/32d5b525b430884c2f4aff66c4207076c6f1c438afc71c7a1eae3929521e47c8.jpg)

> Extracted from the PDF via `mcp__mineru__parse_documents`; figures reference the copied assets in `docs/assets/mosfets/ncep3040q/`.
