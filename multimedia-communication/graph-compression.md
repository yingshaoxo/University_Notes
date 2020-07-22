# Graph Compression

## 一、分类

形式: 实际、抽象

亮度: 黑白、灰度

光谱: 黑白、彩色

维度: 1D, 2D, ...

## 二、人的视觉特性

### 1. 视觉的适应性

所有的感觉都基于对比。如果你突然进入暗室，需要过一段时间，你才能看清东西。

### 2. 对比度特性

$$C = \frac{Light_{max} + Light_{env}}{Light_{min} + Light_{env}} = \frac{最大亮度+环境亮度}{最小亮度+环境亮度}$$

### 3. 视觉的`残留`与`闪烁`

残留: 人的视觉采集器的`采集速度`有限，你可以趁它没来得及反应，送上`下一幅图片`，这样`人类`就会以为他看到的是`连续的真实画面`。\(比如电影就是由 frames 组成的，a frame = a picture\)

闪烁: 频率不高的脉冲，才会让人有闪烁感。

## 三、颜色

### RGB

red, green, blue

### HSB

hue: 色调，光的颜色，取决于光的波长

saturation: 颜色深浅，即与黑色混合的程度，越高越纯、越不黑

brightness: 亮度

### YUV

### HSL

hue, saturation, lightness

### HSV

hue, saturation, value

## 四、图像数字化

### 采样: 像素化

HD: High Definition

720P: 1280x720；高清

1080P: 1920x1080；`隔行扫描`属于`高清`；`逐行扫描`属于`全高清`

4K: 4096x2160

### 量化: 描述每个像素

如`灰度`，0~255

如`RGB`，若一个`像素成分`为`8bit`，则每个像素为 8x3=24 bit

如`黑白`，0 or 1

## 五、图像编码

主要是`预测编码`

* 帧内预测: 如 H.264
* 帧间预测: 如 H.265。利用`下一frame`相对于`上一frame`产生的`移动(或偏移)信息`，来还原图像。

具体的标准有:

* JPEG2000
* CIF: common intermediate format
* H.261、262、263、264、265: block -&gt; macro-block -&gt; group of block -&gt; picture. \(A block is 8x8 pixels\)

