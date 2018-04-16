#### Integration by parts

$$
\begin{align*}
\\ \\
\int f(x)g^\prime(x)dx &= f(x)g(x) - \int f^\prime(x)g(x) \cdot dx
\\ \\
&\Downarrow
\\ \\
\int_a^b f(x)g^\prime(x)dx &= f(x)g(x)|_a^b - \int_a^b f^\prime(x)g(x) \cdot dx
\end{align*}
$$
___

#### Substitution method

$$
\begin{align*}
&\int_1^2 \frac{1}{\sqrt{5x-1}} \cdot dx
\\ \\
&t = \sqrt{5x-1}
\\ \\
& t^2 = 5x-1
\\ \\
&\frac{t^2 + 1}{5} = x
\\ \\
&d[\frac{1}{5} (t^2 + 1)] = dx
\\ \\
&\frac{1}{5} (2t) dt = dx
\\ \\
& x | 1 \rightarrow 2
\\
& t | \sqrt{5 \cdot 1 -1} \rightarrow \sqrt{5 \cdot 2 -1}
\\
& t | 2 \rightarrow 3
\\ \\
&\int_2^3 \frac{1}{t} \cdot (\frac{1}{5} (2t) dt) 
\\ \\
&= \int_2^3 \frac{2}{5} \cdot dt
\\ \\
&= (\frac{2}{5} \cdot t)|_2^3
\\ \\
&= \frac{6}{5} - \frac{4}{5}
\\ \\
&= \frac{2}{5}
\end{align*}
$$