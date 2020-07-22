# OTN \(Optical Transport Network\)

## Tech Terms

![](../../.gitbook/assets/OTN%20Acronyms.png)

I strongly recommend you read this PDF first: [https://www.viavisolutions.com/en-us/literature/g709-optical-transport-network-otn-white-paper-en.pdf](https://www.viavisolutions.com/en-us/literature/g709-optical-transport-network-otn-white-paper-en.pdf)

## What is OTN

Optical Transport Network

ITU-T G.709 is a standard for OTNs

> G. _标准出自 ITU-T 802._ 标准出自 IEEE

* 引入`带外` `光开销通道`
* 引入`前向纠错编码(FEC)`
* 引入`串行连接监控(TCM)`; 电的形式
* 标准化大容量光通道

## OTN与SDH的区别

![](../../.gitbook/assets/The%20difference%20between%20OTN%20and%20SDH.png)

## OTN 的亮点

1. `超大容量`光传送系统
2. 全业务传送。传送分组数据。
3. 智能化

## OTN transport structure

![](../../.gitbook/assets/Basic%20OTN%20transport%20structure.png)

## OCh\(Optical Channel\) structure

![](../../.gitbook/assets/Optical%20Channel%20Structure.png)

![](../../.gitbook/assets/OTN%20frame%20structure.png)

* OPUk = OPUk OH\(开销\) + OPUk净负荷\(4\*3808\)
* ODUk = ODUk开销 + OPUk
* OTUk = OTUk开销 + ODUk + FEC

> OPUk &lt; ODUk &lt; OTUk

* OCh = OCh + OTUk ; 1波
* OMSn = OMSn OH + OCh ; n波
* OTSn = OTS OH + OMSn ; n波

