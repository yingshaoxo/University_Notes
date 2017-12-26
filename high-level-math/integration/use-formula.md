polynomial
多项式
___

Basically, there are two types of indefinite integral formula.

One is `polynomial`, which composed by $$+$$ and $$-$$

Another is `composite function`, which composed by $$\times$$ and $$\div$$
___

For the first type of integral, we use basic formula to each part of it directly:
$$
\begin{align*}
&\int \frac{3x^2 - 2x + 1}{x} dx 
\\ \\ 
=& \int (3x - 2 + \frac{1}{x}) dx
\\ \\
=& \frac{3}{2}x^2 - 2x + \ln{|x|} + C
\end{align*}
$$
___

For the second one, oh my god, it's very complicate.

Here's a template:
$$
\int f(g(x)) \cdot g^\prime(x)dx
\\ \\
\int f(g(x)) \cdot dg(x)
\\ \\
\int f(u) \cdot du
$$

Let's do some exercise:
$$
\begin{align*}
&\int xe^{-x^2} \cdot dx 
\\ \\
=& \int e^{-x^2} \cdot x dx    &\text{//composite function in front}
\\ \\
=& (-\frac{1}{2}) \int e^{-x^2} \cdot (-2)x dx    &\text{//find a way to make x = } (-x^2)^\prime = -2x \text{ while keeping equation's balance}
\\ \\
=& (-\frac{1}{2}) \int e^{-x^2} \cdot d(-x^2)    &\text{//we knew }g^\prime(x)dx = dg(x)
\\ \\
=& (-\frac{1}{2}) e^{-x^2} + C    &\text{//see } -x^2 \text{ as a part, then apply basic integral formula}
\end{align*}
$$

$$
\begin{align*}
\\ \\ \\
&\int \cos(1-3x) \cdot dx
\\ \\
=&\int \cos(1-3x) \cdot 1dx    &\text{//don't forget 1}
\\ \\
=& (-\frac{1}{3})\int \cos(1-3x) \cdot (-3)1dx    &\text{//find a way to make 1 to -3 while keeping equation's balance}
\\ \\
=& (-\frac{1}{3})\int \cos(1-3x) \cdot d(1-3x)    &\text{//} \frac{dy}{dx} dx = dy
\\ \\
=& (-\frac{1}{3}) \sin(1-3x) + C    &\text{//see 1-3x as a part, then use basic formula}
\\ \\ \\
\end{align*}
$$
___

From these exercises, we know a criticle principle is: $$x$$ of $$dx$$ is the original function, it can be just a $$x$$, it also can be, for example, $$x^2$$.

$$
\begin{align*}
\int (x) dx^2 = \int ((x^2)^\prime \cdot x) dx = \int (2x \cdot x) dx = \int (2x^2) dx
\end{align*}
$$

$$
\begin{align*}
\\
&\int (1 \cdot x) dx    &\text{where's 1 come from? } x^\prime = 1
\end{align*}
$$






