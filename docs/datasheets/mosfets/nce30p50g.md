# NCE30P50G Datasheet (Mineru Extract)

> Source: [docs/datasheets/source/NCE30P50G.pdf](../source/NCE30P50G.pdf)

## Device Overview

- P-channel enhancement MOSFET, DFN5x6-EP package
- `VDS = -30 V`, `ID = -50 A`
- Typical `RDS(on)`:
  - 4.4 mOhm @ `VGS = -10 V`, `ID = -10 A`
  - 7 mOhm (max) @ `VGS = -10 V`, `ID = -10 A`
- Gate charge: `Qg = 84 nC` (typ) @ `VDS = -15 V`, `ID = -10 A`, `VGS = -10 V`

![](../assets/mosfets/nce30p50g/dd14503d822acedd2f3eab85adcae8fdb6f1e198b5f606892da0a4d48c1f65a3.jpg)

## Absolute Maximum Ratings (25 degC)

| Parameter | Symbol | Limit | Unit |
| --- | --- | --- | --- |
| Drain-source voltage | `VDS` | -30 | V |
| Gate-source voltage | `VGS` | +/-20 | V |
| Continuous drain current | `ID` | -50 | A |
| Pulsed drain current | `IDM` | -200 | A |
| Power dissipation | `PD` | 35 | W |
| Junction/storage temp. | `TJ, TSTG` | -55 to 150 | degC |

## Thermal Characteristics

| Parameter | Symbol | Typ. | Unit |
| --- | --- | --- | --- |
| Junction-to-case thermal resistance | `RthJC` | 3.6 | degC/W |

## Electrical Characteristics (25 degC)

| Parameter | Symbol | Test Conditions | Min | Typ | Max | Unit |
| --- | --- | --- | --- | --- | --- | --- |
| Drain-source breakdown | `BVDSS` | `VGS = 0 V`, `ID = -250 uA` | -30 | -33 | - | V |
| Zero-gate drain current | `IDSS` | `VDS = -30 V`, `VGS = 0 V` | - | - | 1 | uA |
| Gate-body leakage | `IGSS` | `VGS = +/-20 V`, `VDS = 0 V` | - | - | +/-100 | nA |
| Gate threshold voltage | `VGS(th)` | `VDS = VGS`, `ID = -250 uA` | -1.0 | -1.5 | -2.2 | V |
| `RDS(on)` | `RDS(on)` | `VGS = -10 V`, `ID = -10 A` | - | 4.4 | 7 | mOhm |
| Forward transconductance | `gfs` | `VDS = -10 V`, `ID = -15 A` | - | 20 | - | S |
| Input capacitance | `Ciss` | `VDS = -15 V`, `VGS = 0`, `f = 1 MHz` | - | 3590 | - | pF |
| Output capacitance | `Coss` | same | - | 695 | - | pF |
| Reverse transfer capacitance | `Crss` | same | - | 665 | - | pF |
| Total gate charge | `Qg` | `VDS = -15 V`, `ID = -10 A`, `VGS = -10 V` | - | 84 | - | nC |
| Gate-source charge | `Qgs` | same | - | 11.7 | - | nC |
| Gate-drain charge | `Qgd` | same | - | 25 | - | nC |
| Turn-on delay | `td(on)` | `VDD = -15 V`, `ID = -10 A`, `VGS = -10 V`, `RG = 6 ohm` | - | 13 | - | ns |
| Rise time | `tr` | same | - | 12 | - | ns |
| Turn-off delay | `td(off)` | same | - | 50 | - | ns |
| Fall time | `tf` | same | - | 14 | - | ns |
| Body diode forward voltage | `VSD` | `VGS = 0`, `ID = -10 A` | - | -0.85 | -1.2 | V |
| Reverse recovery time | `trr` | `IF = -10 A`, `di/dt = 100 A/us`, `TJ = 25 degC` | - | - | 45 | ns |
| Reverse recovery charge | `Qrr` | same | - | - | 43 | nC |

![](../assets/mosfets/nce30p50g/072f34ca8e2d493e1e0d731a0c6ce4189676b8145745999c70da34aab9769af9.jpg)

> Extracted from the PDF via `mcp__mineru__parse_documents`; figures reference the copied assets in `docs/assets/mosfets/nce30p50g/`.
