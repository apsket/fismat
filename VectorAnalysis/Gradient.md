# Gradient

The classical way of introducing the gradient is through the directional derivative of a scalar function of the rectangular coordinates $f(x,y,z)$ with continuous partial derivatives in some some subset $D_0$ of its domain $D$. Consider wanting to compute the derivative of the scalar function at some point $P_0 = (x_0, y_0, z_0)$ in $D_0$ and in the direction defined by the unit vector $\hat{u} = \hat{i}a+\hat{j}b+\hat{k}c$. A half-line $t$ passing through $P_0$ and parallel to the vector $\hat{u}$ can be parametrized as $\vec{t}(s) = \vec{r}_0 + s\hat{u}$ where $s\ge0$ and $\vec{r}_0 = \hat{i}x_0+\hat{j}y_0+\hat{k}z_0$ is the vector that connects the origin to the point $P_0$.

Notice that the the parameter $s$ measures length because the vector specifying direction is unitary, i.e. $\lVert s\hat{u} \rVert = |s|\cdot \lVert \hat{u} \rVert = |s|$. The function evaluated at the points defining the half-line $\vec{t}$ can be parametrized through the same length parameter $s$:

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


