### What's the purpose of 3 basic components in AP circuit?

> If we need to block DC, we use a capacitor. 它具有充放电特性和阻止直流电流通过，允许交流电流通过的能力。

> If we need to block very high frequency AC, we use an inductor. 如果电感器在没有电流通过的状态下，电路接通时它将试图阻碍电流流过它；如果电感器在有电流通过的状态下，电路断开时它将试图维持电流不变。类似于稳(压)器。

> If we need to design a filter, we (can) use resistors, capacitors and inductors. 

___

### As the previous

As far as I see, no matter in AC or DC, ohm's law is always useful:
$$
\dot U = \dot I \cdot R 
$$

> 1

* But for different components, `R` is different.

  In Resistor, `R` is $$R$$

  In Inductor, `R` is $$wL$$

  In Capacitor, `R` is $$\frac{1}{wC}$$

* And of course, they becomes different in AC circuit with complex number(复数).
  $$R$$ becomes $$R$$
  $$wL$$ becomes $$jwL$$
  $$\frac{1}{wc}$$ becomes $$-j \cdot \frac{1}{wc}$$
  
* Don't ask me how these things comes from, it's too complex to me to answer. Just remember it.

> 2

For each items, we no longer call them $$R$$, instead, we call them $$Z$$ (复阻抗)

如果几个`阻抗`通过`串`或`并`合在一起， we call them `复阻抗`

> 3

于是，和 DC analysis 一样，串联电阻相加，并联$$\frac{(R1 \times R2)}{(R1+R2)}$$

只是运算上要注意很多事，比如:

$$
\begin{align*}
&\frac{a_1 \angle{b_1}}{a_2 \angle{b_2}} = \frac{a_1}{a_2} \cdot \angle{(b_1 - b_2)}
\\ \\
&a_1 \angle{b_1} \times a_2 \angle{b_2} = a_1 \cdot a_2 \angle{(b_1 + b_2)}
\end{align*}
$$

If you want to do some addition or subtraction, convert your equations to another 复数形式 first (like $$a + jb$$)

> 4 * (not important)

如果得到的复阻抗，虚部为正，电感器起主导作用，整体电路呈感性

如果得到的复阻抗，虚部为负，电容器起主导作用，整体电路呈容性