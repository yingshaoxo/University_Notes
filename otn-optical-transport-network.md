### Tech Terms

![](/assets/OTN Acronyms.png)

I strongly recommend you read this PDF first: https://www.viavisolutions.com/en-us/literature/g709-optical-transport-network-otn-white-paper-en.pdf

### What is OTN
Optical Transport Network

ITU-T G.709 is a standard for OTNs

> G.* 标准出自 ITU-T
> 802.* 标准出自 IEEE

* 引入`带外` `光开销通道`
* 引入`前向纠错编码(FEC)`
* 引入`串行连接监控(TCM)`; 电的形式
* 标准化大容量光通道

### OTN与SDH的区别

![](/assets/The difference between OTN and SDH.png)

### OTN 的亮点
1. `超大容量`光传送系统
2. 全业务传送。传送分组数据。
3. 智能化

### OTN transport structure

![](/assets/Basic OTN transport structure.png)

### OCh(Optical Channel) structure

![](/assets/Optical Channel Structure.png)

![](/assets/OTN frame structure.png)

* OPUk = OPUk OH(开销) + OPUk净负荷(4*3808)
* ODUk = ODUk开销 + OPUk
* OTUk = OTUk开销 + ODUk + FEC

> OPUk < ODUk < OTUk

* OCh = OCh + OTUk ; 1波
* OMSn = OMSn OH + OCh ; n波
* OTSn = OTS OH + OMSn ; n波


