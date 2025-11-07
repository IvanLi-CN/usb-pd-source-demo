> Source: [docs/datasheets/source/SW7203_Software_CN.pdf](../source/SW7203_Software_CN.pdf)

# SW7203 软件流程指导

# 1. 初始化设置

在上电初始化的时候，为保证通信正常，建议 Master先让IIC 保持2S 以上的高电平后再开始通讯，避免因为不同芯片的初始化时间不一致从而导致的通讯失败现象。

# 2. 放电设置

# 2.1. 打开放电

1） 放电调压类型设置，通过 $\mathrm { r e g 0 x } 2 0 [ 0 ]$ 设置放电调压类型；设置 $\scriptstyle \mathrm { r e g 0 x } 2 0 [ 0 ] = 0$ 时，通过寄存器设置放电电压；设置 $\scriptstyle \mathrm { r e g 0 x } 2 0 [ 0 ] = 1$ 时，通过外部反馈电阻设置放电电压；

2） 放电 VBUS 输出电压设置，设置 $\scriptstyle \mathrm { r e g 0 x } 2 0 [ 0 ] = 0$ 时，通过 $\mathrm { r e g 0 x } 2 3 / \mathrm { r e g 0 x } 2 4$ 设置放电VBUS 输出电压，先写 $\mathrm { r e g 0 x 2 3 }$ 后写 $\mathrm { r e g 0 x } 2 4$ ，设置才生效；

3） 放电 VBUS 输出限流设置，通过 $\mathrm { r e g 0 x } 2 5$ 设置放电 VBUS 输出限流；

4） 放电 VBAT 输出限流设置，通过 $\mathrm { r e g 0 x } 2 6$ 设置放电 VBAT 输出限流；

5） 放电VBAT欠压设置，通过 reg0x27设置放电 VBAT欠压，注意 reg0x27 可写入不能读出，读出都是 $0 \mathrm { { x } 0 0 }$ ；

6） 放电 VBAT 欠压迟滞设置，通过 reg0x28 设置放电 VBAT 欠压迟滞；

7） 打开放电，通过 reg0x0D[0]设置为 1，打开放电。

# 2.2. 关闭放电

1） 关闭放电，通过 reg0x0D[0]设置为 0，关闭放电。

# 3. 充电设置

# 3.1. 打开充电

1） 充电目标电压设置，会根据外部电池节数设置自动设置充电目标电压，也可以通过reg0x34/reg0x35 设置充电目标电压，先写 $\mathrm { r e g 0 x } 3 4$ 后写 reg0x35，设置才生效；

2） 充电 VBUS 限流设置，通过 reg0x39 设置充电 VBUS 限流；

3） 充电 VBAT 限流设置，通过 reg0x3A 设置充电 VBAT 限流；

4） 充电 VBUS 限压设置，通过 $\mathrm { r e g 0 x } 3 8$ 设置充电 VBUS 限压；

5） 涓流电压设置，会根据外部电池节数设置自动设置涓流电压，也可以通过 reg0x36 设置涓流电压；

6） 涓流电压迟滞设置，通过 reg0x37[1:0]设置涓流电压迟滞；

7） 涓流电流设置，通过 reg0x37[3:2]设置涓流电流；

8） 不断读取 reg0x04[3]，当 $\scriptstyle \mathrm { r e g 0 x 0 4 } [ 3 ] = 1$ 时，表示适配器接入；通过 reg0x04[3]写 1 清

除此状态；

9） 设置 $\scriptstyle \mathrm { r e g 0 x 1 9 } [ 2 ] = 1$ ，打开 B 口通路管；  
10） 打开充电，通过 $\mathrm { r e g 0 x 0 D [ 4 ] }$ 设置为 1，打开充电。

# 3.2. 关闭充电

1） 不断读取 $\mathrm { r e g 0 x 0 4 } [ 2 ]$ ，当 $\scriptstyle \mathrm { r e g 0 x 0 4 } [ 2 ] = 1$ 时，表示适配器移出，SW7203 将会自动关闭充电并清零 $\mathrm { r e g 0 x 0 D [ 4 ] }$ ；通过 reg0x04[2]写 1 此状态；

2） 设置 reg0x19[2] $\scriptstyle \left| = 0 \right|$ ，关闭 B 口通路管；

# 3.3. 62368 电池温度保护与 IBUS 限流设置

1） 在 NTC 过温，charger done 和充电超时后，IBUS 充电限流将默认被锁定，无法调整。  
此时如果需要调整IBUS 充电限流，可以先设置 $\mathrm { r e g 3 2 } \left[ 6 \right] = 1$ ，然后再调整IBUS 充电限流。

# 4. NVDC 设置

1） LDO充电电流设置，通过 reg0x41设置 LDO充电电流；  
2） VSYSMIN电压设置，会根据外部电池节数设置自动设置 VSYSMIN电压，也可以通过 $\mathrm { r e g 0 x 4 2 }$ 设置 VSYSMIN 电压。

# 5. ADC 数据读取

1） ADC 滤波时间设置，通过 reg0x10[7:6]设置 ADC 滤波时间；  
2） ADC 通道选择，通过 reg0x10[3:0]选择需要读取的 ADC 数据类型；  
3） ADC 数据读取，通过 reg0x11/reg0x12 读取 ADC 数据，并根据如下公式换算成实际值。  
Vbat=N\*7.5mV；  
Vbus $\mathrm { = N ^ { \ast } } 7 . 5 \mathrm { m V }$ ；  
Vsys $\mathrm { = N } ^ { \ast } 7 . 5 \mathrm { m V }$ ；  
Ibat_chg=N\*5mA；  
Ibat_dischg $= \mathrm { N } { } ^ { * } 5 \mathrm { m A }$ ；  
Ibus_chg=N\*5mA；  
Ibus_dischg $\mathbf { \Lambda } { = } \mathbf { N } ^ { * } 5 \mathbf { m } \mathbf { A }$ ；  
Tdie=(N-1839) $/ 6 . 8 2 ^ { \circ } \mathrm { C }$ ；  
Rntc=N\*1.1 /40 KΩ；  
算出NTC 对应电阻值后查表获取 NTC 对应温度。

# 6. 接入检测

SW7203 有一路适配器接入及移出检测及两路负载接入检测，并对应有三路通路管驱动。

# 6.1. 适配器接入及移出检测

1） 读取 reg0x04[3]，当 $\scriptstyle \mathrm { r e g 0 x 0 4 } [ 3 ] = 1$ 时，表示适配器接入；通过 reg0x04[3]写 1 清除此状态；

2） 读取 reg0x04[2]，当 $\scriptstyle \mathrm { r e g 0 x 0 4 } [ 2 ] = 1$ 时，表示适配器移出；通过 reg0x04[2]写 1 清除此状态；

3） 通过控制 reg0x19[2]可打开或关闭 B 口通路管。

# 6.2. A1口负载接入检测

1） 使用 A1 口负载接入检测前，请确保 INDTA1 上未连接任何抽电设备或耗电的线缆，否则可能会出现无法正确识别负载接入的情况。设置 $\mathrm { r e g 0 x 0 C [ 1 ] } { = } 1$ ，打开 INDTA1 的泄放电通路，将 INDTA1 上的电压放到 0。然后再设置 reg0x0C[1]=0 关闭 INDTA1 的泄放电通路；

2） 设置 $\scriptstyle \mathrm { r e g 0 x 1 } 8 [ 1 ] = 1$ ，使能 A1 口负载接入检测；

3） 当放电从打开状态变为关闭状态，或充电从打开状态变为关闭状态时，则需要reg0x0C[3]先写 1 再写 0，来重新使能 A1 口负载接入检测；

4） 读取 reg0x04[0]，当 $\scriptstyle \mathrm { r e g 0 x 0 4 } [ 0 ] = 1$ ，表明有负载接入 A1 口；通过 $\mathrm { r e g 0 x 0 4 [ 0 ] }$ 写 1 清除此状态；

5） 当识别到 A1 口一次负载接入检测后，即 reg0x04[0]=1 时，需要识别下一次 A1 口负载接入检测时，需要通过 reg0x04[0]写 1 清除此状态，然后 reg0x18[1]先写 0 再写 1，来重新使能A1口负载接入检测；

6） 通过控制 reg0x19[1]可打开或关闭 A1 口通路管。

# 6.3. A2 口负载接入检测

1） 使用 A2 口负载接入检测前，请确保 INDTA2 上未连接任何抽电设备或耗电的线缆，否则可能会出现无法正确识别负载接入的情况。设置 $\mathrm { r e g 0 x 0 C } [ 0 ] { = } 1$ ，打开 INDTA2 的泄放电通路，将 INDTA2 上的电压放到 0。然后再设置 $\scriptstyle \mathrm { r e g 0 x 0 C } [ 0 ] = 0$ 关闭 INDTA2 的泄放电通路；

2） 设置 reg0x18[0]=1，使能 A2 口负载接入检测；

3） 当放电从打开状态变为关闭状态，或充电从打开状态变为关闭状态时，需要 reg0x0C[3]先写1再写 0，来重新使能 A2口负载接入检测；

4） 读取 reg0x04[1]，当 reg0x04[1] $\lvert = \rvert$ ，表明有负载接入 A2 口；通过 reg0x04[1]写 1 清除此状态；

5） 当识别到 A2 口一次负载接入检测后，即 $\scriptstyle \mathrm { r e g 0 x 0 4 } [ 1 ] = 1$ 时，需要识别下一次 A2 口负载接入检测时，需要通过 reg0x04[1]写 1 清除此状态，然后 reg0x18[0]先写 0 再写 1，来重新使能 A2 口负载接入检测；

6） 通过控制 reg0x19[0]可打开或关闭 A2 口通路管。

# 7. 泄放电控制

# 7.1. A1 口泄放电控制

1）通过控制 $\mathrm { r e g 0 x 0 C [ 1 ] }$ 可使能 A1 口泄放电状态；  
2）使能之后打开 INDTA1 泄放电功能 $5 0 0 \mathrm { m S }$ ， $5 0 0 \mathrm { m S }$ 后自动结束，但此 bit 不会自动清  
0；  
3）此功能打开不到 $5 0 0 \mathrm { m S }$ 时，可以写 0 提前结束 INDTA1 泄放电功能。

# 7.2. A2 口泄放电控制

1）通过控制 $\mathrm { r e g 0 x 0 C [ 0 ] }$ 可使能A2口泄放电状态；  
2）使能之后打开 INDTA2 泄放电功能 $5 0 0 \mathrm { m S }$ ， $5 0 0 \mathrm { m S }$ 后自动结束，但此 bit 不会自动清  
0；  
3）此功能打开不到 $5 0 0 \mathrm { m S }$ 时，可以写 0 提前结束 INDTA2 泄放电功能。

# 7.3. B口泄放电控制

1）通过控制 $\mathrm { r e g 0 x 0 C } [ 2 ]$ 可使能B 口泄放电状态；  
2）使能之后打开INDTB 泄放电功能 $5 0 0 \mathrm { m S }$ ， $5 0 0 \mathrm { m S }$ 后自动结束，但此 bit 不会自动清 0；  
3）此功能打开不到 $5 0 0 \mathrm { m S }$ 时，可以写0提前结束 INDTB 泄放电功能。

# 7.4. VBUS 泄放电控制

1）通过控制 reg0x0C[3]可使能 VBUS 泄放电状态；  
2）使能之后打开 VBUS 泄放电功能 $5 0 0 \mathrm { m S } , ~ 5 0 0 \mathrm { m S }$ 后自动结束，但此 bit 不会自动清 0；  
3）此功能打开不到 $5 0 0 \mathrm { m s }$ 时，可以写0提前结束 VBUS 泄放电功能。

# 8. 外部事件及异常保护

如果发生外部事件（如适配器接入等），或是异常（如 NTC 过温等），需要读取相应寄存器来获得当前发生的外部事件或异常，读完写 1清0。具体寄存器地址与对应的外部事件或是异常，如下表所示：

<table><tr><td colspan="1" rowspan="1">事件描述</td><td colspan="1" rowspan="1">寄存器地址</td></tr><tr><td colspan="1" rowspan="1">VSYS 过压</td><td colspan="1" rowspan="1">Reg0x04[6]</td></tr><tr><td colspan="1" rowspan="1">充电超时</td><td colspan="1" rowspan="1">Reg0x04[5]</td></tr><tr><td colspan="1" rowspan="1">充电充满</td><td colspan="1" rowspan="1">Reg0x04[4]</td></tr><tr><td colspan="1" rowspan="1">B口接入</td><td colspan="1" rowspan="1">Reg0x04[3]</td></tr><tr><td colspan="1" rowspan="1">B口拔出</td><td colspan="1" rowspan="1">Reg0x04[2]</td></tr><tr><td colspan="1" rowspan="1">A2口负载接入</td><td colspan="1" rowspan="1">Reg0x04[1]</td></tr><tr><td colspan="1" rowspan="1">A1口负载接入</td><td colspan="1" rowspan="1">Reg0x04[0]</td></tr><tr><td colspan="1" rowspan="1">芯片过温</td><td colspan="1" rowspan="1">Reg0x05[7]</td></tr><tr><td colspan="1" rowspan="1">NTC 高低温保护</td><td colspan="1" rowspan="1">Reg0x05[6]</td></tr><tr><td colspan="1" rowspan="1">VBUS过压</td><td colspan="1" rowspan="1">Reg0x05[5]</td></tr><tr><td colspan="1" rowspan="1">VBAT过压</td><td colspan="1" rowspan="1">Reg0x05[4]</td></tr><tr><td colspan="1" rowspan="1">UVLO</td><td colspan="1" rowspan="1">Reg0x05[3]</td></tr><tr><td colspan="1" rowspan="1">VBUS短路</td><td colspan="1" rowspan="1">Reg0x05[2]</td></tr><tr><td colspan="1" rowspan="1">VBUS过载</td><td colspan="1" rowspan="1">Reg0x05[1]</td></tr><tr><td colspan="1" rowspan="1">VSYS 过载</td><td colspan="1" rowspan="1">Reg0x05[0]</td></tr></table>

# 责任及版权申明

珠海智融科技股份有限公司（以下简称“智融科技”）可能随时对所提供的产品、服务及本文件作出修改或更新，且不另行通知。客户应在下订单前获取最新的相关信息，并确认这些信息是否完整且是最新的。

本文件所含信息仅为您提供便利，智融科技不对这些信息作任何明示或暗示、书面或口头、法定或其他形式的声明或保证，包括不但限于产品的用途、特性、使用情况、适销性等方面。智融科技对这些信息及不合理使用这些信息而引起的后果不承担任何责任。

智融科技对应用帮助或客户产品设计不承担任何义务。客户应对其使用智融科技的产品和应用自行负责。客户应提供充分的设计与操作安全验证，且保证在将智融产品集成到任何应用程序中时不会侵犯第三方知识产权，如发生侵权行为智融科技对此概不承担任何责任。

在转售智融科技产品时，如果对该产品参数及其陈述相比存在差异或虚假成分，则会自动丧失智融科技相关产品的所有明示或暗示授权，且对此不正当的、欺诈性商业行为，智融科技保留采取一切合法方式维权。智融科技对任何此类虚假陈述均不承担任何责任或义务。

本文件仅在没有对内容进行任何篡改且带有相关授权、条件、限制和声明的情况下才允许进行复制，否则智融科技有权追究其法律责任。智融科技对此类篡改过的文件不承担任何责任或义务。复制如涉及第三方的信息应当服从额外的限制条件。