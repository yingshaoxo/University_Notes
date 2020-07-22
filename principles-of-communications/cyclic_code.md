# Cyclic code

`(7, 4)`循环码的生多项式 $$g(x)=x^3+x^2+1$$ , 则`D(1010)`的系循环码是多少？

1.

$$
\begin{align*}
1010 \Rightarrow d(x) = x^3 + x^1
\end{align*}
$$

2.

$$
\begin{align*}
&x^{7 - 4} \cdot d(x)
\\ \\
=&x^3 \cdot (x^3 + x)
\\ \\
=&x^6 + x^4
\end{align*}
$$

3.

$$
\begin{align*}
&rem[(x^6 + x^4), g(x)] = 1
\\ \\
&\text{rem( a , b ) returns the remainder after division of a by b}
\end{align*}
$$

4.

$$
\begin{align*}
c(x) &= x^6 + x^4 + 1
\\
&\Downarrow
\\
10&10001
\end{align*}
$$

## hamming code

$$n = 2^r - 1$$

`n` represents the length of codes

`r` represents the 监督码（不传递信息，只为纠错而加的东西）

