# High Efficiency, Synchronous, 4-Switch Buck-Boost Controller

# Feat ures

Single Inductor Architecture Allows $\mathsf { V } _ { \mathsf { I N } }$ Above, Below or Equal to the Regulated VOUT Programmable Input or Output Current Wide $\mathsf { V } _ { \mathsf { I N } }$ Range: 4V to 38V $1 \%$ Output Voltage Accuracy: $ { \boldsymbol { 0 . 8 } }  { \mathsf { V } } <  { \mathsf { V } } _ { 0  { \mathsf { U T } } } < 3 8  { \mathsf { V } }$ Synchronous Rectification: Up to $9 8 \%$ Efficiency Current Mode Control Phase-Lockable Fixed Frequency: 200kHz to 600kHz No Reverse Current During Start-Up Power Good Output Voltage Monitor Internal 5.5V LDO Quad N-Channel MOSFET Synchronous Drive VOUT Disconnected from $\mathsf { V } _ { \mathsf { I N } }$ During Shutdown True Soft-Start and VOUT Short Protection, Even in Boost Mode   
n Available in 28-Lead QFN $( 4 \mathsf { m m } \times 5 \mathsf { m m } )$ and 28-Lead SSOP Packages

# Applicat ions

Automotive Systems   
Distributed DC Power Systems   
High Power Battery-Operated Devices   
Industrial Control

# Descript ion

The $\mathbb { L } \mathbb { C } ^ { \otimes } 3 7 8 9$ is a high performance buck-boost switching regulator controller that operates from input voltages above, below or equal to the output voltage. The constant-frequency, current mode architecture allows a phase-lockable frequency of up to 600kHz, while an output current feedback loop provides support for battery charging. With a wide 4V to 38V (40V maximum) input and output range and seamless, low noise transitions between operating regions, the LTC3789 is ideal for automotive, telecom and battery-powered systems.

The operating mode of the controller is determined through the MODE/PLLIN pin. The MODE/PLLIN pin can select between pulse-skipping mode and forced continuous mode operation and allows the IC to be synchronized to an external clock. Pulse-skipping mode offers high efficiency and low ripple at light loads, while forced continuous mode operates at a constant frequency for noise-sensitive applications.

A PGOOD pin indicates when the output is within $10 \%$ of its designed set point. The LTC3789 is available in low profile 28-pin $4 \mathsf { m m } \times 5 \mathsf { m m } 0 \mathsf { F } \mathsf { N }$ and narrow SSOP packages.

# Typical Applicat ion

![](../assets/ltc3789-datasheet/143c0f015686ca040f5c9d8e7878db1595cf087f864d31543ce9d36a62f62b1c.jpg)  
Efficiency and Power Loss

![](../assets/ltc3789-datasheet/d7ef5605f035913f76a5a15bba035797f2b7d71e74755babfcc021144a73fe2a.jpg)

# Absolut e Maxim um Rat ings (Note 1)

Input Supply Voltage (VIN). . 40V to –0.3V VINSNS, VOUTSNS .. 40V to –0.3V Topside Driver Voltages TG1, TG2, BG1, BG2 Voltages . (Note 6) (BOOST1, BOOST2).. 46V to –0.3V ITH, FREQ, ILIM Voltages .INTVCC to $- 0 . 3 V$ Switch Voltage (SW1, SW2). . 40V to –5V VFB Voltage . . 2.7V to –0.3V Current Sense Voltages (IOSENSE+, IOSENSE–).. 40V to –0.3V RUN, PGOOD Voltage . . 6V to –0.3V BOOST1, BOOST2 – SW1, SW2 . . 6V to –0.3V Operating Junction Temperature Range TG1, TG2 – SW1, SW2 . . 6V to –0.3V (Notes 2, 3) . . $- 4 0 \%$ to $1 2 5 \%$ EXTVCC Voltage .. 14V to –0.3V Storage Temperature Range . . $- 6 5 \textdegree$ to $1 2 5 \%$ INTVCC Voltage .. . 6V to –0.3V INTVCC Peak Output Current. ..100mA SENSE+, SENSE– Voltages .. .INTVCC to –0.3V Lead Temperature (Soldering, 10 sec.) MODE/PLLIN, SS Voltages .. ..INTVCC to –0.3V GN Package.... .. $3 0 0 ^ { \circ } \complement$

# Pin Conf igurat ion

![](../assets/ltc3789-datasheet/2fa3dca20133150fcc6cd1e8d6216362f2d10f6a337665f7d763c2ef701e43d9.jpg)

# ord er inf orm at ion

<table><tr><td rowspan=1 colspan=1>LEAD FREE FINISH</td><td rowspan=1 colspan=1>TAPE AND REEL</td><td rowspan=1 colspan=1>PART MARKING*</td><td rowspan=1 colspan=1>PACKAGEDESCRIPTION</td><td rowspan=1 colspan=1>TEMPERATURERANGE</td></tr><tr><td rowspan=1 colspan=1>LTC3789EGN#PBF</td><td rowspan=1 colspan=1>LTC3789EGN#TRPBF</td><td rowspan=1 colspan=1>LTC3789</td><td rowspan=1 colspan=1>28-Lead Narrow Plastic SSOP</td><td rowspan=1 colspan=1>-40°C to 125C</td></tr><tr><td rowspan=1 colspan=1>LTC3789IGN#PBF</td><td rowspan=1 colspan=1>LTC3789IGN#TRPBF</td><td rowspan=1 colspan=1>LTC3789</td><td rowspan=1 colspan=1>28-Lead Narrow Plastic SSOP</td><td rowspan=1 colspan=1>-40°C to 125℃</td></tr><tr><td rowspan=1 colspan=1>LTC3789EUFD#PBF</td><td rowspan=1 colspan=1>LTC3789EUFD#TRPBF</td><td rowspan=1 colspan=1>3789</td><td rowspan=1 colspan=1>28-Lead (4mm×5mm) Plastic QFN</td><td rowspan=1 colspan=1>-40°C to 125C</td></tr><tr><td rowspan=1 colspan=1>LTC3789IUFD#PBF</td><td rowspan=1 colspan=1>LTC3789IUFD#TRPBF</td><td rowspan=1 colspan=1>3789</td><td rowspan=1 colspan=1>28-Lead (4mm × 5mm) Plastic QFN</td><td rowspan=1 colspan=1>-40°C to 125°℃</td></tr></table>

Consult LTC Marketing for parts specified with wider operating temperature ranges. \*The temperature grade is identified by a label on the shipping container. For more information on lead free part marking, go to: http://www.linear.com/leadfree/ For more information on tape and reel specifications, go to: http://www.linear.com/tapeandreel/

Elect rical Charact erist ics The l denotes the specifications which apply over the specified operating junction temperature range, otherwise specifications are at $T _ { A } = 2 5 ^ { \circ } C$ (Note 2). $V _ { \vert \mathsf { N } } = \mathsf { 1 5 V }$ , $V _ { B U N } = 5 V$ , unless otherwise noted.   

<table><tr><td rowspan=1 colspan=1>SYMBOL</td><td rowspan=1 colspan=1>PARAMETER</td><td rowspan=1 colspan=2>CONDITIONS</td><td rowspan=1 colspan=1>MIN  TYP  MAX</td><td rowspan=1 colspan=1>UNITS</td></tr><tr><td rowspan=1 colspan=1>VIN</td><td rowspan=1 colspan=1>Input Supply Voltage</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>4            38</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>VouT</td><td rowspan=1 colspan=1>Output Voltage</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>0.8            38</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>VFB</td><td rowspan=1 colspan=1>RegulatedFeedback Voltage</td><td rowspan=1 colspan=1>ITH Voltage = 1.2V (Note 4), TA = -40°C to 85°CH=1.2V,TA=125°CTA=-40°Ct0125C</td><td rowspan=1 colspan=1>：</td><td rowspan=1 colspan=1>0.792 0.800 0.8080.7880.800 0.812</td><td rowspan=1 colspan=1>VV</td></tr><tr><td rowspan=1 colspan=1>FB</td><td rowspan=1 colspan=1>Feedback Current</td><td rowspan=1 colspan=1>(Note 4)</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>-15  -50</td><td rowspan=1 colspan=1>nA</td></tr><tr><td rowspan=1 colspan=1>VREFLNREG</td><td rowspan=1 colspan=1>Reference Voltage Line Regulation</td><td rowspan=1 colspan=1>VIN = 4V to 38V (Note 4)</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>0.002 0.02</td><td rowspan=1 colspan=1>%/V</td></tr><tr><td rowspan=1 colspan=1>VLOADREG</td><td rowspan=1 colspan=1>Output Voltage Load Regulation</td><td rowspan=1 colspan=1>(Note 4)Measured in Servo Loop,△lTH Voltage = 1.4V to 2VMeasured in Servo Loop,△ltH Voltage = 2Vto 2.5V</td><td rowspan=1 colspan=1>：</td><td rowspan=1 colspan=1>0.01  0.1-0.01 -0.1</td><td rowspan=1 colspan=1>%%</td></tr><tr><td rowspan=1 colspan=1>gm</td><td rowspan=1 colspan=1>Transconductance Amplifier gm</td><td rowspan=1 colspan=1>ITH=1.2V,Sink/Source 5uA (Nte 4)</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>1.5</td><td rowspan=1 colspan=1>mmho</td></tr><tr><td rowspan=1 colspan=1>lQ</td><td rowspan=1 colspan=1>Input DC Supply CurrentNormal ModeShutdown</td><td rowspan=1 colspan=1>(Note 5)VRUN = OV</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>340   60</td><td rowspan=1 colspan=1>mA</td></tr><tr><td rowspan=1 colspan=1>UVLO</td><td rowspan=1 colspan=1>Undervoltage Lockout</td><td rowspan=1 colspan=1> INTVcc Ramping Down</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>3.4   3.6</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>UVL0 Hyst</td><td rowspan=1 colspan=1>Undervoltage Hysteresis</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>0.4</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>ISENSEISENSE</td><td rowspan=1 colspan=1>SENSE Pins Current</td><td rowspan=1 colspan=1>VSENSE=VSENSE+ = OV</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>0.2   +1</td><td rowspan=1 colspan=1>A</td></tr><tr><td rowspan=1 colspan=1>IOSENSElIOSENSE</td><td rowspan=1 colspan=1>loSENSE Pins Current</td><td rowspan=1 colspan=1>VIOSENSE=VIOSENSE+=10V</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>10   14</td><td rowspan=1 colspan=1>A</td></tr><tr><td rowspan=1 colspan=1>Iss</td><td rowspan=1 colspan=1>Soft-Start Charge Current</td><td rowspan=1 colspan=1>Vss = 0V</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>2     3    4</td><td rowspan=1 colspan=1>A</td></tr><tr><td rowspan=1 colspan=1>VRUN(ON)</td><td rowspan=1 colspan=1>RUN Pin On-Threshold</td><td rowspan=1 colspan=1>VRUN Rising</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>1.22</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>VRUN(HYS)</td><td rowspan=1 colspan=1>RUN Pin On-Hysteresis</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>150</td><td rowspan=1 colspan=1>mV</td></tr><tr><td rowspan=1 colspan=1>IRUN</td><td rowspan=1 colspan=1>RUN Pin Source Current</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>1.2</td><td rowspan=1 colspan=1>uA</td></tr><tr><td rowspan=1 colspan=1>IRUN(HYS)</td><td rowspan=1 colspan=1>RUN Pin Hysteresis Current</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1>uA</td></tr><tr><td rowspan=1 colspan=1>VSENSE(MAX)</td><td rowspan=1 colspan=1>Maximum Current Sense ThresholdBuck Region, (IValley)Boost Region, (Peak)</td><td rowspan=1 colspan=1>VFB = 0.7VVFB =0.7V</td><td rowspan=1 colspan=1>：</td><td rowspan=1 colspan=1>73   90   107123  140  157</td><td rowspan=1 colspan=1>mVmV</td></tr><tr><td rowspan=1 colspan=1>VSENSE(IAVG)</td><td rowspan=1 colspan=1>Maximum Input/Output AverageCurrent Sense Threshold</td><td rowspan=1 colspan=1>LIM=OVILIM FloatingILIM = INTVcc</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>48   50   52.590   100  106130  145  160</td><td rowspan=1 colspan=1>mVmVmV</td></tr><tr><td rowspan=1 colspan=1>RDSPFET(ON)</td><td rowspan=1 colspan=1>Driver Pull-Up On-Resistance</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>2.6</td><td rowspan=1 colspan=1>1</td></tr><tr><td rowspan=1 colspan=1>RDSNFET(ON)</td><td rowspan=1 colspan=1>Driver Pull-Down On-Resistance</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>1.5</td><td rowspan=1 colspan=1>1</td></tr><tr><td rowspan=1 colspan=1>TGtrTGt</td><td rowspan=1 colspan=1>Top Gate Rise TimeTop Gate Fall Time</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>2525</td><td rowspan=1 colspan=1>nsns</td></tr><tr><td rowspan=1 colspan=1>BGtrBGt</td><td rowspan=1 colspan=1>Bottom Gate Rise TimeBottom Gate Fall Time</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>2525</td><td rowspan=1 colspan=1>nsns</td></tr><tr><td rowspan=1 colspan=1>TG/BG t1D</td><td rowspan=1 colspan=1>Top Gate Off to Bottom Gate OnDelay Synchronous Switch-OnDelay Time</td><td rowspan=1 colspan=1>CLOAD =3300pFEach Driver (Note6)</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>60</td><td rowspan=1 colspan=1>ns</td></tr><tr><td rowspan=1 colspan=1>BG/TG t1D</td><td rowspan=1 colspan=1>Bottom Gate Off to Top Gate OnDelay Top Switch-On Delay Time</td><td rowspan=1 colspan=1>CLOAD = 3300pF Each Driver (Note 6)</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>60</td><td rowspan=1 colspan=1>ns</td></tr><tr><td rowspan=1 colspan=1>DFMAX.BO0ST</td><td rowspan=1 colspan=1>Maximum Duty Factor</td><td rowspan=1 colspan=1>% Switch C On</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>90</td><td rowspan=1 colspan=1>%</td></tr><tr><td rowspan=1 colspan=1>DON(MIN,BOOST)</td><td rowspan=1 colspan=1>Minimum Duty Factor for MainSwitch in Boost Operation</td><td rowspan=1 colspan=1>% Switch C On</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>9</td><td rowspan=1 colspan=1>%</td></tr><tr><td rowspan=1 colspan=1>DON(MIN,BUCK)</td><td rowspan=1 colspan=1>Minimum Duty Factor forSynchronous Switch in BuckOperation</td><td rowspan=1 colspan=1>% Switch B On</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>9</td><td rowspan=1 colspan=1>%</td></tr></table>

Elect rical Charact erist ics The l denotes the specifications which apply over the specified operating junction temperature range, otherwise specifications are at $T _ { A } = 2 5 ^ { \circ } C$ (Note 2). $V _ { \vert \mathsf { N } } = 1 5 V$ , $V _ { B U N } = 5 V$ , unless otherwise noted.   

<table><tr><td rowspan=1 colspan=1>SYMBOL</td><td rowspan=1 colspan=1>PARAMETER</td><td rowspan=1 colspan=2>CONDITIONS</td><td rowspan=1 colspan=1>MIN   TYP  MAX</td><td rowspan=1 colspan=1>UNITS</td></tr><tr><td rowspan=1 colspan=6>INTVcc Linear Regulator</td></tr><tr><td rowspan=1 colspan=1>VINTVCCVIN</td><td rowspan=1 colspan=1>Internal Vcc Voltage</td><td rowspan=1 colspan=1>6.5V&lt;VIN&lt;40VVExTvC=OV</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>5.2   5.5   5.8</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>VLDOVIN</td><td rowspan=1 colspan=1>INTVcc Load Regulation</td><td rowspan=1 colspan=1>Icc =OmA t20mA,VExTvCC= OV</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>0.2   1.0</td><td rowspan=1 colspan=1>%</td></tr><tr><td rowspan=1 colspan=1>VINTVCCEXT</td><td rowspan=1 colspan=1>Internal Vcc Voltage</td><td rowspan=1 colspan=1>6.5V &lt;VEXTVCC &lt;14V</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>5.2   5.5   5.8</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>VLDOEXT</td><td rowspan=1 colspan=1>INTVcc Load Regulation</td><td rowspan=1 colspan=1>Icc =0mA to2AVcc=12V</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>0.2   1.0</td><td rowspan=1 colspan=1>%</td></tr><tr><td rowspan=1 colspan=1>VExTvCC</td><td rowspan=1 colspan=1>EXTVcc Switchover Voltage</td><td rowspan=1 colspan=1>Icc =0mA to20mA,EXTVccRamping ositive</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>4.7   4.8</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>VLDOHYS</td><td rowspan=1 colspan=1>EXTVcc Hysteresis</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>0.25</td><td rowspan=1 colspan=1>V</td></tr></table>

# Oscillator and Phase-Locked Loop

<table><tr><td></td><td>Nominal Frequency</td><td>VFREQ = 1.2V</td><td></td><td>350</td><td>400</td><td>440</td><td></td></tr><tr><td>fNOM</td><td></td><td></td><td></td><td></td><td></td><td></td><td>KHz</td></tr><tr><td>fLow</td><td>Low Fixed Frequency</td><td>VFREQ = OV</td><td></td><td>175</td><td>200</td><td>225</td><td>KHz</td></tr><tr><td>fHIGH</td><td>High Fixed Frequency</td><td>VFREQ = 2.4V</td><td></td><td>570</td><td>640</td><td>710</td><td>KHz</td></tr><tr><td>fsYNC</td><td>Synchronizable Frequency</td><td>MODE/PLLIN = External Clock</td><td>·</td><td>200</td><td></td><td>600</td><td>KHz</td></tr><tr><td>RMODE/PLLIN</td><td>MODE/PLLIN Input Resistance</td><td></td><td></td><td></td><td>220</td><td></td><td>k</td></tr><tr><td>IFREQ</td><td>Frequency Setting Current</td><td></td><td></td><td>8</td><td>10</td><td>12</td><td>UA</td></tr></table>

# PGOOD Output

Note 1: Stresses beyond those listed under Absolute Maximum Ratings may cause permanent damage to the device. Exposure to any Absolute Maximum Rating condition for extended periods may affect device reliability and lifetime.   

<table><tr><td rowspan=1 colspan=1>VPGL</td><td rowspan=1 colspan=1>PGOOD Voltage Low</td><td rowspan=1 colspan=1>IPGOOD = 2mA</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>0.1    0.3</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>IPGOOD</td><td rowspan=1 colspan=1>PGOOD Leakage Current</td><td rowspan=1 colspan=1>VPGOOD =5V</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>±1</td><td rowspan=1 colspan=1>UA</td></tr><tr><td rowspan=1 colspan=1>VPG</td><td rowspan=1 colspan=1>PGOOD Trip Level</td><td rowspan=1 colspan=1>VFB with Respect to Set Output VoltageVFB Ramping NegativeVFB Ramping Positive</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>-1010</td><td rowspan=1 colspan=1>%%</td></tr></table>

Note $3 : \top _ { \mathrm { J } }$ is calculated from the ambient temperature $\intercal _ { \mathsf { A } }$ and power dissipation $\mathsf { P } _ { \mathsf { D } }$ according to the following formula: LTC3789GN: $\mathsf { T } _ { \mathsf { J } } = \mathsf { T } _ { \mathsf { A } } + ( \mathsf { P } _ { \mathsf { D } } \bullet 8 0 ^ { \circ } \mathsf { C } N )$ LTC3789UFD: $\mathsf { T } _ { \mathsf { J } } = \mathsf { T } _ { \mathsf { A } } + ( \mathsf { P } _ { \mathsf { D } } \bullet 3 4 ^ { \circ } \mathsf { C } / \mathsf { W } )$

Note 2: The LTC3789 is tested under pulse load conditions such that $\mathsf { T } _ { \mathsf { J } } \approx \mathsf { T } _ { \mathsf { A } }$ . The LTC3789E is guaranteed to meet performance specifications from $0 \%$ to $\mathtt { 8 5 ^ { \circ } C }$ operating junction temperature. Specifications over the $- 4 0 ^ { \circ } \complement$ to $1 2 5 ^ { \circ } 0$ operating junction temperature range are assured by design, characterization and correlation with statistical process controls. The LTC3789I is guaranteed to meet performance specifications over the full $- 4 0 ^ { \circ } \complement$ to $1 2 5 ^ { \circ } 0$ operating junction temperature range.

Note 4: The LTC3789 is tested in a feedback loop that servos $\mathsf { V } _ { \mathsf { I T H } }$ to a specified voltage and measures the resultant $V _ { F B }$ .

Note 5: Dynamic supply current is higher due to the gate charge being delivered at the switching frequency. See the Applications Information section.

Note 6: Do not apply a voltage or current to these pins. They must be connected to capacitive loads only, otherwise permanent damage may occur.

![](../assets/ltc3789-datasheet/8452608bb5c272b548871d8e54745d8776c6453d7bf586f5f2cc7469c1e6dcb7.jpg)

# Typical Perf orm ance Charact erist ics $T _ { A } = 2 5 ^ { \circ } C$ unless otherwise noted.

![](../assets/ltc3789-datasheet/8c5c18208ec345f4daa967269d512c0caff54f55a4cf662a17be255243a87b84.jpg)  
Forced Continuous Mode

![](../assets/ltc3789-datasheet/f6b53f825a205bf9df4e8a1ac396ae6f65562c5534ed0628588f61d7c1dc7b89.jpg)  
Forced Continuous Mode

![](../assets/ltc3789-datasheet/c0a12ef20db8e3703e27d251034036491ca44d773558d2d706dc7eb64dc0789e.jpg)  
Forced Continuous Mode

![](../assets/ltc3789-datasheet/50622a6ee52bf16d10ce41a015bacd7015ab0796f7acdff7d27a27cf035287df.jpg)  
Pulse-Skipping Mode

![](../assets/ltc3789-datasheet/e56b00970ed9f952da82ecd9c10290b07be218c1a683be44921325c95b3ad091.jpg)  
Pulse-Skipping Mode

![](../assets/ltc3789-datasheet/51412a4db36bdc1fdfa996faca2afd5455e0c37133c5bf173c371447647d7ed3.jpg)  
Pulse-Skipping Mode

![](../assets/ltc3789-datasheet/6c8a4e1b016ad41239fa3b46871081ba97543e53b120162c923d525b4acf4ff4.jpg)  
Oscillator Frequency vs Temperature

![](../assets/ltc3789-datasheet/828c6f6f6623dfdf5e06a3bc16c2e8e9cf56a1d08275bde76036cf3e9d27c174.jpg)  
Undervoltage Threshold at ${ \| { \mathsf { N I V } } _ { \complement } } _ { \complement }$ vs Temperature

![](../assets/ltc3789-datasheet/1f0db7880c06d03f661ccdafb0afec82d7a94a99f9679dfc2c72b8806bb74e44.jpg)  
Undervoltage Threshold at $\mathsf { V } _ { \mathsf { I N } }$ vs Temperature

# Typical Perf orm ance Charact erist ics $T _ { A } = 2 5 ^ { \circ } C$ unless otherwise noted.

![](../assets/ltc3789-datasheet/0ef79ef3505cbe6988e2168f73249a46846d3e6b18a87812ef8a9f82b1498a11.jpg)

# Typical Perf orm ance Charact erist ics $T _ { A } = 2 5 ^ { \circ } C$ unless otherwise noted.

![](../assets/ltc3789-datasheet/ea5bc0e7218d233d4e0cd1e4192a6ad17cf9cb4507cd816833559ea7e2377ed1.jpg)

![](../assets/ltc3789-datasheet/4e4bbe4bd399b6f8e2a904aed379d2392b60ecb96a6f46a288d7a460cbb72267.jpg)

![](../assets/ltc3789-datasheet/e25bde7e104f49088601d517e6d8027033eae6e7f1a329a3997795f3419b9845.jpg)

# Pin Funct ions (SSOP/QFN)

$V _ { F B }$ (Pin 1/Pin 26): Error Amplifier Feedback Pin. Receives the feedback voltage for the controller from an external resistive divider across the output.

SS (Pin 2/Pin 27): External Soft-Start Input. The LTC3789 regulates the VFB voltage to the smaller of $0 . 8 \mathsf { V }$ or the voltage on the SS pin. A internal $3 \mu \ A$ pull-up current source is connected to this pin. A capacitor to ground at this pin sets the ramp time to final regulated output voltage.

$\pmb { \ S } \pmb { \mathrm { K } } \pmb { \mathrm { M } } \pmb { \ S } \pmb { \mathrm { F } } ^ { + }$ (Pin 3/Pin 28): The $\left( + \right)$ Input to the Current Sense Comparator. The $\mathsf { I } _ { \mathsf { T } \mathsf { H } }$ pin voltage and controlled offsets between the SENSE– and ${ \tt S E N S E } ^ { + }$ pins, in conjunction with RSENSE, set the current trip threshold.

SENSE– (Pin 4/Pin 1): The $\left( - \right)$ Input to the Current Sense Comparator.

ITH (Pin 5/Pin 2): Error Amplifier Output and Switching Regulator Compensation Point. The channel’s current comparator trip point increases with this control voltage.

SGND (Pin 6/Pins 3, Exposed Pad Pin 29): Small Signal Ground. Must be routed separately from high current grounds to the common $\left( - \right)$ terminals of the $\complement _ { \mathsf { I N } }$ capacitors. In the QFN package, the exposed pad is SGND. It must be soldered to PCB ground for rated thermal performance.

MODE/PLLIN (Pin 7/Pin 4): Mode Selection or External Synchronization Input to Phase Detector. This is a dualpurpose pin. When external frequency synchronization is not used, this pin selects the operating mode. The pin can be tied to SGND or INTVCC. SGND or below $0 . 8 \mathsf { V }$ enables forced continuous mode. INTVCC enables pulse-skipping mode. For external sync, apply a clock signal to this pin. The internal PLL will synchronize the internal oscillator to the clock, and forced continuous mode will be enabled. The PLL composition network is integrated into the IC.

FREQ (Pin 8/Pin 5): Frequency Set Pin. There is a precision $1 0 \mu \ A$ current flowing out of this pin. A resistor to ground sets a voltage which, in turn, programs the frequency. Alternatively, this pin can be driven with a DC voltage to vary the frequency of the internal oscillator.

RUN (Pin 9/Pin 6): Run Control Input. Forcing the pin below $0 . 5 \mathsf { V }$ shuts down the controller, reducing quiescent current. There are $1 . 2 \mu \ A$ pull-up currents for this pin. Once the RUN pin rises above 1.22V, the IC is turned on, and an additional 5µA pull-up current is added to the pin.

VINSNS (Pin 10/Pin 7): $\mathsf { V } _ { \mathsf { I N } }$ Sense Input to the Buck-Boost Transition Comparator. Connect this pin to the drain of the top N-channel MOSFET on the input side.

VOUTSNS (Pin 11/Pin 8): VOUT Sense Input to the BuckBoost Transition Comparator. Connect this pin to the VOUT.

ILIM (Pin 12/Pin 9): Input/Output Average Current Sense Range Input. This pin tied to SGND, INTVCC or left floating, sets the maximum average current sense threshold.

IOSENSE+ (Pin 13/Pin 10): The $\left( + \right)$ Input to the Input/Output Average Current Sense Amplifier.

IOSENSE– (Pin 14/Pin 11): The $\left( - \right)$ Input to the Input/Output Average Current Sense Amplifier.

TRIM (Pin 15/Pin 12): Tie this pin to GND for normal operation. Do not allow this pin to float.

$\mathtt { E X N } _ { \mathtt { C C } }$ (Pin 20/Pin 17): External Power Input to an Internal LDO Connected to ${ \| \mathsf { N P } _ { \complement } } _ { }$ . This LDO supplies INTVCC power, bypassing the internal LDO powered from $\mathsf { V } _ { \mathsf { I N } }$ whenever $\mathsf { E X N } _ { \mathsf { C C } }$ is higher than $4 . 8 \mathsf { V } .$ . See EXTVCC Connection in the Applications Information section. Do not exceed 14V on this pin.

# Pin Funct ions (SSOP/QFN)

INTV (Pin 21/Pin 18): Output of the Internal Linear Low Dropout Regulator. The driver and control circuits are powered from this voltage source. Must be bypassed to power ground with a minimum of 4.7µF tantalum, ceramic, or other low ESR capacitor.

$\mathsf { V } _ { \mathsf { I N } }$ (Pin 22/Pin 19): Main Supply Pin. A bypass capacitor should be tied between this pin and the power ground pin.

BG1, BG2 (Pins 23, 19/Pins 20, 16): High Current Gate Drives for Bottom (Synchronous) N-Channel MOSFETs. Voltage swing at these pins is from ground to INTVCC.

PGND (Pin 24/Pin 21): Driver Power Ground. Connects to COUT and RSENSE (–) terminal(s) of $\complement _ { \mathsf { I N } }$ .

BOOST1, BOOST2 (Pins 25, 18/Pins 22, 15): Bootstrapped Supplies to the Top Side Floating Drivers. Capacitors are connected between the BOOST and SW pins and Schottky diodes are tied between the BOOST and ${ \sf N N } _ { \sf C C }$ pins. Voltage swing at the BOOST1 pin is from INTVCC to $( \mathsf { V } _ { | \mathsf { N } } + \mathsf { I N } \mathsf { T } \mathsf { V } _ { \mathsf { C C } } )$ . Voltage swing at the BOOST2 pin is from ${ \| \mathsf { N T V } _ { \complement } } _ { }$ to $( \mathsf { V } _ { 0 } \mathsf { U } \mathsf { T } + \mathsf { I N } \mathsf { T } \mathsf { V } _ { \mathsf { C } } \mathsf { c } )$ .

TG1, TG2 (Pins 26, 17/Pins 23, 14): High Current Gate Drives for Top $\mathbb { N }$ -Channel MOSFETs. These are the outputs of floating drivers with a voltage swing equal to $\| \mathsf { N T V } _ { \complement } - 0 . 5 \mathsf { V }$ superimposed on the switch node voltage SW.

SW1, SW2 (Pins 27, 16/Pins 24, 13): Switch Node Connections to Inductors. Voltage swing at the SW1 pin is from a Schottky diode (external) voltage drop below ground to $\mathsf { V } _ { \mathsf { I N } }$ . Voltage swing at the SW2 pin is from a Schottky diode voltage drop below ground to VOUT.

PGOOD (Pin 28/Pin 25): Open-Drain Logic Output. PGOOD is pulled to ground when the voltage on the VFB pin is not within $\pm 1 0 \%$ of its regulation window, after the internal 20µs power-bad mask timer expires.

# Block Diagram

![](../assets/ltc3789-datasheet/2ece6a53f862607a0216f64e31bab14f878e01490fc3582e00ab07b76a7f7553.jpg)

# Operat ion

# Main Control Loop

The LTC3789 is a current mode controller that provides an output voltage above, equal to or below the input voltage. The LTC proprietary topology and control architecture employs a current-sensing resistor. The inductor current is controlled by the voltage on the $\mathsf { I } _ { \mathsf { T } \mathsf { H } }$ pin, which is the output of the error amplifier EA. The $V _ { F B }$ pin receives the voltage feedback signal, which is compared to the internal reference voltage by the EA. If the input/output current regulation loop is implemented, the sensed inductor current is controlled by either the sensed feedback voltage or the input/output current.

# $1 \mathsf { N T V } _ { \mathsf { C C } } / \mathsf { E X T V } _ { \mathsf { C C } }$ Power

Power for the top and bottom MOSFET drivers and most other internal circuitry is derived from the ${ \| \mathsf { N N } _ { \complement } } _ { \complement }$ pin. When the $\mathsf { E X N } _ { \mathsf { C C } }$ is left open or tied to a voltage less than $4 . 5 \mathsf { V }$ , an internal $5 . 5 \mathsf { V }$ low dropout (LDO) regulator supplies INTVCC power from $\mathsf { V } _ { \mathsf { I N } }$ . If EXTVCC is taken above $4 . 8 V _ { \mathrm { { i } } }$ , the $5 . 5 \mathsf { V }$ regulator is turned off, and another LDO regulates ${ \| \mathsf { N T V } _ { \complement } } _ { }$ from $\mathsf { E X N } _ { \mathsf { C C } }$ . The $\mathsf { E X N } _ { \mathsf { C C } }$ LDO allows the ${ \| \mathsf { N T V } _ { \complement } } _ { }$ power to be derived from a high efficiency external source such as the LTC3789 regulator output to reduce IC power dissipation. The absolute maximum voltage on $\mathsf { E X N } _ { \mathsf { C C } }$ is $1 4 \lor .$ .

# Internal Charge Pump

Each top MOSFET driver is biased from the floating bootstrap capacitors $\complement _ { \mathsf { A } }$ and $\complement _ { \mathsf { B } }$ , which are normally recharged by ${ \| \mathsf { N P } _ { \complement } } _ { }$ throughanexternaldiodewhenthe topMOSFET is turned off. When the LTC3789 operates exclusively in the buck or boost regions, one of the top MOSFETs is constantly on. An internal charge pump recharges the bootstrap capacitor to compensate for the small leakage current through the bootstrap diode so that the MOSFET can be kept on. However, if a high leakage diode is used suchthattheinternalchargepumpcannotprovidesufficient charges to the external bootstrap capacitor, an internal UVLO comparator, which constantly monitors the drop across the capacitor, will sense the (BOOST – SW) voltage when it is below $3 . 6 \mathbb { V } .$ It will turn off the top MOSFET for about one-twelfth of the clock period every four cycles to allow $\complement _ { A } 0 \ u { \Gamma } \complement _ { \mathsf { B } }$ to recharge.

# Shutdown and Start-Up

The controller can be shut down by pulling the RUN pin low. When the RUN pin voltage is below $0 . 5 \mathsf { V }$ , the LTC3789 goes into low quiescent current mode. Releasing RUN allows an internal $1 . 2 \mu \ A$ current to pull up the pin and enable the controller. When RUN is above the accurate threshold of $1 . 2 2 \vee$ , the internal LDO will power up the INTVCC. At the same time, a 6µA pull-up current will kick in to provide more RUN pin hysteresis. The RUN pin may be externally pulled up or driven directly by logic. Be careful not to exceed the absolute maximum rating of 6V on this pin.

The start-up of the controller’s output voltage VOUT is controlled by the voltage on the SS pin. When the voltage on the SS pin is less than the $0 . 8 \mathsf { V }$ internal reference, the LTC3789 regulates the VFB voltage to the SS voltage instead of the $0 . 8 \mathsf { V }$ reference. This allows the SS pin to be used to program soft-start by connecting an external capacitor from the SS pin to SGND. An internal 3µA pull-up current charges this capacitor, creating a voltage ramp on the SS pin. As the SS voltage rises linearly from 0V to $0 . 8 \mathsf { V }$ (and beyond), the output voltage VOUT rises smoothly from zero to its final value. Alternatively, the SS pin can be used to cause the start-up of VOUT to track that of another supply. When RUN is pulled low to disable the controller, or when ${ \| \mathsf { N T V } _ { \complement } } _ { }$ is below the undervoltage lockout threshold of 3.4V, the SS pin is pulled low by an internal MOSFET. In undervoltage lockout, the controller is disabled and the external MOSFETs are held off.

# Operat ion

# Power switch Control

Figure 1 shows a simplified diagram of how the four power switches are connected to the inductor, $\mathsf { V } _ { \mathsf { I N } } , \mathsf { V } _ { 0 \mathsf { U T } }$ and GND. Figure 2 shows the regions of operation for the LTC3789 as a function of duty cycle, D. The power switches are properly controlled so the transfer between regions is continuous.

# Buck Region $( \mathsf { V } _ { | \mathsf { N } } > > \mathsf { V } _ { 0 \mathsf { U T } } )$

Switch D is always on and switch C is always off in this region. At the start of every cycle, synchronous switch B is turned on first. Inductor current is sensed when synchronous switch B is turned on. After the sensed inductor valley current falls below a reference voltage, which is proportional to $\mathsf { V } _ { \sf I T H } .$ , synchronous switch B is turned off and switch A is turned on for the remainder of the cycle. Switches A and B will alternate, behaving like a typical synchronous buck regulator. The duty cycle of switch A increases until the maximum duty cycle of the converter reaches DMAX_BUCK, given by:

$$
D _ { \sf M A X \_ B U G K } = \left( 1 - \frac { 1 } { 1 2 } \right) \bullet 1 0 0 \% = 9 1 . 6 7 \%
$$

![](../assets/ltc3789-datasheet/9557a9bc3bfb274f8a21df91a0cb73fad0e3751f0ed52d7a2091322c70a1e8e3.jpg)  
Figure 1. Simplified Diagram of the Output Switches

![](../assets/ltc3789-datasheet/55af3256db495b6a02b8ed51dbb723c176a99f1ef33581df937e9c6370444180.jpg)  
Figure 2. Operating Region vs Duty Cycle

![](../assets/ltc3789-datasheet/eaf61188f405c02c347d3f675f44cd4b639f1bcd80b8baf7040d987e08e20f33.jpg)  
Figure 3 shows typical buck region waveforms. If $\mathsf { V } _ { \mathsf { I N } }$ approaches $\mathsf { V } _ { 0 \mathsf { U } } ,$ the buck-boost region is reached.   
Figure 3. Buck Region $( \mathsf { V } _ { \mathsf { I N } } > > \mathsf { V _ { O U T } } )$

# Buck-Boost Region $( \mathsf { V } _ { | \mathsf { N } } \approx \mathsf { V } _ { 0 \mathsf { U T } } )$

When $\mathsf { V } _ { \mathsf { I N } }$ is close to $\mathsf { V } _ { 0 \mathsf { U } \mathsf { T } }$ , the controller enters buckboost region. Figure 4 shows the typical waveforms in this region. At the beginning of a clock cycle, if the controller starts with B and D on, the controller first operates as a buck region. When ICMP trips, switch B is turned off, and switch A is turned on. At $1 2 0 ^ { \circ }$ clock phase, switch C is turned on. The LTC3789 starts to operate as a boost until ICMP trips. Then, switch D is turned on for the remainder of the clock period. If the controller starts with switches A and C on, the controller first operates as a boost, until ICMP trips and switch D is turned on. At $1 2 0 ^ { \circ } ,$ switch B is turned on, making it operate as a buck. Then, ICMP trips, turning switch B off and switch A on for the remainder of the clock period.

# Boost Region $( \mathsf { V } _ { \mathsf { I N } } < < \mathsf { V } _ { \mathsf { O U T } } )$

Switch A is always on and synchronous switch B is always off in the boost region. In every cycle, switch C is turned on first. Inductor current is sensed when synchronous switch C is turned on. After the sensed inductor peak current exceeds what the reference voltage demands, which is proportional to $\mathsf { V } _ { \sf I T H }$ , switch C is turned off and synchronous switch D is turned on for the remainder of the cycle. Switches C and D will alternate, behaving like a typical synchronous boost regulator.

# OPERA TION

The duty cycle of switch C decreases until the minimum duty cycle of the converter reaches DMIN_BOOST, given by:

$$
\mathsf { D } _ { \mathsf { M I N \_ B O 0 S 7 } } = \left( \frac { 1 } { 1 2 } \right) \bullet 1 0 0 \% = 8 . 3 3 \%
$$

![](../assets/ltc3789-datasheet/c6faeb2292bf0d7b8df84282aa252d8176e16e2f25a87fb2eb600f474a6e01dd.jpg)  
Figure 5 shows typical boost region waveforms. If $\mathsf { V } _ { \mathsf { I N } }$ approaches $\mathsf { V } _ { 0 \mathsf { U } \mathsf { T } }$ , the buck-boost region is reached.

![](../assets/ltc3789-datasheet/59505eed00820671a7491e1d9791b065901c74682f09ace0247a2c1abfffd50e.jpg)  
(4a) Buck-Boost Region $( \mathsf { V } _ { \mathsf { I N } } \geq \mathsf { V } _ { \mathsf { O U T } } )$   
Figure 4. Buck-Boost Region

# Light Load Current Operation

The LTC3789 can be enabled to enter pulse-skipping mode or forced continuous conduction mode. To select forced continuous operation, tie the MODE/PLLIN pin to a DC voltage below $0 . 8 \mathsf { V }$ (e.g., SGND). To select pulse-skipping mode of operation, tie the MODE/PLLIN pin to INTVCC.

When the LTC3789 enters pulse-skipping mode, in the boost region, synchronous switch D is held off whenever reverse current through switch A is detected. At very light loads, the current comparator, ICMP , may remain tripped for several cycles and force switch C to stay off for the same number of cycles (i.e., skipping pulses). In the buck region, the inductor current is not allowed to reverse. Synchronous switch B is held off whenever reverse current on the inductor is detected. At very light loads, the current comparator, ICMP , may remain untripped for several cycles, holding switch A off for the same number of cycles. Synchronous switch B also remains off for the skipped cycles. In the buck-boost region, the controller operates alternatively in boost and buck region in one clock cycle, as in continuous operation. A small amount of reverse current is allowed, to minimize ripple. For the same reason, a narrow band of continuous buck and boost operation is allowed on the high and low line ends of the buck-boost region.

![](../assets/ltc3789-datasheet/42fb44b266966480a35251228d5293d5c8c818742c1e31a3fc6d213e1836a568.jpg)  
Figure 5. Boost Region $( \mathsf { V } _ { \mathsf { I N } } < < \mathsf { V } _ { 0 \mathsf { U T } } )$

# Output Overvoltage

If the output voltage is higher than the value commanded by the VFB resistor divider, the LTC3789 will respond according to the mode and region of operation. In continuous conduction mode, the LTC3789 will sink current into the input. If the input supply is capable of sinking current, the LTC3789 will allow up to about 160mV/RSENSE to be sunk into the input. In pulse-skipping mode and in the buck or boost regions, switching will stop and the output will be allowed to remain high. In pulse-skipping mode, and in the buck/boost region as well as the narrow band of continuous boost operation that adjoins it, current sunk into the input through switch A is limited to approximately 40mV/ RDS(ON) of switch A. If this level is reached, switching will stop and the output will rise. In pulse-skipping mode, and in the narrow continuous buck region that adjoins the buck/ boost region, current sunk into the input through RSENSE is limited to approximately 40mV/RSENSE.

# OPERA TION

# Constant-Current Regulation

The LTC3789 provides a constant-current regulation loop for either input or output current. A sensing resistor close to the input or output capacitor will sense the input or output current. When the current exceeds the programmed current limit, the voltage on the $\mathsf { I } _ { \mathsf { T } \mathsf { H } }$ pin will be pulled down to maintain the desired maximum input or output current. The input current limit function prevents overloading the DC input source, while the output current limit provides a building block for battery charger or LED driver applications. It can also serve as an extra current limit protection for a constant-voltage regulation application. The input/ output current limit function has an operating voltage range of GND to the absolute maximum ${ \mathsf { V } } _ { 0 \mathsf { U T } } \left( { \mathsf { V } } _ { \mathsf { I N } } \right)$ .

# Frequency Selection and Phase-Locked Loop (FREQ and MODE/PLLIN Pins)

The selection of switching frequency is a trade-off between efficiency and component size. Low frequency operation increases efficiency by reducing MOSFET switching losses, but requires larger inductance and/or capacitance to maintain low output ripple voltage. The switching frequency of the LTC3789’s controllers can be selected using the FREQ pin. If the MODE/PLLIN pin is not being driven by an external clock source, the FREQ pin can be used to program the controller’s operating frequency from 200kHz to 600kHz.

Switching frequency is determined by the voltage on the FREQ pin. Since there is a precision $1 0 \mu \ A$ current flowing out of the FREQ pin, the user can program the controller’s switching frequency with a single resistor to SGND. A curve is provided in the Applications Information section to show the relationship between the voltage on the FREQ pin and the switching frequency.

A phase-locked loop (PLL) is integrated on the LTC3789 to synchronize the internal oscillator to an external clock source driving the MODE/PLLIN pin. The controller operates in forced continuous mode when it is synchronized. The PLL filter network is integrated inside the LTC3789.

The PLL is capable of locking to any frequency within the range of 200kHz to 600kHz. The frequency setting resistor should always be present to set the controller’s initial switching frequency before locking to the external clock.

# Power Good (PGOOD) Pins

ThePGOODpinisconnected totheopendrainofaninternal N-channel MOSFET. When $V _ { F B }$ is not within $\pm 1 0 \%$ of the $0 . 8 \mathsf { V }$ reference voltage, the PGOOD pin is pulled low. The PGOOD pin is also pulled low when RUN is below $1 . 2 2 \lor$ or when the LTC3789 is in the soft-start phase. There is an internal 20µs power good or bad mask when $\mathsf { V } _ { \mathsf { F B } } \mathsf { g o e s }$ in or out of the $\pm 1 0 \%$ window. The PGOOD pin is allowed to be pulled up by an external resistor to INTVCC or an external source of up to $6 \vee$ .

# Short-Circuit Protection, Current Limit and Current Limit Foldback

The maximum current threshold of the controller is limited by a voltage clamp on the $\mathsf { I } _ { \mathsf { T } \mathsf { H } } \mathsf { p i n }$ . In every boost cycle, the sensed maximum peak voltage is limited to $1 4 0 \mathsf { m V }$ In every buck cycle, the sensed maximum valley voltage is limited to $9 0 { \mathsf { m } } \mathsf { V } .$ . In the buck-boost region, only peak sensed voltage is limited by the same threshold as in the boost region.

The LTC3789 includes current foldback to help limit load current when the output is shorted to ground. If the output falls below $50 \%$ of its nominal output level, then the maximum sense voltage is progressively lowered from its maximum value to one-third of the maximum value. Foldback current limiting is disabled during the soft-start. Under short-circuit conditions, the LTC3789 will limit the current by operating as a buck with very low duty cycles, and by skipping cycles. In this situation, synchronous switch B will dissipate most of the power (but less than in normal operation).

# Applicat ions Inf orm at ion

The Typical Application on the first page is a basic LTC3789 application circuit. External component selection is driven by the load requirement, and begins with the selection of RSENSE and the inductor value. Next, the power MOSFETs are selected. Finally, $\complement _ { \mathsf { I N } }$ and $\complement _ { 0 \updownarrow \tau }$ are selected. This circuit can be configured for operation up to an input voltage of $3 8 \mathsfit { V }$ .

# RSENSE Selection and Maximum Output Current

RSENSE is chosen based on the required output current. The current comparator threshold sets the peak of the inductor current in the boost region and the maximum inductor valley current in the buck region. In the boost region, the maximum average load current at $\mathsf { V } _ { \mathsf { I N ( M I N ) } }$ is:

$$
{ \sf I } _ { 0 0 \sf T ( \sf M A X , B 0 0 S \sf 7 ) } = \left( \frac { 1 4 0 \sf m V } { { \sf R } _ { \sf S E N S E } } - \frac { \Delta { \sf I } _ { \sf L } } { 2 } \right) \bullet \frac { { \sf V } _ { \sf I N ( \sf M I N ) } } { { \sf V } _ { 0 0 \sf I 7 } }
$$

where $\Delta \mathfrak { l }$ is peak-to-peak inductor ripple current. In the buck region, the maximum average load current is:

$$
| \mathsf { \Gamma } _ { 0 \mathsf { U T } ( \mathsf { M A X } , \mathsf { B U C K } ) } = \frac { 9 0 \mathsf { m V } } { \mathsf { R } _ { \mathsf { S E N S E } } } + \frac { \Delta \mathsf { l } _ { \mathsf { L } } } { 2 }
$$

![](../assets/ltc3789-datasheet/f71e2f0b1e62e4ea03621c0c090bb4932e06358951be919a013ef9b8d87d8e21.jpg)  
Figure 6 shows how ILOAD(MAX) • RSENSE varies with input and output voltage.   
Figure 6. Load Current vs $\nu _ { \sf I N } / \nu _ { \sf 0 U T }$

The maximum current sensing RSENSE value for the boost region is:

$$
\frac { 2 \bullet 1 4 0 \mathsf { m V } \bullet \mathsf { V } _ { \mathsf { I N } ( \mathsf { M I N } ) } } { 2 \bullet | _ { 0 \mathsf { U T } ( \mathsf { M A X } , \mathsf { B O O S T } ) } \bullet \mathsf { V } _ { 0 \mathsf { U T } } + \Delta | _ { \mathsf { L } , \mathsf { B O O S T } } \bullet \mathsf { V } _ { \mathsf { I N } ( \mathsf { M I N } ) } }
$$

The maximum current sensing RSENSE value for the buck region is:

$$
R _ { \mathbb { S } \in \mathbb { N S E } ( \mathbb { M A X } ) } = \frac { 2 \bullet 9 0 \mathsf { m V } } { 2 \bullet | _ { 0 \sqcup \mathsf { T } ( \mathbb { M A X } , \mathbb { B } \cup \mathbb { C K } ) } - \Delta | _ { \mathsf { L } , \mathbb { B } \cup \mathbb { C K } } }
$$

The final RSENSE value should be lower than the calculated RSENSE(MAX) in both the boost and buck regions. A $20 \%$ to $30 \%$ margin is usually recommended.

# Programming Input/Output Current Limit

As shown in Figures 7 and 8, input/output current sense resistor RSENSE2 should be placed between the bulk capacitor for $\mathsf { V } _ { \mathsf { I N } } / \mathsf { V } _ { 0 \mathsf { U T } }$ and the decoupling capacitor. A lowpass filter formed by $\mathsf { R } _ { \mathsf { F } }$ and $\complement _ { \ F }$ is recommended to reduce the switching noise and stabilize the current loop. The input/ output current limit is set by the ILIM pin for 50mV, 100mV or 140mV with $\mathsf { I } _ { \mathsf { L } } | \mathsf { M } | ^ { \mathsf { p } }$ ulled to the GND, floating, or tied to ${ \| \mathsf { N P } _ { \mathsf { C C } } }$ , respectively. If input/output current limit is not desired, the IOSENSE+ and IOSENSE– pins should be shorted to either ${ \mathsf { V } } _ { 0 \mathsf { U T } } \circ { \mathsf { r } } \ V _ { | \mathsf { N } }$ .

![](../assets/ltc3789-datasheet/65f3a2b5e0251b7ade47471c543914dc2f790b3f55a05ff64f760b1069014a33.jpg)  
Figure 7. Programming Output Current Limit

![](../assets/ltc3789-datasheet/cae03b6dec42a8ba1da6fb3aedaf0113a476ff3a2f796b7eb0e95f109c65b9f3.jpg)  
Figure 8. Programming Input Current Limit

# APPLICA TIONS IN FOR MATION

With the typical 100Ω resistors shown here, the value of capacitor $\complement _ { \ F }$ should be 1µF to 2.2µF. The current loop’s transfer function should approximate that of the voltage loop. Crossover frequency should be one-tenth the switching frequency, and gain should decrease by 20dB/decade. Similar current and voltage loop transfer functions will ensure overall system stability.

When the IOSENSE common mode voltage is above ${ \sim } 3 . 2 \lor$ the IOSENSE– pin sources 10µA. The IOSENSE+ pin, however, sources 18.3µA, $2 6 . 6 \mu \mathsf { A }$ and $3 5 \mu \ A$ when the ILIM pin is low, floating, and high, respectively, and when a constant current is being regulated. The error introduced by this mismatch can be offset to a first order by scaling the IOSENSE+ and IOSENSE– resistors accordingly. For example, if the IOSENSE+ branch has a 100Ω resistor, the $1 . 8 3 \mathsf { m V }$ across it can be replicated in the IOSENSE– branch by using a 182Ω resistor.

When the IOSENSE common mode voltage falls below ${ \sim } 3 . 2 \lor$ by a diode drop, the IOSENSE current decreases linearly; it reaches approximately $- 3 0 0 \mu \mathrm { A }$ at zero volts. The values of the diode drop and maximum current sinking can vary by $20 \%$ to $30 \%$ due to process variation. Ensure that IOSENSE common mode voltage never exceeds its absolute maximum of $0 . 3 \mathsfit { V }$ below ground. Pay special attention to short-circuit conditions in high power applications.

# Slope Compensation

Slope compensation provides stability in constantfrequency architectures by preventing subharmonic oscillations at high duty cycles in boost operation and at low duty cycles in buck operation. This is accomplished internally by adding a compensating ramp to the inductor current signal at duty cycles in excess of $40 \%$ in the boost region, or subtracting a ramp from the inductor current signal at lower than $40 \%$ duty cycles in the buck region. Normally, this results in a reduction of maximum inductor peak current for duty cycles ${ > } 4 0 \%$ in the boost region, or an increase of maximum inductor current for duty cycles ${ < } 4 0 \%$ in the buck region. However, the LTC3789 uses a scheme that counteracts this compensating ramp, which allows the maximum inductor current to remain unaffected throughout all duty cycles.

# Phase-Locked Loop and Frequency Synchronization

The LTC3789 has a phase-locked loop (PLL) comprised of an internal voltage-controlled oscillator (VCO) and a phase detector. This allows the turn-on of the top MOSFET of the controller to be locked to the rising edge of an external clock signal applied to the MODE/PLLIN pin. The phase detector is an edge sensitive digital type that provides zero degrees phase shift between the external and internal oscillators. This type of phase detector does not exhibit false locking to harmonics of the external clock.

The output of the phase detector is a pair of complementary current sources that charge or discharge the internal filter network. There is a precision $1 0 \mu \ A$ of current flowing out of the FREQ pin. This allows a single resistor to SGND to set the switching frequency when no external clock is applied to the MODE/PLLIN pin. The internal switch between FREQ and the integrated PLL filter network is on, allowing the filter network to be at the same voltage on the FREQ pin. Operating frequency is shown in Figure 9 and specified in the Electrical Characteristics table. If an external clock is detected on the MODE/PLLIN pin, the internal switch previously mentioned will turn off and isolate the influence of the FREQ pin. Note that the LTC3789 can only be synchronized to an external

![](../assets/ltc3789-datasheet/ca70b84f682c8801d150da45efb32794afa75c16ac4c747e1d5e8fc957910f09.jpg)  
Figure 9. Relationship Between Oscillator Frequency and Voltage at the FREQ Pin

# APPLICA TIONS IN FOR MATION

clock whose frequency is within range of the LTC3789’s internal VCO. This is guaranteed to be between 200kHz and 600kHz. A simplified block diagram is shown in Figure 10.

![](../assets/ltc3789-datasheet/bd0ae907dd04f630a004b9439256192ff37531802b3dc428333c84252db4b526.jpg)  
Figure 10. Phase-Locked Loop Block Diagram

If the external clock frequency is greater than the internal oscillator’s frequency, fOSC, then current is sourced continuously from the phase detector output, pulling up the filter network. When the external clock frequency is less than fOSC, current is sunk continuously, pulling down the filter network. If the external and internal frequencies are the same but exhibit a phase difference, the current sources turn on for the amount of time corresponding to the phase difference. The voltage on the filter network is adjusted until the phase and frequency of the internal and external oscillators are identical. At the stable operating point, the phase detector output is high impedance and the filter capacitor holds the voltage.

Typically, the external clock (on the MODE/PLLIN pin) input high threshold is $1 . 6 \mathsf { V }$ , while the input low threshold is 1V.

# Inductor Selection

The operating frequency and inductor selection are interrelated in that higher operating frequencies allow the use of smaller inductor and capacitor values. The inductor value has a direct effect on ripple current. The inductor current ripple $\Delta \mathfrak { l }$ is typically set to $20 \%$ to $40 \%$ of the maximum inductor current in the boost region at $\mathsf { V } _ { \mathsf { I N ( M I N ) } }$ .

For a given ripple the inductance terms in continuous mode are as follows:

$$
\begin{array} { r l } & { \mathsf { L } _ { \mathsf { B O O S T } } > \frac { \mathsf { V } _ { \mathsf { I N } ( \mathsf { M } \mathsf { I N } ) } ) ^ { 2 } \bullet ( \mathsf { V } _ { \mathsf { O U T } } - \mathsf { V } _ { \mathsf { I N } ( \mathsf { M } \mathsf { I N } ) } ) \bullet \mathsf { I } 0 0 } { \mathsf { f } \bullet \mathsf { I } _ { \mathsf { O U T } ( \mathsf { M A X } ) } \bullet \mathsf { o } _ { \mathsf { \Omega } } \mathsf { R i p p l e } \bullet \mathsf { V } _ { \mathsf { O U T } } \mathrm {  { \mathrm { ~ \Omega } } } ^ { 2 } } \mathsf { H } , } \\ & { \mathsf { L } _ { \mathsf { B U C K } } > \frac { \mathsf { V } _ { \mathsf { O U T } } \bullet \left( \mathsf { V } _ { \mathsf { I N } ( \mathsf { M A X } ) } - \mathsf { V } _ { \mathsf { O U T } } \right) \bullet \mathsf { I } 0 0 } { \mathsf { f } \bullet \mathsf { I } _ { \mathsf { O U T } ( \mathsf { M A X } ) } \bullet \mathsf { o } _ { \mathsf { \Omega } } \mathsf { R i p p l e } \bullet \mathsf { V } _ { \mathsf { I N } ( \mathsf { M A X } ) } } \mathsf { H } } \end{array}
$$

where:

f is operating frequency, Hz   
$\%$ Ripple is allowable inductor current ripple   
$\mathsf { V } _ { \mathsf { I N ( M I N ) } }$ is minimum input voltage, V   
$\mathsf { V } _ { \mathsf { I N } ( \mathsf { M A X } ) }$ is maximum input voltage, V   
VOUT is output voltage, V   
IOUT(MAX) is maximum output load current, A

For high efficiency, choose an inductor with low core loss, such as ferrite. Also, the inductor should have low DC resistance to reduce the I2R losses, and must be able to handle the peak inductor current without saturating. To minimize radiated noise, use a toroid, pot core or shielded bobbin inductor.

# $\complement _ { \parallel N }$ and COUT Selection

In the boost region, input current is continuous. In the buck region, input current is discontinuous. In the buck region, the selection of input capacitor $\complement _ { \mathsf { I N } }$ is driven by the need to filter the input square wave current. Use a low ESR capacitor sized to handle the maximum RMS current. For buck operation, the input RMS current is given by:

$$
| _ { \mathsf { R M S } } \approx | _ { 0 \mathsf { U T } ( \mathsf { M A X } ) } \bullet \frac { \mathsf { V } _ { 0 \mathsf { U T } } } { \mathsf { V } _ { \mathsf { I N } } } \bullet \sqrt { \frac { \mathsf { V } _ { \mathsf { I N } } } { \mathsf { V } _ { 0 \mathsf { U T } } } - 1 }
$$

This formula has a maximum at $\mathsf { V } _ { | \mathsf { N } } = 2 \mathsf { V } _ { 0 \mathsf { U T } }$ , where $\mathsf { I } _ { \mathsf { R M S } } = \mathsf { I } _ { 0 \mathsf { U T } ( \mathsf { M A X } ) } / 2$ . This simple worst-case condition is commonly used for design because even significant deviations do not offer much relief. Note that ripple current ratings from capacitor manufacturers are often based on only 2000 hours of life which makes it advisable to derate the capacitor.

# APPLICA TIONS IN FOR MATION

In the boost region, the discontinuous current shifts from the input to the output, so COUT must be capable of reducing the output voltage ripple. The effects of ESR (equivalent series resistance) and the bulk capacitance must be considered when choosing the right capacitor for a given output ripple voltage. The steady ripple due to charging and discharging the bulk capacitance is given by:

$$
\mathsf { R i p p l e } \left( \mathsf { B o o s t , C a p } \right) = \frac { \mathsf { I _ { 0 \cup T ( M A X ) } \bullet \left( \mathsf { V _ { 0 \cup T } - V _ { \mathsf { I N ( M I N ) } }  } } { \ma\right)thsf { C _ { 0 \cup T } \bullet V _ { 0 \cup T } \bullet f } } \mathsf { V } } { \mathsf { C _ { 0 \cup T } } \bullet \mathsf { V _ { 0 \cup T } } \bullet \mathsf { I } }
$$

where $\complement _ { 0 \cup \intercal }$ is the output filter capacitor.

The steady ripple due to the voltage drop across the ESR is given by:

$$
\Delta \mathsf { V } _ { \mathsf { B 0 0 S 7 , E S R } } = \mathsf { I } _ { \mathsf { O U T } ( \mathsf { M A X , B 0 0 S 7 } ) } \bullet \mathsf { E S R }
$$

In buck mode, $\mathsf { V } _ { 0 \mathsf { U } \mathsf { T } }$ ripple is given by:

$$
\Delta V _ { 0 \mathsf { U T } } \leq \Delta | _ { \mathsf { L } } \bullet ( \mathsf { E S R } + 1 / ( 8 \bullet \mathsf { f } \bullet \mathsf { C } _ { 0 \mathsf { U T } } )
$$

Multiple capacitors placed in parallel may be needed to meet the ESR and RMS current handling requirements. Dry tantalum, special polymer, aluminum electrolytic and ceramic capacitors are all available in surface mount packages. Ceramic capacitors have excellent low ESR characteristics but can have a high voltage coefficient. Capacitors are now available with low ESR and high ripple current ratings, such as OS-CON and POSCAP.

# Power MOSFET Selection and Efficiency Considerations

TheLTC3789requiresfourexternal N-channelpowerMOSFETs, two for the top switches (switches A and D, shown in Figure 1) and two for the bottom switches (switches B and C, shown in Figure 1). Important parameters for the power MOSFETs are the breakdown voltage VBR,DSS, threshold voltage $V _ { G S , T H }$ , on-resistance RDS(ON), reverse transfer capacitance CRSS and maximum current IDS(MAX).

The drive voltage is set by the 5.5V INTVCC supply. Consequently, logic-level threshold MOSFETs must be used in LTC3789 applications.

In order to select the power MOSFETs, the power dissipated by the device must be known. For switch A, the maximum power dissipation happens in the boost region, when it remains on all the time. Its maximum power dissipation at maximum output current is given by:

$$
\mathsf { P } _ { \mathsf { A , B O O S T } } = \left( \frac { \mathsf { V } _ { \mathsf { O U T } } } { \mathsf { V } _ { \mathsf { I N } } } \bullet \mathsf { I } _ { \mathsf { O U T } ( \mathsf { M A X } ) } \right) ^ { 2 } \bullet \mathsf { \rho } _ { \tau } \bullet \mathsf { R } _ { \mathsf { D S ( O N ) } }
$$

where $\rho _ { \tau }$ is a normalization factor (unity at $2 5 ^ { \circ } \mathrm { C }$ ) accounting for the significant variation in on-resistance with temperature, typically about $0 . 4 \% / ^ { \circ } \complement$ , as shown in Figure 11. For a maximum junction temperature of $1 2 5 \%$ , using a value $\rho _ { \tau } = 1 . 5$ is reasonable.

![](../assets/ltc3789-datasheet/90cf75b346e0fa780ea4f3cdc51967fa298b10a358301b69be904a7347fd6827.jpg)  
Figure 11. Normalized RDS(ON) vs Temperature

Switch B operates in the buck region as the synchronous rectifier. Its power dissipation at maximum output current is given by:

$$
\mathsf { P } _ { \mathsf { B , B U C K } } = \frac { \mathsf { V } _ { \mathsf { I N } } - \mathsf { V } _ { \mathsf { O U T } } } { \mathsf { V } _ { \mathsf { I N } } } \bullet \mathsf { I 0 U T } ( \mathsf { M A X } ) ^ { 2 } \bullet \mathsf { p } _ { \tau } \bullet \mathsf { R } _ { \mathsf { D S } ( \mathsf { T } }
$$

Switch C operates in the boost region as the control switch. Its power dissipation at maximum current is given by:

$$
\mathsf { P } _ { \mathtt { C } , \mathtt { B } 0 0 \mathtt { S } \mathtt { T } } = \frac { \left( \mathsf { V } _ { 0 \sqcup \mathtt { T } } - \mathsf { V } _ { 1 \mathtt { N } } \right) \mathsf { V } _ { 0 \sqcup \mathtt { T } } } { { \mathsf { V } _ { 1 \mathtt { N } } } ^ { 2 } } \bullet \mathsf { I } _ { 0 \sqcup \mathtt { T } ( \mathsf { M } \mathtt { A } \mathtt { X } ) } ^ { 2 } \bullet \mathsf { p } _ { \mathtt {tau } }
$$

$$
\bullet \mathsf { R } _ { \mathsf { D S } ( 0 \mathsf { N } ) } + \mathsf { k } \bullet \mathsf { V } _ { 0 \mathsf { U T } } { } ^ { 3 } \bullet \frac { \mathsf { I } _ { 0 \mathsf { U T } ( \mathsf { M A X } ) } } { \mathsf { V } _ { \mathsf { I N } } } \bullet \mathsf { C } _ { \mathsf { R S S } } \bullet \mathsf { f }
$$

# APPLICA TIONS IN FOR MATION

where CRSS is usually specified by the MOSFET manufacturers. The constant k, which accounts for the loss caused by reverse recovery current, is inversely proportional to the gate drive current and has an empirical value of 1.7.

For switch D, the maximum power dissipation happens in the boost region, when its duty cycle is higher than $50 \%$ . Its maximum power dissipation at maximum output current is given by:

$$
\mathsf { P } _ { \mathsf { D } , \mathsf { B } 0 0 \mathsf { S } \mathsf { T } } = \frac { \mathsf { V } _ { | \mathsf { N } | } } { \mathsf { V } _ { 0 \mathsf { U } \mathsf { T } } } \bullet \left( \frac { \mathsf { V } _ { 0 \mathsf { U } \mathsf { T } } } { \mathsf { V } _ { | \mathsf { N } | } } \bullet \mathsf { I } _ { 0 \mathsf { U } \mathsf { T } ( \mathsf { M } \mathsf { A } \mathsf { X } ) } \right) ^ { 2 } \bullet \mathsf { p } _ { \tau } \bullet \mathsf { R } _ { \mathsf { D } \mathsf { S } ( \mathsf { T } \hdots \hdots \hdots }
$$

For the same output voltage and current, switch A has the highest power dissipation and switch B has the lowest power dissipation unless a short occurs at the output.

From a known power dissipated in the power MOSFET, its junction temperature can be obtained using the following formula:

$$
\mathsf { T } _ { \mathsf { J } } = \mathsf { T } _ { \mathsf { A } } + \mathsf { P } \bullet \mathsf { R } _ { \mathsf { T } \mathsf { H } ( \mathsf { J } \mathsf { A } ) }
$$

The $\mathsf { R } _ { \mathsf { T H } ( \mathsf { J A } ) }$ to be used in the equation normally includes the $\mathsf { R } _ { \mathsf { T H } ( \mathsf { J C } ) }$ for the device plus the thermal resistance from the case to the ambient temperature $( \mathsf { R } _ { \mathsf { T H } ( \mathsf { J C } ) } )$ . This value of ${ \sf T } _ { \sf \sf \sf { J } }$ can then be compared to the original, assumed value used in the iterative calculation process.

# Schottky Diode (D1, D2) Selection

The Schottky diodes, D1 and D2, shown in Figure 13, conduct during the dead time between the conduction of the power MOSFET switches. They are intended to prevent the body diode of synchronous switches B and D from turning on and storing charge during the dead time. In particular, D2 significantly reduces reverse recovery current between switch D turn-off and switch C turn-on, which improves converter efficiency and reduces switch C voltage stress. In order for the diode to be effective, the inductance between it and the synchronous switch must be as small as possible, mandating that these components be placed adjacently.

# ${ \| \mathsf { N I V } _ { \complement } } _ { }$ Regulators and EXTVCC

The LTC3789 features a true PMOS LDO that supplies power to ${ \| \mathsf { N N } _ { \complement } } _ { \complement }$ from the $\mathsf { V } _ { \mathsf { I N } }$ supply. ${ \| \mathsf { N N } _ { \complement } } _ { \complement }$ powers the gate drivers and much of the LTC3789’s internal circuitry. The linear regulator regulates the voltage at the INTVCC pin to $5 . 5 \mathsf { V }$ when $\mathsf { V } _ { \mathsf { I N } }$ is greater than $6 . 5 \mathsf { V } .$ . $\mathsf { E X N } _ { \mathsf { C C } }$ can supply the needed power when its voltage is higher than $4 . 8 \mathsf { V }$ through another on-chip PMOS LDO. Each of these can supply a peak current of 100mA and must be bypassed to ground with a minimum of 1µF ceramic capacitor or low ESR electrolytic capacitor. No matter what type of bulk capacitor is used, an additional 0.1µF ceramic capacitor placed directly adjacent to the INTVCC and PGND pins is highly recommended. Good bypassing is needed to supply the high transient current required by the MOSFET gate drivers and to prevent interaction between the channels.

High input voltage applications in which large MOSFETs are being driven at high frequencies may cause the maximum junction temperature rating for the LTC3789 to be exceeded. The ${ | \mathsf { N P } \mathrm { \complement } } _ { } \complement \complement$ current, which is dominated by the gate charge current, may be supplied by either the $5 . 5 \mathsf { V }$ linear regulator from $\mathsf { V } _ { \mathsf { I N } }$ or the $5 . 5 \mathsf { V }$ LDO from EXTVCC . When the voltage on the $\mathsf { E X N } _ { \mathsf { C C } }$ pin is less than $4 . 5 \mathsf { V }$ , the linear regulator from $\mathsf { V } _ { \mathsf { I N } }$ is enabled. Power dissipation for the IC in this case is highest and is equal to $\mathsf { V } _ { | \mathsf { N } } \bullet \mathsf { I }$ INTVCC. The gate charge current is dependent on operating frequency, as discussed in the Efficiency Considerations section. The junction temperature can be estimated by using the equations given in Note 3 of the Electrical Characteristics. For example, the LTC3789 INTVCC current is limited to less than 24mA from a 24V supply in the SSOP package and not using the EXTVCC supply:

$$
T _ { \mathrm { J } } = 7 0 ^ { \circ } \mathsf { C } + ( 2 8 \mathsf { m A } ) ( 2 4 \mathsf { V } ) ( 8 0 ^ { \circ } \mathsf { C } / \mathsf { W } ) = 1 2 5 ^ { \circ } \mathsf { C }
$$

To prevent the maximum junction temperature from being exceeded, the input supply current must be checked while operating in continuous conduction mode (MODE/PLLIN $= { \tt S G N D } )$ at maximum $\mathsf { V } _ { \mathsf { I N } }$ . When the voltage applied to $\mathsf { E X N } _ { \mathsf { C C } }$ rises above $4 . 8 \lor$ , the ${ \| \mathsf { N T V } _ { \complement } } _ { }$ linear regulator from $\mathsf { V } _ { \mathsf { I N } }$ is turned off and the linear regulator from $\mathsf { E X N } _ { \mathsf { C C } }$ is turned on and remains on as long as the voltage applied to EXTVCC remains above $4 . 5 \mathsf { V }$ . Using EXTVCC allows the MOSFET driver and control power to be derived from the LTC3789’s switching regulator output during normal operation and from the $\mathsf { V } _ { \mathsf { I N } }$ when the output is out of regulation (e.g., start-up, short-circuit). Do not apply more than 14V to $\mathsf { E X N } _ { \mathsf { C C } }$ .

# APPLICA TIONS IN FOR MATION

Significant efficiency and thermal gains can be realized by powering $\mathsf { E X N } _ { \mathsf { C C } }$ from the output, since the $\mathsf { V } _ { \mathsf { I N } }$ current resulting from the driver and control currents will be scaled by a factor of (Duty Cycle)/(Switcher Efficiency).

Tying the $\mathsf { E X N } _ { \mathsf { C C } }$ pin to a $1 2 \vee$ output reduces the junction temperature in the previous example from $1 2 5 ^ { \circ } 0$ to $9 7 \%$ :

$$
\mathsf { T } _ { \mathsf { J } } = 7 0 ^ { \circ } \mathsf { C } + ( 2 8 \mathsf { m } \mathsf { A } ) ( 1 2 \mathsf { V } ) ( 8 0 ^ { \circ } \mathsf { C } / \mathsf { W } ) = 9 7 ^ { \circ } \mathsf { C }
$$

Powering $\mathsf { E X N } _ { \mathsf { C C } }$ from the output can also provide enough gate drive when $\mathsf { V } _ { \mathsf { I N } }$ drops below $5 \vee$ . This allows a wider operating range for $\mathsf { V } _ { \mathsf { I N } }$ after the controller start into regulation.

The following list summarizes the three possible connections for $\mathsf { E X N } _ { \mathsf { C C } }$ :

1. $\mathsf { E X N } _ { \mathsf { C C } }$ left open (or grounded). This will cause ${ \| \mathsf { N P } _ { \complement } } _ { }$ to be powered from the internal $5 . 5 \mathsf { V }$ regulator at the cost of a small efficiency penalty.   
2. EXTVCC connected directly to $\mathsf { V } _ { 0 \mathsf { U T } } ( 4 . 7 \mathsf { V } < \mathsf { V } _ { 0 \mathsf { U T } } < 1 4 \mathsf { V } )$ . This is the normal connection for the $5 . 5 \mathsf { V }$ regulator and provides the highest efficiency.   
3. EXTVCC connected to an external supply. If an external supply is available in the $4 . 7 \lor$ to 14V range, it may be used to power EXTVCC provided it is compatible with the MOSFET gate drive requirements.

Note that there is an internal body diode from ${ \| \mathsf { N N } _ { \complement } } _ { \complement }$ to $\mathsf { V } _ { \mathsf { I N } }$ . When ${ \| \mathsf { N N } _ { \complement } } _ { \complement }$ is powered from $\mathsf { E X N } _ { \mathsf { C C } }$ and $\mathsf { V } _ { \mathsf { I N } }$ drops lower than $4 . 5 \mathsf { V }$ , the diode will create a back-feeding path from EXTVCC to $\mathsf { V } _ { \mathsf { I N } }$ . To limit this back-feeding current, a $1 0 \Omega \sim 1 5 \Omega$ resistor is recommended between the system $\mathsf { V } _ { \mathsf { I N } }$ voltage and the chip $\mathsf { V } _ { \mathsf { I N } }$ pin. To truly eliminate this back-feeding current, a blocking Schottky diode should be connected between the system $\mathsf { V } _ { \mathsf { I N } }$ and the chip $\mathsf { V } _ { \mathsf { I N } }$ .

# Output Voltage

The LTC3789 output voltage is set by an external feedback resistive divider carefully placed across the output capacitor. The resultant feedback signal is compared with

the internal precision $0 . 8 \mathsf { V }$ voltage reference by the error amplifier. The output voltage is given by the equation:

$$
\ifmmode \mathsf { V } _ { 0 \sqcup \intercal } = 0 . 8 \lor \bullet \left( 1 + \frac { \mathsf { R } 2 } { \mathsf { R } 1 } \right)
$$

where R1 and R2 are defined in Figure 13.

# Topside MOSFET Driver Supply $( \mathbb { C } _ { \mathsf { A } } , \mathbb { D } _ { \mathsf { A } } , \mathbb { C } _ { \mathsf { B } } , \mathbb { D } _ { \mathsf { B } } )$

Referring to Figure 13, the external bootstrap capacitors $\complement _ { \mathsf { A } }$ and $\complement _ { \mathsf { B } }$ connected to the BOOST1 and BOOST2 pins supply the gate drive voltage for the topside MOSFET switches A and D. When the top switch A turns on, the switch node SW1 rises to $\mathsf { V } _ { \mathsf { I N } }$ and the BOOST1 pin rises to approximately $\mathsf { V } _ { | \mathsf { N } } + \mathsf { I N } \mathsf { T } \mathsf { C } \mathsf { C }$ . When the bottom switch B turns on, the switch node SW1 drops to low and the boost capacitor $\complement _ { \mathsf { A } }$ is charged through $\mathsf { D } _ { \mathsf { A } }$ from ${ \| \mathsf { N P } _ { \complement } } _ { }$ . When the top switch D turns on, the switch node SW2 rises to $\mathsf { V } _ { 0 \mathsf { U } \mathsf { T } }$ and the BOOST2 pin rises to approximately $\mathsf { V } _ { 0 \mathsf { U T } } + \mathsf { I N T } _ { \mathsf { C C } }$ . When the bottom switch C turns on, the switch node SW2 drops to low and the boost capacitor $\complement _ { \mathsf { B } }$ is charged through $\mathsf { D } _ { \mathsf { A } }$ from INTVCC. The boost capacitors $\complement _ { \mathsf { A } }$ and $\complement _ { \mathsf { B } }$ need to store about 100 times the gate charge required by the top switches A and D. In most applications, a 0.1µF to 0.47µF, X5R or X7R dielectric capacitor is adequate.

# Undervoltage Lockout

The LTC3789 has two functions that help protect the controller in case of undervoltage conditions. A precision UVLO comparator constantly monitors the INTVCC voltage to ensure that an adequate gate-drive voltage is present. It locks out the switching action when ${ | \mathsf { N T V } _ { \complement } } { \sf C }$ is below 3.4V. To prevent oscillation when there is a disturbance on the ${ \sf N N } _ { \sf C C }$ , the UVLO comparator has 400mV of precision hysteresis.

Another way to detect an undervoltage condition is to monitor the $\mathsf { V } _ { \mathsf { I N } }$ supply. Because the RUN pin has a precision turn-on reference of $1 . 2 2 \vee$ , one can use a resistor divider to $\mathsf { V } _ { \mathsf { I N } }$ to turn on the IC when $\mathsf { V } _ { \mathsf { I N } }$ is high enough. An extra $5 \mu \mathsf { A }$ of current flows out of the RUN pin once its voltage passes 1.22V. One can program the hysteresis of the run comparator by adjusting the values of the resistive divider.

# APPLICA TIONS IN FOR MATION

# Soft-Start Function

When a capacitor is connected to the SS pin, a soft-start current of 3µA starts to charge the capacitor. A soft-start function is achieved by controlling the output ramp voltage according to the ramp rate on the SS pin. Current foldback is disabled during this phase to ensure smooth soft-start. When the chip is in the shutdown state with its RUN pin voltage below $1 . 2 2 \lor$ , the SS pin is actively pulled to ground. The soft-start range is defined to be the voltage range from 0V to $0 . 8 \mathsf { V }$ on the SS pin. The total soft-start time can be calculated as:

$$
\mathfrak { t } _ { \mathtt { S } 0 \mathsf { F } \mathsf { T } \mathbb { S } \mathsf { T } A \mathsf { R } \mathsf { T } } = 0 . 8 \bullet \frac { \mathbb { C } _ { \mathbb { S } \mathbb { S } } } { 3 \mu \mathbb { A } }
$$

Regardless of the mode selected by the MODE/PLLIN pin, the regulator will always start in pulse-skipping mode up to $\mathsf { S S } = 0 . 8 \mathsf { V }$ .

# Fault Conditions: Current Limit and Current Foldback

The maximum inductor current is inherently limited in a current mode controller by the maximum sense voltage. In the boost region, maximum sense voltage and the sense resistance determine the maximum allowed inductor peak current, which is:

$$
\mathsf { I } _ { \mathsf { L } ( \mathsf { M A X , B O O S T } ) } = \frac { 1 4 0 \mathsf { m V } } { \mathsf { R } _ { \mathsf { S E N S E } } }
$$

In the buck region, maximum sense voltage and the sense resistance determine the maximum allowed inductor valley current, which is:

$$
1 _ { \mathsf { L } ( \mathsf { M A X , B U C K } ) } = { \frac { 9 0 { \mathsf { m V } } } { \mathsf { R } _ { \mathsf { S E N S E } } } }
$$

To further limit current in the event of a short circuit to ground, the LTC3789 includes foldback current limiting. If the output falls by more than $50 \%$ , then the maximum sense voltage is progressively lowered to about one-third of its full value.

# Efficiency Considerations

The percent efficiency of a switching regulator is equal to the output power divided by the input power times $100 \%$ . It is often useful to analyze individual losses to determine what is limiting the efficiency and which change would produce the most improvement. Although all dissipative elements in circuit produce losses, four main sources account for most of the losses in LTC3789 circuits:

1. DC I2R losses. These arise from the resistances of the MOSFETs, sensingresistor, inductorandPCboardtraces and cause the efficiency to drop at high output currents.

2. MOSFET Transition loss. This loss arises from the brief amount of time switch A or switch C spends in the saturated region during switch node transitions. It depends upon the input voltage, load current, driver strengthandMOSFETcapacitance, amongotherfactors.

3. INTVCC current. This is the sum of the MOSFET driver and control currents. This loss can be reduced by supplying ${ \| \mathsf { N N } _ { \complement } } _ { \complement }$ current through the $\mathsf { E X N } _ { \mathsf { C C } }$ pin from a high efficiency source, such as the output (if $4 . 7 \lor <$ $\mathsf { V } _ { 0 \mathsf { U T } } < 1 4 \mathsf { V } )$ or alternate supply if available.

4. $\complement _ { \mathsf { I N } }$ and COUT loss. The input capacitor has the difficult job of filtering the large RMS input current to the regulator in buck mode. The output capacitor has the more difficult job of filtering the large RMS output current in boost mode. Both $\complement _ { \mathsf { I N } }$ and $\complement _ { 0 \lor \ J }$ are required to have low ESR to minimize the AC I2R loss and sufficient capacitance to prevent the RMS current from causing additional upstream losses in fuses or batteries.

5. Other losses. Schottky diodes D1 and D2 are responsible for conduction losses during dead time and light load conduction periods. Inductor core loss should also be considered. Switch C causes reverse recovery current loss in boost mode.

When making adjustments to improve efficiency, the input current is the best indicator of changes in efficiency. If one makes a change and the input current decreases, then the efficiency has increased. If there is no change in input current, then there is no change in efficiency.

# APPLICA TIONS IN FOR MATION

# Design Example

$V _ { \vert \mathrm { N } } = 5 V$ to 18V $\mathsf { V } _ { 0 \mathsf { U T } } = 1 2 \mathsf { V }$ $\mathsf { I } _ { 0 \mathsf { U T } ( \mathsf { M A X } ) } = 5 \mathsf { A }$ $\mathsf { f } = 4 0 0 \mathsf { k H z }$

Maximum ambient temperature $= 6 0 ^ { \circ } 0$

Set the frequency at 400kHz by applying 1.2V on the FREQ pin (see Figure 7). The $1 0 \mu \ A$ current flowing out of the FREQ pin will give 1.2V across a 120k resistor to GND. The inductance value is chosen first based on a $30 \%$ ripple current assumption. In the buck region, the ripple current is:

$$
\Delta \mathsf { I } _ { \mathsf { L , B U C K } } = \frac { \mathsf { V _ { 0 } u } _ { \mathsf { T } } } { \mathsf { f } \bullet \mathsf { L } } \bullet \left( 1 - \frac { \mathsf { V _ { 0 } u } _ { \mathsf { T } } } { \mathsf { V _ { | \mathsf { N } } } } \right)
$$

$$
| _ { \mathsf { R I P P L E , B U C K } } \ = \ { \frac { \Delta | _ { _ { \mathsf { L , B U C K } } } \bullet 1 0 0 } { | _ { _ { 0 \sqcup \mathsf { T } } } } } \%
$$

The highest value of ripple current occurs at the maximum input voltage. In the boost region, the ripple current is:

$$
 \Delta \mathsf { I } _ { \mathsf { L , B O O S T } } = \frac { \mathsf { V } _ { \mathsf { I N } } } { \mathsf { f } \bullet \mathsf { L } } \bullet ( 1 - \frac { \mathsf { V } _ { \mathsf { I N } } } { \mathsf { V } _ { \mathsf { O U T } } } )
$$

$$
| _ { \mathsf { R I P P L E , B O O S T } } = \frac { \Delta | _ { \mathsf { L , B O O S T } } \bullet 1 0 0 } { | _ { \mathsf { I N } } } \%
$$

The highest value of ripple current occurs at $\mathsf { V } _ { \mathsf { I N } } = \mathsf { V } _ { 0 \mathsf { U T } } / 2$ .

A 6.8µH inductorwillproduce $1 1 \%$ rippleintheboostregion $( V _ { \vert \mathsf { N } } = 6 V )$ and $2 9 \%$ ripple in the buck region $( \mathsf { V } _ { | \mathsf { N } } = 1 8 \mathsf { V } )$ .

The RSENSE resistor value can be calculated by using the maximum current sense voltage specification with some accommodation for tolerances.

$$
R _ { \mathtt { S E M S E } } = \frac { 2 \bullet 1 4 0 \mathsf { m V } \bullet \mathsf { V } _ { \mathsf { I N } ( \mathsf { M I N } ) } } { 2 \bullet | _ { \mathsf { O U T } ( \mathsf { M A X } , \mathsf { B O O S T } ) } \bullet \mathsf { V } _ { \mathsf { O U T } } + \Delta | _ { \mathsf { L , B O O S T } } \bullet \mathsf { V } _ { \mathsf { I N } ( \mathsf { M I N } ) } }
$$

Select an RSENSE of 10mΩ.

Output voltage is 12V. Select R1 as 20k. R2 is:

$$
{ \mathsf { R } } 2 = { \frac { \mathsf { V } _ { 0 \sqcup \top } \bullet { \mathsf { R } } 1 } { 0 . 8 } } - { \mathsf { R } } 1
$$

Select R2 as 280k. Both R1 and R2 should have a tolerance of no more than $1 \%$ .

# Selecting MOSFET Switches

The MOSFETs are selected based on voltage rating and RDS(ON) value. It is important to ensure that the part is specified for operation with the available gate voltage amplitude. In this case, the amplitude is $5 . 5 \mathsf { V }$ and MOSFETs with an RDS(ON) value specified at $V _ { \sf G S } = 4 . 5 V$ can be used.

Select QA and QB.With $1 8 \mathsf { V }$ maximum input voltage MOSFETs with a rating of at least $3 0 \vee$ are used. As we do not yet knowtheactualthermalresistance (circuitboarddesignand airflow have a major impact) we assume that the MOSFET thermal resistance from junction to ambient is $5 0 ^ { \circ } \complement / W$ .

If we design for a maximum junction temperature, $\mathsf { T } _ { \mathsf { J } ( \mathsf { M A X } ) }$ $= 1 2 5 \%$ , the maximum RDS(ON) value can be calculated. First, calculate the maximum power dissipation:

$$
\begin{array} { l l } { \mathsf { P } _ { \mathsf { D } ( \mathsf { M A X } ) } = \left( \frac { \mathsf { T } _ { \mathsf { J } ( \mathsf { M A X } ) } - \mathsf { T } _ { \mathsf { A } ( \mathsf { M A X } ) } } { \mathsf { R } _ { ( \mathsf { j } - \mathsf { a } ) } } \right) } \\ { \mathsf { P } _ { \mathsf { D } ( \mathsf { M A X } ) } = \frac { ( 1 2 5 - 6 0 ) } { 5 0 } = 1 . 3 \mathsf { W } } \end{array}
$$

The maximum dissipation in QA occurs at minimum input voltage when the circuit operates in the boost region and QA is on continuously. The input current is then:

$$
\frac { \mathsf { V } _ { 0 \cup \mathsf { T } } \bullet \mathsf { I } _ { 0 \cup \mathsf { T } ( \mathsf { M A X } ) } } { \mathsf { V } _ { 1 \mathsf { N } ( \mathsf { M I N } ) } } , ~ 0 \mathsf { R } ~ 1 2 \mathsf { A }
$$

We calculate a maximum value for RDS(ON):

$$
\mathsf { R } _ { \mathsf { D S } ( 0 \mathsf { N } ) } \left( 1 2 5 ^ { \circ } \mathsf { C } \right) < \frac { \mathsf { P } _ { \mathsf { D } ( \mathsf { M A X } ) } } { \mathsf { I } _ { \mathsf { N } ( \mathsf { M A X } ) } { } ^ { 2 } }
$$

$$
{ \sf R } _ { \sf D S ( O N ) } \left( 1 2 5 ^ { \circ } { \sf C } \right) < \frac { 1 . 3 { \sf W } } { \left( 1 2 { \sf A } \right) ^ { 2 } } = 0 . 0 0 9 \Omega
$$

# APPLICA TIONS IN FOR MATION

The Vishay SiR422DP has a typical RDS(ON) of 0.010Ω at ${ \bar { \mathsf { I } } } _ { \mathsf { J } } = 1 2 5 ^ { \circ } { \mathsf { C } }$ and $\mathsf { V } _ { \mathsf { G S } } = 4 . 5 \mathsf { V }$ .

The maximum dissipation in QB occurs at maximum input voltage when the circuit is operating in the buck region. The dissipation is:

$$
\mathsf { P } _ { \mathsf { B , B U C K } } = \frac { \mathsf { V } _ { \mathsf { I N } } - \mathsf { V } _ { \mathsf { O U T } } } { \mathsf { V } _ { \mathsf { I N } } } \bullet \mathsf { I } _ { \mathsf { O U T } ( \mathsf { M A X } ) } { } ^ { 2 } \bullet \mathsf { p } _ { \tau } \bullet \mathsf { R } _ { \mathsf { D S } ( \mathsf { O N } ) }
$$

$$
\mathsf { R } _ { \mathsf { D S } ( 0 \mathbb { N } ) } ( 1 2 5 ^ { \circ } \mathsf { C } ) < \frac { 1 . 3 \mathsf { W } } { \frac { 1 8 \lor \mathsf { T } 0 \mathrm { ~ } - 1 2 \lor } { 1 8 \lor } \bullet ( 5 \mathsf { A } ) ^ { 2 } } = 0 . 1 5 6 \Omega
$$

This seems to indicate that a quite small MOSFET can be used for QB if we only look at power loss. However, with 5A current the voltage drop across 0.156Ω is 0.78V, which means the MOSFET body diode is conducting. To avoid body diode current flow we should keep the maximum voltage drop well below $0 . 5 \mathsf { V }$ , using, for example, Vishay Si4840BDY in the SO-8 package $( \mathsf { R } _ { \mathsf { D S O N } ( \mathsf { M A X } ) } = 0 . 0 1 2 \Omega )$

Select QC and QD.With 12V output voltage we need MOSFETs with $2 0 \vee$ or higher rating.

The highest dissipation occurs at minimum input voltage when the inductor current is highest. For switch QC the dissipation is:

$$
\begin{array} { r l } & { \mathsf { P } _ { \mathsf { G } , \mathsf { B O O S T } } = \frac { \left( \mathsf { V } _ { \mathsf { O U T } } - \mathsf { V } _ { \mathsf { I N } } \right) \mathsf { V } _ { \mathsf { O U T } } } { \mathsf { V } _ { \mathsf { I N } } } } \\ & { \bullet \mathsf { I } _ { 0 \sqcup \mathsf { T } ( \mathbb { M A X } ) } 2 \bullet \mathsf { \rho } _ { \mathsf { o } } \bullet \mathsf { R } _ { 0 \mathsf { S } ( 0 \mathbb { N } ) } } \\ & { + \textup { k } \bullet \mathsf { V } _ { 0 \sqcup \mathsf { T } } ^ { 3 } \bullet \frac { \mathsf { I } _ { 0 \sqcup \mathsf { T } ( \mathbb { M A X } ) } } { \mathsf { V } _ { \mathsf { I N } } } \bullet \mathsf { C } _ { \mathsf { R S S } } \bullet \mathsf { \rho } _ { \mathsf { f } } } \end{array}
$$

where CRSS is usually specified by the MOSFET manufacturers. The constant k, which accounts for the loss caused by reverse recovery current, is inversely proportional to the gate drive current and has an empirical value of 1.7.

The dissipation in switch QD is:

$$
\begin{array} { r } { \mathsf { P } _ { \mathsf { D , B O O S T } } = \frac { \mathsf { V } _ { \mathsf { I N } } } { \mathsf { V } _ { \mathsf { O U T } } } \bullet \left( \frac { \mathsf { V } _ { \mathsf { O U T } } } { \mathsf { V } _ { \mathsf { I N } } } \bullet \mathsf { I } _ { 0 \mathsf { U T } ( \mathbb { M A X } ) } \right) ^ { 2 } } \\ { \bullet \mathsf { p } _ { \tau } \bullet \mathsf { R } _ { \mathsf { D S ( O N ) } } } \end{array}
$$

Vishay SiR484OY is a possible choice for QC and QD. The calculated power loss at $5 V$ input voltage is then 1.3W for QC and 0.84W for QD.

$\complement _ { \mathsf { I N } }$ is chosen to filter the square current in the buck region. In this mode, the maximum input current peak is:

$$
I _ { | \mathrm { N , P E A K ( M A X , B U C K ) } } = 5 \mathsf { A } \bullet \left( 1 + \frac { 2 9 \% } { 2 } \right) = 5 . 7 \mathsf { A }
$$

A low ESR (10mΩ) capacitor is selected. Input voltage ripple is $5 7 \mathsf { m } \mathsf { V }$ (assuming ESR dominates the ripple).

COUT is chosen to filter the square current in the boost region. In this mode, the maximum output current peak is:

$$
I _ { 0 \mathsf { U T } , \mathsf { P E A K } ( \mathsf { M A X } , \mathsf { B O O S } \mathsf { T } ) } = \frac { 1 2 } { 5 } \bullet 5 \bullet \left( 1 + \frac { 1 1 \% } { 2 } \right) = 1 0 . 6 \mathsf { A }
$$

A low ESR (5mΩ) capacitor is suggested. This capacitor will limit output voltage ripple to 53mV (assuming ESR dominates the ripple).

# PC Board Layout Checklist

The basic PC board layout requires a dedicated ground plane layer. Also, for high current, a multilayer board provides heat sinking for power components.

• The ground plane layer should not have any traces and should be as close as possible to the layer with power MOSFETs. Place $\complement _ { \mathsf { I N } }$ , switch A, switch B and D1 in one compact area. Place COUT, switch C, switch D and D2 in one compact area. One layout example is shown in Figure 12. Use immediate vias to connect the components (including the LTC3789’s SGND and PGND pins) to the ground plane. Use several large vias for each power component.

# APPLICA TIONS IN FOR MATION

• Use planes for $\mathsf { V } _ { \mathsf { I N } }$ and $\mathsf { V } _ { 0 \mathsf { U } \mathsf { T } }$ to maintain good voltage filtering and to keep power losses low.

• Flood all unused areas on all layers with copper. Flooding with copper will reduce the temperature rise of power components. Connect the copper areas to any DC net $( \mathsf { V } _ { | \mathsf { N } } 0 \mathsf { r } G \mathsf { N } \mathsf { D } )$ . When laying out the printed circuit board, the following checklist should be used to ensure proper operation of the LTC3789. These items are also illustrated in Figure 13.

• Segregate the signal and power grounds. All smallsignal components should return to the SGND pin at one point, which is then tied to the PGND pin close to the inductor current sense resistor RSENSE.

• Place switch B and switch C as close to the controller as possible, keeping the PGND, BG and SW traces short.

• Keep the high dV/dT SW1, SW2, BOOST1, BOOST2, TG1 and TG2 nodes away from sensitive small-signal nodes.

• The path formed by switch A, switch B, D1 and the $\complement _ { \mathsf { I N } }$ capacitor should have short leads and PC trace lengths. The path formed by switch C, switch D, D2 and the COUT capacitor also should have short leads and PC trace lengths.

![](../assets/ltc3789-datasheet/3c3432ed5b18641cdf8385184178f6f5d8615c8c93dca9d21121f5f1f31370ca.jpg)  
Figure 12. Switches Layout

• The output capacitor $\left( - \right)$ terminals should be connected as closely as possible to the $\left( - \right)$ terminals of the input capacitor.

• Connect the top driver boost capacitor $\complement _ { \mathsf { A } }$ closely to the BOOST1 and SW1 pins. Connect the top driver boost capacitor $\complement _ { \mathsf { B } }$ closely to the BOOST2 and SW2 pins.

• Connect the input capacitors $\complement _ { \mathsf { I N } }$ and output capacitors COUT closely to the power MOSFETs. These capacitors carry the MOSFET AC current in the boost and buck region.

• Connect VFB pin resistive dividers to the $\left( + \right)$ terminals of COUT and signal ground. A small $V _ { F B }$ bypass capacitor may be connected closely to the LTC3789 SGND pin. The R2 connection should not be along the high current or noise paths, such as the input capacitors.

• Route SENSE– and SENSE+ leads together with minimum PC trace spacing. Avoid having sense lines pass through noisy areas, such as switch nodes. The filter capacitor between ${ \tt S E N S E } ^ { + }$ and SENSE– should be as close as possible to the IC. Ensure accurate current sensing with Kelvin connections at the sense resistor. One layout example is shown in Figure 14.

• Connect the $\mathsf { I } _ { \mathsf { T } \mathsf { H } }$ pin compensation network closely to the IC, between ${ \mathsf { I } } _ { \mathsf { T } \mathsf { H } } \mathsf { a n d }$ the signal ground pins. The capacitor helps to filter the effects of PCB noise and output voltage ripple voltage from the compensation loop.

• Connect the ${ \| \mathsf { N P } _ { \complement } } _ { }$ bypass capacitor, CVCC, closely to the IC, between the INTVCC and the power ground pins. This capacitor carries the MOSFET drivers’ current peaks. An additional 1µF ceramic capacitor placed immediately next to the INTVCC and PGND pins can help improve noise performance substantially.

# 25

# APPLICA TIONS IN FOR MATION

![](../assets/ltc3789-datasheet/5438a60b0b791d16d3af09eb59a0443cd0d61c260eb9246a4028314ac722ccb7.jpg)  
Figure 13. LTC3789 12V/5A, Buck-Boost Regulator

![](../assets/ltc3789-datasheet/fd0228d809be7e59516db0e59eb798bc37dadd552764ef555016b4acc9e9e089.jpg)  
Figure 14. Sense Lines Layout

# Package Descript ion

Please refer to http://www.linear.com/designtools/packaging/ for the most recent package drawings.

GN Package 28-Lead Plastic SSOP (Narrow .150 Inch) (Reference LTC DWG # 05-08-1641)

![](../assets/ltc3789-datasheet/dcb9b837a7d011417eb8490ae79451a9e2dd8416e48b5de325e0d21fbec3df3c.jpg)

27

# Package Descript ion

Please refer to http://www.linear.com/designtools/packaging/ for the most recent package drawings.

UFD Package 28-Lead Plastic QFN $( 4 \mathsf { m m } \times 5 \mathsf { m m } )$ ) (Reference LTC DWG # 05-08-1712 Rev B)

![](../assets/ltc3789-datasheet/a1821c34b14fbdc53bdd08454882fde960ece89e3cc94fe106ab78c255e2b91d.jpg)

![](../assets/ltc3789-datasheet/8bf31711f519f8b57d73ffb5f6dffe89ae1400de211dcf67fa902c8e868eaa74.jpg)  
RECOMMENDED SOLDER PAD PITCH AND DIMENSIONS

NOTE:   
1. DRAWING PROPOSED TO BE MADE A JEDEC PACKAGE OUTLINE MO-220 VARIATION (WXXX-X).   
2. DRAWING NOT TO SCALE   
3. ALL DIMENSIONS ARE IN MILLIMETERS   
4. DIMENSIONS OF EXPOSED PAD ON BOTTOM OF PACKAGE DO NOT INCLUDE MOLD FLASH. MOLD FLASH, IF PRESENT, SHALL NOT EXCEED 0.15mm ON ANY SIDE   
5. EXPOSED PAD SHALL BE SOLDER PLATED   
6. SHADED AREA IS ONLY A REFERENCE FOR PIN 1 LOCATION ON THE TOP AND BOTTOM OF PACKAGE

# Revision Hist ory

<table><tr><td rowspan=1 colspan=1>REV</td><td rowspan=1 colspan=1>DATE</td><td rowspan=1 colspan=1>DESCRIPTION</td><td rowspan=1 colspan=1>PAGE NUMBER</td></tr><tr><td rowspan=2 colspan=1>A</td><td rowspan=2 colspan=1>9/11</td><td rowspan=2 colspan=1>Updated Features,Description and Typical Application.Updated Electrical Characteristics section.Updated text in MODE/PLLIN, BOOST1, BOOST2, SW1, SW2 in Pin Functions section.Updated text in Operation section.Updated text in Applications Information section.Updated Figure 13.Updated Typical Application and Related Parts.</td><td rowspan=1 colspan=1>139,10</td></tr><tr><td rowspan=1 colspan=1>12-1516-252630</td></tr><tr><td rowspan=1 colspan=1>B</td><td rowspan=1 colspan=1>07/14</td><td rowspan=1 colspan=1>Updated Application SchematicUpdated Nominal Frequency ResistorUpdated VouTsNs and VIN SectionsUpdated LBoosT equation</td><td rowspan=1 colspan=1>149,1018</td></tr><tr><td rowspan=1 colspan=1>C</td><td rowspan=1 colspan=1>11/14</td><td rowspan=1 colspan=1>Added TG1, TG2 Absolute Maximum RatingsAdded Note 6Replaced Figure 9Added Text</td><td rowspan=1 colspan=1>241721</td></tr></table>

# Typical Applicat ion

# 24V/5A Buck-Boost Regulator

![](../assets/ltc3789-datasheet/403d6170cfb6a866722c194ca87c962f50f630d69508cf45195321fc9810f4ac.jpg)

# Relat ed Part s

<table><tr><td rowspan=1 colspan=1>PART NUMBER</td><td rowspan=1 colspan=1>DESCRIPTION</td><td rowspan=1 colspan=1>COMMENTS</td></tr><tr><td rowspan=1 colspan=1>LTC3780</td><td rowspan=1 colspan=1>High Effciency (Up to 98%) Synchronous,4-Switch Buck-BoostDC/DC Controller</td><td rowspan=1 colspan=1>4V ≤VIN ≤36V,0.8V≤VouT≤30V, 5mm × 5mm QFN-32 andSSOP-24 Packages</td></tr><tr><td rowspan=1 colspan=1>LTC3785</td><td rowspan=1 colspan=1>High Efficiency (Up to 98%)Synchronous,4-Switch Buck-BoostDC/DC Controller</td><td rowspan=1 colspan=1>2.7V ≤VIN ≤10V,2.7V≤VouT≤10V,4mm × 4mmQFN-24 Package</td></tr><tr><td rowspan=1 colspan=1>LTM4605</td><td rowspan=1 colspan=1>High Efficiency Buck-Boost DC/DC uModuleTM RegulatorComplete Power Supply</td><td rowspan=1 colspan=1>4.5V≤VIN≤20V,0.8V≤VouT≤16V,15mm×15mm×2.8mmLGA Package</td></tr><tr><td rowspan=1 colspan=1>LTM4607</td><td rowspan=1 colspan=1>High Efficiency Buck-Boost DC/DC uModule RegulatorComplete Power Supply</td><td rowspan=1 colspan=1>4.5V≤VIn≤36V,0.8V≤Vout≤25V,15mm×15mm×2.8mmLGA Package</td></tr><tr><td rowspan=1 colspan=1>LTM4609</td><td rowspan=1 colspan=1>High Efficiency Buck-Boost DC/DC uModule RegulatorComplete Power Supply</td><td rowspan=1 colspan=1>4.5V≤ VIN≤36V,0.8V≤VouT≤34V,15mm ×15mm ×2.8mmLGA Package</td></tr><tr><td rowspan=1 colspan=1>LTC3112</td><td rowspan=1 colspan=1>2.5A Synchronous Buck-Boost DC/DC Converter</td><td rowspan=1 colspan=1>2.7V ≤VIN ≤15V,2.5V≤VouT≤14V,4mm ×5mm DFN-16 andTSSOP-20 Packages</td></tr><tr><td rowspan=1 colspan=1>LTC3533</td><td rowspan=1 colspan=1>2A Synchronous Buck-Boost Monolithic DC/DC Converter</td><td rowspan=1 colspan=1>1.8V≤VIN≤5.5V,1.8V≤V0UT≤5.25V,IQ= 40uA,IsD&lt;1uA,3mm×4mm DFN-14 Package</td></tr></table>