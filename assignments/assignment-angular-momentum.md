# Angular momentum assignment

## 1. Writing budget equations in flux form

Physical laws for fluds are often most succinctly expressed in Lagrangian form following parcels, e.g. 

$$ \frac{DA}{Dt} = S_A $$

where $A$ is any scalar tracer per unit mass of fluid, and $S_A$ represents sources or sinks of that tracer. When working with budgets of $A$ averaged in space and time, it is frequently useful to express the conservation equation in **flux form**, meaning that a divergence of a flux of $A$ appears in the equation. Therefore, we need to be comfortable with the transformation to flux form. In this exercise you will work through the transformation in a few different ways.

### a. Volumetric flux in height coordinates

In height coordinates (e.g. $x,y,z$) we can define the volumetric flux of scalar $A$ as $\rho A \vec{v}$ where $\rho$ is the density of the fluid and $\vec{v}$ is the three dimensional velocity.

In general for any scalar $A$, show that the above conservation equation can be written in terms of this volumetric flux as

$$ \frac{\partial A}{\partial t} + \nabla \cdot \left( \rho A \vec{v} \right) = \rho S_A $$

#### Hints

Make use of the fact that the conservation of mass (continuity equation) is 
$$ \frac{D\rho}{Dt} + \rho \nabla \cdot \vec{v} $$
and the material derivative can be expressed in advective form as
$$ \frac{D(~)}{Dt} = \frac{\partial (~)}{\partial t} + \vec{v} \cdot \nabla (~)$$

You may also find these product rule identites helpful:

$$ \frac{D (AB)}{Dt} = A \frac{DB}{Dt} + B \frac{DA}{Dt} $$

$$ \nabla \cdot (\vec{v} B) = \vec{v} \cdot \nabla B + B \nabla \cdot \vec{v} $$ 

which are true for any scalars $A, B$ and vector field $\vec{v}$


### b. Flux in pressure coordinates

In pressure coordinates we have $\vec{v} = (u,v,\omega)$ and the conservation of mass takes on a simpler form:
$$ \nabla \cdot \vec{v} = 0 $$

In this coordinate system, so that the conservation equation for $A$ can be simply written as

$$ \frac{\partial A}{\partial t} + \nabla \cdot \left( \vec{v} A \right) = S_A $$
where $\vec{v} A$ is the flux of $A$ per unit mass.


## 2. Angular momentum in cylindrical coordinates

When working with the rotating tank in the lab, it is natural to use cylindrical coordinates. Show that the angular momentum of a fluid in cylindrical coordinates is

\begin{equation}
M = \Omega r^2 + rv
\end{equation}

where $\Omega$ is the rotation rate of the tank, $r$ is the radius, and $v$ is the tangential velocity.

## 3. Conservation of angular momentum in the cylindrical tank

Derive a conservation equation for the angular momentum, i.e., $\frac{DM}{Dt}$. The tangential momentum equation is

\begin{equation}
\frac{Dv}{Dt} = -\frac{1}{\rho r} \frac{\partial p}{\partial \theta} - \frac{uv}{r} - 2 \Omega u + F_\theta
\end{equation}

where $\rho$ is the density, $p$ is the pressure, $\theta$ is the azimuthal angle, $u$ is the radial velocity, $F_\theta$ is the friction, and the advective form of the total derivative in cylindrical coordinates is:

\begin{equation}
\frac{D}{Dt} = \frac{\partial}{\partial t} + u\frac{\partial}{\partial r} + \frac{v}{r}\frac{\partial}{\partial \theta} + w\frac{\partial}{\partial z} 
\end{equation}

Qualitatively describe what the terms represent in the conservation equation for the angular momentum.

## 4. Angular momentum balance in the tank

Convert the advection term into flux form, using the fact that for an incompressible fluid $\nabla \cdot \mathbf{u} = 0$. Take the zonal and time average of the conservation equation. Assume a steady state and the divergence of the vertical flux of angular momentum is negligible. Under these set of assumptions what is the balance in the zonal and time mean angular momentum budget?

In words, draw an analogy between this budget in the tank and the angular momentum budget we derived for the atmosphere.

%%% IN FUTURE VERSIONS, 4) vertically integrate, eliminate tank M, and only look at relative M component
