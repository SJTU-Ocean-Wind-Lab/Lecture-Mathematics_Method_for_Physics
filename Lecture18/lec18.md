# Chapter 18: Equations of Mathematical Physics and Travelling Waves

We derive the basic equations of mathematical physics, state the data needed to select a solution, and solve the one-dimensional wave equation by characteristic coordinates. Throughout, $a>0$ denotes wave speed; $\kappa>0$ denotes thermal diffusivity, written as $a^2$ in the handwritten heat-equation notes.

## 1. Three Basic Equations

### 1.1 Wave, Heat, and Potential Equations

For a scalar field $u=u(\boldsymbol{x},t)$, the Laplacian in three dimensions is

$$
\Delta u=u_{xx}+u_{yy}+u_{zz}. \tag{1}
$$

The three principal models considered in this course are:

1. **Wave equation:** displacement evolves according to

$$
u_{tt}-a^2\Delta u=f(\boldsymbol{x},t). \tag{2}
$$

2. **Heat equation:** temperature evolves according to

$$
u_t-\kappa\Delta u=f(\boldsymbol{x},t). \tag{3}
$$

3. **Potential equation:** a stationary field satisfies

$$
\Delta u=f(\boldsymbol{x}). \tag{4}
$$

When the right-hand side is zero, the equation is **homogeneous**. The homogeneous potential equation is **Laplace's equation**; its solutions are called **harmonic functions**. The nonhomogeneous equation $\Delta u=f$ is a form of **Poisson's equation**. The source symbol $f$ has a different physical meaning in each model.

### 1.2 Classification of Second-Order Equations

Consider a linear equation in two independent variables whose principal part is

$$
A u_{xx}+2B u_{xy}+C u_{yy}+\text{lower-order terms}=f. \tag{5}
$$

At a point where $A,B,C$ do not all vanish, its type is determined by $D=B^2-AC$:

- **Hyperbolic:** $D>0$, as in $u_{tt}-a^2u_{xx}=0$.
- **Elliptic:** $D<0$, as in $u_{xx}+u_{yy}=0$.
- **Parabolic:** $D=0$, as in $u_t-\kappa u_{xx}=0$.

The characteristic-direction equation is

$$
A(\mathrm{d}y)^2-2B\,\mathrm{d}x\,\mathrm{d}y+C(\mathrm{d}x)^2=0. \tag{6}
$$

Its discriminant is $4(B^2-AC)$, which gives the same classification. If the coefficient of $u_{xy}$ is instead denoted by $B$ rather than $2B$, the corresponding discriminant is $B^2-4AC$.

## 2. Derivation of the Governing Equations

### 2.1 Small Transverse Vibrations of a String

Let a taut string have constant tension $T>0$ and constant mass per unit length $\rho_s>0$. Let $u(x,t)$ be its transverse displacement, and let $q(x,t)$ be the transverse force per unit length. Assume small slopes, $|u_x|\ll1$, so that arc length is approximately horizontal length and $\sin\alpha\approx\tan\alpha=u_x$.

For the element $[x,x+\mathrm{d}x]$, Newton's second law gives, to first order,

$$
T\bigl[u_x(x+\mathrm{d}x,t)-u_x(x,t)\bigr]
+q(x,t)\,\mathrm{d}x
=\rho_s\,\mathrm{d}x\,u_{tt}(x,t). \tag{7}
$$

Divide by $\mathrm{d}x$ and take the limit:

$$
\rho_s u_{tt}=T u_{xx}+q,
\qquad
u_{tt}-a^2u_{xx}=f,
\qquad
a^2=\frac{T}{\rho_s},\quad f=\frac{q}{\rho_s}. \tag{8}
$$

The case $q=0$ describes free vibration; $q\ne0$ describes forced vibration. The analogous membrane model in two spatial dimensions contains $u_{xx}+u_{yy}$ instead of $u_{xx}$.

### 2.2 Heat Conduction from Energy Conservation

Let $K>0$ be thermal conductivity, $\rho>0$ density, and $c_p>0$ specific heat, all constant. Fourier's law states that the heat-flux vector is

$$
\boldsymbol{q}=-K\nabla u. \tag{9}
$$

Use the **outward** unit normal $\boldsymbol{n}$ on the boundary of an arbitrary fixed volume $\Omega$. If $Q$ is heat generated per unit volume per unit time, conservation of energy gives

$$
\frac{\mathrm{d}}{\mathrm{d}t}\int_\Omega \rho c_p u\,\mathrm{d}V
=-\int_{\partial\Omega}\boldsymbol{q}\cdot\boldsymbol{n}\,\mathrm{d}S
+\int_\Omega Q\,\mathrm{d}V. \tag{10}
$$

Substitute Fourier's law and apply the divergence theorem:

$$
\int_\Omega \rho c_p u_t\,\mathrm{d}V
=\int_\Omega K\Delta u\,\mathrm{d}V+\int_\Omega Q\,\mathrm{d}V. \tag{11}
$$

Because $\Omega$ is arbitrary, the local equation is

$$
u_t-\kappa\Delta u=f,
\qquad \kappa=\frac{K}{\rho c_p},\quad f=\frac{Q}{\rho c_p}. \tag{12}
$$

For spatially varying conductivity, the conduction term before division by $\rho c_p$ is $\nabla\cdot(K\nabla u)$ rather than $K\Delta u$.

### 2.3 Stationary Temperature and Potential Problems

When a temperature field becomes time independent, $u_t=0$. With no internal heat source, the heat equation reduces to $\Delta u=0$. Thus the same potential equation arises as the steady limit of heat conduction. With a source, the steady equation is $\Delta u=-Q/K$.

## 3. Initial and Boundary Conditions

### 3.1 Initial Data

A governing equation alone usually admits many solutions. A physical problem also specifies initial and/or boundary data.

- The heat equation is first order in time and requires the initial temperature $u(\boldsymbol{x},0)=\varphi(\boldsymbol{x})$.
- The wave equation is second order in time and requires both initial displacement and velocity:

$$
u(\boldsymbol{x},0)=\varphi(\boldsymbol{x}),
\qquad u_t(\boldsymbol{x},0)=\psi(\boldsymbol{x}). \tag{13}
$$

A problem with initial data on an unbounded spatial domain is an **initial-value problem**. On a bounded domain, initial data and spatial boundary data together form an **initial-boundary-value problem**.

### 3.2 Three Types of Boundary Conditions

Let $\partial_n u=\nabla u\cdot\boldsymbol{n}$, with $\boldsymbol{n}$ outward. The standard boundary conditions are:

1. **Dirichlet condition:** $u|_{\partial\Omega}=g$ prescribes the field itself.
2. **Neumann condition:** $\partial_n u|_{\partial\Omega}=g$ prescribes its normal derivative.
3. **Robin condition:** $(\partial_n u+\sigma u)|_{\partial\Omega}=g$ prescribes a linear combination.

For heat conduction, a homogeneous Dirichlet condition fixes the boundary at zero reference temperature; a homogeneous Neumann condition describes insulation. Newton cooling into surroundings at temperature $u_\infty$ gives

$$
-K\partial_n u=h(u-u_\infty),
\qquad
\partial_n u+\frac{h}{K}u=\frac{h}{K}u_\infty, \tag{14}
$$

where $h\ge0$ is a heat-transfer coefficient.

For a vibrating string, $u=0$ describes a fixed end and $u_x=0$ a free end. An end attached to a linear spring of stiffness $k_s$ satisfies $T\partial_n u+k_su=0$. On $0<x<\ell$, the outward derivative is $-u_x$ at $x=0$ and $u_x$ at $x=\ell$, so spring conditions become

$$
-T u_x(0,t)+k_su(0,t)=0,
\qquad
T u_x(\ell,t)+k_su(\ell,t)=0, \tag{15}
$$

when the same spring stiffness is used at both ends. The sign depends on the endpoint and normal convention.

**Compatibility.** For a smooth fixed-end wave solution, the initial data must agree with the boundary conditions, for example $\varphi(0)=\varphi(\ell)=0$ and $\psi(0)=\psi(\ell)=0$ when these endpoint traces exist.

## 4. Travelling Waves and Characteristic Coordinates

### 4.1 Reduction to a Mixed Derivative

Consider the homogeneous wave equation on the whole line:

$$
u_{tt}-a^2u_{xx}=0,\qquad -\infty<x<\infty. \tag{16}
$$

Introduce characteristic coordinates and write the transformed unknown as $U$:

$$
\xi=x+at,\qquad \eta=x-at,\qquad u(x,t)=U(\xi,\eta). \tag{17}
$$

The chain rule yields

$$
\begin{aligned}
u_x&=U_\xi+U_\eta,&
u_t&=a(U_\xi-U_\eta),\\
u_{xx}&=U_{\xi\xi}+2U_{\xi\eta}+U_{\eta\eta},&
u_{tt}&=a^2(U_{\xi\xi}-2U_{\xi\eta}+U_{\eta\eta}).
\end{aligned} \tag{18}
$$

Consequently,

$$
u_{tt}-a^2u_{xx}=-4a^2U_{\xi\eta}=0. \tag{19}
$$

Integrating $U_{\xi\eta}=0$ first in $\eta$ and then in $\xi$ gives $U=F(\xi)+G(\eta)$. Hence the general twice continuously differentiable solution is

$$
\boxed{u(x,t)=F(x+at)+G(x-at).} \tag{20}
$$

The term $F(x+at)$ travels to the left at speed $a$; $G(x-at)$ travels to the right. The lines $x\pm at=\text{constant}$ are the two characteristic families.

### 4.2 Derivation of d'Alembert's Formula

Impose initial data $u(x,0)=\varphi(x)$ and $u_t(x,0)=\psi(x)$. Then

$$
F(x)+G(x)=\varphi(x),
\qquad F'(x)-G'(x)=\frac{\psi(x)}{a}. \tag{21}
$$

Let $H'(x)=\psi(x)$. Up to constants that cancel in $F+G$,

$$
F(x)=\frac{\varphi(x)}2+\frac{H(x)}{2a},
\qquad
G(x)=\frac{\varphi(x)}2-\frac{H(x)}{2a}. \tag{22}
$$

Substitution produces **d'Alembert's formula**:

$$
\boxed{
u(x,t)=\frac{\varphi(x+at)+\varphi(x-at)}2
+\frac{1}{2a}\int_{x-at}^{x+at}\psi(s)\,\mathrm{d}s.
} \tag{23}
$$

For example, $\varphi\in C^2$ and $\psi\in C^1$ are sufficient for this formula to define a classical solution. Its value at $(x,t)$ depends only on initial data in $[x-at,x+at]$, expressing finite propagation speed.

**Example: displacement $x$ and velocity $\cos x$.** With $\varphi(x)=x$ and $\psi(x)=\cos x$,

$$
u(x,t)=x+\frac{\sin(x+at)-\sin(x-at)}{2a}
=x+\frac{\cos x\sin(at)}{a}. \tag{24}
$$

## 5. Nonhomogeneous Wave Equations

### 5.1 The Source-Term Extension

For $u_{tt}-a^2u_{xx}=f(x,t)$ on the whole line, the extension of d'Alembert's formula is

$$
\begin{aligned}
u(x,t)={}&\frac{\varphi(x+at)+\varphi(x-at)}2
+\frac{1}{2a}\int_{x-at}^{x+at}\psi(s)\,\mathrm{d}s\\
&+\frac{1}{2a}\int_0^t
\int_{x-a(t-\tau)}^{x+a(t-\tau)}f(s,\tau)\,\mathrm{d}s\,\mathrm{d}\tau.
\end{aligned} \tag{25}
$$

The last term is the response to the source with zero initial data. It follows by applying the homogeneous initial-velocity formula to each forcing time $\tau$ and integrating those responses. Differentiation verifies that its wave operator is $f$ and that its initial displacement and velocity vanish, under sufficient regularity.

### 5.2 Reduction by a Particular Solution

If a convenient particular solution $W$ satisfies $W_{tt}-a^2W_{xx}=f$, let $v=u-W$. Then $v$ satisfies the homogeneous equation, with adjusted initial data

$$
v(x,0)=\varphi(x)-W(x,0),
\qquad
v_t(x,0)=\psi(x)-W_t(x,0). \tag{26}
$$

**Example: a time-dependent force.** Solve

$$
\begin{cases}
u_{tt}-u_{xx}=-\sin t,&x\in\mathbb{R},\ t>0,\\
u(x,0)=\cos x,\qquad u_t(x,0)=\mathrm{e}^x.
\end{cases} \tag{27}
$$

Choose $W(t)=\sin t$. Then $v=u-\sin t$ has initial displacement $\cos x$ and initial velocity $\mathrm{e}^x-1$. D'Alembert's formula with $a=1$ gives

$$
\begin{aligned}
v(x,t)
&=\frac{\cos(x+t)+\cos(x-t)}2
+\frac12\int_{x-t}^{x+t}(\mathrm{e}^s-1)\,\mathrm{d}s\\
&=\cos x\cos t+\mathrm{e}^x\sinh t-t.
\end{aligned} \tag{28}
$$

Therefore,

$$
\boxed{u(x,t)=\cos x\cos t+\mathrm{e}^x\sinh t-t+\sin t.} \tag{29}
$$

Direct substitution checks the equation and both initial conditions. For a finite string, spatial boundary conditions must also be enforced; the next lecture develops the eigenfunction method for that setting.
