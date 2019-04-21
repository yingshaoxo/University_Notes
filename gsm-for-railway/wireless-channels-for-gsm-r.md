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

___

信道组合: 将逻辑信道装在物理信道上。

> GSM-R 系统上下行帧在时间上不同步(时差很小)，但在程序处理时，编号是同步的。这样做可以避免`移动台`在同一时隙进行收发，便于`帧调整`以及`收发机的调谐转换(收、发 状态切换)`

___

### 帧结构

![](/assets/GSM-R系统各种帧及时隙的格式.jpg)

8时隙 = 一个 TDMA 帧 = 4.615 ms = 156.25 bit

业务复帧 = 26帧

控制复帧 = 51帧

超帧 = 51 x 26 x 4

超高帧 = 2048 个超帧

> 说实话，我不知道记这些玩意儿有什么用

#### 业务信道

![](/assets/业务信道的组合方式.jpg)

T: TCH

A: SACCH

#### 控制信道

##### 方式一: `BCH和CCCH在TS0上组合` + `SDCCH和SACCH在TS1上复用` = 下行 +　上行

![](/assets/RACH在TS0上的组合.jpg) 

F: FCCH

S: SCH

B: BCCH

C: CCCH

I: 占位的，没有实际的意义

> F、S分散排列，利于手机快速入网

> B、C连续

> 占满51

![](/assets/SDCCH和SACCH在TS1上的组合.jpg)

D: SDCCH

A: SACCH

> 4帧连排

##### 方式二: `广播、公用、专用控制信道`一起，在TS0传

![](/assets/所有控制信道均在TS0上的组合.jpg)