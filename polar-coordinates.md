To be honest, it should be called `Polar Coordinate System`

> In mathematics, the polar coordinate system is a two-dimensional coordinate system in which each point on a plane is determined by a distance from a reference point and an angle from a reference direction.

![](/assets/polar_coordinates.png)

* The `reference point` (analogous to the origin of a Cartesian coordinate system, the center point) is called the `pole`
* The `ray` from the pole in the reference direction is the `polar axis`

You can represent any point in this system with `(distance, angle)`, for example, `(3, 60 degree)`

or generally, $$(\rho, \theta)$$

$$\rho$$: rho

$$\theta$$: theta

___

### Converting between polar and Cartesian coordinates

$$
x = \rho \cdot \cos{\theta}
$$

$$
y = \rho \cdot \sin{\theta}
$$

$$
\rho = \sqrt{x^2 + y^2}
$$

___

# Question and Answers

___

#### In polar coordinate system, a circle equation is $$\rho = 8 \cdot \sin{\theta}$$, a line equation is $$\theta=\frac{\pi}{3}$$, what's the max distance for a point at that circle to the line?

> the answer is 6

##### First, we need to convert all information from `polar coordinate` to `Cartesian coordinate`:

###### 1. circle
$$
\begin{align*}
\rho &= 8 \cdot \sin{\theta}
\\
\rho &= 8 \cdot \frac{y}{\rho}
\\
{\rho}^2 &= 8y
\\
x^2 + y^2 &= 8y
\\
x^2 + y^2 - 8y &= 0
\\
x^2 + (y-4)^2 &= 16 = 4^2
\\ 
\end{align*}
$$
so now we know the center point of that circle is `(0, 4)`, radius of the circle is `4`

###### 2. line
we know $$\theta=\frac{\pi}{3}$$ is nothing but a line of 60 degree angle.

And we also know a general line could be represented as $$y = slope \cdot x$$

And $$slope = \tan(\theta)$$

so:
$$
\begin{align*}
slope &= \tan\frac{\pi}{3}
\\
&= \sqrt{3}
\\ \\
y &= \sqrt{3} \cdot x
\\ 
\end{align*}
$$

##### How to get the max distance?

Inner a circle, `diameter` is the longest line segment you can get.

> A special line drawn inside a circle is called a chord. A chord can be of different lengths. The longest length of the chord is called a diameter. Two times the radius makes a diameter.

And for the distance between a point($$x_0, y_0$$) and a line($$ax + by + c = 0$$), there's a formula for it:

$$
distance = \frac{|a(x_0) + b(y_0) + c|}{\sqrt{a^2 + b^2}}
$$ 

So first, we need to choose a line as close a diameter as possible.

For some reason, people already known `the distance between a line and circle center` + `the radius of that circle` = `the max distance for a point at that circle to the line`.

so:
$$
\begin{align*}
\text{distance between circle center and line} &= \frac{|\sqrt{3} \cdot 0 + (-1) \cdot (-4)|}{\sqrt{\sqrt{3}^2 + 1^2}}
\\
&= \frac{4}{2}
\\
&= 2
\\ \\
\text{max distance} &= 4 + \text{radius of that circle}
\\
\text{max distance} &= 4 + 2
\\
\text{max distance} &= 6
\end{align*}
$$

___

Thank you for reading, I love the feeling of doing this.