#### 一. 二极管的单向导电性
![](/assets/diode.png)
```
\draw (0, 0) to [empty diode, v_<=$diode$](4, 0);
```
1. 三角形那边是`P型半导体`，竖线那边是`N型半导体`
2. 你只需要记住三角形那边是正极流入，竖线那边是负极流出，电流才会流通就行了

#### 二、volt-ampere characteristic （伏安特性）
![](/assets/volt-ampere characteristic.png)
1. 正向（正半轴；三角形那边输入正电）
$$
\begin{align*}
\text{OA} &\longrightarrow \text{从无法导通到导通}
\\ \\
&\Downarrow
\\ \\
\text{导通硅板材质}&\text{二极管需要 } 0.6 - 0.7 V \text{ 的电压}
\\
\text{导通锗板材质}&\text{二极管需要 } 0.2 - 0.3 V \text{ 的电压}
\end{align*}
$$
2. 反向（负半轴；竖线那边输入正电）
$$
\begin{align*}
\text{O to Breakdown Point} &\longrightarrow \text{截止，基本不通电，该二极管可看作开路}
\\ \\
\text{Breakdown Point to } \infty &\longrightarrow \text{击穿，二极管被烧坏，可将它看作短路}
\end{align*}
$$

#### 三、看电路图法则
从所求电子元件的电压正极出发，每经过一个节点，追踪出每一条电子移动的线路或轨迹