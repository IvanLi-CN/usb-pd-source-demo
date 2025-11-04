# PL5501 Datasheet Digest (DS-PL5501-Rev.1.0)

- Source: [PL5501-datasheet.pdf](source/PL5501-datasheet.pdf)
- Language: English
- Notes: Four-switch buck-boost PD controller with analog/PWM programmable voltage and current control for USB PD designs.

## Highlights

- 3.6-32 V input range with seamless buck, boost, and buck-boost transition using constant on-time control.
- External IADJ/VADJ pins allow analog or PWM control of voltage reference and current limit with integrated 5 V/55 mA LDO for host MCU supply.
- Supports 150/300/600/1200 kHz switching, programmable soft-start, comprehensive protections, and dual current-sense loops for VIN and VBUS regulation.

## Applications

- USB Power Delivery car chargers and HUB power.  
- Industrial PC and embedded systems power.  
- Automotive start-stop auxiliary conversion.

## Key Electrical Specifications

| Parameter | Value |
| --- | --- |
| Input voltage | 3.6 – 32 V (36 V max) |
| Output voltage | 2 – 32 V programmable |
| Gate driver current | 2 A source / sink |
| Switching frequency | 150 / 300 / 600 / 1200 kHz |
| LDO output | 5 V / 55 mA |
| Package | QFN-32 (4 mm × 4 mm) |

![Typical Application](../assets/pl5501-datasheet/ff24827b452ee6fb9768677dfaeb969c92e7ba62bfc3e747aed433f8c7e8ef7e.jpg)

<details>
<summary>Full Extract</summary>

# High Efficiency 4-Switch Buck-Boost Controller

# 1 Features

# 3 Description

Buck-Boost Controller for Step-Up/Step-Down DC/DC Conversion Dynamical programming of Output current and Output voltage using PWM signal or analog signal 2V to $_ { 3 2 \lor }$ wide output range Comprehensive protection features including Output Short Protection (OSP), Cycle-by-Cycle input and output Peak Current Limit, thermal regulation, thermal shutdown, input UVLO, input OVP, output OVP etc. Adjustable Switching Frequency using resistor Frequency dithering for good EMI performance  Integrated 2-A MOSFET Gate Drivers Input or Output Average Current Limiting with stable CC loop 5V/55mA low $\mathsf { I } _ { \mathsf { q } }$ LDO to power system MCU Available in QFN4x4-32 Package

# 2 Applications

 Automotive Start-Stop Systems   
 Industrial PC Power Supplies   
 USB Power Delivery   
 Car charger HUB Power

PL5501 is a synchronous 4-switch Buck-Boost controller capable of regulating the output voltage at above or below the input voltage. PL5501 operates over a wide input voltage range of $3 . 6 \lor$ to 32 V (36 V maximum) to support a variety of applications.

PL5501 employs Constant ON time control in buck, boost and buck-boost operation modes for superior load and line regulation. The switching frequency could be set to 150kHz, 300kHz, 600kHz or 1200kHz based on different resistor value between FREQ pin and GND pin. The device also features a programmable soft-start function and offers all kinds of protection features including cycle-by-cycle current limiting, input under voltage lockout (UVLO), output over voltage protection (OVP), input Over Voltage Protection, thermal shutdown and output short protection etc.

VADJ, IADJ pins are used to program output VBUS voltage and output current limit, provides voltage control loop, constant current loop, thermal regulation loop, temperature sensing, which makes PL5501 an excellent option for USB Power Delivery (PD) application.

# 4 Typical Application Schematic

![](../assets/pl5501-datasheet/ff24827b452ee6fb9768677dfaeb969c92e7ba62bfc3e747aed433f8c7e8ef7e.jpg)  
Fig. 1 Application Schematic

# 5 Pin Configuration and Functions

![](../assets/pl5501-datasheet/3afb42484d12cc74946af18b962d6456807156cb49789e104661e6c0ea57d99f.jpg)  
Fig. 2 Pin-Function (QFN4X4-32)

<table><tr><td colspan="2" rowspan="1">Pin</td><td colspan="1" rowspan="2">Description</td></tr><tr><td colspan="1" rowspan="1">Number</td><td colspan="1" rowspan="1">Name</td></tr><tr><td colspan="1" rowspan="1">1</td><td colspan="1" rowspan="1">VADJ</td><td colspan="1" rowspan="1">Connect a 0-2V analog voltage or a PWM signal to program voltage reference on VREF pin.Connect this pin to VDD will force VREF to constant 2V.</td></tr><tr><td colspan="1" rowspan="1">2</td><td colspan="1" rowspan="1">IADJ</td><td colspan="1" rowspan="1">Connect a 0-2V analog voltage or a PWM signal to program voltage reference on IREF pin.Connect this pin to VDD will force IREF to 2V.</td></tr><tr><td colspan="1" rowspan="1">3,6,8,11,30</td><td colspan="1" rowspan="1">NC</td><td colspan="1" rowspan="1"></td></tr><tr><td colspan="1" rowspan="1">4</td><td colspan="1" rowspan="1">IREF</td><td colspan="1" rowspan="1">Reference voltage for input and output current limiting loop.</td></tr><tr><td colspan="1" rowspan="1">5</td><td colspan="1" rowspan="1">VREF</td><td colspan="1" rowspan="1">Voltage reference for voltage control loop</td></tr><tr><td colspan="1" rowspan="1">7</td><td colspan="1" rowspan="1">LDO</td><td colspan="1" rowspan="1">Low quiescent current 5V/55mA LDO. Directly powered from VIN pin. LDO can be used aspower supply for application processor such as MCU. When EN is low, only this LDO will beactive to power MCU and keep low quiescent current for the whole system.</td></tr><tr><td colspan="1" rowspan="1">9</td><td colspan="1" rowspan="1">FREQ</td><td colspan="1" rowspan="1">Connect to GND to set the switching frequency at 150kHz. Connect this pin to VDD to setswitching frequency at 300kHz. Connect to a resistor divider between VDD and GND to setfrequency to 600k and 1200k Hz.</td></tr><tr><td colspan="1" rowspan="1">10</td><td colspan="1" rowspan="1">COMP</td><td colspan="1" rowspan="1">Error Amplifier output.</td></tr><tr><td colspan="1" rowspan="1">12</td><td colspan="1" rowspan="1">FB2</td><td colspan="1" rowspan="1">VBUS voltage feedback. Connect a resistor divider between VBUS and GND to FB2 toprogram VBUS voltage.</td></tr><tr><td colspan="1" rowspan="1">13</td><td colspan="1" rowspan="1">CSN2</td><td colspan="1" rowspan="1">The minus input of output current sense.</td></tr><tr><td colspan="1" rowspan="1">14</td><td colspan="1" rowspan="1">CSP2</td><td colspan="1" rowspan="1">The positive input of output current sense.</td></tr><tr><td colspan="1" rowspan="1">15</td><td colspan="1" rowspan="1">VBUS</td><td colspan="1" rowspan="1">Connect this pin to the output voltage.</td></tr><tr><td colspan="1" rowspan="1">16</td><td colspan="1" rowspan="1">HG2</td><td colspan="1" rowspan="1">High side MOSFET driver 2.</td></tr><tr><td colspan="1" rowspan="1">17</td><td colspan="1" rowspan="1">BST2</td><td colspan="1" rowspan="1">Boost pin for high side MOSFET driver 2.</td></tr><tr><td colspan="1" rowspan="1">18</td><td colspan="1" rowspan="1">SW2</td><td colspan="1" rowspan="1">Connect this pin to the Switching point 2 of the power stage.</td></tr><tr><td colspan="1" rowspan="1">19</td><td colspan="1" rowspan="1">LG2</td><td colspan="1" rowspan="1">Low side MOSFET driver output 2.</td></tr><tr><td colspan="1" rowspan="1">20</td><td colspan="1" rowspan="1">VCC</td><td colspan="1" rowspan="1">6.6V power supply for high side and low side driver</td></tr><tr><td colspan="1" rowspan="1">21</td><td colspan="1" rowspan="1">LG1</td><td colspan="1" rowspan="1">Low side MOSFET driver output1.</td></tr><tr><td colspan="1" rowspan="1">22</td><td colspan="1" rowspan="1">SW1</td><td colspan="1" rowspan="1">Connect this pin to the Switching point1 of the power stage.</td></tr><tr><td colspan="1" rowspan="1">23</td><td colspan="1" rowspan="1">BST1</td><td colspan="1" rowspan="1">Boost pin for high side MOSFET driver1.</td></tr><tr><td colspan="1" rowspan="1">24</td><td colspan="1" rowspan="1">HG1</td><td colspan="1" rowspan="1">High side MOSFET driver1.</td></tr><tr><td colspan="1" rowspan="1">25</td><td colspan="1" rowspan="1">VIN</td><td colspan="1" rowspan="1">Connect this pin to the Input voltage.</td></tr><tr><td colspan="1" rowspan="1">26</td><td colspan="1" rowspan="1">CSP1</td><td colspan="1" rowspan="1">The positive input of input current sense.</td></tr><tr><td colspan="1" rowspan="1">27</td><td colspan="1" rowspan="1">CSN1</td><td colspan="1" rowspan="1">The minus input of input current sense.</td></tr><tr><td colspan="1" rowspan="1">28</td><td colspan="1" rowspan="1">EN</td><td colspan="1" rowspan="1">Logic High will enable the converter. Logic Low will disable the whole PL5501 except LDO.Only LDO is working to power system MCU when EN is low. EN is pulled high internally by ahigh value resistor.</td></tr><tr><td colspan="1" rowspan="1">29</td><td colspan="1" rowspan="1">AGND</td><td colspan="1" rowspan="1">Signal Ground.</td></tr><tr><td colspan="1" rowspan="1">31</td><td colspan="1" rowspan="1">TS</td><td colspan="1" rowspan="1">temperature sense</td></tr><tr><td colspan="1" rowspan="1">32</td><td colspan="1" rowspan="1">VDD</td><td colspan="1" rowspan="1">5.4V power supply for PL5501 control core.</td></tr></table>

# 6 Device Marking Information

![](../assets/pl5501-datasheet/92f1765d552c5927a947d1fa401ea5bbd89bc136a71cfb9f17f87c0228409745.jpg)

<table><tr><td rowspan=1 colspan=1>Part Number</td><td rowspan=1 colspan=1>Order Information</td><td rowspan=1 colspan=1>Package</td><td rowspan=1 colspan=1>Package Qty</td><td rowspan=1 colspan=1>Top Marking</td></tr><tr><td rowspan=1 colspan=1>PL5501</td><td rowspan=1 colspan=1>PL5501IQN32</td><td rowspan=1 colspan=1>QFN4x4 - 32</td><td rowspan=1 colspan=1>4000</td><td rowspan=1 colspan=1>5501RAAYMD</td></tr></table>

PL5501: Part Number RAAYMD: RAA: LOT NO.; YMD: Package Date

# 7 Specifications

# 7.1 Absolute Maximum Ratings(Note1)

<table><tr><td rowspan=1 colspan=1>PARAMETER</td><td rowspan=1 colspan=1>MIN                         MAX</td><td rowspan=1 colspan=1>Unit</td></tr><tr><td rowspan=1 colspan=1>VIN, VBUS, CSN1, CSN2, CSP1, CSP2,SW1, SW2</td><td rowspan=1 colspan=1>-0.3                           40</td><td rowspan=9 colspan=1></td></tr><tr><td rowspan=1 colspan=1>HG1, BST1 to SW1</td><td rowspan=1 colspan=1>-0.3                           7</td></tr><tr><td rowspan=1 colspan=1>HG2, BST2 to SW2</td><td rowspan=1 colspan=1>-0.3                           7</td></tr><tr><td rowspan=1 colspan=1>LG1, LG2, VCC to GND</td><td rowspan=1 colspan=1>-0.3                           7</td></tr><tr><td rowspan=1 colspan=1>CSP1 to CSN1</td><td rowspan=1 colspan=1>-0.3                          0.6</td></tr><tr><td rowspan=1 colspan=1>CSP2 to CSN2</td><td rowspan=1 colspan=1>-0.3                          0.6</td></tr><tr><td rowspan=1 colspan=1>VIN to CSP1, CSN1</td><td rowspan=1 colspan=1>-0.3                          0.6</td></tr><tr><td rowspan=1 colspan=1>VBUS to CSP2, CSN2</td><td rowspan=1 colspan=1>-0.3                          0.6</td></tr><tr><td rowspan=1 colspan=1>Other Pins to GND</td><td rowspan=1 colspan=1>-0.3                           6</td></tr></table>

# 7.2 Handling Ratings

<table><tr><td rowspan=1 colspan=1>PARAMETER</td><td rowspan=1 colspan=1>DEFINITION</td><td rowspan=1 colspan=1>MIN            MAX</td><td rowspan=1 colspan=1>UNIT</td></tr><tr><td rowspan=1 colspan=1>TsT</td><td rowspan=1 colspan=1>Storage Temperature Range</td><td rowspan=1 colspan=1> -65         2 150</td><td rowspan=1 colspan=1>°C</td></tr><tr><td rowspan=1 colspan=1>TJ</td><td rowspan=1 colspan=1>Junction Temperature</td><td rowspan=1 colspan=1>+150</td><td rowspan=1 colspan=1>°C</td></tr><tr><td rowspan=1 colspan=1>TL</td><td rowspan=1 colspan=1>Lead Temperature</td><td rowspan=1 colspan=1>+260</td><td rowspan=1 colspan=1>°C</td></tr><tr><td rowspan=1 colspan=1>VESD</td><td rowspan=1 colspan=1>HBM Human body model</td><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>kV</td></tr></table>

# 7.3 Recommended Operating Conditions (Note 2)

<table><tr><td></td><td>PARAMETER</td><td>MIN</td><td>MAX</td><td>Unit</td></tr><tr><td>Input Voltages</td><td>VIN</td><td>3.6</td><td>32</td><td>V</td></tr><tr><td>Temperature</td><td>Operating junction temperature range, TJ</td><td>-40</td><td>+125</td><td>°C</td></tr></table>

# 7.4 Thermal Information(Note 3)

<table><tr><td rowspan=1 colspan=1>Symbol</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>QFN4X4-32</td><td rowspan=1 colspan=1>Unit</td></tr><tr><td rowspan=1 colspan=1>θJA$</td><td rowspan=1 colspan=1>Junction to ambient thermal resistance</td><td rowspan=1 colspan=1>44</td><td rowspan=2 colspan=1>CM</td></tr><tr><td rowspan=1 colspan=1>θjc</td><td rowspan=1 colspan=1>Junction to case thermal resistance</td><td rowspan=1 colspan=1>9</td></tr></table>

# Notes:

1) Exceeding these ratings may damage the device.   
2) The device function is not guaranteed outside of the recommended operating conditions.   
3) Measured on approximately 1” square of 1 oz copper.

7.5 Electrical Characteristics (Typical at $\mathsf { V I N } = 1 2 \mathsf { V }$ , ${ \mathsf { T } } _ { \mathsf { J } } = 2 5 ^ { \circ } { \mathsf { C } }$ , unless otherwise noted.)   

<table><tr><td rowspan=1 colspan=1>Supply voltages</td><td rowspan=1 colspan=1>PARAMETER</td><td rowspan=1 colspan=1>CONDITION</td><td rowspan=1 colspan=1>MIN TYP MAX</td><td rowspan=1 colspan=1>UNIT</td></tr><tr><td rowspan=1 colspan=1>VIN</td><td rowspan=1 colspan=1>Input voltage</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>3.6             32</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=2 colspan=1>IQ VIN</td><td rowspan=1 colspan=1>VIN Shutdown Current</td><td rowspan=1 colspan=1>EN=OV, VIN=7.2V</td><td rowspan=1 colspan=1>15</td><td rowspan=1 colspan=1>uA</td></tr><tr><td rowspan=1 colspan=1>VIN Supply Current</td><td rowspan=1 colspan=1>No Switching, FB=2.1V</td><td rowspan=1 colspan=1>1000</td><td rowspan=1 colspan=1>uA</td></tr><tr><td rowspan=1 colspan=1>VBUS</td><td rowspan=1 colspan=1>Bus line voltage</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>3.6             32</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=2 colspan=1>Io_VBUS</td><td rowspan=1 colspan=1>VBUS Shutdown Current</td><td rowspan=1 colspan=1>EN=OV, VBUS=7.2V</td><td rowspan=1 colspan=1>15</td><td rowspan=1 colspan=1>uA</td></tr><tr><td rowspan=1 colspan=1>VBUS Supply Current</td><td rowspan=1 colspan=1>No Switching</td><td rowspan=1 colspan=1>1200</td><td rowspan=1 colspan=1>uA</td></tr><tr><td rowspan=1 colspan=1>Vvcc</td><td rowspan=1 colspan=1>Driver power supply voltage</td><td rowspan=1 colspan=1>VIN=15V</td><td rowspan=1 colspan=1>6.6</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>VVDD</td><td rowspan=1 colspan=1>Control core power supply voltage</td><td rowspan=1 colspan=1>VIN =15V</td><td rowspan=1 colspan=1>5.4</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>VLDO</td><td rowspan=1 colspan=1>LDO output voltage</td><td rowspan=1 colspan=1>VIN =15V</td><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>ILDO</td><td rowspan=1 colspan=1>LDO output current</td><td rowspan=1 colspan=1>VLDO =5V</td><td rowspan=1 colspan=1>55</td><td rowspan=1 colspan=1>mA</td></tr><tr><td rowspan=1 colspan=1>UVLO/EN</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>Y</td></tr><tr><td rowspan=2 colspan=1>VIN_Uv</td><td rowspan=1 colspan=1>VIN UVLO Rising</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>3.5</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>UVLO Hysteresis</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>300</td><td rowspan=1 colspan=1>mV</td></tr><tr><td rowspan=2 colspan=1>VBUS_uv</td><td rowspan=1 colspan=1>VIN UVLO Rising</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>3.5</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>UVLO Hysteresis</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>300</td><td rowspan=1 colspan=1>mV</td></tr><tr><td rowspan=2 colspan=1>VEN_UV</td><td rowspan=1 colspan=1>Operation Threshold</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>1.1 1.2 1.3</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>Hysteresis</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>200</td><td rowspan=1 colspan=1>mV</td></tr><tr><td rowspan=1 colspan=1>Control loop</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>VFB2</td><td rowspan=1 colspan=1>VFB2 regulation voltage</td><td rowspan=1 colspan=1>FB2 voltage</td><td rowspan=1 colspan=1>1.96    2 2.04</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>GmEA</td><td rowspan=1 colspan=1>Error amplifier gm</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>450</td><td rowspan=1 colspan=1>us</td></tr><tr><td rowspan=1 colspan=1>Isink</td><td rowspan=1 colspan=1>COMP sink/source current</td><td rowspan=1 colspan=1>VFB=VREF+100mV</td><td rowspan=1 colspan=1>15</td><td rowspan=1 colspan=1>uA</td></tr><tr><td rowspan=1 colspan=1>IsOURCe</td><td rowspan=1 colspan=1>COMP source current</td><td rowspan=1 colspan=1>VFB=VREF-100mV</td><td rowspan=1 colspan=1>20</td><td rowspan=1 colspan=1>uA</td></tr><tr><td rowspan=1 colspan=1>IFB2</td><td rowspan=1 colspan=1>FB2 bias current</td><td rowspan=1 colspan=1>FB2 in regulation</td><td rowspan=1 colspan=1>100</td><td rowspan=1 colspan=1>nA</td></tr><tr><td rowspan=1 colspan=5>Frequency                                                                      </td></tr><tr><td rowspan=4 colspan=1>Fsw</td><td rowspan=4 colspan=1>Switching Frequency</td><td rowspan=1 colspan=1>FREQ 0-0.4V, short FREQpin to GND.</td><td rowspan=1 colspan=1>150</td><td rowspan=1 colspan=1>KHz</td></tr><tr><td rowspan=1 colspan=1>FREQ 1.8-5.4V, shortFREQ pin to VDD.</td><td rowspan=1 colspan=1>300</td><td rowspan=1 colspan=1>KHz</td></tr><tr><td rowspan=1 colspan=1>FREQ 0.4-0.85V</td><td rowspan=1 colspan=1>600</td><td rowspan=1 colspan=1>KHZ</td></tr><tr><td rowspan=1 colspan=1>FREQ 0.85-1.8V</td><td rowspan=1 colspan=1>1200</td><td rowspan=1 colspan=1>KHZ</td></tr><tr><td rowspan=1 colspan=1>Current Limit</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=2 colspan=1>ICCLIM_VIN</td><td rowspan=2 colspan=1>VIN average current Limit,VcsP1-VcsN1</td><td rowspan=1 colspan=1>Boost mode</td><td rowspan=1 colspan=1>80</td><td rowspan=1 colspan=1>mV</td></tr><tr><td rowspan=1 colspan=1>Buckmode</td><td rowspan=1 colspan=1>40</td><td rowspan=1 colspan=1>mV</td></tr><tr><td rowspan=1 colspan=1>ICCLIM_BUS</td><td rowspan=1 colspan=1>Bus average current Limit,VcSP2- VcsN2</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>40</td><td rowspan=1 colspan=1>mV</td></tr><tr><td rowspan=1 colspan=5>NMOS Driver</td></tr><tr><td rowspan=2 colspan=1>(Note 4)IHDRV1,2</td><td rowspan=1 colspan=1>Driver peak source current</td><td rowspan=1 colspan=1>VBST-VSW=6.6V</td><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>A</td></tr><tr><td rowspan=1 colspan=1>Driver peak sink current</td><td rowspan=1 colspan=1>VBST-VSW=6.6V</td><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>A</td></tr><tr><td rowspan=2 colspan=1></td><td rowspan=1 colspan=1>Driver peak source current</td><td rowspan=1 colspan=1>VCC=6.6V</td><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>A</td></tr><tr><td rowspan=1 colspan=1>Driver peak sink current</td><td rowspan=1 colspan=1>VCC=6.6V</td><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>A</td></tr><tr><td rowspan=2 colspan=1>VBSTUV</td><td rowspan=1 colspan=1>UVLO</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>UVLO Hysteresis</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>300</td><td rowspan=1 colspan=1>mV</td></tr><tr><td rowspan=1 colspan=3>Output Protection</td><td rowspan=1 colspan=2></td></tr><tr><td rowspan=1 colspan=1>Vovp</td><td rowspan=1 colspan=1>Output over voltage threshold</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>110</td><td rowspan=1 colspan=1>%</td></tr><tr><td rowspan=1 colspan=1>VUVP</td><td rowspan=1 colspan=1>Output under voltage threshold</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>50</td><td rowspan=1 colspan=1>%</td></tr><tr><td rowspan=1 colspan=5>VADJ, IADJ</td></tr><tr><td rowspan=2 colspan=1>VTH_VADJy(Note 4)</td><td rowspan=1 colspan=1>VPWM low voltage</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>0.4</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>VPWMhigh voltage</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>2.5</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=2 colspan=1>VTHIADU 4)</td><td rowspan=1 colspan=1>IPWMlow voltage</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>0.4</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>IPWMhigh voltage</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>2.5</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>TsD (Noie 4)</td><td rowspan=1 colspan=1>Thermal Shutdown Threshold</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>150</td><td rowspan=1 colspan=1>°C</td></tr><tr><td rowspan=1 colspan=1>THy s(Note 4)</td><td rowspan=1 colspan=1>Thermal Shutdown Hysteresis</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>20</td><td rowspan=1 colspan=1>°C</td></tr></table>

Notes: 4) Guaranteed by design

# 8 Typical Characteristics

![](../assets/pl5501-datasheet/828c2b1407ef6f3934e2329d2aeb053d5818dcb2f813816821b892055ee4f0f2.jpg)  
Fig. 3 Efficiency

![](../assets/pl5501-datasheet/ffcbe8ea99e7347badce47d98934ab58efd6de426131c4f7b95114fd6c5228e5.jpg)  
Fig. 4 Efficiency

![](../assets/pl5501-datasheet/0b3c342d97c8ae91b864fda1ad63f4462ec30f6c2f1dcacf55a56c6cf4e6c3a9.jpg)  
Fig. 5 Efficiency

![](../assets/pl5501-datasheet/fd814d24203d48d7f79c2a166bf771f7497872aba4e0b092dd6c6a3cd7bab0d3.jpg)  
Fig. 6 Efficiency

![](../assets/pl5501-datasheet/9cdf29ed535ff8531872c90f0d6b1259acf3cc6ce9d35f67220be1633e1462b7.jpg)  
Fig.7 Start up waveform, Iout $\mathtt { \Gamma = 0 A }$

![](../assets/pl5501-datasheet/a2632c803985f0236cf6032a98d848bb609b80efa2cc365ae0b5aced40a30390.jpg)  
Fig.8 Start up waveform, Iout $= 2 \mathsf { A }$

![](../assets/pl5501-datasheet/4fe753677c08b01b1a67683aeb86d7a4ce29af60b8647ce4304d6f96294e8303.jpg)

![](../assets/pl5501-datasheet/fcf6814b6c4fd711316914e679474be39a6d7e79eb5794fe9f902401a1e7144c.jpg)

# CH1: SW1 CH2:SW2 CH3:Vout CH4:IL

Vin=8.4V Vout=12V

![](../assets/pl5501-datasheet/d4f7ca2d503256677eaea65b51609be217dddd117c4720ed965ed805e320a558.jpg)  
Fig.9 Start up waveform, Iout $\mathtt { \Gamma = 0 A }$

![](../assets/pl5501-datasheet/cb24b5f31c61932f6ac915768d2b34158e79c2676ddf0bca2838d8b7a02f25d4.jpg)  
Fig.10 Start up waveform, Iout $\mathtt { = } \mathtt { 3 } \mathtt { A }$

# CH1: SW1 CH2:SW2 CH3:Vout CH4:IL

# CH1: SW1 CH2:SW2 CH3:Vout CH4:IL

Vin=12V Vout=12V

![](../assets/pl5501-datasheet/8c3db6d4f2374a8455062f8f36a449912675e071f52232ec8ed14236dba37408.jpg)  
Fig.11 Start up waveform, Iout $\mathtt { \Gamma = 0 A }$   
Fig.13 Start up waveform, Iout $\mathtt { \Gamma = 0 A }$

![](../assets/pl5501-datasheet/161e37af7a8a03f12e52157a9bfb9b6aa4dcaa5b043fef9b8ff4e4e0ab5fac2c.jpg)  
Fig.12 Start up waveform, Iout $\mathtt { = } \mathtt { 3 } \mathtt { A }$   
Fig.14 Start up waveform, Iout $\mathtt { = } \mathtt { 3 } \mathtt { A }$

# CH1:SW1 CH2:SW2 CH3:Vout CH4:IL

# CH1: SW1 CH2:SW2 CH3:Vout CH4:IL

Vin=24V Vout=12V

Vin=24V Vout=12V

![](../assets/pl5501-datasheet/ecfe817542dfc0f1790260dcbe4bf512b068fe7f2b5456b0131f6e9842c55f3e.jpg)

![](../assets/pl5501-datasheet/ccd31de0dd9821d39a3ba1443999cab2744c477b4c8fa2b24dd30ce568d8c849.jpg)

![](../assets/pl5501-datasheet/d060b31e156fdf50c66a2388e5d4c22be8dcbe2ffb5e693087b7e256660b001a.jpg)

# 9 Detailed Descriptions

# 9.1 Overview

PL5501 is a synchronous 4-switch Buck-Boost controller capable of regulating the output voltage at, above, or below the input voltage. PL5501 operates over a wide input voltage range of $3 . 6 \ V$ to $_ { 3 2 \mathrm { ~ V ~ } }$ $3 6 \vee$ maximum) to support a variety of applications. It operates in buck mode when $\vee _ { \mathsf { I N } }$ is greater than VOUT and in the boost mode when $\vee _ { \mathsf { I N } }$ is less than VOUT. When $V _ { \sf I N }$ is close to $\mathsf { V o u r }$ , the device operates in a proprietary buck-boost mode. The control scheme provides smooth operation for any input/output combination within the specified operating range.

# 9.2 Enable/UVLO

When EN is greater than 1.2V operating threshold, the control loop starts to work and regulate output to target voltage.   
When EN pin is below the standby threshold (1.1V typical), PL5501 stops working with only LDO is active to power MCU.   
EN is pulled high to 4V internally using a 2Meg resistor.

# 9.3 Over current Protection and short circuit protection

PL5501 provides cycle-by-cycle current limit to protect against over current and short circuit conditions. When VOUT is drop to UV threshold, PL5501 will go into hiccup mode to lower down power consumption.

# 9.4 Average Input/Output Current Limiting

PL5501 provides optional average current limiting capability to limit either the input or the output current. The average current limiting circuit uses an additional current sense resistor connected in series with the input supply or output voltage of the converter. A current sense gm amplifier with inputs at the CSP1 and CSN1 pins monitors the voltage across the sensing resistor and compares it with an internal $4 0 ~ \mathsf { m V }$ reference. If the drop across the sense resistor is greater than 40 mV, the gm amplifier regulates COMP voltage to lower down input or output current. The target constant current is given by Equation 1:

$$
\begin{array} { r } { I _ { C L ( A V G ) } = \frac { 4 0 m V } { R _ { S N S } } } \end{array}
$$

The average current loop can be disabled by shorting CSP1 to CSN1 or CSP2 to CSN2.

# 9.5 Frequency Setting (FREQ) and frequency dithering

PL5501 switching frequency can be programmed at $1 5 0 ~ \mathsf { k H z }$ , $3 0 0 ~ \mathsf { k H z }$ or $6 0 0 ~ \mathsf { k H z }$ and $1 2 0 0 ~ \mathsf { k H z }$ by voltage at FREQ pin to GND. When FREQ is connected to AGND, the switching frequency is set at $1 5 0 \mathsf { k H z }$ . When FREQ is connected to VDD, the switching frequency is set at $3 0 0 ~ \mathsf { k H z }$ . A voltage divider between VDD and GND pin can be used to program switching frequency if $6 0 0 ~ \mathsf { k H z }$ or $1 2 0 0 ~ \mathsf { k H z }$ is required.

# 9.6 Integrated Gate Drivers

PL5501 provides four N-channel MOSFET gate drivers: two floating high-side gate drivers at the HG1 and HG2 pins, and two ground referenced low-side drivers at the LG1 and LG2 pins. Each driver is capable of sourcing 2 A and sinking 2 A peak current. In buck operation, LG1 and HG1 are switched by the PWM controller while HG2 remains continuously on. In boost operation, LG2 and HG2 are switched while HG1 remains continuously on. In DCM buck operation, LG1 and HG2 are turned off when the inductor current drops to zero (diode emulation).

The gate drive output HG2 remains off before the first high side switch is turned on to prevent reverse current flow from a pre-biased output..

# 9.7 Thermal Shutdown

PL5501 is protected by a thermal shutdown circuit that shuts down the device when the internal junction temperature exceeds $1 6 0 ^ { \circ } \mathsf { C }$ (typical). The soft-start capacitor is discharged when thermal shutdown is triggered and the gate drivers are disabled. The converter automatically restarts when the junction temperature drops by the thermal shutdown hysteresis of $1 5 ^ { \circ } \mathrm { C }$ below the thermal shutdown threshold.

# 9.8 VREF and IREF

VREF pin is the final reference voltage used in the voltage regulation loop. When VADJ is connected to VDD, When VADJ is connected to a PWM signal, PWM signal will first be chopped to 2V and filter out using an internal resistor and external capacitor on VREF pin. The capacitor on VREF pin is also acting as soft-start capacitor at power up or in output voltage transition period. It is recommend using a relatively large capacitor such as 470nF for VREF pin and IREF pin.

The same mechanism works for IADJ and IREF pin.

# 9.9 TS:

PL5501 is provides external over temperature protection function. PL5501 works normally when TS pin voltage is between 2.6V-3.8V,When TS pin is below the $2 . 6 \lor$ , PL5501 stops working .

# 10 Applications and Implementation

The typical application on the first page is a basic PL5501 application circuit. External component selection is driven by the load requirement, and begins with the selection of RS1, RS2 and the inductor value. Next, the power MOSFETs need to be selected. Finally, $\mathsf { C } _ { \mathsf { I N } }$ and ${ \mathsf { C o u r } }$ are selected. This circuit can be configured for operation up to an input voltage of 32V.

# 10.1 $\mathtt { R _ { C S } }$ Selection

As shown in Figures 32, input/output current sense resistor RCS1/RCS2 should be placed between the bulk capacitor for VIN/VBUS and the decoupling capacitor. A low pass filter formed by RF and CF is recommended to reduce the switching noise and stabilize the current loop. If input/output current limit is not desired, then CSP1/CSN1 and CSP2/CSN2 pins should be shorted to either VIN or VBUS. Place CSP1/CSN1, CSP2/CSN2 symmetrically and keep them away switching signals such as BST1, BST2, SW1, SW2, VIN, VBUS etc.

# 10.2 Inductor Selection

The operating frequency and inductor selection are interrelated in that higher operating frequencies allow the use of smaller inductor and capacitor values. The inductor value has a direct effect on ripple current. The inductor current ripple $\Delta { \sf l } _ { \sf L }$ is typically set to $20 \%$ to $40 \%$ of the maximum inductor current in the boost region at VIN(MIN).

For a given ripple, the inductance terms in continuous mode are as follows:

$$
\begin{array} { r } { \mathsf { L } _ { \mathsf { B O O S T } } > \frac { \mathsf { V } _ { \mathsf { I N } ( \mathsf { M I N } ) } { 2 } ^ { \star } ( \mathsf { V } _ { \mathsf { O U T } } - \mathsf { V } _ { \mathsf { I N } ( \mathsf { M I N } ) } ) ^ { \star } 1 0 0 0 } { \mathsf { f } ^ { \star } \Delta \mathsf { l } _ { \mathsf { L } } ^ { \star } \mathsf { V } _ { \mathsf { O U T } } } \mathsf { u } \mathsf { H } } \\ { \mathsf { L } _ { \mathsf { B U C K } } > \frac { \mathsf { V } _ { \mathsf { O U T } } { \star } \bigl ( \mathsf { V } _ { \mathsf { I N } ( \mathsf { M A X } ) } - \mathsf { V } _ { \mathsf { O U T } } \bigr ) ^ { \star } 1 0 0 0 } { \mathsf { f } ^ { \star } \Delta \mathsf { l } _ { \mathsf { L } } ^ { \star } \mathsf { V } _ { \mathsf { I N } ( \mathsf { M A X } ) } } \mathsf { u } \mathsf { H } } \end{array}
$$

where: f is operating frequency, kHz

$\mathsf { V } _ { \mathsf { I N ( M I N ) } }$ is minimum input voltage, V

$\mathsf { V } _ { \mathsf { I N } ( \mathsf { M A X } ) }$ is maximum input voltage, V

$\mathsf { V o u r }$ is output voltage, V

$\Delta \mathfrak { l } _ { \mathrm { L } }$ is maximum inductor ripple current, A, usually select $2 0 { \sim } 4 0 \%$ maximum output current.

For high efficiency, choose an inductor with low core loss, such as ferrite. Also, the inductor should have low DC resistance to reduce the I2R losses, and must be able to handle the peak inductor current without saturating. To minimize radiated noise, use a toroid, pot core or shielded bobbin inductor.

# $1 0 . 3 \complement _ { \mathrm { I N } }$ and $\mathtt { c } _ { \mathtt { o u r } }$ Selection

In the boost region, input current is continuous. In the buck region, input current is discontinuous. In the buck region, the selection of input capacitor $\mathsf { C } _ { \mathsf { I N } }$ is driven by the need to filter the input square wave current. Use a low ESR capacitor sized to handle the maximum RMS current. For buck operation, the input RMS current is given by:

$$
\mathsf { I } _ { \mathsf { C I N } } { = } \mathsf { I } _ { \mathsf { O U T } ( \mathsf { M A X } ) } \times \sqrt { \frac { \mathsf { V } _ { \mathsf { O U T } } } { \mathsf { V } _ { \mathsf { I N } } } } \times \left( 1 - \frac { \mathsf { V } _ { \mathsf { O U T } } } { \mathsf { V } _ { \mathsf { I N } } } \right)
$$

This input current has a maximum at $\mathsf { V } _ { \mathsf { I N } } = 2 \mathsf { V } _ { \mathsf { O U T } } , \mathsf { I } _ { \mathsf { C I N } ( \mathsf { M A X } ) } = \mathsf { I } _ { \mathsf { O U T } ( \mathsf { M A X } ) } / 2$ .

In the boost region, COUT must be capable of reducing the output voltage ripple because of the discontinuous output current. The effects of ESR (equivalent series resistance) and the bulk capacitance must be considered when choosing the right capacitor for a given output ripple voltage. The steady ripple due to charging and discharging the bulk capacitance is given by:

$$
{ \Delta } { \mathsf { V } } _ { ( { \mathsf { B O O S T } } , { \mathsf { C a p } } ) } { = } { \frac { { \mathsf { I } } _ { { \mathsf { O U T } } ( { \mathsf { M A X } } ) } \cdot { \mathsf { \Phi } } \left( { \mathsf { V } } _ { { \mathsf { O U T } } } - { \mathsf { V } } _ { { \mathsf { I N } } ( { \mathsf { M N } } ) } \right) } { { \mathsf { C } } _ { { \mathsf { O U T } } } \cdot { \mathsf { V } } _ { { \mathsf { O U T } } } \cdot { \mathsf { \Phi } } ^ { * } { \mathsf { V } } } } \ { \mathsf { V } }
$$

where COUT is the output filter capacitor.

The steady ripple due to the voltage drop across the ESR is given by:

In buck mode, VOUT ripple is given by:

$$
\Delta \mathsf { V } _ { \mathsf { O U T } } \leq \Delta \mathsf { I } _ { \mathsf { L } } ^ { \star } \left( \mathsf { E S R } + \frac { 1 } { 8 ^ { \star } \mathsf { f } ^ { \star } \mathsf { C } _ { \mathsf { O U T } } } \right)
$$

Multiple capacitors placed in parallel may be needed to meet the ESR and RMS current handling requirements.

# 10.4 Power MOSFET Selection and Efficiency Considerations

PL5501 requires four external N-channel power MOSFETs, two for the top switches (switches Q1 and Q3, shown in Figure 32) and two for the bottom switches (switches Q2 and Q4, shown in Figure 32). Important parameters for the power MOSFETs are the breakdown voltage VBR, DSS, threshold voltage $\mathsf { V } _ { \mathsf { G S } , \mathsf { T H } }$ , on-resistance ${ \mathsf { R } } _ { { \mathsf { D } } { \mathsf { S } } ( { \mathsf { O N } } ) }$ , input capacitance $\mathsf { C } _ { \mathsf { i } \mathsf { S } \mathsf { S } }$ and maximum current IDS(MAX). The drive voltage is set by the 6.6V VCC supply to make the MOSFET’s selection more flexible.

# 10.5 Output voltage setting

The PL5501 output voltage is set by an external feedback resistive divider carefully placed across the output capacitor. The $1 \%$ resistance accuracy of this resistor divider is preferred. The resultant feedback signal is compared with the internal precision 2V voltage reference by the error amplifier. The output voltage is given by the equation:

$$
\begin{array} { r } { V _ { O U T } = 2 V * \left( 1 + \frac { R _ { 1 } } { R _ { 2 } } \right) } \end{array}
$$

Where $\mathsf { R } _ { 1 }$ is the upper resistor and ${ \sf R } _ { 2 }$ is the lower resistor in the feedback network.

# 11 PCB Layout

# 11.1 Guideline

Layout is a critical portion of good power supply design. The following guidelines will help users design a PCB with the best power conversion performance, thermal performance, and minimized generation of unwanted EMI.

1. The feedback network, resistor R1 and R2, should be kept close to the FB2 pin. Keep VBUS sensing path away from noisy nodes and preferably through a layer on the other side of shielding layer.   
2. The input /output bypass capacitor must be placed as close as possible to the VIN/VBUS pin and ground. Grounding for both the input and output capacitors should consist of localized top side planes that connect to the GND pin and PAD. It is a good practice to place a ceramic cap near the VINand VBUS pin to reduce the high frequency injection current.   
3. The inductor L should be placed close to the SW1and SW2 pin to reduce magnetic and electrostatic noise.   
4. Current sensing pairs (CSP1,CSN1), (CSP2,CSN2) need to be placed carefully, Layout the lines symmetrically and keep them away from noisy nodes such as BST1,BST2, SW1, SW2, HG1,HG2, LG1,LG2 etc. Connect these nodes directly to the two terminals of current sensing resistors Rcs1, Rcs2 to form an accurate Kelvin connection.

# 11.2 Application Examples

![](../assets/pl5501-datasheet/d05ed5a8a1bf13435484555bbc5ed17b68c63a0891149b049155df0287b5cfae.jpg)  
Fig. 31 Schematic

# 12 Packaging Information

![](../assets/pl5501-datasheet/a82f82cea50120ab6f4902bbbb1ea2e911ab600a46e59000bfd7fe2fd4ca9e96.jpg)

![](../assets/pl5501-datasheet/d668f9679de0e065a883b01b9113bbdd3235e8e0d99eb5b0a2c5d18711cbd383.jpg)

![](../assets/pl5501-datasheet/58ec0ecf8def0fabb93680ca852260c4f7c46d54b66c16ea5903c604b4c7f09a.jpg)  
SIDE VIEW

<table><tr><td rowspan=2 colspan=1>Symbol</td><td rowspan=1 colspan=2>Dimensions In Millimeters</td><td rowspan=1 colspan=2>Dimensions In Inches</td></tr><tr><td rowspan=1 colspan=1>Min.</td><td rowspan=1 colspan=1>Max.</td><td rowspan=1 colspan=1>Min.</td><td rowspan=1 colspan=1>Max.</td></tr><tr><td rowspan=1 colspan=1>A</td><td rowspan=1 colspan=1>0.700</td><td rowspan=1 colspan=1>0.800</td><td rowspan=1 colspan=1>0.028</td><td rowspan=1 colspan=1>0.031</td></tr><tr><td rowspan=1 colspan=1>A1</td><td rowspan=1 colspan=1>0.000</td><td rowspan=1 colspan=1>0.050</td><td rowspan=1 colspan=1>0.000</td><td rowspan=1 colspan=1>0.002</td></tr><tr><td rowspan=1 colspan=1>A3</td><td rowspan=1 colspan=2>0.203REF.</td><td rowspan=1 colspan=2>0.008REF.</td></tr><tr><td rowspan=1 colspan=1>D</td><td rowspan=1 colspan=1>3.900</td><td rowspan=1 colspan=1>4.100</td><td rowspan=1 colspan=1>0.154</td><td rowspan=1 colspan=1>0.161</td></tr><tr><td rowspan=1 colspan=1>E</td><td rowspan=1 colspan=1>3.900</td><td rowspan=1 colspan=1>4.100</td><td rowspan=1 colspan=1>0.154</td><td rowspan=1 colspan=1>0.161</td></tr><tr><td rowspan=1 colspan=1>D1</td><td rowspan=1 colspan=1>2.500</td><td rowspan=1 colspan=1>2.700</td><td rowspan=1 colspan=1>0.098</td><td rowspan=1 colspan=1>0.106</td></tr><tr><td rowspan=1 colspan=1>E1</td><td rowspan=1 colspan=1>2.500</td><td rowspan=1 colspan=1>2.700</td><td rowspan=1 colspan=1>0.098</td><td rowspan=1 colspan=1>0.106</td></tr><tr><td rowspan=1 colspan=1>k</td><td rowspan=1 colspan=2>0.300REF.</td><td rowspan=1 colspan=2>0.012REF.</td></tr><tr><td rowspan=1 colspan=1>b</td><td rowspan=1 colspan=1>0.150</td><td rowspan=1 colspan=1>0.250</td><td rowspan=1 colspan=1>0.006</td><td rowspan=1 colspan=1>0.010</td></tr><tr><td rowspan=1 colspan=1>e</td><td rowspan=1 colspan=2>0.400BSC.</td><td rowspan=1 colspan=2>0.016BSC.</td></tr><tr><td rowspan=1 colspan=1>L</td><td rowspan=1 colspan=1>0.300</td><td rowspan=1 colspan=1>0.500</td><td rowspan=1 colspan=1>0.012</td><td rowspan=1 colspan=1>0.020</td></tr></table>

# IMPORTANT NOTICE

Powlicon Inc. assumes no responsibility for any error which may appear in this document. Powlicon Inc. reserves the right to change devices or specifications detailed herein at any time without notice. Powlicon Inc. does not assume any liability arising out of the application or use of any product described herein; neither it does it convey any license under its patent rights, nor the rights of others. Powlicon Inc. products are not authorized for use as critical components in life support devices or systems without written approval letter from the Chief Executive Officer of Powlicon Inc. The use of products in such applications shall assume all risks of such use and will agree to not hold against Powlicon Inc. for any damage.
</details>
