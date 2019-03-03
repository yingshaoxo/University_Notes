### 光纤的结构

纤芯、包层、涂覆层

折射率: 纤芯($$n_1$$) > 包层($$n_2$$)

包层直径统一为$$125 \mu m$$

纤芯为$$65 \mu m 或 9 \mu m$$

溶接需去包层

实际导通率以 `OTDR(Optical time-domain reflectometer)` 为准

___

### 光纤导光原理

反射(镜面对称)、折射(光入水)

全反射: 没有折射，只有反射

___

空气到纤芯有一定折射

光源入射角越小越好

___

$$
\begin{align*}
数值孔徑 = NA = \sin(\theta_{max}) = \sqrt{ {n_1}^2 - {n_2}^2 }
\end{align*}
$$

> 数值孔徑表示光纤接收入射光的能力。

> $${\theta}_{max}$$ 表示最大入射角

* 不要直视激光
* 溶接时，数值孔徑需一致(同厂家、型号、批次)

___

### 光纤分类

##### 1. 按波长

* 短波: $$\lambda = 850 nm$$ | 短距离通信
* 长波: $$\lambda = 1310 nm$$ or $$\lambda = 1550$$

##### 2. 按模式

* 单模(SMF)(Single-Mode Fiber)
* 多模(MMF)(Multi-Mode Fiber)

___

$$归一化频率 = V = \frac{2\pi}{\lambda} \cdot a \cdot \sqrt{ {n_1}^2 - {n_2}^2 }$$

> $$a = 纤芯半径$$，$$\lambda = 光源波长$$

如果$$V > 2.405$$，多模

如果$$V < 2.405$$，单模 $$\Rightarrow$$ $$\lambda > \frac{2 \pi}{2.405} \cdot a \cdot NA = 单模传输的截止波长$$

> 单、双模划分取决于波长

___

`多模`会产生`模式色散`，降低传输容量(速率)，只适合短距离通信

色散: 在光学中，将`复色光`分解成`单色光`的过程，叫光的`色散`； `单色光`为红，绿，蓝“三原色”

___

单模`芯徑`一定细($$9 \mu m$$)，细的不一定单模

多模`芯徑`一定粗($$65 \mu m$$)，粗的不一定单模

___

##### 3. 按折射率

> 以下皆指 光纤到包层 的折射率变化

* 阶跃型
* 渐变型: 可以减少色散