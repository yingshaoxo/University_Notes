# Logic expressions

> In China, everything becomes weird.

## 一、Basic thing

$$A + B$$ means $$(A \text{ or } B)$$

$$A \cdot B$$ means $$(A \text{ and } B)$$

$$\overline{A}$$ means $$(\text{not } A)$$

## 二、Simple rule

$$AB + AC = A(B + C)$$

$$\overline{AB} = \overline{A} + \overline{B}$$

$$\overline{A + B} = \overline{A} \cdot \overline{B}$$

## 三、Complex rule

$$A + \overline{A}B = A + B$$

$$
\begin{align*}
&AB + \overline{A}C + BC
\\ \\
=& AB + \overline{A}C + BC \cdot (A + \overline{A})
\\ \\
=& AB + \overline{A}C + ABC + \overline{A}BC
\\ \\
=& AB(C + 1) + \overline{A}C(B + 1)
\\ \\
=& AB + \overline{A}C
\end{align*}
$$

