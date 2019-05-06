# The limitation of a function

> Graph math problem will give you a better experience of solving problems. Imaging too. But so sad that I can't draw graphs for this book on this period of time.

$$
\lim_{x \to \infty}{\frac{1}{x^2}} = 0
$$

Why does this happen? We could imagine, if $$x^2$$ goes on and on, to infinite, $$\frac{1}{x^2}$$ will more and more approaching $$0$$.

There's another limit equation that similar to the above:

$$
\lim_{x \to 0}{\frac{1}{x^7}} = \infty
$$

Why does this happen? If $$x^7$$ approach to $$0$$, $$\frac{1}{x^7}$$ goes bigger and bigger, it's infinite.

As you can see, normally, if you are asked getting the limitation of a basic simple function, all you have to do is calculate the y value of f\(x\).

$$
\begin{align*}
\lim_{x \to 1}{x^2 + 5} &= 6
\\ \\
\lim_{x \to -2}{\sin(x + 2)} &= 0
\\ \\
\lim_{x \to 1}{\sqrt[999]{x^{277}}} &= 1
\end{align*}
$$

![](https://github.com/yingshaoxo/university-notes/tree/cc7cb1e4698c6d680876321163907ff1e1b4ac91/high-level-math/function-limitation-and-continuity-of-function/assets/x%5E2.png)

Above is a graph of $$f(x) = x^2$$.

If I ask you what's the limitation of $$\lim_{x \to 2}{x^2}$$, the real meaning is $$\lim_{x \to 2^-}{x^2}$$ and $$\lim_{x \to 2^+}{x^2}$$ **exist and equal.**

$$\lim_{x \to 2^-}{x^2}$$ means `x` from `less than 2` to `2`, what `y` will be approaching

$$\lim_{x \to 2^+}{x^2}$$ means `x` form `greater than 2` to `2`, what `y` will be approaching to.

Here comes a new definition of continuity when you think about it. No matter greater than 2 or less than 2, they all approaching 4, this means they are continuous in x

