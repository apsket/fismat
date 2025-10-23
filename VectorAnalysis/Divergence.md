# Divergence

The divergence is standardly introduced in different ways depending on the context. We begin by introducing it through the system-free definition of divergence from the flux of a field, and later derive algebraic expressions for it.

Consider a vector field $`\vec{F}`$ and a closed piecewise smooth surface $\delta V$ enclosing volume $V$. The flux of $`\vec{F}`$ through the surface $`\delta V`$ is

```math
\iint_{\delta V} \vec{F} \cdot \hat{n} dS \tag{1}
```

with $\hat{n}$ a unit vector normal to the surface at each point, with the convention of pointing outwards from the enclosed volume.

If one dividides the volume into $`N`$ volumes, then

```math
\sum_{i=1}^{N} \iint_{S_{i}} \vec{F} \cdot \hat{n} dS_{i}  = \iint_{\delta V} \vec{F} \cdot \hat{n} dS \tag{2}
```

because any given common surface $`D`$ to sub-surfaces $`S_{i}`$, $`S_{j}`$ contributes to zero in total. The integral at a common surface contributes with different signs at each of $`S_{i}`$, $`S_{j}`$ because their unit normals are always oppositely oriented at every point on the common surface.

The fluxes are too surface dependent and do not provide any information inherent to the field, they are extensive quantities. Moreover, shrinking the volume of interest to zero would cause the flux to vanish. We could scale to another extensive quantity to peek at the field properties. A natural quantity for this could be the volume.

```math
\frac{ \iint_{\delta V} \vec{F} \cdot \hat{n} dS }{ V } \tag{3}
```

The limit of the above quantity as the volume shrinks to zero would be a characteristic of the field, provided it exists. The divergence at a point is then defined as

```math
\textnormal{div } F = \lim_{V\to 0} \frac{ \iint_{\delta V} \vec{F} \cdot \hat{n} dS }{ V } \tag{4}
```
where the volume in question must include the point. The divergence can be interpreted as the limiting behavior of a flux per unit volume at a point, a scalar quantity.

As it is proportional to a flux, the divergence contains information of how the point acts as source (if positive) or sink (if negative) of the field at a given point. A zero divergence indicates the all field that "enters" the flux ultimately leaves it.

## Divergence Theorem

Consider the volume and its partitions. Since the fluxes are equal, one can do an algebraic trick to pave the way for the divergence expression

```math
\iint_{\delta V} \vec{F} \cdot \hat{n} dS = \sum_{i=1}^{N} \iint_{S_{i}} \vec{F} \cdot \hat{n} dS_{i} = \sum_{i=1}^{N} V_{i} \left( \frac{1}{V_{i}} \iint_{S_{i}} \vec{F} \cdot \hat{n} dS_{i} \right) \tag{5}
```

Then evaluate at the limiting behavior to bring out the divergence

```math
\lim_{N\to\infty, V_{i}\to 0} \sum_{i=1}^{N} V_{i} \left( \frac{1}{V_{i}} \iint_{S_{i}} \vec{F} \cdot \hat{n} dS_{i} \right) = \iiint_{V} \textnormal{div F} dV \tag{6}
```

Resulting in the divergence theorem

```math
\iint_{\delta V} \vec{F} \cdot \hat{n} dS = \iiint_{V} \textnormal{div F} dV \tag{7}
```

Which equates the flux through a surface to the integral of the ratio of flux to volume through a volume. Notice that this property is allowed entirely because the flux of a field is independent of the its partitions, i.e. it's an extensive quantity. This key insight can be used to derive algebraic expressions for the divergence.


## Rectangular Coordinates

Now consider Cartesian coordinates and a natural enclosing surface of this system, a rectangular prism. Subdivide the enclosed volume into similar rectangular sub-volumes with no overlapping finite volume measures. The flux through each of these volumes is given by

```math
\iint_{S_{i}} \vec{F} \cdot \hat{n} dS_{i} \tag{8}
```

evaluating over each of its enclosing surface. Again note the validity of equation (2): the flux to the original outermost surface can be equated to the sum of the fluxes through all surface partitions. All surfaces not belonging to the outermost surface contribute exactly twice in the sum, but with opposing directions of its unit normals. The net contribution of inner surfaces to the flux is therefore zero.

Consider one of the partitioned volume regions. Focusing on the $yz$-parallel faces, the net flux is approximately equal to

```math
\Delta y \Delta z  \left( -\hat{x} \cdot \vec{F_{x_1}^*} \right) + \Delta y \Delta z  \left( \hat{x} \cdot \vec{F_{x_2}^*} \right) = \left( F_{x_2}^* - F_{x_1}^* \right) \Delta y \Delta z \tag{9}
```

where $`\vec{F_{x_i}^*}`$ is a representative value of the field in the $x_i$ face (e.g. the surface midpoint) and $`F_{x_i}^*`$ is the $`x`$-component of the representative value of the $x_i$ face. The unit normals are inverses of each other , $`-\hat{x}`$ and $`\hat{x}`$ for the smallest and largest $`x`$-valued surface because unit normal must be volume-outward facing. The flux approaches the real flux in the limit as the surfaces shrink to zero. Inspired by the known validity of the divergence definition, we are interesed in the limiting behavior as volumes shrink to zero, so we can mutiply and divide by the same quantity

```math
\left( F_{x_2}^* - F_{x_1}^* \right) \Delta y \Delta z  = \left( \frac{F_{x_2}^* - F_{x_1}^*}{\Delta x} \right) \Delta x\Delta y \Delta z  = \left( \frac{\Delta F_{x}^{*}}{\Delta x} \right) \Delta x\Delta y \Delta z \tag{10}
```

which is of course done attempting to introduce a derivative expression times a volume element. We are moving from an explicit flux computation using the field component to a computation that involves rates of change of the field component. Considering all six rectangular faces, the net flux becomes

```math
\left( \frac{\Delta F_{x}^{*}}{\Delta x} \right) \Delta x\Delta y \Delta z + \left( \frac{\Delta F_{y}^{*}}{\Delta y} \right) \Delta x\Delta y \Delta z + \left( \frac{\Delta F_{z}^{*}}{\Delta z} \right) \Delta x\Delta y \Delta z = \left( \frac{\Delta F_{x}^{*}}{\Delta x} + \frac{\Delta F_{y}^{*}}{\Delta y} + \frac{\Delta F_{z}^{*}}{\Delta z} \right) \Delta x\Delta y \Delta z \tag{11}
```

The ratio of this flux to the volume $`\Delta x \Delta y \Delta z`$ is simply

```math
\frac{\Delta F_{x}^{*}}{\Delta x} + \frac{\Delta F_{y}^{*}}{\Delta y} + \frac{\Delta F_{z}^{*}}{\Delta z} \tag{12}
```

which is volume dependent but not proportional to it. By definition, this is the approximate value of the divergence throughout the box and it will become exact in the limit of shrinking volume

```math
\textnormal{div } F = \lim_{V_{i}\to 0} \left( \frac{\Delta F_{x}^{*}}{\Delta x} + \frac{\Delta F_{y}^{*}}{\Delta y} + \frac{\Delta F_{z}^{*}}{\Delta z} \right) =  \frac{\partial F_x}{\partial x} + \frac{\partial F_y}{\partial y} + \frac{\partial F_z}{\partial z} \tag{13}
```

Back to the global picture, summing over all volume partitions, the net flux can be approximated as

```math
\sum_{i} \left( \frac{\Delta F_{x_i}^{*}}{\Delta x_i} + \frac{\Delta F_{y_i}^{*}}{\Delta y_i} + \frac{\Delta F_{z_i}^{*}}{\Delta z_i} \right) \Delta x_i \Delta y_i \Delta z_i \tag{14}
```

In the limit of partitions, the Riemann sum becomes an integral

```math
\lim_{x_i, y_i, z_i \to 0}\sum_{i} \left( \frac{\Delta F_{x_i}^{*}}{\Delta x_i} + \frac{\Delta F_{y_i}^{*}}{\Delta y_i} + \frac{\Delta F_{z_i}^{*}}{\Delta z_i} \right) \Delta x_i \Delta y_i \Delta z_i = \iiint_{V} \left( \frac{\partial F_x}{\partial x} + \frac{\partial F_y}{\partial y} + \frac{\partial F_z}{\partial z}  \right) dx dy dz \tag{15}
```

where the integrand can be expressed in terms of the nabla operator as $`\nabla\cdot F`$. Equating both expressions for the net flux

```math
\iint_{\delta V} \vec{F} \cdot \hat{n} dS = \iiint_{V} (\nabla\cdot F) dV \tag{16}
```

We have recovered the divergence theorem, now in Cartesian coordinates.

For non-rectangular volumes, the box treatment is still applicable because the region can be approximated by very small rectangular volumes in the limiting behavior.



## Divergence in Curvilinear Coordinates

Let's start with another derivation of the divergence before generalizing.


### Divergence in Cylindrical Coordinates

The focus for the flux computation has to shift to the cylindrical volume element defined by a starting point $`(\rho_0, \theta_0, z_0)`$ and final position from changes to the coordinates $`(\rho_0+\Delta \rho, \theta_0+\Delta \theta, z_0+\Delta z)`$.

Through a constant $`\rho`$ surface, the approximate surface area is $(\rho\Delta \theta)(\Delta z)$. Each factor is the arc length associated with a coordinate change and the area is rectangular in the limit as the deltas approach zero because the coordinates are orthogonal. Through the constant $`\rho`$ surface characterized by $`\rho_1, \rho_2`$, the net flux is approximately equal to 

```math
\rho_1\Delta\theta\Delta z \left(-\hat{\rho} \cdot \vec{F_{\rho_1}^*} \right) + \rho_2\Delta\theta\Delta z \left(\hat{\rho} \cdot \vec{F_{\rho_1}^*}\right) = \Delta\theta\Delta z \left( \rho_2 F_{\rho_2}^* - \rho_1 F_{\rho_1}^* \right) = \left( \frac{\Delta (\rho F_{\rho})}{\Delta\rho} \right) \Delta\rho\Delta\theta\Delta z \tag{17}
```

Starred values mean again a representative of the value at the surface of interest. Notice that the scale factor $`\rho`$ (associated to the $`\theta`$ angle coordinate change) is involved in the flux difference and cannot be factored out.

For a constant $`\theta`$ surface, the surface area is exactly $(\Delta \rho)(\Delta z)$. The net flux through these surfaces is approximately equal to 

```math
\Delta\rho\Delta z \left( -\hat{\theta} \cdot \vec{F_{\theta_1}^*} \right) + \Delta\rho\Delta z \left( \hat{\theta} \cdot \vec{F_{\theta_2}^*} \right) = \Delta\rho\Delta z \left( F_{\theta_2}^* - F_{\theta_1}^* \right) = \left( \frac{\Delta F_{\theta}}{\Delta\theta}  \right) \Delta\rho\Delta\theta\Delta z \tag{18}
```

The surface area for constant $`z`$ is approximately equal to $`(\Delta \rho)(\rho^{*}\Delta \theta)`$, where $`\rho^{*}`$ is a representative of the radial distance in the surfaces where coordinate $`\rho`$ is itself changing and it can be considered the same for both surfaces. Again, orthogonality of the coordinates causes the surface area to become more accurate as the deltas shrink to zero. The net flux through constant $`z`$ surfaces is approximately equal to

```math
\Delta\rho \left( \rho^{*}\Delta\theta \right) \left( -\hat{z} \cdot \vec{F_{z_1}^*}  \right) + \Delta\rho \left( \rho^{*}\Delta\theta \right) \left( \hat{z} \cdot \vec{F_{z_2}^*}  \right) = \Delta\rho \Delta\theta \left(  \rho^{*} F_{z}^* - \rho^{*} F_{z_2}^* \right) = \left( \frac{\Delta (\rho^{*} F_z)}{\Delta z} \right) \Delta\rho\Delta\theta\Delta z \tag{19}
```

The scale factor $`\rho`$ (associated to the $`\theta`$ angle coordinate change) is involved in the flux difference but can be factored out because it is the same for both surfaces. We nevertheless keep it along with the field delta for consistency through all coordinates.

To be able to integrate throughout the total volume we must explicitly include the volume element $`\Delta V =  \rho^{*}\Delta\rho\Delta\theta\Delta z`$. The fluxes become

```math
\begin{aligned}
\frac{1}{\rho^{*}} \left( \frac{\Delta (\rho F_{\rho})}{\Delta\rho} \right) \Delta V \\\\
\frac{1}{\rho^{*}} \left( \frac{\Delta F_{\theta}}{\Delta\theta}  \right) \Delta V \\\\
\frac{1}{\rho^{*}} \left( \frac{\Delta (\rho^{*} F_z)}{\Delta z} \right) \Delta V
\end{aligned}
```

Summing through all partitions and finding the limit as partitions shrink to zero, we get the volume integral

```math
\lim_{\Delta \rho_{i}, \Delta \theta_{i}, \Delta z_{i} \to 0}\sum_{i} \left( \frac{1}{\rho^{*}} \left( \frac{\Delta (\rho F_{\rho})}{\Delta\rho} \right) + \frac{1}{\rho^{*}} \left( \frac{\Delta F_{\theta}}{\Delta\theta}  \right) + \frac{1}{\rho^{*}} \left( \frac{\Delta (\rho^{*} F_z)}{\Delta z} \right) \right) \rho^{*}\Delta\rho\Delta\theta\Delta z =
\iiint_{V} \left( \frac{1}{\rho} \frac{\partial}{\partial \rho} \left( \rho F_{\rho} \right) + \frac{1}{\rho} \frac{\partial }{\partial \theta} \left( F_{\theta} \right) + \frac{\partial }{\partial z} \left( F_{z} \right) \right) \rho d\rho d\theta dz \tag{20}
```

We then have for the divergence in cylindrical coordinates

```math
\nabla \cdot F = \frac{1}{\rho} \frac{\partial}{\partial \rho} \left( \rho F_{\rho} \right) + \frac{1}{\rho} \frac{\partial }{\partial \theta} \left( F_{\theta} \right) + \frac{\partial }{\partial z} \left( F_{z} \right) \tag{21}
```


### General Expression for the Divergence in Curvilinear Coordinates

In general, note that the flux difference for each coordinate requires the difference in the field component scaled by the scale factors of the remaining coordinates. Since divergence is to be integrated over a volume, the scale factors also reappear as common divisors across all terms in making up the volume element. It is natural then to show that for curvilinear coordinates, the divergence is expressed as

```math
\nabla \cdot F = \frac{1}{h_{u} h_{v} h_{w}} \cdot \frac{\partial  }{\partial u} \left( h_{v}h_{w} F_{u} \right) + \frac{1}{h_{u} h_{v} h_{w}} \cdot \frac{\partial  }{\partial v} \left( h_{u}h_{w} F_{v} \right) + \frac{1}{h_{u} h_{v} h_{w}} \cdot \frac{\partial }{\partial w} \left( h_{u}h_{v} F_{w} \right) \tag{22}
```

where the scale factors are the standard $`h_{x_{i}} = \lVert \partial_{x_i} \vec{r} \rVert`$.

For spherical coordinates, this would mean

```math
\nabla \cdot F = \frac{1}{r^{2}\sin{\theta}} \cdot \frac{\partial  }{\partial r} \left( \left(r^{2}\sin{\theta}\right) F_{r} \right) + \frac{1}{r^{2}\sin{\theta}} \cdot \frac{\partial  }{\partial \theta} \left( \left(r\sin{\theta}\right) F_{\theta} \right) + \frac{1}{r^{2}\sin{\theta}} \cdot \frac{\partial }{\partial \phi} \left( r F_{\phi} \right) \tag{23}
```

Simplifying terms

```math
\nabla \cdot F = \frac{1}{r^{2}} \cdot \frac{\partial  }{\partial r} \left( r^{2} \cdot F_{r} \right) + \frac{1}{r\sin{\theta}} \cdot \frac{\partial  }{\partial \theta} \left( \sin{\theta}\cdot F_{\theta} \right) + \frac{1}{r\sin{\theta}} \cdot \frac{\partial }{\partial \phi} \left( F_{\phi} \right) \tag{24}
```
