### History
PDH -> SDH -> DWDM -> OTN(optical trissmission network) -> ASON

地铁: 早期PDH，后期SDH、OTN(open transmit network)

resource:`《光传送网技术的原理和测试》`and `http://www.txrjy.com`

PDH、SDH： 时分复用
DWDM：波分复用
OTN：两者皆有

> ~~速率不同可以配置同一波长~~

### WDM 的业务
* STM-N (N=16、64); STM-16=2488Mb/s; STM-64=9953Mb/s
* GE、XGE

> SDH的业务: E1, E3, E4, FE, GE

### WDM特点
1. 超大容量传输
2. 节省光纤资源
3. 透明传输(不修改原数据)
4. 用EDFA实现**超长距离传输**(1530-1570nm)
5. 高可靠
6. 可组成`全光网络`
7. 没有复用段保护

### 传输方式
* 双纤单向 (常见)
* 单纤双向 (比如PON(passive optical network)(比如`光猫`的一根光纤))

### 应用模式
* 集成式 (输入波长需不同)
* 开放式 (输入波长可相同，后部设备(OTU, Optical Transform Unit)自动改变波长) (常用)

### 分类
* CWDM(Coarse Wavelength-division multiplexing): 粗波分复用，信道间隔20nm
* DWDM(Dense Wavelength-division multiplexing): 密集波分复用,信道间隔1.6nm，0.8nm，0.4 nm 

### DWDM 组成
光放大器、光中继放大、 光接受机、 光监控信道 和 网络管理系统

![](/assets/DWDM System.png)

* OTU: Optical Transform Unit, 光转发器/接收器
* OMU: Optical Multiplexer Unit
* OSC: Optical Supervisory Channel, 光监控信道(1510nm); 这个波不会经过放大器
* ODU: Optical Demultiplexer Unit, 光分波器
* OBA: Optical Booster amplifier; 光放大器 在 发送端
* OLA: Optical in Line Amplifier; 光放大器 在 线路上
* OPA: Optical Pre Amplifier; 光放大器 在 接收端

光发送机: OTU, OMU, OBA

光接收机: OPA, ODU, OTU, 色散补偿模块(DCM, dispersion compensation module, 一般加在OPA上)

1. `信道1~n 进光` 为1310nm，经过OTU转化为不同波长, 然后40个波长被OMU合成一个信号，送到单根光纤。
2. 经过OSC后加上一波变为41波

> 如果用了OBA/OPA，`线路须中继距离`从60公里变为100公里。(公里=km)
> OLA可以换OBA，因为LA的增益是可调的
> OPA > OLA >= OBA, OPA可以换OLA、OBA
> OSC速率2Mbit/s


### DWDM 的波长
![](/assets/G692 wavelength and frequency table.png)

> 4个STM-4 或 STM-16 在WDM系统都一样，需要4个不同的波长
> 双向线，来回最好用同样的波长, 方便
> 合波后再作通道保护(双路径)

#### 40波(40 channels)    
频率间隔0.1 THz, 波长间隔约等于0.8

40波制下第25波频率 = 192+0.1*25

#### 80波(80 channels)
频率间隔0.05 THz

80波制下第25波频率 = 192+0.05*25

#### ~~160波(160 channels)~~
~~频率间隔0.05~~

~~160波制下第25波频率 = 192+0.05*25~~

### An important question

![](/assets/WDM Frequency table design.png)

* `站M1`与`站M2`之间有`4个STM-64业务`，双路径
* `站M1`与`站M3`之间有`4个STM-64业务`，双路径
* `站M1`与`站M4`之间有`4个STM-64业务`，双路径
* `站M2`与`站M4`之间有`4个STM-64业务`，双路径
* `站M3`与`站M4`之间有`4个STM-64业务`，双路径
* `站M3`与`站M6`之间有`4个STM-16业务`

We ask you to design a frequency table for DWM system.

|   | 站M1 | 站M2 | 站M3 | 站M4 | 站M5 | 站M6 |
| ------ | ------ | ------ | ------ | ------ | ------ | ------ |
| 站M1 |  | 192.10~192.40 THz | 192.50~192.80 THz | 192.90~193.20 THz |  |  |
| 站M2 | 192.10~192.40 THz |  |  | 193.30~193.60 THz |  |  |
| 站M3 | 192.50~192.80 THz |  |  | 193.70~194.00 THz |  | 194.10~194.40 THz |
| 站M4 | 192.90~193.20 THz | 193.30~193.60 THz | 193.70~194.00 THz |  |  |  |
| 站M5 |  |  |  |  |  |  |
| 站M6 |  |  | 194.10~194.40 THz |  |  |  |