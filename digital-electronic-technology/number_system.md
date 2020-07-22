# Number system

## 1. 基础

Binary\(2进制\)，0、1

Octal\(8进制\)，0~7

Hexadecimal\(16进制\)，0~9 and A~F\(10~15\)

Decimal\(10进制\)，0~9

## 2. 进制转换

2 $$\rightarrow$$ 10

$$
\overset{2}{1}\overset{1}{0}\overset{0}{1} = 1 \times 2^0 + 0 \times 2^1 + 1 \times 2^2 = 5
$$

16 $$\rightarrow$$ 10

$$
\overset{1}{F}\overset{0}{F} = 15 \times 16^0 + 15 \times 16^1 = 255
$$

10 $$\rightarrow$$ 2

$$
\begin{align*}
43 \div 2 &= 21 \ldots 1
\\
21 \div 2 &= 10 \ldots 1
\\
10 \div 2 &= 5 \ldots 0
\\
5 \div 2 &= 2 \ldots 1
\\
2 \div 2 &= 1 \ldots 0
\\
1 \div 2 &= 0 \ldots 1
\\
\text{the resu} &\text{lt is 101011}
\end{align*}
$$

## 3. 编码种类

* 有权值，如`8421码`

$$(0001)_{8421码} = (1 \times 1 + 0 \times 2 + 0 \times 4 + 0 \times 8)_{10}$$

* 无权值，如`格雷码`

