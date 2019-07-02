Please read the book "The ComSoc Guide to Next Generation Optical Transport SDH, SONET, OTN" before you get started the following read.
___

通信网的发展历史(The history of communication network): 

1. PDH (Plesiochronous Digital Hierarchy)
2. SDH (Synchronous Digital Hierarchy)
3. DWDM (Dense Wavelength Division Multiplexing)
4. OTN (Optical Transport Network)
5. PTN (Packet Transmission Network)
___

# SDH (Synchronous Digital Hierarchy)

> STM-N: Synchronous Transport Module of level N

**STM-1**： 155 Ｍb/s

**STM-4**： 622 Ｍb/s

**STM-16**： 2488 Ｍb/s or 2.5Gbit/s

**STM-64**： 9953 Ｍb/s or 10Gbit/s

> 它被用在铁路等专网。(为了稳定，`专用网络`一般使用落后技术)

>　话说自从我学了这个专业，才发现`网络`不仅指`The world wide network`

![](/assets/中国铁路传输网结构.png)

1. 最上面一横排是`骨干层`，由`大型车站`组成，使用`OTN/DWDM`，速度可达`40x10G`

2. 第二排是`汇聚层`，由`小型车站`或`铁路局`组成，使用`SDH`，速度可达`2.5G (STM-16)`

3. 最后一排以及各种圆圈是`接入层`，表示一段线路(因为线路上才有大量`基站`)，使用`SDH`，速度可达`622 Mbit/s (STM-4)`