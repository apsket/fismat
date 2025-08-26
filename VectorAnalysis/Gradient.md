# Gradient

The classical way of introducing the gradient is through the directional derivative of a scalar function of the rectangular coordinates $f(x,y,z)$ with continuous partial derivatives in some some subset $D_0$ of its domain $D$. Consider wanting to compute the derivative of the scalar function at some point $P_0 = (x_0, y_0, z_0)$ in $D_0$ and in the direction defined by the unit vector $\hat{u} = \hat{i}a+\hat{j}b+\hat{k}c$. A half-line $t$ passing through $P_0$ and parallel to the vector $\hat{u}$ can be parametrized as $\vec{t}(s) = \vec{r}_0 + s\hat{u}$ where $s\ge0$ and $\vec{r}_0 = \hat{i}x_0+\hat{j}y_0+\hat{k}z_0$ is the vector that connects the origin to the point $P_0$.

Notice that the the parameter $s$ measures length because the vector specifying direction is unitary, i.e. $\lVert s\hat{u} \rVert = |s|\cdot \lVert \hat{u} \rVert = |s|$. The function along the points defining the half-line $\vec{t}$ is a function of the length parameter $s$ only:

$$
\begin{gather}
f(\vec{r'}\in t) = f(s) \\\\
x(s) = x_0 + s\cdot a \\\\
y(s) = y_0 + s\cdot b \\\\
z(s) = z_0 + s\cdot c
\end{gather}
$$

To compute the directional derivative in the direction of $\hat{u}$, one simply computes the derivative of the above parametrization with respect to $s$ and makes use of the chain rule:

$$
\frac{df}{ds} = \frac{df}{dx}\cdot\frac{dx}{ds} + \frac{df}{dy}\cdot\frac{dy}{ds} + \frac{df}{dz}\cdot\frac{dz}{ds} = \frac{df}{dx}a + \frac{df}{dy}b + \frac{df}{dz}c
$$

The above expression can be identified as a dot product between the unit vector $\hat{u}$ and another vector defined by partial derivatives:

$$
\frac{df}{ds} = \left( \hat{i}\frac{df}{dx} + \hat{j}\frac{df}{dy} + \hat{k}\frac{df}{dz} \right) \bullet \hat{u}
$$

The vector $\hat{i}\partial_{x}f + \hat{j}\partial_{y}f + \hat{k}\partial_{z}f$ is called the gradient of $f$ and usually denoted as $\nabla f$ or $\textnormal{grad} f$. The directional derivative of $f$ in the direction of $\hat{u}$ can then be written as:

$$
\frac{df}{ds} = \nabla f \bullet \hat{u}
$$

This is a product of a vector depending only on position and a vector defining direction.

# Properties of the gradient

The gradient points in the direction of maximum change of the function $f$. To see this notice that in the above expression the directional derivative is maximum when the gradient and the unit vector are parallel. Since the gradient depends only on position, it defines the direction and amount of maximum change.

The gradient is also perpendicular to the level curves of $f$. To see this consider a given level surface $f = f_0$. At any point in this surface, the function $f$ does not change. In particular, fixing a point $P_0$ in the surface $f = f_0$, any curve in the surface and passing through $P_0$ can be parametrized by a single length variable $s'\ge0$. Such curve defines a unit tangent $\hat{u'}$ at $P_0$. Since $f$ does not change along the curve, $df/ds = 0$ at $P_0$ and so the gradient is perpendicular to the tangent to the curve in the surface. This is true for any curve passing through $P_0$ and living in the surface $f = f_0$, so the gradient is perpendicular to the surface at point $P_0$. 



