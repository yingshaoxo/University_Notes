# ZXONM E300 Practice

两个`设备(网元)`之间，需要保持`时隙号`和`AUG号`一致，方能通信。

OL1\[1-1-1\]\[1-2\]TU12\(1\)

OL1\[1-1-1\]\[port-AUG\]TU12\(time slot\)

OL1\[板卡号\]\[端口号-AUG号\]TU12\(时隙\)

`Ethernet 以太网` 需要使用 `SE板`

`E1 同轴铜线` 需要使用 `EPE板`

`光纤` 需要使用 `OL板`

TU12: 2M 速率

TU3: 34M 速率

![](../../.gitbook/assets/Chinese%20SDH复用结构.png)

`E1`的载体是`同轴线`，用`EPE板`接入，一个时隙是 2M \(bit\)

`ETH(ernet)`以太网的载体是`网线`，用`SE板`接入，一个时隙是 2M \(bit\)。凡是涉及以太网的SDH，都要配置 VCG、VLAN

> SE 只是一个“中转器”，用来把以太网的数据转为SDH数据

SDH 是 IP网络 的前一代传输系统，也可以理解为被淘汰了的一套系统。

