# Chapter 20: Integral Transforms and Nonhomogeneous Problems

Integral transforms replace differentiation in one variable by algebraic operations, reducing a PDE to a family of ordinary differential equations. We use the spatial Fourier transform for heat conduction on the whole line, and a spatial eigenfunction expansion followed by a time Laplace transform for a forced finite string.

## 1. Fourier Transform in the Spatial Variable

### 1.1 Transform Convention

For an integrable function $v$ on $\mathbb{R}$, define

$$
\widehat v(\xi)=\mathcal{F}[v](\xi)
=\int_{-\infty}^{\infty}v(x)\mathrm{e}^{-\mathrm{i}\xi x}\,\mathrm{d}x. \tag{1}
$$

With the corresponding inversion conditions,

$$
v(x)=\frac{1}{2\pi}\int_{-\infty}^{\infty}
\widehat v(\xi)\mathrm{e}^{\mathrm{i}\xi x}\,\mathrm{d}\xi. \tag{2}
$$

For a time-dependent function, transform only in $x$ and regard $t$ as a parameter. If the derivatives are integrable and the boundary terms vanish at infinity, integration by parts gives

$$
\mathcal{F}_x[u_x]=\mathrm{i}\xi\widehat u,
\qquad \mathcal{F}_x[u_{xx}]=-\xi^2\widehat u. \tag{3}
$$

If differentiation under the integral is justified, $\mathcal{F}_x[u_t]=\partial_t\widehat u$.

The spatial convolution and its transform are

$$
(v*w)(x)=\int_{-\infty}^{\infty}v(x-s)w(s)\,\mathrm{d}s,
\qquad \mathcal{F}[v*w]=\widehat v\,\widehat w. \tag{4}
$$

The forward transform has no normalization factor, and the inverse has $1/(2\pi)$. These factors must remain consistent when identifying a heat kernel.

## 2. Heat Conduction on the Whole Line

### 2.1 Transforming the Initial-Value Problem

Consider an infinitely long rod:

$$
\begin{cases}
u_t-\kappa u_{xx}=f(x,t),&x\in\mathbb{R},\ t>0,\\
u(x,0)=\varphi(x),
\end{cases}
\qquad \kappa>0. \tag{5}
$$

Let $\widehat u=\mathcal{F}_x[u]$, $\widehat f=\mathcal{F}_x[f]$, and $\widehat\varphi=\mathcal{F}[\varphi]$. Transforming both the equation and initial condition gives

$$
\partial_t\widehat u+\kappa\xi^2\widehat u=\widehat f(\xi,t),
\qquad \widehat u(\xi,0)=\widehat\varphi(\xi). \tag{6}
$$

This is a first-order linear ODE for every fixed $\xi$. Multiply by the integrating factor $\mathrm{e}^{\kappa\xi^2t}$ and integrate:

$$
\widehat u(\xi,t)
=\mathrm{e}^{-\kappa\xi^2t}\widehat\varphi(\xi)
+\int_0^t\mathrm{e}^{-\kappa\xi^2(t-\tau)}\widehat f(\xi,\tau)\,\mathrm{d}\tau. \tag{7}
$$

### 2.2 The Gaussian Kernel

The Gaussian transform pair is

$$
\mathcal{F}[\mathrm{e}^{-\beta x^2}](\xi)
=\sqrt{\frac\pi\beta}\mathrm{e}^{-\xi^2/(4\beta)},
\qquad \beta>0. \tag{8}
$$

It follows that

$$
G(x,t)=\mathcal{F}^{-1}[\mathrm{e}^{-\kappa\xi^2t}](x)
=\frac{1}{\sqrt{4\pi\kappa t}}
\exp\left(-\frac{x^2}{4\kappa t}\right),\qquad t>0. \tag{9}
$$

This is the **heat kernel** or **fundamental solution**. For positive time it satisfies

$$
G_t-\kappa G_{xx}=0,
\qquad G(x,t)>0,
\qquad \int_{-\infty}^{\infty}G(x,t)\,\mathrm{d}x=1. \tag{10}
$$

Although $G$ becomes singular as $t\downarrow0$, its convolution with suitable initial data approaches those data, pointwise at continuity points or in the appropriate integral sense.

### 2.3 Inversion and the Poisson Integral Formula

Invert the transformed solution using the convolution theorem:

$$
u(x,t)=(G(\cdot,t)*\varphi)(x)
+\int_0^t(G(\cdot,t-\tau)*f(\cdot,\tau))(x)\,\mathrm{d}\tau. \tag{11}
$$

Written as integrals, this becomes

$$
\begin{aligned}
u(x,t)={}&\int_{-\infty}^{\infty}
\frac{\exp[-(x-s)^2/(4\kappa t)]}{\sqrt{4\pi\kappa t}}
\varphi(s)\,\mathrm{d}s\\
&+\int_0^t\int_{-\infty}^{\infty}
\frac{\exp[-(x-s)^2/(4\kappa(t-\tau))]}{\sqrt{4\pi\kappa(t-\tau)}}
f(s,\tau)\,\mathrm{d}s\,\mathrm{d}\tau.
\end{aligned} \tag{12}
$$

The source integral is understood up to $\tau<t$, with its endpoint limit taken through the convolution. For a sufficiently regular source the limit is integrable in time.

When $f=0$, the formula reduces to the **Poisson integral formula for the heat equation**:

$$
\boxed{u(x,t)=\frac{1}{\sqrt{4\pi\kappa t}}
\int_{-\infty}^{\infty}\mathrm{e}^{-(x-s)^2/(4\kappa t)}\varphi(s)\,\mathrm{d}s.} \tag{13}
$$

Here the Gaussian kernel gives positive weight to every spatial point for any $t>0$, in contrast to the finite interval of dependence in d'Alembert's wave formula. This is a property of the heat-equation model.

## 3. Homogenization of Boundary Conditions

### 3.1 Subtract an Auxiliary Function

Spatial eigenfunction expansions are most direct when the boundary conditions are homogeneous. If the prescribed boundary values are not zero, choose an auxiliary function $W$ satisfying those same boundary data, and write $v=u-W$.

For a forced wave equation, this changes the entire problem to

$$
\begin{aligned}
v_{tt}-a^2v_{xx}&=f-W_{tt}+a^2W_{xx},\\
v(x,0)&=\varphi(x)-W(x,0),\\
v_t(x,0)&=\psi(x)-W_t(x,0).
\end{aligned} \tag{14}
$$

For the heat equation, the corresponding change is

$$
v_t-\kappa v_{xx}=f-W_t+\kappa W_{xx},
\qquad v(x,0)=\varphi(x)-W(x,0). \tag{15}
$$

An auxiliary function that matches only the boundary data need not satisfy the original PDE. Its residual must be included in the new source term. The adjusted initial data must also be retained.

### 3.2 Useful Choices on an Interval

Let all endpoint data below be functions of $t$; the formulas also apply when they are constants. Derivatives in this subsection are **coordinate derivatives $u_x$ at the endpoints**, not outward normal derivatives.

**Two prescribed values:** for $u(0,t)=\mu_0(t)$ and $u(\ell,t)=\mu_\ell(t)$, take

$$
W(x,t)=\mu_0(t)+\frac{\mu_\ell(t)-\mu_0(t)}{\ell}x. \tag{16}
$$

**Value on the left, derivative on the right:** for $u(0,t)=\mu_0(t)$ and $u_x(\ell,t)=\nu_\ell(t)$, take

$$
W(x,t)=\mu_0(t)+\nu_\ell(t)x. \tag{17}
$$

**Derivative on the left, value on the right:** for $u_x(0,t)=\nu_0(t)$ and $u(\ell,t)=\mu_\ell(t)$, take

$$
W(x,t)=\nu_0(t)(x-\ell)+\mu_\ell(t). \tag{18}
$$

**Two prescribed derivatives:** for $u_x(0,t)=\nu_0(t)$ and $u_x(\ell,t)=\nu_\ell(t)$, take

$$
W(x,t)=\nu_0(t)x+\frac{\nu_\ell(t)-\nu_0(t)}{2\ell}x^2. \tag{19}
$$

These choices are not unique. Their purpose is to give $v=u-W$ a boundary pair whose eigenfunctions are known.

## 4. Eigenfunction Expansion and the Laplace Transform

### 4.1 Reduction of a Forced String to Modal ODEs

After boundary homogenization, consider

$$
\begin{cases}
u_{tt}-a^2u_{xx}=f(x,t),&0<x<\ell,\ t>0,\\
u(0,t)=u(\ell,t)=0,\\
u(x,0)=\varphi(x),\qquad u_t(x,0)=\psi(x).
\end{cases} \tag{20}
$$

Let $k_n=n\pi/\ell$ and $\omega_n=ak_n$. Expand

$$
\begin{aligned}
u(x,t)&=\sum_{n=1}^{\infty}q_n(t)\sin(k_nx),\\
f(x,t)&=\sum_{n=1}^{\infty}f_n(t)\sin(k_nx),\\
\varphi(x)&=\sum_{n=1}^{\infty}\varphi_n\sin(k_nx),\qquad
\psi(x)=\sum_{n=1}^{\infty}\psi_n\sin(k_nx).
\end{aligned} \tag{21}
$$

The coefficients are

$$
\begin{aligned}
f_n(t)&=\frac2\ell\int_0^\ell f(x,t)\sin(k_nx)\,\mathrm{d}x,\\
\varphi_n&=\frac2\ell\int_0^\ell\varphi(x)\sin(k_nx)\,\mathrm{d}x,\\
\psi_n&=\frac2\ell\int_0^\ell\psi(x)\sin(k_nx)\,\mathrm{d}x.
\end{aligned} \tag{22}
$$

Orthogonality reduces the PDE to independent problems:

$$
q_n''+\omega_n^2q_n=f_n(t),
\qquad q_n(0)=\varphi_n,\quad q_n'(0)=\psi_n. \tag{23}
$$

### 4.2 Applying the Time Laplace Transform

Use the one-sided Laplace transform

$$
Q_n(p)=\mathcal{L}[q_n](p)=\int_0^\infty q_n(t)\mathrm{e}^{-pt}\,\mathrm{d}t,
\qquad F_n(p)=\mathcal{L}[f_n](p), \tag{24}
$$

for $\operatorname{Re}p$ sufficiently large and data of suitable exponential order. Integration by parts gives

$$
\mathcal{L}[q_n'']=p^2Q_n-p\varphi_n-\psi_n. \tag{25}
$$

Therefore,

$$
(p^2+\omega_n^2)Q_n=F_n+p\varphi_n+\psi_n,
\qquad
Q_n=\frac{F_n+p\varphi_n+\psi_n}{p^2+\omega_n^2}. \tag{26}
$$

The elementary inverse pairs are

$$
\mathcal{L}^{-1}\left[\frac{p}{p^2+\omega^2}\right]=\cos(\omega t),
\qquad
\mathcal{L}^{-1}\left[\frac{1}{p^2+\omega^2}\right]=\frac{\sin(\omega t)}{\omega}. \tag{27}
$$

For functions of time, convolution is causal:

$$
(r*_t s)(t)=\int_0^t r(\tau)s(t-\tau)\,\mathrm{d}\tau,
\qquad \mathcal{L}[r*_t s]=\mathcal{L}[r]\,\mathcal{L}[s]. \tag{28}
$$

This differs from the whole-line spatial convolution used for the heat kernel. Inversion now gives

$$
\boxed{
q_n(t)=\varphi_n\cos(\omega_nt)
+\frac{\psi_n}{\omega_n}\sin(\omega_nt)
+\frac{1}{\omega_n}\int_0^t f_n(\tau)\sin(\omega_n(t-\tau))\,\mathrm{d}\tau.
} \tag{29}
$$

Substituting $q_n$ into the sine expansion reconstructs $u$. The three terms are the responses to initial displacement, initial velocity, and external forcing. The forced term has zero displacement and velocity at $t=0$.

For other homogeneous endpoint pairs, use the corresponding eigenfunctions. If a Neumann zero mode is present, its ODE is $q_0''=f_0$ and must be integrated separately; division by $\omega_0=0$ is invalid.

## 5. Example with Nonzero Boundary Values and Forcing

### 5.1 Problem and Boundary Lifting

Consider the example from the final handwritten lecture:

$$
\begin{cases}
u_{tt}-a^2u_{xx}=\sin(2\pi x/\ell)\cos(2\pi x/\ell),\\
u(0,t)=3,\qquad u(\ell,t)=0,\\
u(x,0)=3(1-x/\ell),\qquad u_t(x,0)=\sin(4\pi x/\ell),
\end{cases} \tag{30}
$$

on $0<x<\ell$, $t>0$. Define

$$
k=\frac{4\pi}{\ell},\qquad\omega=ak,\qquad
L(x)=3\left(1-\frac{x}{\ell}\right). \tag{31}
$$

Since $\sin(2\pi x/\ell)\cos(2\pi x/\ell)=\tfrac12\sin(kx)$, putting $z=u-L$ gives homogeneous endpoint values and

$$
z_{tt}-a^2z_{xx}=\tfrac12\sin(kx),
\qquad z(x,0)=0,\quad z_t(x,0)=\sin(kx). \tag{32}
$$

Only the fourth sine mode is excited. Write $z=r(t)\sin(kx)$; then

$$
r''+\omega^2r=\tfrac12,
\qquad r(0)=0,\quad r'(0)=1. \tag{33}
$$

### 5.2 Evaluate the Modal Convolution

The inverse-transform formula yields

$$
\begin{aligned}
r(t)&=\frac{\sin(\omega t)}{\omega}
+\frac{1}{2\omega}\int_0^t\sin(\omega(t-\tau))\,\mathrm{d}\tau\\
&=\frac{\sin(\omega t)}{\omega}
+\frac{1-\cos(\omega t)}{2\omega^2}.
\end{aligned} \tag{34}
$$

Thus the complete solution is

$$
\boxed{
u(x,t)=3\left(1-\frac{x}{\ell}\right)
+\left[\frac{1-\cos(\omega t)}{2\omega^2}
+\frac{\sin(\omega t)}{\omega}\right]\sin(kx).
} \tag{35}
$$

Both endpoints remain fixed at their prescribed values because $\sin(kx)$ vanishes there. At $t=0$, $r=0$ and $r'=1$, giving the required initial data. Finally, $r''+\omega^2r=1/2$ verifies the PDE.

### 5.3 The Stationary Particular-Solution Method

Alternatively, choose a stationary function that satisfies both the boundary data and the source equation:

$$
W(x)=L(x)+\frac{\sin(kx)}{2\omega^2},
\qquad -a^2W''=\tfrac12\sin(kx). \tag{36}
$$

Then $v=u-W$ satisfies a homogeneous fixed-end wave problem with

$$
v(x,0)=-\frac{\sin(kx)}{2\omega^2},
\qquad v_t(x,0)=\sin(kx). \tag{37}
$$

Its single-mode solution is

$$
v(x,t)=\left[-\frac{\cos(\omega t)}{2\omega^2}
+\frac{\sin(\omega t)}{\omega}\right]\sin(kx). \tag{38}
$$

Adding $W$ reproduces the same solution. This example connects boundary homogenization, separation of variables, and the Laplace-transform convolution formula.

## 6. Choosing and Checking a Method

- On the whole line, the spatial Fourier transform turns spatial derivatives into powers of $\mathrm{i}\xi$ and leads to integral kernels.
- On a finite interval with standard homogeneous endpoints, spatial eigenfunctions encode the boundary conditions and yield modal ODEs.
- For time-dependent modal forcing, a one-sided Laplace transform incorporates the initial data and produces causal convolutions.
- For nonzero boundary values, subtract an auxiliary function first and update the source and initial data consistently.

In every case, reconstruct the physical field and verify the PDE, the boundary conditions, and the initial data. A transform-space expression alone is not the final solution.
