# SW7201 寄存器手册

# 1 版本历史

V1.0: 初始版本针对芯片版本 1

# 2 寄存器

注意 : 未定义的寄存器或bit 不能被改写

# 2.1 REG 0x01: 版本号

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-3</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>2-0</td><td rowspan=1 colspan=1>芯片版本号</td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x1</td></tr></table>

# 2.2 REG $\mathbf { 0 x 0 2 }$ : 中断使能 1

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-6</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1>充电超时事件中断使能0：使能1：禁止</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>4</td><td rowspan=1 colspan=1>充电充满事件中断使能0：使能1：禁止</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>3</td><td rowspan=1 colspan=1>B口适配器接入事件中断使能0：使能1：禁止</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>B口适配器移出事件中断使能0：使能1：禁止</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>A2 口负载接入事件中断使能0:使能1：禁止</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>A1口负载接入事件中断使能0：使能1：禁止</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.3 REG $\mathbf { 0 x 0 3 }$ : 中断使能 2

<table><tr><td colspan="1" rowspan="1">Bit</td><td colspan="1" rowspan="1">Description</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">Default</td></tr><tr><td colspan="1" rowspan="1">7</td><td colspan="1" rowspan="1">芯片过温事件中断使能</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1"></td><td colspan="1" rowspan="1">0：使能1：禁止</td><td colspan="1" rowspan="1"></td><td colspan="1" rowspan="1"></td></tr><tr><td colspan="1" rowspan="1">6</td><td colspan="1" rowspan="1">NTC 过温事件中断使能0：使能1：禁止</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">5</td><td colspan="1" rowspan="1">VBUS输出过压事件中断使能0：使能1：禁止</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">4</td><td colspan="1" rowspan="1">VBAT过压事件中断使能0：使能1：禁止</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">3</td><td colspan="1" rowspan="1">VBAT欠压事件中断使能0：使能1：禁止</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">2</td><td colspan="1" rowspan="1">VBUS输出短路事件中断使能0：使能1：禁止</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">1</td><td colspan="1" rowspan="1">VBUS 输出过载事件中断使能0：使能1：禁止</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">0</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1"></td><td colspan="1" rowspan="1"></td></tr></table>

# 2.4 REG 0x04: 状态指示 1

<table><tr><td colspan="1" rowspan="1">Bit</td><td colspan="1" rowspan="1">Description</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">Default</td></tr><tr><td colspan="1" rowspan="1">7-6</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">1</td></tr><tr><td colspan="1" rowspan="1">5O</td><td colspan="1" rowspan="1">充电超时事件状态指示0：未发生充电超时事件1：发生充电超时事件此bit通过写1清零</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">4</td><td colspan="1" rowspan="1">充电充满事件状态指示0：未发生充电充满事件1： 发生充电充满事件此bit通过写1清零</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">3</td><td colspan="1" rowspan="1">B口适配器接入事件状态指示0：未发生B口适配器接入事件1：发生B口适配器接入事件此 bit通过写1清零</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">2</td><td colspan="1" rowspan="1">B口适配器移出事件状态指示0：未发生B口适配器移出事件1：发生B口适配器移出事件此 bit通过写1清零</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">1</td><td colspan="1" rowspan="1">A2口负载接入事件状态指示0：未发生A2口负载接入事件1：发生A2口负载接入事件此bit通过写1清零</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">0</td><td colspan="1" rowspan="1">A1口负载接入事件状态指示0：未发生A1口负载接入事件1：发生A1口负载接入事件此 bit通过写1清零</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr></table>

# 2.5 REG 0x05: 状态指示 2

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1> Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>芯片过温事件状态指示0：未发生芯片过温事件1：发生芯片过温事件此 bit通过写1清零</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>6</td><td rowspan=1 colspan=1>NTC过温事件状态指示0：未发生NTC过温事件1：发生NTC 过温事件此 bit通过写1清零</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1>VBUS输出过压事件状态指示0：未发生VBUS 输出过压事件1：发生VBUS 输出过压事件此bit通过写1清零</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>4</td><td rowspan=1 colspan=1>VBAT过压事件状态指示0：未发生VBAT过压事件1：发生VBAT过压事件此 bit通过写1清零</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>3O</td><td rowspan=1 colspan=1>VBAT欠压事件状态指示0:：未发生VBAT欠压事件1:禁止VBAT欠压事件此 bit 通过写1清零</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>VBUS输出短路事件状态指示0：未发生VBUS输出短路事件1：发生VBUS输出短路事件此bit通过写1清零</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>VBUS输出过载事件状态指示0：未发生VBUS输出过载事件1：发生VBUS 输出过载事件此 bit通过写1清零</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr></table>

2.6 REG 0x06: 系统状态指示  

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>充电状态指示0：未处于充电状态1：处于充电状态</td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>6</td><td rowspan=1 colspan=1>放电状态指示0：未处于放电状态1：处于放电状态</td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>5-3</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>62368降电流降电压状态指示0：未处于62368 降电流降电压状态1：处于62368 降电流降电压状态</td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>B口适配器接入状态指示位0：B口适配器无接入1：B口适配器接入</td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.7 REG 0x0C: 泄放电控制

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description                                        1</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-4</td><td rowspan=1 colspan=1>1/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>3</td><td rowspan=1 colspan=1>VBUS泄放电使能使能之后打开VBUS 泄放电功能 500mS，500mS后自动结束，但此bit不会自动清0。此功能打开不到500mS时，可以写0提前结束VBUS 泄放电功能。0：禁止1:使能</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>3</td><td rowspan=1 colspan=1>INDTB泄放电使能使能之后打开INDTB 泄放电功能 500mS，500mS后自动结束，但此 bit不会自动清0。此功能打开不到500mS 时，可以写0提前结束INDTB 泄放电功能禁止1:使能</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>INDTA1泄放电使能使能之后打开 INDTA1泄放电功能500mS，500mS后自动结束，但此bit不会自动清0。此功能打开不到 500mS 时，可以写0提前结束INDTA1泄放电功能0：禁止1：使能</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>INDTA2 泄放电使能使能之后打开INDTA2 泄放电功能500mS，500mS后自动结</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

<table><tr><td>0：禁止 1:使能</td><td>束，但此bit 不会自动清0。此功能打开不到 500mS 时，可以 写0提前结束INDTA2 泄放电功能</td></tr></table>

# 2.8 REG 0x0D: 工作模式控制

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-5</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>4</td><td rowspan=1 colspan=1>充电开关控制打开充电前，需要确保INDTB已接到VBUS，否则可能无法打开充电。0：关闭充电1：打开充电</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>3-1</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>放电开关控制0：关闭放电1：打开放电</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.9 REG 0x0F: 芯片复位检测

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-1</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>芯片复位检测此 bit寄存器可以辅助MCU确定芯片是否发生复位。芯片上电后，将此bit设置为1，后续MCU 定时查询此bit，若此bit为0，则证明芯片发生复位。</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.10 REG 0x10: ADC 配置

<table><tr><td colspan="1" rowspan="1">Bit</td><td colspan="1" rowspan="1">Description</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">Default</td></tr><tr><td colspan="1" rowspan="1">7-6</td><td colspan="1" rowspan="1">ADC滤波时间设置10mS1:20mS2：40mS3:80mS</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">5-4</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">/</td></tr><tr><td colspan="1" rowspan="1">3-0</td><td colspan="1" rowspan="1">ADC 数据类型选择（选择寄存器Reg0x11和Reg0x12中的数据是什么类型）0: VBAT 电压（VBAT= Adc_data[11:0]*7.5mV)1: VBUS 电压（VBUS= Adc_data[11:0]*7.5mV)2~3：保留</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td>4: 5: VBUS充电电流 6: 7: 8: 10~15：保留</td><td>：VBAT充电电流（IBAT_CHG=Adc_data[11:0]*5mA） （IBUS_CHG= Adc_data[11:0]*5mA) VBAT放电电流（IBAT_DISCHG=Adc_data[11:0]*5mA） VBUS 放电电流（IBUS_DISCHG= Adc_data[11:0]*5mA） 芯片温度（TDIE=(Adc_data[11:0]-1839)/6.82℃） 9: NTC 电压（VNTC= Adc_data[11:0]*1.1mV）</td><td></td><td></td></tr></table>

# 2.11 REG 0x11: ADC 数据高 8bits

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-0</td><td rowspan=1 colspan=1>ADC 数据高 8bitsAdc_data[11:04]</td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.12 REG 0x12: ADC 数据低 4bits

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-4</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>3-0</td><td rowspan=1 colspan=1>ADC 数据低 4bitsAdc_data[03:00]</td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.13 REG 0x18: 负载接入检测及低功耗模式控制

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-5</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>4</td><td rowspan=1 colspan=1>关机低功耗模式使能0：使能1：禁止</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>3-2</td><td></td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>A1口负载接入检测使能0：禁止1:使能</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>A2 口负载接入检测使能0:禁止1:使能</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.14 REG 0x19: 通路控制

<table><tr><td colspan="1" rowspan="1">Bit</td><td colspan="1" rowspan="1">Description</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">Default</td></tr><tr><td colspan="1" rowspan="1">7-3</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">/</td></tr><tr><td colspan="1" rowspan="1">2</td><td colspan="1" rowspan="1">GATEB通路开关控制0：关闭</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1"></td><td colspan="1" rowspan="1">1：打开</td><td colspan="1" rowspan="1"></td><td colspan="1" rowspan="1"></td></tr><tr><td colspan="1" rowspan="1">1</td><td colspan="1" rowspan="1">GATEA1通路开关控制0：关闭1：打开</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">0</td><td colspan="1" rowspan="1">GATEA2通路开关控制0：关闭1：打开</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr></table>

# 2.15 REG 0x1A: I2C 地址设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-2</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>1-0</td><td rowspan=1 colspan=1>I2C 地址设置，7位地址0:0x3C（读0x79，写0x78）1:0x38（读0x71，写0x70）2:0x1C 读0x39,写0x38）3:Ox18 读0x31，写0x30）</td><td rowspan=1 colspan=1> R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.16 REG $\mathbf { 0 x 2 0 }$ : 功能设置 1

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-6</td><td rowspan=1 colspan=1>开关频率设置，充放电共用此设置0:300KHz1: 200KHz2:400KHz3:800KHz</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1>强制PWM模式使能0：禁止1：使能</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>4-3</td><td></td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>NTC 过温保护使能0：使能1：禁止</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>功率管最小导通时间设置0：下管最小导通时间112nS，上管最小导通时间133nS1：下管最小导通时间58nS，上管最小导通时间81nS</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>VBUS输出调压方式选择0：I2C 调压1：FB 调压</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.17 REG 0x21: 功能设置 2

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-6</td><td rowspan=1 colspan=1>M2关M1开死区设置0:60nS1:20nS2:40nS3:80nS</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x2</td></tr><tr><td rowspan=1 colspan=1>5-4</td><td rowspan=1 colspan=1>M1关M2开死区设置0:60nS1: 20nS2:40nS3:60nS</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x2</td></tr><tr><td rowspan=1 colspan=1>3-2</td><td rowspan=1 colspan=1>M3关M4开死区设置0:60nS1: 20nS2: 40nS3:80nS</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x2</td></tr><tr><td rowspan=1 colspan=1>1-0</td><td rowspan=1 colspan=1>M4关M3开死区设置0:60nS1: 20nS2:40nS3:60nS</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x2</td></tr></table>

# 2.18 REG 0x22: 功能设置 3

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-6O7</td><td rowspan=1 colspan=1>M2 功率管内阻设置0: 2.5mΩ1:5mΩ2:7.5mΩ3:10mΩ</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x3</td></tr><tr><td rowspan=1 colspan=1>5-4</td><td rowspan=1 colspan=1>电感感值设置默认值由LSET电阻设置0：1uH1: 2.2uH2：3.3uH3: 4.7uH</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>3-0</td><td rowspan=1 colspan=1>一</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr></table>

2.19 REG 0x23: 放电 VBUS 输出电压设置高 8bits  

<table><tr><td>Bit</td><td>Description</td><td>R/W</td><td>Default</td></tr><tr><td>7-0</td><td>放电VBUS输出电压设置高8bits，Vbus_dischg[10:03] 共11bits，10mV/Step，偏置3V，最高可设置到22V，超过 22V 将维持在22V。先写Vbus_dischg[10:03]，后写 Vbus_dischg[02:00]，设置才生效。 VBUS_DISCHG=3000mV+Vbus_dischg[10:00]*10mV</td><td>R/W</td><td>0x0</td></tr></table>

# 2.20 REG 0x24: 放电 VBUS 输出电压设置低 3bits

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1> Default</td></tr><tr><td rowspan=1 colspan=1>7-3</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>2-0</td><td rowspan=1 colspan=1>放电VBUS 输出电压设置低3bits，Vbus_dischg[02:00]共11bits，10mV/Step，偏置3V，最高可设置到 22V，超过 22V将维持在22V。先写Vbus_dischg[10:03]，后写Vbus_dischg[02:00]，设置才生效。VBUS_DISCHG=3000mV+Vbus_dischg[10:00]*10mV</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.21 REG 0x25: 放电 VBUS 输出限流设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>6-0</td><td rowspan=1 colspan=1>放电VBUS输出限流设置，Ibus_dischg[6:0]共 7bits，50mA/Step，偏置0.5A，最高可设置到6.85A。默认值为5.3A。IBUS_DISCHG=500mA+Ibus_dischg[6:0]*50mA</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x60</td></tr></table>

# 2.22 REG 0x26: 放电 VBAT 输出限流设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>6-0</td><td rowspan=1 colspan=1>放电VBAT输出限流设置，Ibat_dischg[6:0]共 7bits，100mA/Step，偏置0.1A，最高可设置到12A，超过12A 将维持在12A。默认值为12A。IBAT_DISCHG=100mA+Ibat_dischg[6:0]*100mA</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x77</td></tr></table>

# 2.23 REG 0x27: 放电 VBAT 欠压设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>6-0</td><td rowspan=1 colspan=1>放电VBAT欠压设置，Vbat_uvlo[6:0]</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x3</td></tr></table>

<table><tr><td></td><td>共 7bits,0.1V/Step,偏置2.7V,最高可设置到13.2V,超过13.2V 将维持在13.2V。默认值为3V。 VBAT_UVLO=2.7V+Vbat_uvlo[6:0]*0.1V</td></tr></table>

# 2.24 REG $\mathbf { 0 } \mathbf { x } 2 \mathbf { 8 }$ : 放电 VBAT 欠压迟滞设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-5</td><td rowspan=1 colspan=1>一</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>4-0</td><td rowspan=1 colspan=1>放电VBAT欠压迟滞设置，Vbat_uvlo_hys[4:0]共 5bits，0.1V/Step，偏置0.4V，最高可设置到2V，超过2V将维持在2V。VBAT_UVLO_HYS=0.4V+Vbat_uvlo_hys[4:0]*0.1V</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.25 REG 0x30: 功能设置 4

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>适配器移出是否清除充电开关控制位0：清除1：不清除</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>6</td><td rowspan=1 colspan=1>充满停充使能0：使能1：禁止</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>5-4</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>1</td></tr><tr><td rowspan=1 colspan=1>3-2</td><td rowspan=1 colspan=1>充满截止电流设置0：100mA1:200mA2:300mA3：400mA</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>1-0</td><td rowspan=1 colspan=1>电池节数设置默认值由 BSSET 电阻设置0:   节1: 2节3节3:    节</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.26 REG 0x31: 功能设置 5

<table><tr><td colspan="1" rowspan="1">Bit</td><td colspan="1" rowspan="1">Description</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">Default</td></tr><tr><td colspan="1" rowspan="1">7-4</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">/</td><td colspan="1" rowspan="1">/</td></tr><tr><td colspan="1" rowspan="1">3-2</td><td colspan="1" rowspan="1">芯片过温温度设置0: 120°℃1:130℃</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x3</td></tr><tr><td colspan="1" rowspan="1"></td><td colspan="1" rowspan="1">2:140℃3: 150℃</td><td colspan="1" rowspan="1"></td><td colspan="1" rowspan="1"></td></tr><tr><td colspan="1" rowspan="1">1-0</td><td colspan="1" rowspan="1">峰值限流设置，充放电共用此设置0:12A1:14A2:16A3:18A</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x3</td></tr></table>

# 2.27 REG 0x32: 功能设置 6

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>62368功能使能0：使能1：禁止</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>6</td><td rowspan=1 colspan=1>处于62368的高低温状态，降低IBUS 限流功能使能0：使能1：禁止</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>4</td><td rowspan=1 colspan=1>充电超时使能0：使能1：禁止</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>3-2</td><td rowspan=1 colspan=1>涓流充电超时时间设置0：30分钟1：1小时2：2小时3：4小时</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x3</td></tr><tr><td rowspan=1 colspan=1>1-0O</td><td rowspan=1 colspan=1>恒流充电超时时间设置0：12小时1：24小时2:48小时3:72小时</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x3</td></tr></table>

# 2.28 REG 0x33: 功能设置 7

<table><tr><td>Bit</td><td>Description</td><td>R/W</td><td>Default</td></tr><tr><td rowspan="5">7-6</td><td>处于62368的低温状态，降低限流设置 当 REG32[6]=O 时，同时降低 IBUS 和 IBAT 的限流值；</td><td>R/W</td><td>0x0</td></tr><tr><td>REG32[6]=1时，只降低 IBAT的限流值 0：降低到设置值的1/2</td><td></td><td></td></tr><tr><td>1: 降低到设置值的1/4 2：不降低</td><td></td><td></td></tr><tr><td>3：保留</td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr><tr><td colspan="1" rowspan="1">5-4</td><td colspan="1" rowspan="1">处于62368的高温状态，降低限流设置当 REG32[6]=O 时，同时降低 IBUS 和 IBAT 的限流值；REG32[6]=1时，只降低IBAT的限流值0：降低到设置值的1/21：降低到设置值的1/42：不降低3：保留</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">3</td><td colspan="1" rowspan="1">处于62368的低温状态，降低充电目标电压设置0：充电目标电压降低电池节数设置值*0.1V1：不降低充电目标电压</td><td colspan="1" rowspan="1">R/W0</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">2</td><td colspan="1" rowspan="1">处于62368的高温状态，降低充电目标电压设置0：充电目标电压降低电池节数设置值*0.1V1：不降低充电目标电压</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">1</td><td colspan="1" rowspan="1">62368低温迟滞0: 5℃1: 10°℃</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr><tr><td colspan="1" rowspan="1">0</td><td colspan="1" rowspan="1">62368高温迟滞0:5℃1: 10℃</td><td colspan="1" rowspan="1">R/W</td><td colspan="1" rowspan="1">0x0</td></tr></table>

# 2.29 REG 0x34: 充电目标电压设置高 8bits

<table><tr><td>Bit</td><td>Description</td><td>R/W</td><td>Default</td></tr><tr><td>7-0</td><td>充电目标电压设置高8bits，Vbat_target[10:03] 共11bits，10mV/Step，偏置3V，最高可设置到19.2V，超过 19.2V将维持在 19.2V。先写 Vbat_target[10:03]，后写 Vbat_target[02:00]，设置才生效。默认值根据BSSET电阻设置 的电池节数，设置为电池节数*4.2V。 VBUS_TARGET=3000mV+Vbat_target[10:00]*10mV</td><td>R/W</td><td>0x0</td></tr></table>

# 2.30 REG 0x35: 充电目标电压设置低 3bits

<table><tr><td>Bit</td><td> Description</td><td>R/W</td><td>Default</td></tr><tr><td>7-0</td><td>充电目标电压设置低3bits，Vbat_target[10:03] 共11bits，10mV/Step，偏置3V，最高可设置到19.2V，超过 19.2V将维持在19.2V。先写Vbat_target[10:03]，后写 Vbat_target[O2:00]，设置才生效。默认值根据BSSET电阻设置 的电池节数，设置为电池节数*4.2V。</td><td>R/W</td><td>0x0</td></tr></table>

2.31 REG 0x36: 涓流电压设置   

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>V</td></tr><tr><td rowspan=1 colspan=1>6-0</td><td rowspan=1 colspan=1>涓流电压设置，Ibat_trickle[6:0]共 7bits,0.1V/Step,偏置2.5V,最高可设置到13.2V,超过13.2V将维持在13.2V。默认值根据BSSET电阻设置的电池节数，设置为电池节数*2.9V。VBAT_TRICKLE=2.5V+Ibat_trickle[6:0]*0.1V</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.32 REG 0x37: 涓流电流设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1> R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-4</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>3-2</td><td rowspan=1 colspan=1>涓流电流设置0: 100mA1: 200mA2:300mA3：400mA</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>1-0</td><td rowspan=1 colspan=1>涓流电压迟滞设置默认值根据 BSSET 电阻设置的电池节数，设置为电池节数*0.1V。0：0.1V1:0.2V2:0.3V3:0.4V</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.33 REG 0x38: 充电 VBUS 限压设置

<table><tr><td>Bit</td><td>Description</td><td>R/W</td><td>Default</td></tr><tr><td>7-0</td><td>充电VBUS 限压设置，Vbus_hold[7:0] 共 8bits，0.1V/Step，偏置4V，最高可设置到 20V，超过 20V 将维持在 20V 不变。当输入电压降低到设置好的充电VBUS 限 压门限时将降低充电电流以保证输入电压不低于充电VBUS限 压门限。</td><td>R/W</td><td>0x4</td></tr></table>

# 2.34 REG 0x39: 充电 VBUS 输入限流设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>1</td></tr><tr><td rowspan=1 colspan=1>6-0</td><td rowspan=1 colspan=1>充电VBUS输入限流设置，Ibus_chg[6:0]</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x40</td></tr></table>

<table><tr><td></td><td>共 7bits，50mA/Step，偏置0.5A，最高可设置到6.85A。 IBUS_CHG=500mA+Ibus_chg[6:0]*50mA</td><td></td></tr></table>

# 2.35 REG 0x3A: 充电 VBAT 输入限流设置

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>6-0</td><td rowspan=1 colspan=1>充电VBAT输入限流设置，Ibat_chg[6:0]共 7bits，100mA/Step，偏置0.1A，最高可设置到12A，超过12A 将维持在12A。IBAT_CHG=100mA+Ibat_chg[6:0]*100mA</td><td rowspan=1 colspan=1>R/WV</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.36 REG 0x43: NTC 设置 1

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1> R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-6</td><td rowspan=1 colspan=1>放电NTC 高温门限0:50℃1:55℃2:60℃3:65℃</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>5-4</td><td rowspan=1 colspan=1>放电NTC 低温门限0: -10℃1: -5℃2：0℃3: -20℃</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>3-2O</td><td rowspan=1 colspan=1>充电NTC 高温门限0:45℃1:40℃2: 50℃3: 55℃</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr><tr><td rowspan=1 colspan=1>1-0</td><td rowspan=1 colspan=1>充电NTC 低温门限0:0℃10℃2:5℃3: -5℃</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>0x0</td></tr></table>

# 2.37 REG 0x44: NTC 设置 2

<table><tr><td rowspan=1 colspan=1>Bit</td><td rowspan=1 colspan=1>Description</td><td rowspan=1 colspan=1>R/W</td><td rowspan=1 colspan=1>Default</td></tr><tr><td rowspan=1 colspan=1>7-2</td><td rowspan=1 colspan=1>/</td><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>/</td></tr><tr><td rowspan=1 colspan=1>1-0</td><td rowspan=1 colspan=1>NTC工作电流指示0:20uA</td><td rowspan=1 colspan=1>R</td><td rowspan=1 colspan=1>0x0</td></tr></table>

<table><tr><td>1: 40uA 2: 80uA 3： 保留</td></tr><tr><td></td></tr></table>

![](../assets/sw7201-register/8172b70224758b0b9a45a446e1404ffcd12d30c7ddfd128fd021d56c91e68c1a.jpg)

# 免责声明

珠海智融科技股份有限公司（以下简称“智融科技”）可能随时对所提供的产品、服务及本文件作出修改或更新，且不另行通知。客户应在下订单前获取最新的相关信息，并确认这些信息是否完整且是最新的。本文件所含信息仅为您提供便利，智融科技不对这些信息作任何明示或暗示、书面或口头、法定或其他形式的声明或保证，包括不但限于产品的用途、特性、使用情况、适销性等方面。智融科技对这些信息及不合理使用这些信息而引起的后果不承担任何责任。

智融科技对应用帮助或客户产品设计不承担任何义务。客户应对其使用智融科技的产品和应用自行负责。客户应提供充分的设计与操作安全验证，且保证在将智融产品集成到任何应用程序中时不会侵犯第三方知识产权，如发生侵权行为智融科技对此概不承担任何责任。

在转售智融科技产品时，如果对该产品参数及其陈述相比存在差异或虚假成分，则会自动丧失智融科技相关产品的所有明示或暗示授权，且对此不正当的、欺诈性商业行为，智融科技保留采取一切合法方式维权。智融科技对任何此类虚假陈述均不承担任何责任或义务。

本文件仅在没有对内容进行任何篡改且带有相关授权、条件、限制和声明的情况下才允许进行复制，否则智融科技有权追究其法律责任。智融科技对此类篡改过的文件不承担任何责任或义务。复制如涉及第三方的信息应当服从额外的限制条件。