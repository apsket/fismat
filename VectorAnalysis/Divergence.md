# Divergence

The divergence is standardly introduced in different ways depending on the context. An intuitive introduction, though not a formal proof, arises from studying the flux of a field. Consider a vector field $\vec{F}$ and a closed piecewise smooth surface $\delta V$ enclosing volume $V$. The flux of $\vec{F}$ through the surface $\delta V$ is

```math
\iint_{\delta V} \vec{F} \cdot \hat{n} dS
```

with $\hat{n}$ a unit vector normal to the surface at each point, with the convention of pointing outwards from the enclosed volume.

Now consider Cartesian coordinates and a natural enclosing surface of this system, a rectangular prism. Let's subdivide the enclosed volume into similar rectangular sub-volumes with no overlapping finite volume measures. The flux through each of these volumes is given by the same expression as above, evaluating over each of its enclosing surface. Note that the flux to the original outermost surface can be equated to the sum of the fluxes through all surface partitions. All surfaces not belonging to the outermost surface contribute exactly twice in the sum, but with opposing directions of its unit normals while. The net contribution of inner surfaces to the flux is therefore zero.

Consider one of the partitioned volume regions. Focusing on the $yz$-parallel faces, the net flux is approximately equal to

```math
\Delta y \Delta z  \left( -\hat{x} \cdot \vec{F_{x_1}^*} \right) + \Delta y \Delta z  \left( \hat{x} \cdot \vec{F_{x_2}^*} \right) = \left( F_{x_2}^* - F_{x_1}^* \right) \Delta y \Delta z
```

where $`\vec{F_{x_i}^*}`$ is a representative value of the field in the $x_i$ face (e.g. the surface midpoint) and $`F_{x_i}^*`$ is the $`x`$-component of the representative value of the $x_i$ face. The unit normals are inverses of each other , $`-\hat{x}`$ and $`\hat{x}`$ for the smallest and largest $`x`$-valued surface because unit normal must be volume-outward facing. The flux approaches the real flux in the limit as the surfaces shrink to zero. Since we are interesed in the limiting behavior as volumes shrink to zero, we can introduce

```math
\left( F_{x_2}^* - F_{x_1}^* \right) \Delta y \Delta z  = \left( \frac{F_{x_2}^* - F_{x_1}^*}{\Delta x} \right) \Delta x\Delta y \Delta z  = \left( \frac{\Delta F_{x}^{*}}{\Delta x} \right) \Delta x\Delta y \Delta z
```

which is of course done attempting to pave the way to a derivative expression. We are moving from an explicit flux computation using the field component to a computation that involves rates of change of the field component. Considering all six rectangular faces, the net flux becomes

```math
\left( \frac{\Delta F_{x}^{*}}{\Delta x} \right) \Delta x\Delta y \Delta z + \left( \frac{\Delta F_{y}^{*}}{\Delta y} \right) \Delta x\Delta y \Delta z + \left( \frac{\Delta F_{z}^{*}}{\Delta z} \right) \Delta x\Delta y \Delta z = \left( \frac{\Delta F_{x}^{*}}{\Delta x} + \frac{\Delta F_{y}^{*}}{\Delta y} + \frac{\Delta F_{z}^{*}}{\Delta z} \right) \Delta x\Delta y \Delta z
```

Now summing over all volume partitions, the net flux can be approximated as

```math
\sum_{i} \left( \frac{\Delta F_{x_i}^{*}}{\Delta x_i} + \frac{\Delta F_{y_i}^{*}}{\Delta y_i} + \frac{\Delta F_{z_i}^{*}}{\Delta z_i} \right) \Delta x_i \Delta y_i \Delta z_i
```

In the limit of partitions, the Riemann sum becomes an integral

```math
\lim_{x_i, y_i, z_i \to 0}\sum_{i} \left( \frac{\Delta F_{x_i}^{*}}{\Delta x_i} + \frac{\Delta F_{y_i}^{*}}{\Delta y_i} + \frac{\Delta F_{z_i}^{*}}{\Delta z_i} \right) \Delta x_i \Delta y_i \Delta z_i = \iiint_{V} \left( \frac{\partial F_x}{\partial x} + \frac{\partial F_y}{\partial y} + \frac{\partial F_z}{\partial z}  \right) dx dy dz
```

where the integrand is called the divergence of the field and is usually denoted as $`\nabla\cdot F`$. Equating both expressions for the net flux

```math
\iint_{\delta V} \vec{F} \cdot \hat{n} dS = \iiint_{V} (\nabla\cdot F) dV
```

which is the divergence theorem. For non-rectangular volumes, the theorem is still applicable because the region can be approximated by rectangular volumes of the required size.



## Divergence in Curvilinear Coordinates

Let's start with another derivation of the divergence before generalizing.


### Divergence in Cylindrical Coordinates

The focus for the flux computation has to shift to the cylindrical volume element defined by a starting point $`(\rho_0, \theta_0, z_0)`$ and final position from changes to the coordinates $`(\rho_0+\Delta \rho, \theta_0+\Delta \theta, z_0+\Delta z)`$.

Through a constant $`\rho`$ surface, the approximate surface area is $(\rho\Delta \theta)(\Delta z)$. Each factor is the arc length associated with a coordinate change and the area is rectangular in the limit as the deltas approach zero because the coordinates are orthogonal. Through the constant $`\rho`$ surface characterized by $`\rho_1, \rho_2`$, the net flux is approximately equal to 

```math
\rho_1\Delta\theta\Delta z \left(-\hat{\rho} \cdot \vec{F_{\rho_1}^*} \right) + \rho_2\Delta\theta\Delta z \left(\hat{\rho} \cdot \vec{F_{\rho_1}^*}\right) = \Delta\theta\Delta z \left( \rho_2 F_{\rho_2}^* - \rho_1 F_{\rho_1}^* \right) = \left( \frac{\Delta (\rho F_{\rho})}{\Delta\rho} \right) \Delta\rho\Delta\theta\Delta z
```

Starred values mean again a representative of the value at the surface of interest. Notice that the scale factor $`\rho`$ (associated to the $`\theta`$ angle coordinate change) is involved in the flux difference and cannot be factored out.

For a constant $`\theta`$ surface, the surface area is exactly $(\Delta \rho)(\Delta z)$. The net flux through these surfaces is approximately equal to 

```math
\Delta\rho\Delta z \left( -\hat{\theta} \cdot \vec{F_{\theta_1}^*} \right) + \Delta\rho\Delta z \left( \hat{\theta} \cdot \vec{F_{\theta_2}^*} \right) = \Delta\rho\Delta z \left( F_{\theta_2}^* - F_{\theta_1}^* \right) = \left( \frac{\Delta F_{\theta}}{\Delta\theta}  \right) \Delta\rho\Delta\theta\Delta z
```
The surface area for constant $`z`$ is approximately equal to $`(\Delta \rho)(\rho^{*}\Delta \theta)`$, where $`\rho^{*}`$ is a representative of the radial distance in the surfaces where coordinate $`\rho`$ is itself changing and it can be considered the same for both surfaces. Again, orthogonality of the coordinates causes the surface area to become more accurate as the deltas shrink to zero. The net flux through constant $`z`$ surfaces is approximately equal to

```math
\Delta\rho \left( \rho^{*}\Delta\theta \right) \left( -\hat{z} \cdot \vec{F_{z_1}^*}  \right) + \Delta\rho \left( \rho^{*}\Delta\theta \right) \left( \hat{z} \cdot \vec{F_{z_2}^*}  \right) = \Delta\rho \Delta\theta \left(  \rho^{*} F_{z}^* - \rho^{*} F_{z_2}^* \right) = \left( \frac{\Delta (\rho^{*} F_z)}{\Delta z} \right) \Delta\rho\Delta\theta\Delta z
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
\iiint_{V} \left( \frac{1}{\rho} \frac{\partial}{\partial \rho} \left( \rho F_{\rho} \right) + \frac{1}{\rho} \frac{\partial }{\partial \theta} \left( F_{\theta} \right) + \frac{\partial }{\partial z} \left( F_{z} \right) \right) \rho d\rho d\theta dz
```

We then have for the divergence in cylindrical coordinates

```math
\nabla \cdot F = \frac{1}{\rho} \frac{\partial}{\partial \rho} \left( \rho F_{\rho} \right) + \frac{1}{\rho} \frac{\partial }{\partial \theta} \left( F_{\theta} \right) + \frac{\partial }{\partial z} \left( F_{z} \right)
```


### General Expression for the Divergence in Curvilinear Coordinates

In general, note that the flux difference for each coordinate requires the difference in the field component scaled by the scale factors of the remaining coordinates. Since divergence is to be integrated over a volume, the scale factors also reappear as common divisors across all terms in making up the volume element. It is natural then to show that for curvilinear coordinates, the divergence is expressed as

```math
\nabla \cdot F = \frac{1}{h_{u} h_{v} h_{w}} \cdot \frac{\partial  }{\partial u} \left( h_{v}h_{w} F_{u} \right) + \frac{1}{h_{u} h_{v} h_{w}} \cdot \frac{\partial  }{\partial v} \left( h_{u}h_{w} F_{v} \right) + \frac{1}{h_{u} h_{v} h_{w}} \cdot \frac{\partial }{\partial w} \left( h_{u}h_{v} F_{w} \right)
```

where the scale factors are the standard $`h_{x_{i}} = \lVert \partial_{x_i} \vec{r} \rVert`$.

For spherical coordinates, this would mean

```math
\nabla \cdot F = \frac{1}{r^{2}\sin{\theta}} \cdot \frac{\partial  }{\partial r} \left( \left(r^{2}\sin{\theta}\right) F_{r} \right) + \frac{1}{r^{2}\sin{\theta}} \cdot \frac{\partial  }{\partial \theta} \left( \left(r\sin{\theta}\right) F_{\theta} \right) + \frac{1}{r^{2}\sin{\theta}} \cdot \frac{\partial }{\partial \phi} \left( r F_{\phi} \right)
```

Simplifying terms

```math
\nabla \cdot F = \frac{1}{r^{2}} \cdot \frac{\partial  }{\partial r} \left( r^{2} \cdot F_{r} \right) + \frac{1}{r\sin{\theta}} \cdot \frac{\partial  }{\partial \theta} \left( \sin{\theta}\cdot F_{\theta} \right) + \frac{1}{r\sin{\theta}} \cdot \frac{\partial }{\partial \phi} \left( F_{\phi} \right)
```
