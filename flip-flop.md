# Flip-flop (触发器)

触发器（英语：Flip-flop, FF），中国大陆译作“触发器”、台湾及香港译作“正反器”，是一种有两种稳态的用于储存组件，可记录二进位制数字信号“1”和“0”。

触发器可以分成几种常见的类型： SR(设置－重置，"set-reset"), D(数据或延迟，"data" or "delay"), T(反转，"toggle")，和 JK。

___

#### RS触发器

基本RS触发器又称SR锁存器，是触发器中最简单的一种。
![](/assets/Flip-flop_RS.png)

$$
\begin{align*}
&S: &0, 0, 1, 1
\\
&R: &0, 1, 0, 1
\\
&Q_{next}: &Q, 0, 1, x
\\ \\
&\text{x means 不允许}
\end{align*}
$$

> Anyway, if you use computer, these things doesn't matter.

___

# Rules

R: reset

S: set
___

正常情况，$$R、S$$：

$$
\begin{align*}
set = 1 \text{ , } reset = 0 \text{ , } Q^{n + 1} = 1
\\ \\
set = 0 \text{ , } reset = 1 \text{ , } Q^{n + 1} = 0
\end{align*}
$$

非正常情况，$$\bar{R}、\bar{S}$$：

$$
\begin{align*}
set = 0 \text{ , } reset = 1 \text{ , } Q^{n + 1} = 1
\\ \\
set = 1` \text{ , } reset = 0 \text{ , } Q^{n + 1} = 0
\end{align*}
$$
___

CP(clock pulse)：

当其为高电平时才检测 RS、D or JK 的电平值
___

J = set

K = reset
___

T = 1 ，反相

T = 0 ，保持

___

D = 0 ， 0

D = 1 ， 1
