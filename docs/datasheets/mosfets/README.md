# MOSFET Datasheet Index

汇总 `docs/datasheets/mosfets` 目录下的每份手册，按沟道类型与封装整理，每条目突出耐压/电流和 RDS(on) 关键指标，方便快速定位合适的器件。

## P-Channel 器件

### SOIC-8
- `AO4407A` — -30 V / -12 A 负载开关用 P 沟道器件，RDS(on) 11 mΩ@VGS=-20 V、13 mΩ@-10 V、17 mΩ@-6 V；数据见 `docs/datasheets/mosfets/ao4407a.md`。

### DFN5x6（含 DFN 5x6 标记）
- `AON6405` — -30 V / -30 A，RDS(on) 5.2 mΩ@VGS=-10 V、7.6 mΩ@-4.5 V；`docs/datasheets/mosfets/aon6405.md`。
- `AONS20485` — -40 V / -40 A，RDS(on) 15 mΩ@VGS=-10 V、20 mΩ@-4.5 V；`docs/datasheets/mosfets/aons20485.md`。
- `NCE20P70G` — -20 V / -70 A，RDS(on) 3 mΩ@VGS=-4.5 V、4 mΩ@-2.5 V、8 mΩ@-1.8 V；`docs/datasheets/mosfets/nce20p70g.md`。
- `NCE30P30G` — -30 V / -30 A，典型 RDS(on) 7.4 mΩ@VGS=-10 V、11 mΩ@-4.5 V；`docs/datasheets/mosfets/nce30p30g.md`。
- `NCE30P50G` — -30 V / -50 A，典型 RDS(on) 4.4 mΩ@VGS=-10 V（最大 7 mΩ），适合大电流负载；`docs/datasheets/mosfets/nce30p50g.md`。

### DFN3.3x3.3（含 -8L 型号）
- `NCE20P45Q` — -20 V / -45 A，RDS(on) 7 mΩ@VGS=-4.5 V、9 mΩ@-2.5 V、12 mΩ@-1.8 V；`docs/datasheets/mosfets/nce20p45q.md`。
- `NCE30P28Q` — -30 V / -28 A，RDS(on) 9 mΩ@VGS=-10 V、17 mΩ@-4.5 V；`docs/datasheets/mosfets/nce30p28q.md`。
- `NCE40P20Q` — -40 V / -20 A，RDS(on) 18 mΩ@VGS=-10 V、28 mΩ@-4.5 V；`docs/datasheets/mosfets/nce40p20q.md`。

### PowerDI 3333-8
- `DMP3013SFV` — -30 V P 沟道，ID -35 A（Tc=25 °C），RDS(on) 9.5 mΩ@VGS=-10 V、17 mΩ@-4.5 V；`docs/datasheets/mosfets/dmp3013sfv.md`。

### TO-252-2L
- `NCE01P30K` — -100 V / -30 A，典型 RDS(on) 44 mΩ@VGS=-10 V、48 mΩ@-4.5 V；`docs/datasheets/mosfets/nce01p30k.md`。

### SOP-8
- `NCE40P13S` — -40 V / -13 A，RDS(on) 15 mΩ@VGS=-10 V，适合中等功率侧；`docs/datasheets/mosfets/nce40p13s.md`。

## N-Channel 器件

### DFN5x6（含 DFN5X6-8L）
- `AON6414A` — 30 V / 30 A（50 A 脉冲），RDS(on) <8 mΩ@VGS=10 V、<10.5 mΩ@4.5 V；`docs/datasheets/mosfets/aon6414a.md`。
- `NCEP01ND35AG` — 100 V / 35 A，典型 RDS(on) 24 mΩ@VGS=10 V、27 mΩ@4.5 V，适合高压同步整流；`docs/datasheets/mosfets/ncep01nd35ag.md`。
- `NCEP035N85GU` — 85 V / 130 A，典型 RDS(on) 2.7 mΩ@VGS=10 V；`docs/datasheets/mosfets/ncep035n85gu.md`。
- `NCEP3045GU` — 30 V / 45 A，RDS(on) 5.8 mΩ@VGS=10 V、8.0 mΩ@4.5 V；`docs/datasheets/mosfets/ncep3045gu.md`。
- `NCEP3090GU` — 30 V / 90 A，RDS(on) 2.0 mΩ@VGS=10 V、3.1 mΩ@4.5 V；`docs/datasheets/mosfets/ncep3090gu.md`。
- `NCEP40T14G` — 40 V / 140 A，RDS(on) 1.6 mΩ@VGS=10 V、2.3 mΩ@4.5 V；`docs/datasheets/mosfets/ncep40t14g.md`。
- `NCEP6080AG` — 60 V / 80 A，RDS(on) <4 mΩ@VGS=10 V（typ 3.5 mΩ）、<5 mΩ@4.5 V；`docs/datasheets/mosfets/ncep6080ag.md`。
- `NCEP6090AGU` — 60 V / 90 A，典型 RDS(on) 2.8 mΩ@VGS=10 V、3.5 mΩ@4.5 V；`docs/datasheets/mosfets/ncep6090agu.md`。

### DFN3x3 / DFN3x3 EP
- `AON7410` — 30 V / 24 A，RDS(on) <20 mΩ@VGS=10 V、<26 mΩ@4.5 V；`docs/datasheets/mosfets/aon7410.md`。
- `AON7508` — 30 V / 32 A 的 DFN 3x3 EP 封装，RDS(on) <3.0 mΩ@VGS=10 V、<4.6 mΩ@4.5 V；`docs/datasheets/mosfets/aon7508.md`。
- `NCE3035Q` — 30 V / 35 A，RDS(on) <7 mΩ@VGS=10 V、<11 mΩ@4.5 V；`docs/datasheets/mosfets/nce3035q.md`。

### DFN3.3x3.3（含 3.3×3.3-8L）
- `NCE3025Q` — 30 V / 25 A，RDS(on) <10 mΩ@VGS=10 V、<14 mΩ@4.5 V；`docs/datasheets/mosfets/nce3025q.md`。
- `NCEP3040Q` — 30 V / 40 A，典型 RDS(on) 6.8 mΩ@VGS=10 V、9.5 mΩ@4.5 V；`docs/datasheets/mosfets/ncep3040q.md`。
- `NCEP3065QU` — DFN3.3×3.3-8L，30 V / 65 A（45.5 A@100 °C），RDS(on) 1.9 mΩ@VGS=10 V、3.0 mΩ@4.5 V；`docs/datasheets/mosfets/ncep3065qu.md`。

### TO-252-2L
- `NCE2030K` — 20 V / 30 A，RDS(on) <13 mΩ@VGS=10 V（典型 10.5 mΩ），适合大电流板载开关；`docs/datasheets/mosfets/nce2030k.md`。

### PowerPAK 1212-8
- `SiS454DN` — 20 V / 35 A，RDS(on) 3.7 mΩ@VGS=10 V、5.4 mΩ@4.5 V，Qg 18.5 nC；`docs/datasheets/mosfets/sis454dn.md`。

### Package TBD
- `AON7408` — 30 V / 18 A，RDS(on) <20 mΩ@VGS=10 V、<32 mΩ@4.5 V；原始 PDF 未标出封装，可先在 `docs/datasheets/mosfets/aon7408.md` 查询尺寸图再确认。

> 如果后续有新增手册，只需在相同格式下追加条目，即可保持按类型/封装的检索体验。
