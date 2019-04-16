## GSM-R 无线信道与信道组合

信道组合: 所谓组合，是将不同`逻辑信道`装在一个`物理信道`上传输。(说白了就是一根网线上我想传什么就传什么，音乐、视频、文本)

> 对于 GSM-R，一个频点上的一帧就是一个物理信道

___

### 无线信道类型

#### 物理信道(Physical Channels)

#### 逻辑信道(Logical Channels)

##### 1. 业务信道(TCH, Traffic Channels)

传语音

##### 2. 控制信道(CCH, Control Channels)

###### 广播信道(BCH, Broadcast Channels): 都是`下行信道`

* 频率校正信道(FCCH, frequency correction channel)
* 同步信道(SCH, synchronization channel)
* 广播控制信道(BCCH, Broadcast control channel): 提供位置区标识。手机开机后会持续监听。

###### 公共控制信道(CCCH, Common Control Channels)

* 寻呼信道(PCH, paging channel): downlink only.
* 随机接入信道(RACH, random access channel): uplink only. 手机要求接入网络与对方通话
* 接入许可信道(AGCH, access grant channel): downlink only.
* 通知信道(NCH, notification channel): downlink only. 语音组呼通知。

##### 3. 专用控制(DCCH, Dedicated Control Channels): 用于`通话时`传输`控制信令`

* 独立专用控制信道(SDCCH, stand-alone dedicated control channel): 上下行信道，呼叫建立前告诉你用哪个TCH信道
* 慢速随路控制信道(SACCH, slow associated control channel): 通话时，慢速控制`发射功率`、`发射时间提前量`等
* 快速随路控制信道(FACCH, fast associated control channel): 通话时的`紧急控制`

___

Reference:

https://simcom07.blogspot.com/2011/08/gsm-logical-channels.html