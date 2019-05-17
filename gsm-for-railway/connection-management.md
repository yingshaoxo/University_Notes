### 主呼(主动呼叫), connection setup

RACH -> AGCH -> PCH -> RACH -> AGCH -> SDCCH

___

### 被呼(被别人呼叫), incoming call

PCH -> RACH -> AGCH -> SDCCH -> FACCH -> TCH

___

### 小区选择

> 刚开机时做的事

1. MS扫描所有频率，存储`电平值最大的`载波
2. MS调频到最强载波，接入`频率校正信道FCCH`
3. 读取该载波的`同步信道SCH`
4. 读取该载波的`广播控制信道BCCH`

___

### 小区重选

> 已经进行了`小区选择`后，做的事

测量临近小区的`广播控制信道BCCH`，记录`电平值较大的6个小区`，提取它们所包含的信息，如果满足一定条件，就转移到对应的小区。

___

References:

https://people.kth.se/~johanmon/attic/2g1723/lectures/signaling.pdf