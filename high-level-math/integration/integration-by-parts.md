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
\int f(x)g^\prime(x) \cdot dx &= f(x)g(x) - \int f^\prime(x)g(x) \cdot dx
\\ \\
\int x \cos{x} dx &=  x \sin{x} - \int 1 \sin{x} \cdot dx
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

