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

* OUT: Optical Transform Unit, 光转发器/接收器
* OMU: Optical Multiplexer Unit
* OSC: Optical Supervisory Channel, 光监控信道(1510nm); 这个波不会经过放大器
* ODU: Optical Demultiplexer Unit, 光分波器
* OBA: Optical Booster amplifier; 光放大器 在 发送端
* OLA: Optical in Line Amplifier; 光放大器 在 线路上
* OPA: Optical Pre Amplifier; 光放大器 在 接收端


1. `信道1~n 进光` 为1310nm，经过OTU转化为不同波长, 然后40个波长被OMU合成一个信号，送到单根光纤。
2. 经过OSC后加上一波变为41波

> 如果用了OBA/OPA，`线路须中继距离`从60公里变为100公里。

### DWDM 的波长
![](/assets/G692 wavelength and frequency table.png)

40波的频率间隔为0.1THz
