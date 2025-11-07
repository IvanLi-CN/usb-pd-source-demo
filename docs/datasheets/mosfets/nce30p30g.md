# NCE30P30G Datasheet (Mineru Extract)

> Source: [docs/datasheets/source/NCE30P30G.pdf](../source/NCE30P30G.pdf)

## Device Overview

- P-channel enhancement MOSFET, DFN5x6-8L package
- `VDS = -30 V`, `ID = -30 A`
- Typical `RDS(on)`:
  - 7.4 mOhm @ `VGS = -10 V`, `ID = -15 A`
  - 11 mOhm @ `VGS = -4.5 V`, `ID = -10 A`
- Gate charge: `Qg = 24 nC` (typ) @ `VDS = -15 V`, `ID = -15 A`
- Input capacitance: `Ciss = 2640 pF`

![](../assets/mosfets/nce30p30g/a2bdb9d2a7b96d71ca0804444763fd8893d4be32222a6548e58f71f1f567b4be.jpg)

## Absolute Maximum Ratings (25 degC)

| Parameter | Symbol | Limit | Unit |
| --- | --- | --- | --- |
| Drain-source voltage | `VDS` | -30 | V |
| Gate-source voltage | `VGS` | +/-20 | V |
| Continuous drain current | `ID` | -30 | A |
| Pulsed drain current | `IDM` | -160 | A |
| Power dissipation | `PD` | 80 | W |
| Junction/storage temp. | `TJ, TSTG` | -55 to 150 | degC |

## Thermal Characteristics

| Parameter | Symbol | Typ. | Unit |
| --- | --- | --- | --- |
| Junction-to-case thermal resistance | `RthJC` | 1.56 | degC/W |

## Electrical Characteristics (25 degC)

| Parameter | Symbol | Test Conditions | Min | Typ | Max | Unit |
| --- | --- | --- | --- | --- | --- | --- |
| Drain-source breakdown | `BVDSS` | `VGS = 0 V`, `ID = -250 uA` | -30 | -33 | - | V |
| Zero-gate drain current | `IDSS` | `VDS = -30 V`, `VGS = 0 V` | - | - | -1 | uA |
| Gate-body leakage | `IGSS` | `VGS = +/-20 V`, `VDS = 0 V` | - | - | +/-100 | nA |
| Gate threshold voltage | `VGS(th)` | `VDS = VGS`, `ID = -250 uA` | -1.0 | -1.5 | -2.2 | V |
| `RDS(on)` | `RDS(on)` | `VGS = -10 V`, `ID = -15 A` | - | 7.4 | 10 | mOhm |
| `RDS(on)` | `RDS(on)` | `VGS = -4.5 V`, `ID = -10 A` | - | 11 | 15 | mOhm |
| Forward transconductance | `gfs` | `VDS = -15 V`, `ID = -15 A` | 40 | 59 | - | S |
| Input capacitance | `Ciss` | `VDS = -15 V`, `VGS = 0`, `f = 1 MHz` | - | 2640 | - | pF |
| Output capacitance | `Coss` | same as above | - | 415 | - | pF |
| Reverse transfer capacitance | `Crss` | same as above | - | 200 | - | pF |
| Total gate charge | `Qg` | `VDS = -15 V`, `ID = -15 A`, `VGS = -10 V` | - | 24 | - | nC |
| Gate-source charge | `Qgs` | same | - | 4 | - | nC |
| Gate-drain charge | `Qgd` | same | - | 12 | - | nC |
| Turn-on delay | `td(on)` | `VDD = -15 V`, `RL = 1 ohm`, `RG = 25 ohm` | - | 14 | - | ns |
| Rise time | `tr` | same | - | 27 | - | ns |
| Turn-off delay | `td(off)` | same | - | 40 | - | ns |
| Fall time | `tf` | same | - | 20 | - | ns |
| Body diode forward voltage | `VSD` | `VGS = 0`, `ID = -15 A` | - | -0.9 | -1.2 | V |
| Reverse recovery time | `trr` | `IF = -15 A`, `di/dt = 100 A/us` | - | 46 | - | ns |
| Reverse recovery charge | `Qrr` | same | - | 33 | - | nC |

![](../assets/mosfets/nce30p30g/6878f27647820822939f0a0802e5815a83fef8a8470686a2eec6e4f6fb10b3f6.jpg)

> Extracted from the PDF via `mcp__mineru__parse_documents`; figures reference the copied assets in `docs/assets/mosfets/nce30p30g/`.
