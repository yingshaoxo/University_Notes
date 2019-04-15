## 有损音频编码

#### 增量调制(delta modulation)

![](/assets/DELTA-MODULATION.png)

斜率过载: `输出`不能适应`输入`的`快速变化` (Delta 太大，没办法`跟踪`快速的`斜率变化`)

#### 自适应增量调制(adaptive delta modulation)

增量调制的一种改进。其特点是: 自动调节 delta。(感觉和 PCM 一模一样)

#### 差分脉冲编码调制(Differential Pulse code modulation)

![](/assets/Differential Pulse code modulation.jpg)

动态变化，只传变化值(不传原值)，减少传输的 data

####　自适应差分脉冲编码(Adaptive Differential Pulse code modulation)

#### 音频子带编码: 针对不同频带，作不同的编码(类似于分层抽样)

理论根据: 听觉的`隐蔽特性`

#### 矢量量化(Vector Quantization)

类似于字典编码，只不过是用`一小串代码`代表`一大串代码` (如`表情包`可以用`一串数字`来`标识`)

#### 线性预测编码(Linear predictive coding)

#### 感知编码(Perceptual Coding): 只记录那些能被人听到的声音

比如 mp3

___

## 音频编码标准

![](/assets/音频编码标准.png)

> MP3 是 MPEG-1 中的第三层

> AAC: advanced audio coding

> HDTV: high definition television