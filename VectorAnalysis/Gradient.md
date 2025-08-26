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
\frac{df}{ds} = \frac{\partial f}{\partial x}\cdot\frac{\partial x}{\partial s} + \frac{\partial f}{\partial y}\cdot\frac{\partial y}{\partial s} + \frac{\partial f}{\partial z}\cdot\frac{\partial z}{\partial s} = \frac{\partial f}{\partial x}a + \frac{\partial f}{\partial y}b + \frac{\partial f}{\partial z}c
$$

The above expression can be identified as a dot product between the unit vector $\hat{u}$ and another vector defined by partial derivatives:

$$
\frac{df}{ds} = \left( \hat{i}\frac{\partial f}{\partial x} + \hat{j}\frac{\partial f}{\partial y} + \hat{k}\frac{\partial f}{\partial z} \right) \bullet \hat{u}
$$

The vector $\hat{i}\partial_{x}f + \hat{j}\partial_{y}f + \hat{k}\partial_{z}f$ is called the gradient of $f$ and usually denoted as $\nabla f$ or $\textnormal{grad} f$. The directional derivative of $f$ in the direction of $\hat{u}$ can then be written as:

$$
\frac{df}{ds} = \nabla f \bullet \hat{u}
$$

This is a product of a vector depending only on position and a vector defining direction.

# Properties of the Gradient

The gradient points in the direction of maximum change of the function $f$. To see this notice that in the above expression the directional derivative is maximum when the gradient and the unit vector are parallel. Since the gradient depends only on position, it defines the direction and amount of maximum change.

The gradient is also perpendicular to the level curves of $f$. To see this consider a given level surface $f = f_0$. At any point in this surface, the function $f$ does not change. In particular, fixing a point $P_0$ in the surface $f = f_0$, any curve in the surface and passing through $P_0$ can be parametrized by a single length variable $s'\ge0$. Such curve defines a unit tangent $\hat{u'}$ at $P_0$. Since $f$ does not change along the curve, $df/ds = 0$ at $P_0$ and so the gradient is perpendicular to the tangent to the curve in the surface. This is true for any curve passing through $P_0$ and living in the surface $f = f_0$, so the gradient is perpendicular to the surface at point $P_0$. 



# Other Coordinate Systems

Consider other coordinate systems with coordinates $(u, v, w)$ that can be mapped to the standard Cartesian coordinates $(x, y, z)$. One could be tempted to write the gradient with respect to these coordinates as $\hat{e_u} \partial_{u}f + \hat{e_v} \partial_{v}f + \hat{e_w} \partial_{w}f$, where the vectors are the orthonormal basis $\hat{e_i} = \partial_{i}\vec{r} / \lVert \partial_{i}\vec{r} \rVert$ of the coordinate system and which could be position dependent. However, if we want to have the gradient to have the same geometrical meaning as the one defined by the rectangular coordinates, the gradient should have a different form.


To deduce the form of the gradient, consider the scalar function dependent on the Cartesian coordinates $f(x, y, z)$. Notice a few things. First, the directions of the change of each coordinate are perpendicular to one another. Second, each any change in a coordinate defines a measure of length in a given direction. Consider now another set of Cartesian coordinates $(x',y',z')$ that differ from $(x, y, z)$ only in the alignmento of the coordinate axes. That is, the primed and un-primed rectangular coordinate systems are different only up to a rotation. The function $f$ as defined from physical space can be written to depend on either of these coordinate systems without a preference, i.e. $f(x, y, z) = f(x',y',z')$ once the coordinates are mapped to the same point in physical space $(x, y, z) \leftrightarrow (x',y',z')$. The gradient evaluated at a point in space is independent of the coordinate system chose, so one must have:

$$
\nabla f(x,y,z) = \nabla f(x',y',z'), \textnormal{ with } (x, y, z) \leftrightarrow (x',y',z')
$$

which means

$$
\hat{i}\frac{\partial f}{\partial x} + \hat{j}\frac{\partial f}{\partial y} + \hat{k}\frac{\partial f}{\partial z} = \hat{i'}\frac{\partial f}{\partial x'} + \hat{j'}\frac{\partial f}{\partial y'} + \hat{k'}\frac{\partial f}{\partial z'}, \textnormal{ with } (x, y, z) \leftrightarrow (x',y',z')
$$

So the gradient can be understood as being computable as the rate of change of the function with respect to the length coordinate of each of the orthogonal directions. We understand $\partial_{u} f$ to mean the rate of change of the function with respect to the coordinate $u$. We also know that $\lVert \partial_u \vec{r} \rVert$ is the ratio of change in length of physical space to the change in the coordinate $u$. Then $\partial_u f / \lVert \partial_u \vec{r} \rVert$ is the rate of change of $f$ with respect to the change in length associated to $u$, in the direction $\hat{e}_u$.

Thus, for a set of generalized coordinates $(u, v, w)$ that define an orthonormal basis $\{\hat{e}_i\}$ at each point in space, one could find the gradient as:

```math
\nabla f(u, v, w) = \hat{e}_u \frac{1}{\lVert \partial_u \vec{r} \rVert} \cdot \frac{\partial f}{\partial u} + \hat{e}_v \frac{1}{\lVert \partial_v \vec{r} \rVert} \cdot \frac{\partial f}{\partial v} + \hat{e}_w \frac{1}{\lVert \partial_w \vec{r} \rVert} \cdot \frac{\partial f}{\partial v}
```



For cylindrical coordinates where $(\rho, \theta, z)$ parametrize position in physical space as $\vec{r} = \hat{i} \rho\cos{\theta} +  \hat{j} \rho\sin{\theta} + \hat{k} z$, the scaling factors are:

```math
\begin{gather}
\left\lVert \frac{\partial \vec{r}}{\partial \rho} \right\rVert = \left\lVert \hat{i} \cos{\theta} +  \hat{j} \sin{\theta} \right\rVert =  1 \\\\
\left\lVert \frac{\partial \vec{r}}{\partial \theta} \right\rVert = \left\lVert -\hat{i} \rho\sin{\theta} +  \hat{j} \rho\cos{\theta} \right\rVert =  \rho \\\\
\left\lVert \frac{\partial \vec{r}}{\partial z} \right\rVert = \left\lVert \hat{k} \right\rVert =  1
\end{gather}
```

One could also have noted that the coordinates $\rho$ and $z$ are already length coordinates. The coordinate $\theta$ is an angle with circles in the $xy$-plane as coordinate curves so, a point in space being fixed, the arc length associated to the $\theta$ coordinate is $\Delta s = \rho_0\Delta\theta$ and so the rate of change of arc length is simply $\rho$. The gradient in cylindrical coordinates becomes:

```math
\nabla f(\rho, \theta, z) = \hat{e}_\rho \frac{\partial f}{\partial\rho} + \hat{e}_\theta \frac{1}{\rho}\cdot\frac{\partial f}{\partial\theta} + \hat{e}_z \frac{\partial f}{\partial z}
```

For spherical coordinates, $(r, \theta, \phi)$ (with $\theta$ as the polar angle) parametrize position as $\vec{r} = \hat{i} r\sin{\theta}\cos{\phi} + \hat{j} r\sin{\theta}\sin{\phi} + \hat{k}r\cos{\theta}$. The variable $r$ is already a length variable. The variables $\theta$ and $\phi$ are angular variables with readily identified relations to arc length: $r\Delta\theta$ and $r\sin{\theta}\Delta\phi$, respectively. One then has for the gradient:

```math
\nabla f(r, \theta, \phi) = \hat{e}_r \frac{\partial f}{\partial r} + \hat{e}_\theta \frac{1}{r}\cdot\frac{\partial f}{\partial\theta} + \hat{e}_\phi \frac{1}{r\sin{\theta}}\cdot \frac{\partial f}{\partial \phi}
```


# Another Approach to the Gradient in Curvilinear Coordinates

One can also derive the form of the gradient in curvilinear coordinates by projecting the gradient in Cartesian coordinates in the basis defined by the curvilinear coordinates. For the position parametrized by coordinates $\vec{r}(u, v, w) = \hat{i}x(u,v,w) + \hat{j}y(u,v,w) + \hat{k}z(u,v,w)$, the unit vector associated to $u$ is:

```math
\hat{e}_{u} = \frac{1}{\lVert \partial_{u}\vec{r} \rVert} \cdot \frac{\partial \vec{r}}{\partial u} = \frac{1}{\lVert \partial_{u}\vec{r} \rVert}  \cdot\left( \hat{i} \frac{\partial x}{\partial u} + \hat{j} \frac{\partial y}{\partial u} + \hat{k} \frac{\partial z}{\partial u} \right)
```

Taking the gradient in Cartesian coordinates,

```math
\nabla f = \hat{i}\frac{\partial f}{\partial x} + \hat{j}\frac{\partial f}{\partial y} + \hat{k}\frac{\partial f}{\partial z}
```

The component of the gradient in $\hat{e}_{u}$ is

```math
\nabla f \bullet \hat{e}_{u} = \left( \hat{i}\frac{\partial f}{\partial x} + \hat{j}\frac{\partial f}{\partial y} + \hat{k}\frac{\partial f}{\partial z} \right) \bullet \frac{1}{\lVert \partial_{u}\vec{r} \rVert} \left( \hat{i} \frac{\partial x}{\partial u} + \hat{j} \frac{\partial y}{\partial u} + \hat{k} \frac{\partial z}{\partial u} \right) = \frac{1}{\lVert \partial_{u}\vec{r} \rVert} \cdot \left( \frac{\partial f}{\partial x} \cdot \frac{\partial x}{\partial u} + \frac{\partial f}{\partial y} \cdot \frac{\partial y}{\partial u} + \frac{\partial f}{\partial z} \cdot \frac{\partial z}{\partial u} \right) = \frac{1}{\lVert \partial_{u}\vec{r} \rVert} \cdot \frac{\partial f}{\partial u}
```

After identifying the chain rule. The component of the gradient in the directions $\hat{e}_v$ and $\hat{e}_w$ follows similarly. The gradient is therefore

```math
\nabla f(u, v, w) = \hat{e}_u \frac{1}{\lVert \partial_u \vec{r} \rVert} \cdot \frac{\partial f}{\partial u} + \hat{e}_v \frac{1}{\lVert \partial_v \vec{r} \rVert} \cdot \frac{\partial f}{\partial v} + \hat{e}_w \frac{1}{\lVert \partial_w \vec{r} \rVert} \cdot \frac{\partial f}{\partial v}
```

Which is exactly the same form as the one obtained before.
