# Arquimedes's Principle

In a gravitational field, a body totally or partially submerged in a fluid experiences an upward force equal to the weight of the displaced fluid. This is known as Arquimedes's principle. It is usually justified by means of a thought experiment. Consider an arbitray portion of the fluid at rest. This portion of the fluid has a weight but the net force is zero, therefore the force applied at its surface must equal the weight of the fluid. Moreover, the net torque on the portion of the fluid is also zero so the surface forces must be occurring through its center of gravity. If one substitutes this portion of fluid by a solid with the same shape, the forces applied should be the same as before because they depend only on the pressure of the fluid at a point. This forces may now excert a non-zero net torque on the solid because the net force may not act along the center of gravity of the solid object.

This is a brilliant argument for the existence of buoyancy. Two objects with the same volume will experience the same upward force irregardless of their shape. The local forces at their surfaces might be very different, but the resultant force is the same nonetheless. One might be interested in deriving this principle from a local view in the hopes of gaining further insight to the phenomena.

## Differential Derivation

Consider a simple static fluid in a uniform gravitational field of acceleration $g$ parallel along the direction $z$; it's pressure $p$ is dependent only on depth $z$ as $p = \rho gz$. Let $V$ and $S$ be the volume and surface of an object submerged on the fluid. The net force on this object is

```math
\vec{F}_{net} = -\iint_{\delta V} \rho gz \hat{n} dS = -\rho g \iint_{\delta V} z \hat{n} dS
```

where the unit normal $\hat{n}$ is dependent on the position at the surface of the solid and defined to be outward facing with respect to the object. This integral accounts for all contributions of force due to pressure at the surface of the solid. One might recognize in the equation a form similar to a flux. This observation leads to try cast the equation into one that allows for the application of the divergence theorem. Start by separating the integral of interest into each of its rectangular components

```math
\iint_{\delta V} z \hat{n} dS =  \hat{i}\iint_{\delta V} (z\hat{i})\bullet\hat{n} dS + \hat{j}\iint_{\delta V} (z\hat{j})\bullet\hat{n} dS + \hat{k}\iint_{\delta V} (z\hat{k})\bullet\hat{n} dS
```

Now each of the integrals is suitable for the application of the divergence theorem

```math
\begin{aligned}
\iint_{\delta V} (z\hat{i})\bullet\hat{n} dS  = \iiint_{V} \nabla\cdot(z\hat{i})dV = 0 \\\\
\iint_{\delta V} (z\hat{j})\bullet\hat{n} dS = \iiint_{V} \nabla\cdot(z\hat{j})dV = 0 \\\\
\iint_{\delta V} (z\hat{k})\bullet\hat{n} dS = \iiint_{V} \nabla\cdot(z\hat{k})dV = \iiint_{V} dV = V
\end{aligned}
```

The first two integrals are exactly zero because the integrand itself is zero everywhere and the integral for the depth component is exactly the volume $V$. This means

```math
\iint_{\delta V} z \hat{n} dS = \hat{k} V
```

and thus 

```math
\vec{F}_{net} = -\hat{k} g (\rho V) = - \hat{k} g M
```

where $M$ is the mass of the displaced fluid. Note that since $z$ was defined as the depth, the unit vector $\hat{k}$ points downards and so the net force points against the uniform gravitational field.

In this regard, Arquimedes's principle can be understood in the same intuition as the divergence theorem which relates flux of a field to its rate of change through a volume. In general, if the pressure $p$ where not a simple function of depth but rather depended more generally on position and other variables $\\{T\\}$, Arquimedes's principle would no longer hold

```math
\vec{F}_{net} = -\iint_{\delta V} p(\vec{r}, \{T\}) \hat{n} dS = -\left( \hat{i}\iiint_{V} \nabla\cdot(p\hat{i}) dV + \hat{j}\iiint_{V}\nabla\cdot(p\hat{j}) dV + \hat{k}\iiint_{V}\nabla\cdot(p\hat{k}) dV  \right) = -\iiint_{V} (\nabla p) dV
```
