# SW7201 Register Manual (RG106_2_v1.0)

- Source: [SW7201_Register_CN.pdf](source/SW7201_Register_CN.pdf)
- Language: Chinese (register reference)
- Notes: Bit definitions for SW7201 system control, ADC telemetry, protection thresholds, and status reporting.

## Contents Overview

- Version history and register access precautions (undefined bits must not be modified).
- Interrupt enables/status (0x02-0x05), fault reporting, and GPIO/NTC configuration registers.
- Charge/discharge control registers, current limit setters, PPS voltage scaling, and ADC readouts.

## Usage Tips

- Preserve reserved bits when writing multi-byte registers.
- Configure INT/SCL/SDA pull-ups per hardware guide before enabling interrupts.
- Sequence register initialization before clearing PSTOP to start power-path operation.

<details>
<summary>Full Register Tables (CN)</summary>

# SW7201 寄存器手册

# 1 版本历史

V1.0: 初始版本针对芯片版本 1

# 2 寄存器

注意 : 未定义的寄存器或bit 不能被改写

# 2.1 REG 0x01: 版本号

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-3</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>2-0</td><td rowspan=1 colspan=1>H</td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x1</td></tr></table>

# 2.2 REG $\mathbf { 0 x 0 2 }$ : 中断使能 1

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-6</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1>14O:E1: </td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>4</td><td rowspan=1 colspan=1>140:E1: </td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>3</td><td rowspan=1 colspan=1>B 140:E1: E</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>B 10:1:</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>A2 10: 1: </td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>A110E1:</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.3 REG $\mathbf { 0 x 0 3 }$ : 中断使能 2

<table><tr><td colspan="1" rowspan="1">Bit</td><td colspan="1" rowspan="1">Description</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">Default</td></tr><tr><td colspan="1" rowspan="1">7</td><td colspan="1" rowspan="1">H1</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1"></td><td colspan="1" rowspan="1">0:1: </td><td colspan="1" rowspan="1"></td><td colspan="1" rowspan="1"></td></tr><tr><td colspan="1" rowspan="1">6</td><td colspan="1" rowspan="1">NTC1OE1: </td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">5</td><td colspan="1" rowspan="1">VBUSOE1: </td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">4</td><td colspan="1" rowspan="1">VBATE0E1: </td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">3</td><td colspan="1" rowspan="1">VBATE14O:1: </td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">2</td><td colspan="1" rowspan="1">VBU O:E1: </td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">1</td><td colspan="1" rowspan="1">VBUOE1: </td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">0</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1"></td><td colspan="1" rowspan="1"></td></tr></table>

# 2.4 REG 0x04: 状态指示 1

<table><tr><td colspan="1" rowspan="1">Bit</td><td colspan="1" rowspan="1">Description</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">Default</td></tr><tr><td colspan="1" rowspan="1">7-6</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">I</td></tr><tr><td colspan="1" rowspan="1">50</td><td colspan="1" rowspan="1">140: 1: bit 1#</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">4</td><td colspan="1" rowspan="1">0: 41: 14bit 1#</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">3</td><td colspan="1" rowspan="1">B0:11:14bit1</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">2</td><td colspan="1" rowspan="1">B10: 141: 14bit1#</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">1</td><td colspan="1" rowspan="1">20: 21 A2bit1#</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">0</td><td colspan="1" rowspan="1">10: 1: 1bit 1</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr></table>

# 2.5 REG 0x05: 状态指示 2

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>EH0: 141: #4bit 1</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>6</td><td rowspan=1 colspan=1>NTC0: NT#141: NTC1bit1</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1>BUS0: VBUS #141: VBUS E14bit 1#</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>4</td><td rowspan=1 colspan=1>VBATE0: VBATE41: VBATE14bit 1</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>30</td><td rowspan=1 colspan=1>VBATE10::  VBAT E141:VBAT I bit is1#</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>BU0: BU1: VBUS bit1</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>VBUS0:  VBU1: VBUS 14bit1</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr></table>

2.6 REG 0x06: 系统状态指示

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>#0: 1: </td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>6</td><td rowspan=1 colspan=1>0: 1: </td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>5-3</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>623680:623681:62368</td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>B:B:B</td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.7 REG 0x0C: 泄放电控制

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description                                        /</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-4</td><td rowspan=1 colspan=1>//</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>3</td><td rowspan=1 colspan=1>VBUS BU 500500  b  . 500m 0BUS 0: E1:E</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>NDTBNTB 500500m    500 0INDTB1: </td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>INDTADT 500500   500 OINDTO: 1:E</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>NDTAT  500500</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

<table><tr><td>0: :</td><td>b  500 0NDT</td></tr></table>

# 2.8 REG 0x0D: 工作模式控制

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-5</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>4</td><td rowspan=1 colspan=1>UF0:1: </td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>3-1</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>A</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>#0: 1: </td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.9 REG 0x0F: 芯片复位检测

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-1</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>HECU  bit M bi bi0,E</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.10 REG 0x10: ADC 配置

<table><tr><td colspan="1" rowspan="1">Bit</td><td colspan="1" rowspan="1">Description</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">Default</td></tr><tr><td colspan="1" rowspan="1">7-6</td><td colspan="1" rowspan="1">ADC10mS1:20mS2:40mS3: 80mS</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">5-4</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">/</td></tr><tr><td colspan="1" rowspan="1">3-0</td><td colspan="1" rowspan="1">ADC  Reg0x11  Reg0x12E10: VBAT E (VBAT= Adc_data[11:0]*7.5mV)1: VBUS E (VBUS= Adc_data[11:0]*7.5mV)2~3: </td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td>4: 5: VBUS 6: 7: 8: 10~15: </td><td>:VBAT  IBAT_CHG= Adc_data[11:0]*5mA) (IBUS_CHG= Adc_data[11:0]*5mA) VBAT  IBAT_DISCHG= Adc_data[11:0]*5mA VBUS IBUS_DISCHG= Adc_data[11:0]*5m TDIE=( Adc_data[11:0]-1839)/6.82 ) 9: NTC E (VNTC= Adc_data[11:0]*1.1mV)</td><td></td><td></td></tr></table>

# 2.11 REG 0x11: ADC 数据高 8bits

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-0</td><td rowspan=1 colspan=1>ADC 8bitsAdc_data[11:04]</td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.12 REG 0x12: ADC 数据低 4bits

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-4</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>3-0</td><td rowspan=1 colspan=1>ADC  4bitsAdc_data[03:00]</td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.13 REG 0x18: 负载接入检测及低功耗模式控制

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-5</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>4</td><td rowspan=1 colspan=1>E0E1: </td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>3-2</td><td></td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>A1 0:1:E </td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>A20::</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.14 REG 0x19: 通路控制

<table><tr><td colspan="1" rowspan="1">Bit</td><td colspan="1" rowspan="1">Description</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">Default</td></tr><tr><td colspan="1" rowspan="1">7-3</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">/</td></tr><tr><td colspan="1" rowspan="1">2</td><td colspan="1" rowspan="1">GATEB0:</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1"></td><td colspan="1" rowspan="1">1: TFF</td><td colspan="1" rowspan="1"></td><td colspan="1" rowspan="1"></td></tr><tr><td colspan="1" rowspan="1">1</td><td colspan="1" rowspan="1">GATEA0:1: TFF</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">0</td><td colspan="1" rowspan="1">GATEA0: 1: TFF</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr></table>

# 2.15 REG 0x1A: I2C 地址设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-2</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>1-0</td><td rowspan=1 colspan=1>12C 70:0x3C0x79,0x78)1:0x38(r0x71,$0x702:0x1C 0x39,$0x383:0x18 0x31,$0x30</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.16 REG $\mathbf { 0 x 2 0 }$ : 功能设置 1

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-6</td><td rowspan=1 colspan=1>0: 300KHz1: 200KHz2:400KHz3: 800KHz</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1>PWM0: 1: </td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>4-3</td><td></td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>NTC0:1:E</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>IEE0: F 112nS E 133nS1:T58nS 81nS</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>VBUS0: I2C E1: FBiE</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.17 REG 0x21: 功能设置 2

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-6</td><td rowspan=1 colspan=1>M2M10:60nS1:20nS2:40nS3:80nS</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x2</td></tr><tr><td rowspan=1 colspan=1>5-4</td><td rowspan=1 colspan=1>M1M2F0:60nS1: 20nS2:40nS3:60nS</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x2</td></tr><tr><td rowspan=1 colspan=1>3-2</td><td rowspan=1 colspan=1>M3M40:60nS1: 20nS2: 40nS3:80nS</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x2</td></tr><tr><td rowspan=1 colspan=1>1-0</td><td rowspan=1 colspan=1>M4M30:60nS1: 20nS2:40nS3:60nS</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x2</td></tr></table>

# 2.18 REG 0x22: 功能设置 3

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-60</td><td rowspan=1 colspan=1>M20: 2.5mΩ1:5mΩ2:7.5mΩ3:10mΩ</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x3</td></tr><tr><td rowspan=1 colspan=1>5-4</td><td rowspan=1 colspan=1>EEEELSET0:1uH1: 2.2uH2: 3.3uH3: 4.7uH</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>3-0</td><td rowspan=1 colspan=1>I</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr></table>

2.19 REG 0x23: 放电 VBUS 输出电压设置高 8bits

<table><tr><td>Bit</td><td>Description</td><td>R/W</td><td>Default</td></tr><tr><td>7-0</td><td>VBUS  8bitVbus_dischg[10:03] 11bit10mV/Step3V 22V22V #  22V   Vbus_dischg[10:03] 5 Vbus_dischg[02:00], VBUS_DISCHG=3000mV+Vbus_dischg[10:00]*10mV</td><td>R/W</td><td>0x0</td></tr></table>

# 2.20 REG 0x24: 放电 VBUS 输出电压设置低 3bits

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-3</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>2-0</td><td rowspan=1 colspan=1> VBUS   3bitVbus_dischg[02:00]11bits10mV/Step3V22V 22 #  22V  Vbus_dischg[10:03] 5Vbus_dischg[02:00],VBUS_DISCHG=3000mV+Vbus_dischg[10:00]*10mV</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.21 REG 0x25: 放电 VBUS 输出限流设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>|</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>6-0</td><td rowspan=1 colspan=1> VBUS Ibus_dischg[6:0]7bits50mA/Step0.5A 6.85A5.3AIBUS_DISCHG=500mA+Ibus_dischg[6:0]*50mA</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x60</td></tr></table>

# 2.22 REG 0x26: 放电 VBAT 输出限流设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>6-0</td><td rowspan=1 colspan=1> VBAT Ibat_dischg[6:0]7bits100mA/Step 0.1A12A12A 12A12AIBAT_DISCHG=100mA+Ibat_dischg[6:0]*100mA</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x77</td></tr></table>

# 2.23 REG 0x27: 放电 VBAT 欠压设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>6-0</td><td rowspan=1 colspan=1> VBAT EVbat_uvlo[6:0]</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x3</td></tr></table>

<table><tr><td></td><td>7bits 0.1V/Step2.7V13.2V13.2V #13.2V3V VBAT_UVLO=2.7V+Vbat_uvlo[6:0]*0.1V</td></tr></table>

# 2.24 REG $\mathbf { 0 } \mathbf { x } 2 \mathbf { 8 }$ : 放电 VBAT 欠压迟滞设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-5</td><td rowspan=1 colspan=1>I</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>4-0</td><td rowspan=1 colspan=1> VBAT EVbat_uvlo_hys[4:0]5bits0.1V/Step 0.4V 2V2V #2VVBAT_UVLO_HYS=0.4V+Vbat_uvlo_hys[4:0]*0.1V</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.25 REG 0x30: 功能设置 4

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>01: T</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>6</td><td rowspan=1 colspan=1>E0:E1: </td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>5-4</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>|</td></tr><tr><td rowspan=1 colspan=1>3-2</td><td rowspan=1 colspan=1>0:100mA1:200mA2:300mA3:400mA</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>1-0</td><td rowspan=1 colspan=1> BSSET E0:   1: 233:    </td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.26 REG 0x31: 功能设置 5

<table><tr><td colspan="1" rowspan="1">Bit</td><td colspan="1" rowspan="1">Description</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">Default</td></tr><tr><td colspan="1" rowspan="1">7-4</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">/</td></tr><tr><td colspan="1" rowspan="1">3-2</td><td colspan="1" rowspan="1">CHNEE0: 1201: 130</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x3</td></tr><tr><td colspan="1" rowspan="1"></td><td colspan="1" rowspan="1">2: 1403: 150</td><td colspan="1" rowspan="1"></td><td colspan="1" rowspan="1"></td></tr><tr><td colspan="1" rowspan="1">1-0</td><td colspan="1" rowspan="1">0: 12A1:14A2:16A3:18A</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x3</td></tr></table>

# 2.27 REG 0x32: 功能设置 6

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>62368 0E1: </td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>6</td><td rowspan=1 colspan=1> 62368U0E1: </td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>4</td><td rowspan=1 colspan=1>EO:E1: </td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>3-2</td><td rowspan=1 colspan=1>0:30112:23:4</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x3</td></tr><tr><td rowspan=1 colspan=1>1-00</td><td rowspan=1 colspan=1>0:121: 242: 48 JH3:72H</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x3</td></tr></table>

# 2.28 REG 0x33: 功能设置 7

<table><tr><td>Bit</td><td>Description</td><td>R/W</td><td>Default</td></tr><tr><td rowspan="5">7-6</td><td>62368 REG32[6]=0 BUS BAT  </td><td>R/W</td><td>0x0</td></tr><tr><td>REG32[6]=1  BAT 0: 1/2</td><td></td><td></td></tr><tr><td>1: 1 1/4 2: T</td><td></td><td></td></tr><tr><td>3:1</td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr><tr><td colspan="1" rowspan="1">5-4</td><td colspan="1" rowspan="1">623681REG32[6]=0 BUSBAT ;REG32[6]=1 1 IBAT 0:1 1/21:1/42: TP13:1</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">3</td><td colspan="1" rowspan="1">623680:*.11:</td><td colspan="1" rowspan="1">R/W0</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">2</td><td colspan="1" rowspan="1">623680:0.11:</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">1</td><td colspan="1" rowspan="1">623680: 51: 10</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">0</td><td colspan="1" rowspan="1">623680: 51: 10</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr></table>

# 2.29 REG 0x34: 充电目标电压设置高 8bits

<table><tr><td>Bit</td><td>Description</td><td>R/W</td><td>Default</td></tr><tr><td>7-0</td><td>8bitsVbat_target[10:03] 11bits10mV/Step3V 19.2V 19.2V#19.2VVbat_target[10:03] Vbat_target[02:00]BSSET 4.2V VBUS_TARGET=3000mV+Vbat_target[10:00]*10mV</td><td>R/W</td><td>0x0</td></tr></table>

# 2.30 REG 0x35: 充电目标电压设置低 3bits

<table><tr><td>Bit</td><td>Description</td><td>R/W</td><td>Default</td></tr><tr><td>7-0</td><td>3bitsVbat_target[10:03] 11bits10mV/Step3V 19.2V 19.2V##19.2VVbat_target[10:03] Vbat_target[02:00]BSSET #4.2V</td><td>R/W</td><td>0x0</td></tr></table>

2.31 REG 0x36: 涓流电压设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>6-0</td><td rowspan=1 colspan=1>Ibat_trickle[6:0]7bits 0.1V/Step,2.5V13.2V13.2V#13.2BSSETE*2.9VVBAT_TRICKLE=2.5V+Ibat_trickle[6:0]*0.1V</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.32 REG 0x37: 涓流电流设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-4</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>3-2</td><td rowspan=1 colspan=1>0: 100mA1:200mA2:300mA3:400mA</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>1-0</td><td rowspan=1 colspan=1>BT*0.1V0:0.1V1:0.2V2:0.3V3:0.4V</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.33 REG 0x38: 充电 VBUS 限压设置

<table><tr><td>Bit</td><td>Description</td><td>R/W</td><td>Default</td></tr><tr><td>7-0</td><td>VBUS EVbus_hold[7:0] 8bits0.1V/Step4V 20V 20V 2EBU BU EIJE</td><td>R/W</td><td>0x4</td></tr></table>

# 2.34 REG 0x39: 充电 VBUS 输入限流设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>6-0</td><td rowspan=1 colspan=1> VBUS λIbus_chg[6:0]</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x40</td></tr></table>

<table><tr><td></td><td>7bits50mA/Step0.5A 6.85A IBUS_CHG=500mA+Ibus_chg[6:0]*50mA</td><td></td></tr></table>

# 2.35 REG 0x3A: 充电 VBAT 输入限流设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>6-0</td><td rowspan=1 colspan=1> VBAT Ibat_chg[6:0]7bits100mA/Step0.1A12A12A  12AIBAT_CHG=100mA+Ibat_chg[6:0]*100mA</td><td rowspan=1 colspan=1>R/WR</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.36 REG 0x43: NTC 设置 1

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-6</td><td rowspan=1 colspan=1>T0:501:552:603:65</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>5-4</td><td rowspan=1 colspan=1> T0: -101: -52:03: -20</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>3-20</td><td rowspan=1 colspan=1>NTC0:451:402: 503: 55C</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>1-0</td><td rowspan=1 colspan=1>NTC0:01:102:53: -5C</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.37 REG 0x44: NTC 设置 2

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-2</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>1-0</td><td rowspan=1 colspan=1>NTC IFO: 20uA</td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x0</td></tr></table>

<table><tr><td>1:40uA 2: 80uA 3: 1</td></tr><tr><td></td></tr></table>

![](../assets/sw7201-register/8172b70224758b0b9a45a446e1404ffcd12d30c7ddfd128fd021d56c91e68c1a.jpg)

# 免责声明

珠海智融科技股份有限公司（以下简称“智融科技”）可能随时对所提供的产品、服务及本文件作出修改或更新，且不另行通知。客户应在下订单前获取最新的相关信息，并确认这些信息是否完整且是最新的。本文件所含信息仅为您提供便利，智融科技不对这些信息作任何明示或暗示、书面或口头、法定或其他形式的声明或保证，包括不但限于产品的用途、特性、使用情况、适销性等方面。智融科技对这些信息及不合理使用这些信息而引起的后果不承担任何责任。

智融科技对应用帮助或客户产品设计不承担任何义务。客户应对其使用智融科技的产品和应用自行负责。客户应提供充分的设计与操作安全验证，且保证在将智融产品集成到任何应用程序中时不会侵犯第三方知识产权，如发生侵权行为智融科技对此概不承担任何责任。

在转售智融科技产品时，如果对该产品参数及其陈述相比存在差异或虚假成分，则会自动丧失智融科技相关产品的所有明示或暗示授权，且对此不正当的、欺诈性商业行为，智融科技保留采取一切合法方式维权。智融科技对任何此类虚假陈述均不承担任何责任或义务。

本文件仅在没有对内容进行任何篡改且带有相关授权、条件、限制和声明的情况下才允许进行复制，否则智融科技有权追究其法律责任。智融科技对此类篡改过的文件不承担任何责任或义务。复制如涉及第三方的信息应当服从额外的限制条件。</details>
