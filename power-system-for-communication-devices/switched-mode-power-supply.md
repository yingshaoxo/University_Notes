### High Frequency Switched-mode Power Supply

A `switched-mode power supply` is an electronic power supply that incorporates a switching regulator to convert electrical power efficiently. Like other power supplies, an SMPS transfers power from a DC or AC source (often mains power) to DC loads.

___

![](/assets/高频开关电源系统.jpg)

* 防雷器并联。`雷击产生大电流时`电阻变小，导电到大地。
* 虽然整个系统输入`380V三相电`，`整流模块`却只用了`一相220V`
* 整流模块输出 -48V (将`正极接地`即可产生`负电流`)
* 这个系统的负载需要接到负极，因为正极接了地
* 接触器上的`分流器`在这里被用来`测电压`，从而根据公式推导出`电流`
* LVD(Low Voltage Disconnect): 低压脱离装置，低压时保护电池； 或者可用来 根据设备的重要程度依次断电

___

#### 直流的配电方式

##### 低电阻配电: 粗电线，电阻小

优点: 电阻小，线路损耗、压降小

缺点: 某一负载短路后，使直流瞬间增大，损坏设备

##### 高阻配电: 细电线，电阻大

优点: 克服`低阻配电短路 事故`的影响

缺点: 电阻大，线路损耗大

____

#### 直流配电作用

* 测量
* 报警
* 保护
