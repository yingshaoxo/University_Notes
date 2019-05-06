# Series

Series is actually the sum of some array \(or list\).

$$\sum_{n=1}^{4} n = 1 + 2 + 3 + 4$$

$$\sum_{n=1}^{\infty} n = 1 + 2 + 3 + 4 + ...$$

Say if we got an series:

$$\sum_{n=1}^{\infty} u_n = u_1 + u_2 + u_3 + u_4 + ... + u_{\infty}$$

If we can find a way to represent its sum, for example,

$$S_n = u_1 + u_2 + u_3 + u_4 + ... + u_n$$

If $$S_n$$ exists and it's not $$\infty$$, then we could say $$S_n$$ approaching to a constant

Also, in the same way, we could say as n goes up, $$\sum_{n=1}^{\infty} u_n$$ converges to a constant

In other words, the series $$\sum_{n=1}^{\infty} u_n$$ converges; or $$\sum_{n=1}^{\infty} u_n$$ is a convergent series

converge 收敛

diverge 发散

Let's get started!

$$\sum_{n=1}^{\infty} u_n \text{ converges} \Rightarrow \lim_{n \to \infty}{u_n} = 0$$

$$\sum_{n=1}^{\infty} u_n \text{ diverges} \Leftrightarrow \lim_{n \to \infty}{u_n} \not= 0$$

We all know $$u_n$$ is the last item in a series, if the sum of that series want to be a constant, the last item must equal to 0, so $$\lim_{n \to \infty}{u_n}$$ has to be 0

If it's not, well, as if the last item of that series not 0, the sum of that series is uncertain, so we say the series diverges

harmonic series

$$\sum_{n=1}^{\infty} \frac{1}{n} = \frac{1}{1} + \frac{1}{2} + \frac{1}{3} + ...$$

$$\lim_{n \to \infty}{\frac{1}{n}} = 0$$

But it's a `divergent` series

Geometric Series \(几何级数\)

$$\sum_{n=0}^{\infty} q^n$$

When $$|q| < 1$$, `converges`

Why? Just think about it, as `n` goes up, everytime, the last item of this series times a value which less than 1, so the item will be smaller and smaller, in the end, the last item of that series became zero, that means, the sum of this series is a constant, also, we could say it converges, that series is a convergent series.

When $$|q| \ge 1$$, `diverges`

Why? Just think about it, as `n` goes up, everytime, the last item of this series times a value which greater or equal to 1, so the item will be bigger and bigger, in the end, the last item of that series becomes infinite, that means, the sum of this series is also infinity, so, we say it diverges, that series is a divergent series.

p-series \(p级数\)

$$\sum_{n=1}^{\infty} \frac{1}{n^p}$$

When $$p > 1$$, `converges` \(收敛\)

Why? If $$p > 1$$, everytime as `n` goes up, $$n^p$$ gets bigger and bigger, until infinite, so $$\frac{1}{\infty} = 0$$. The sum of that series has limitation, it's a constant, so the series converges.

When $$p \le 1$$, `diverges` \(发散\)

Why? If $$p \le 1$$, everytime as `n` goes up, $$n^p$$ gets smaller and smaller, until 0, so $$\frac{1}{0} = \infty$$. The sum of that series does not have a limitation, it's infinite, so the series diverges.

Positive series \(正向级数\)

A series with terms that are all positive.

$$\sum_{n=1}^{\infty} u_n \text{ , } (u_n > 0)$$

$$\text{Set } \text{ } l = \lim_{n \to \infty}{\frac{u_{n+1}}{u_n}}$$

when $$l < 1$$ , $$u_{n+1} < u_n$$ , `converges`

when $$l > 1$$ , $$u_{n+1} > u_n$$ , `diverges`

when $$l = 1$$ , $$u_{n+1} = u_n$$ , `uncertain`

alternating series \(交错级数\)

$$\sum_{n=0}^{\infty} (-1)^n a_n$$

The signs of the general terms alternate between positive and negative.

If the following conditions are met, `converges` \(otherwise, diverges\):

1. $$u_n \ge u_{n+1}$$
2. $$\lim_{n \to \infty} u_n = 0$$

~The first condition said, the last item must be less than before, that's good, in that case, we will not get an infinite number in the last item~

The second condition just like normal series

Power series \(幂级数\)

$$\sum_{n=1}^{\infty} x^n \cdot \text{(an expression which only related n)}$$

The main characteristic of this series is **it has a variable x**

1. If we have a series $$\sum_{n=1}^{\infty} x^n \cdot \frac{1}{n}$$
2. Get `domain of convergence`

   $$
   \begin{align*}
    &\rho = \lim_{n \to \infty} |\frac{\text{n expression}+1}{\text{n expression}}|  = \lim_{n \to \infty} |\frac{\frac{1}{n+1}}{\frac{1}{n}}| = 1
    \\ \\
    &\text{interval of convergece } = (-\frac{1}{\rho}, \frac{1}{\rho}) = (-1, 1)
    \\ \\
    &\because \text{when } x = -\frac{1}{\rho} = -1 \text{ , } \sum_{n=1}^{\infty} \frac{(-1)^n}{n} \text{ converges}
    \\ \\
    &\text{ }\text{ }\text{ }\text{ }\text{ } \text{when } x = \frac{1}{\rho} = 1 \text{ , } \sum_{n=1}^{\infty} \frac{(1)^n}{n} \text{ diverges}
    \\ \\
    &\therefore \text{domain of convergence is } [-1, 1)
    \end{align*}
   $$

3. Get `Sum function`

   $$
   \begin{align*}
    &S(x) = \sum_{n=1}^{\infty} x^n \cdot \frac{1}{n} \text{ , } x \in [-1, 1)
    \\ \\
    &\text{take defivative of }S(x):
    \\ \\
    &S^\prime (x) = \frac{1}{n} \cdot (\sum_{n=1}^{\infty} x^n)^\prime
    \\ \\
    & = \frac{1}{n} \cdot \sum_{n=1}^{\infty} n \cdot x^{n - 1} =  \sum_{n=1}^{\infty} x^{n - 1} = \frac{1}{1 - x}
    \\ \\
    & S(x) = \int_0^x  \frac{1}{1-x} = - \ln(1-x)
    \end{align*}
   $$

All these series, converges if and only if the associated sequence of partial sums converges.

