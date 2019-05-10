# SDH Equipments

单台机器大约占地19英寸: 60x60 cm

然后有很多板子:

* NCP\(网元控制板\)。网元=网络单元，属于网络中的一个个体，你把它理解为一台计算机\(Server\)也没有问题。
* Qx Interface。可接电源。
* CS板\(时钟交换板\): clock and swicth
* OW: 公务板

配ip: 192.168.1.18。第三个才是`主机标识`，与正常ip网不一样。

## SDH elements\(node\)\(网元\)

### 1. 终端复用器

> 复用器 = Multiplexer

![](../../.gitbook/assets/zhong-duan-fu-yong-qi.png)

它的作用是将`支路端口的低速信号`复用到`线路端口的高速信号STM-N中`，或从`STM-N的信号中`分出`低速的支路信号`。

值得注意的是，它的`线路端口`只`输入/输出一路STM-N信号`，而`支路端口`却可以`输出/输入多路低速支路信号`。

### 2. 分插复用器\(ADM, Add-drop multiplexer\)

![](../../.gitbook/assets/fen-cha-fu-yong-qi.png)

它用于`SDH传输网络的转接站点`，例如链路的`中间结点`。它是一个三端口的器件。

两侧是`高速信号`，下面是`低速信号`。

### 3. 数字交叉连接器\(DXC, Digital cross connect system\)

![](../../.gitbook/assets/shu-zi-jiao-cha-lian-jie-qi.png)

它完成的主要是`STM-N信号的交叉连接功能`，是一个多端口器件。

它实际上相当于一个交叉矩阵，完成各个信号间的交叉连接。

### 4. 再生中继器\(GEG, Regenerator\)

![](../../.gitbook/assets/zai-sheng-zhong-ji-qi.png)

如果`上一层光纤线路传输的距离`比较长，这时候就需要一个`再生中继器`对光信号进行放大，然后再送到`下一段光纤`。

功能：放大、整形、定时提取。

## SDH 设备的线路板

### 1. 光线路传输板

* `OL64板`有`1 个 STM-64 光接口`
* `OL16板`有`1 个 STM-16 光接口`
* `OL4板`有`4 个 STM-4 光接口`
* `OL1板`有`8 个 STM-1 光接口`

### 2. 电业务支路板

* `EPE1板`有`62 个 2M 电接口`。

  > E1: 2M bit/s

* `EPE3板`有`6 个 34M 电接口`。

  > E3: 34M bit/s

* `SEC板`有`8 个 10M or 100M 电接口`，`1 个 1000M 电接口`。

  > ETH: 10M bit/s。FE: 100M bit/s。 GE: 1000M bit/s

References:

[https://en.wikipedia.org/wiki/Synchronous\_optical\_networking](https://en.wikipedia.org/wiki/Synchronous_optical_networking)

[https://zhuanlan.zhihu.com/p/31930140](https://zhuanlan.zhihu.com/p/31930140)
