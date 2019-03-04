### 一、容量计算

#### 1. 文本容量

设分辨率为$$1280 \times 768$$，字符大小为$$8 \times 8$$点阵，每个字符用2字节表示

$$全屏字符 = (\frac{1280}{8} \times \frac{768}{8}) \times 2 \approx 10\ (MB)$$

#### 2. 数字音频

采样率为 44.1 kHz，采样精度为16位的双声道音频

$$1分钟数据量 = (44.1 \times 1000) \times 16 \times 2 \times 60 \approx 10\ (MB)$$

#### 3. 图像容量

$$1024 \times 768$$的彩图，每像素用24bit表示

$$数据量 = 1024 \times 768 \times 24 = 2.25\ (MB)$$

___

### 二、冗余

D = I + R

信息量 = 数据量 - 冗余量

1. 空间: 图像中颜色相近的像素，可以被划归为一个颜色(用`大色块`代替一堆`小色块`)
2. 时间: 如前后帧`背景(音)`相同
3. 结构: 物体表面纹理(3D游戏地面建模就是用的纹理重复技术)
4. 知识: 人脑预先知道的东西不必重复传输(如头下面是身子，如果身子不动，那么就拍脸好了)
5. 视听: 人的听觉、视觉传感器有接收范围，超过就听不到也看不到了
6. 信息熵冗余(编码冗余): ~~过于高深，暂时不解释~~

** 熵(entropy): 注意这个字念shang**

___

### 三、压缩种类

无损: 去掉或减少冗余，压缩比`2:1`到`5:1`

有损: 失真压缩，压缩比`50:1`到`200:1`

___

### 四、压缩的理论基础

#### 1. 信息度量

某事件x，出现的概率为$$P(x_i)$$，$$0 \leq P(x_i) \leq 1$$

该事件信息量 $$I(x_i) = -\log_2{P(x_i)}$$

#### 2. 信息熵

$$H(x) = - \sum_{i=1}^{N} P(x_i) \cdot \log_2 {P(x_i)}$$

![](/assets/entropy_example_question.jpg)

平均码长: $$\bar{L} = \sum_i P(x_i) \cdot n(x_i)$$

无失真条件: $$平均码长  = \bar{L} \geq \frac{H(x)}{\log_2{n}}$$

编码效率: $$\eta = \frac{H(x)}{\bar{L}}$$，百分制

> 百分制 0~100 是对比度量的好方法

___

### 五、压缩的性能比较

* 压缩比: `压缩前`比`压缩后`，越大越好
* 重现质量: 主要指图像、声音
* 压缩、解压的速度