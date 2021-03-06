# SDH Equipments

单台机器大约占地19英寸: 60x60 cm

然后有很多板子:

* NCP\(网元控制板\)。网元=网络单元，属于网络中的一个个体，你把它理解为一台计算机\(Server\)也没有问题。
* Qx Interface。可接电源。
* CS板\(时钟交换板\): clock and swicth
* OW: 公务板

配ip: 192.168.1.18。第三个才是`主机标识`，与正常ip网不一样。

## SDH光接口代码

`应用类型-STM等级.尾标数`，如`V-16.2`

1. 类型
   * I: 局内通信，&lt; 2km
   * S: 短距离局间，2-40km
   * L: 长距离局间，40-80km
   * V: 超长距离局间，80-120km
   * U: 甚长距离局间，120-160km
2. STM等级
   * 1: STM-1, 155Mbit/s
   * 4: STM-4, 622Mbit/s
   * 16: STM-16, 2488Mbit/s or 2.5Gbit/s
   * 64: STM-64, 9953Mbit/s
3. 尾标
   * 1: 1310nm，G652
   * 2: 1550nm，G652或G654
   * 3: 1550nm, G653
   * 5: 1550nm, G655 

## SDH网管

### 网管接口

* F
* X
* Q: 其中`Qx`只包含OSI的`下三层功能`

### 网络管理层\(从下至上\)

网元层、网元管理层、网络管理层、业务管理层、商务管理层

## SDH elements\(node\)\(网元\)

### 1. 终端复用器

> 复用器 = Multiplexer

![](../../.gitbook/assets/终端复用器.png)

它的作用是将`支路端口的低速信号`复用到`线路端口的高速信号STM-N中`，或从`STM-N的信号中`分出`低速的支路信号`。

值得注意的是，它的`线路端口`只`输入/输出一路STM-N信号`，而`支路端口`却可以`输出/输入多路低速支路信号`。

### 2. 分插复用器\(ADM, Add-drop multiplexer\)

![](../../.gitbook/assets/分插复用器.png)

它用于`SDH传输网络的转接站点`，例如链路的`中间结点`。它是一个三端口的器件。

两侧是`高速信号`，下面是`低速信号`。

### 3. 数字交叉连接器\(DXC, Digital cross connect system\)

![](../../.gitbook/assets/数字交叉连接器.png)

它完成的主要是`STM-N信号的交叉连接功能`，是一个多端口器件。

它实际上相当于一个交叉矩阵，完成各个信号间的交叉连接

DXC的配置类型通常采用`DXC m/n`，其中`m`表示`光纤 接入端口的最高速率等级`，`n`表示`同轴电线 交叉连接中的最低速率等级`

具体的速率需要查表:

![](../../.gitbook/assets/DXC%20m%20or%20n%20ratio%20table.png)

### 4. 再生中继器\(GEG, Regenerator\)

![](../../.gitbook/assets/再生中继器.png)

如果`上一层光纤线路传输的距离`比较长，这时候就需要一个`再生中继器`对光信号进行放大，然后再送到`下一段光纤`。

功能：放大、整形、定时提取。

## SDH 设备的线路板

### 1. 光线路传输板

* `OL64板`有`1 个 STM-64 光接口`
* `OL16板`有`1 个 STM-16 光接口`
* `OL4板`有`4 个 STM-4 光接口`
* `OL1板`有`8 个 STM-1 光接口`

### 2. 电业务支路板

* `EPE1板`有`63 个 2M 电接口`。

  > E1: 2M bit/s

* `EPE3板`有`6 个 34M 电接口`。

  > E3: 34M bit/s

* `SEC板`有`8 个 10M or 100M 电接口`，`1 个 1000M 电接口`。

  > ETH: 10M bit/s。FE: 100M bit/s。 GE: 1000M bit/s

这些`电接口`连接的是`同轴线`。注意，这里的`E1、E3、ETH`都不是指`以太网`，只是套用了`以太网的速率标准`。

References:

[https://en.wikipedia.org/wiki/Synchronous\_optical\_networking](https://en.wikipedia.org/wiki/Synchronous_optical_networking)

[https://zhuanlan.zhihu.com/p/31930140](https://zhuanlan.zhihu.com/p/31930140)

