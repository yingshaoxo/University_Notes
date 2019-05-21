> 一阶导数描述函数的单调性和极值

The first derivation described whether the `y` of that function should increasing or decreasing:
$$
\text{First derivation} > 0 \text{ , increasing}
\\
\text{First derivation} < 0 \text{ , decreasing}
\\
$$

First decreasing, then increasing, you'll get a minimum

First increasing, then decreasing, you'll get a maximum
___

Increasing intervals
递增区间

Decreasing intervals
递减区间
___

```
import numpy as np
from scipy.misc import derivative

# define a function
def f(x):
    return x**2
    
# define x range
unit = 0.1
input_x = np.arange(-2, 2 + unit, unit)

# find what x make f prime of x equle 0 
whole_derivative = [(index, derivative(f, x, dx=1e-6)) for index, x in enumerate(input_x)]
x_of_zero_derivative = [input_x[index] for index, d in whole_derivative if abs(d) < 0.1]
the_x = x_of_zero_derivative[len(x_of_zero_derivative)//2]

# get each side derivative of the_x 
left_x = the_x - 1
right_x = the_x + 1
left_derivative = derivative(f, left_x, dx=1e-6)
right_derivative = derivative(f, right_x, dx=1e-6)

# do a conclution
if left_derivative < 0:
    print('from negative infinite to 0, the function is decreasing')
if right_derivative > 0:
    print('from 0 to positive infinite, the function is increasing')
if left_derivative < 0 and right_derivative > 0:
    print('the f({x})={y} is the mininum of x**2'.format(x=int(the_x), y=f(int(the_x))))
```

![](/assets/x^2 for 0 derivative.png)