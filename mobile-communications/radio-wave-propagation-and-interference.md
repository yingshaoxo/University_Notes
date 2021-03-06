# Radio wave Propagation and Interference

## 无线电波的波段是如何划分的？ 简要说明各波段的作用。

1. ELF极低频 3~30Hz
2. SLF超低频 30~300Hz
3. ULF特低频 300~3000Hz
4. VLF甚低频 3~30kHz
5. LF低频 30~300kHz
6. MF中频 300~3000kHz
7. HF高频 3~30MHz
8. VHF甚高频 30~300MHz
9. UHF特高频 300~3000MHz \|  **短距离通信、移动通信、电视通信** 
10. SHF超高频 3~30GHz
11. EHF极高频 30~300GHz 

## 什么是反射波、绕射波和散射波？

**反射波**: 当电磁波传播中遇到两种不同介质的光滑界面时，如果界面尺寸比电磁波波长大得多，就会产生镜面反射。反射发生于地球表面、建筑物和墙壁表面等。

**绕射波**: 当接收机与发射机之间的无线路径被尖利的边缘阻挡时发生绕射。绕射使得无线电信号绕地球曲线表面传播，使其能传播到阻挡物后面。

**散射波**: 当电波穿行的介质中存在小于波长的物体，并且单位体积内阻挡体个数非常多时，产生散射波。散射波产生于粗糙表面、小物体和其他不规则物体。

## 电波传播时会产生哪些效应？

* **阴影**效应: 由地形结构引起的传播损耗，属于**慢衰落**
* **多徑**效应: 由于散射引起同一信号沿多条路径传播，使得接收到的信号相互叠加、起伏变化大，属于**快衰落**
* **多普勒**效应: 由于物体高速移动，使得信号频率产生偏移，属于**快衰落**

## 信号的衰落是怎样产生的？ 快衰落与慢衰落有何不同？

产生: 移动通信中，由于散射次数很多，接收点所收到的`信号的强度(电平值)`随机起伏

快衰落: 信号`瞬时`起伏变化

慢衰落: 信号`慢速`起伏变化

## 信道有哪些类型？ 各有什么特点？

### 狭义上

1. 有线信道: 电缆、光缆 ； 稳定、可靠
2. 无线信道: 空气 ； 方便、灵活

### 广义上

1. 调制信道
2. 编码信道

## 移动通信的噪声有哪些？

* **无线电**噪声: 其他无线电
* **工业**噪声: 其他电气设备 
* **天电**噪声: 来自大自然、宇宙
* **内部**噪声: 来自设备本身的电气元件

## 移动通信中的干扰有哪些？

* **同信道\(同频\)**干扰: 一山不容二虎，同一频率在同一区域会互相干扰
* **相邻信道**干扰: 由于频率切分不完全，所以多出来的一部分\(偏移频率信号\)会互相干扰
* **互调**干扰: 由传输系统中的非线性电路引起，内部元器件会互相干扰

## 如何减小或避免邻道干扰？

* 信道间留一定的`间隔`
* 提高接收机的频率`稳定度`和`准确度`

## 如何减小互调干扰？

* 加大`发射机`与`天线`的`距离`
* 采用`单向隔离器件`
* 选用`高级器件`
* 采用`自动功率控制系统`
* 选用`无三阶互调信道组`

