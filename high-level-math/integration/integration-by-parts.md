`Integration by parts` is a method to find integrals of products.  
___

$$
\begin{align*}
\text{Product Rule} &\rightarrow \text{Integration by Parts}
\\ \\
\frac{d}{dx}[f(x)g(x)] &= f^\prime(x)g(x) + f(x)g^\prime(x)
\\ \\
f(x)g(x) &= \int f^\prime(x)g(x) \cdot dx + \int f(x)g^\prime(x) \cdot dx
\\ \\
f(x)g(x) - \int f^\prime(x)g(x) \cdot dx &= \int f(x)g^\prime(x) \cdot dx
\\ \\
&\Downarrow
\\ \\
\int f(x)g^\prime(x) \cdot dx &= f(x)g(x) - \int f^\prime(x)g(x) \cdot dx
\end{align*} 
$$
___

$$
\begin{align*}
\int f(x)g^\prime(x)dx &= f(x)g(x) - \int f^\prime(x)g(x) \cdot dx
\\ \\
\int x \cos{x} \cdot dx &=  x \sin{x} - \int 1 \sin{x} \cdot dx
\\ \\
&= x \sin{x} - (-\cos{x} + C)
\\ \\
&= x \sin{x} + \cos{x} - C
\\ \\
&= x \sin{x} + \cos{x} + C
\end{align*}
$$
___

$$
\begin{align*}
& \int f(x)g^\prime(x) \cdot dx = f(x)g(x) - \int f^\prime(x)g(x) \cdot dx
\\ \\
\int (\ln{x}) dx = \int (\ln{x}) \cdot 1 dx &= \ln{x} \cdot x - \int \frac{1}{x} \cdot x dx
\\ \\
&= \ln{x} \cdot x - x + C
\end{align*}
$$
___

$$
\begin{align*}
\int f(x)g^\prime(x) \cdot dx &= f(x)g(x) - \int f^\prime(x)g(x) \cdot dx
\\ \\ \\
\int x^2 e^x dx &= x^2 e^x - \int 2x e^x dx
\\ \\
\int x^2 e^x dx &= x^2 e^x - 2\int x e^x dx
\\ \\ \\
\int x e^x dx &= x e^x - \int 1 e^x dx
\\ \\
&= x e^x - e^x
\\ \\ \\
\int x^2 e^x dx &= x^2 e^x - 2(x e^x - e^x)
\\ \\
&= x^2 e^x - 2x e^x + 2e^x
\end{align*}
$$
___
