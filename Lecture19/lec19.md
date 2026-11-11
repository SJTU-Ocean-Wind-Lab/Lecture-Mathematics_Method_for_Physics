# Chapter 19: Method of Separation of Variables

Separation of variables converts a homogeneous PDE with homogeneous boundary conditions into an eigenvalue problem and ordinary differential equations. We first solve a finite-string problem, then use the same spatial eigenfunctions for heat and potential equations.

## 1. A String with Two Fixed Ends

### 1.1 The Initial-Boundary-Value Problem

Let $a>0$ and $\ell>0$. Consider

$$
\begin{cases}
u_{tt}-a^2u_{xx}=0,&0<x<\ell,\ t>0,\\
u(0,t)=u(\ell,t)=0,\\
u(x,0)=\varphi(x),\qquad u_t(x,0)=\psi(x).
\end{cases} \tag{1}
$$

Seek a nonzero separated solution $u(x,t)=X(x)T(t)$. Substitution into the PDE gives $XT''-a^2X''T=0$. Where division is possible,

$$
\frac{X''(x)}{X(x)}=\frac{T''(t)}{a^2T(t)}=-\lambda. \tag{2}
$$

The two sides depend on different independent variables and therefore equal a constant. The resulting equations, valid also at zeros by continuity, are

$$
X''+\lambda X=0,\qquad T''+a^2\lambda T=0,
\qquad X(0)=X(\ell)=0. \tag{3}
$$

The boundary condition at the right fixed end is $X(\ell)=0$, not $X'(\ell)=0$.

### 1.2 Eigenvalues and Eigenfunctions

An **eigenvalue** is a value of $\lambda$ for which the spatial boundary-value problem admits a nonzero solution $X$, called an **eigenfunction**.

**Case $\lambda=0$.** The general solution $X=C_1+C_2x$ satisfies both fixed-end conditions only when $C_1=C_2=0$. Thus zero is not an eigenvalue for this boundary pair.

**Case $\lambda=-\mu^2<0$.** Write $X=C_1\cosh(\mu x)+C_2\sinh(\mu x)$. The left condition sets $C_1=0$; since $\sinh(\mu\ell)>0$, the right condition sets $C_2=0$. Again there is no nonzero solution.

**Case $\lambda=k^2>0$.** The general solution is $X=C_1\cos(kx)+C_2\sin(kx)$. The conditions require $C_1=0$ and $\sin(k\ell)=0$. Therefore,

$$
k_n=\frac{n\pi}{\ell},\qquad
\lambda_n=k_n^2,\qquad
X_n(x)=\sin(k_nx),\qquad n=1,2,\ldots. \tag{4}
$$

The time equation has angular frequency $\omega_n=ak_n$ and solution

$$
T_n(t)=A_n\cos(\omega_nt)+B_n\sin(\omega_nt). \tag{5}
$$

### 1.3 Superposition and Orthogonality

Each product $X_nT_n$ satisfies the PDE and homogeneous boundary conditions. Linearity suggests the series

$$
u(x,t)=\sum_{n=1}^{\infty}
\bigl[A_n\cos(\omega_nt)+B_n\sin(\omega_nt)\bigr]\sin(k_nx). \tag{6}
$$

The sine eigenfunctions are orthogonal:

$$
\int_0^\ell\sin(k_nx)\sin(k_mx)\,\mathrm{d}x
=\begin{cases}0,&n\ne m,\\\ell/2,&n=m.\end{cases} \tag{7}
$$

At $t=0$, the displacement and velocity expansions are

$$
\varphi(x)=\sum_{n=1}^{\infty}A_n\sin(k_nx),
\qquad
\psi(x)=\sum_{n=1}^{\infty}\omega_n B_n\sin(k_nx). \tag{8}
$$

Multiply by $\sin(k_mx)$ and integrate over $[0,\ell]$. Orthogonality gives

$$
A_n=\frac{2}{\ell}\int_0^\ell\varphi(x)\sin(k_nx)\,\mathrm{d}x,
\qquad
B_n=\frac{2}{\ell\omega_n}\int_0^\ell\psi(x)\sin(k_nx)\,\mathrm{d}x. \tag{9}
$$

The factor $1/\omega_n$ in $B_n$ is essential: differentiating $\sin(\omega_nt)$ produces $\omega_n$.

## 2. Examples for Fixed Ends

### 2.1 A Polynomial Initial Displacement

Take $\varphi(x)=C x(\ell-x)$ and $\psi(x)=0$, where $C$ absorbs the constant amplitude factor used in the source example. Then $B_n=0$. Two integrations by parts give

$$
\int_0^\ell x(\ell-x)\sin(k_nx)\,\mathrm{d}x
=\frac{2[1-(-1)^n]}{k_n^3}. \tag{10}
$$

It follows that

$$
A_n=\frac{4C\ell^2}{n^3\pi^3}[1-(-1)^n]. \tag{11}
$$

Only odd modes remain:

$$
u(x,t)=\frac{8C\ell^2}{\pi^3}
\sum_{j=0}^{\infty}
\frac{\cos((2j+1)\pi at/\ell)\sin((2j+1)\pi x/\ell)}{(2j+1)^3}. \tag{12}
$$

### 2.2 Initial Data Containing Only Two Modes

Suppose

$$
\varphi(x)=\sin\frac{\pi x}{\ell},
\qquad \psi(x)=\sin\frac{4\pi x}{\ell}. \tag{13}
$$

Orthogonality yields $A_1=1$, $B_4=\ell/(4\pi a)$, and all other coefficients zero. Thus

$$
u(x,t)=\cos\frac{\pi at}{\ell}\sin\frac{\pi x}{\ell}
+\frac{\ell}{4\pi a}\sin\frac{4\pi at}{\ell}\sin\frac{4\pi x}{\ell}. \tag{14}
$$

Although the general method gives an infinite series, data involving finitely many eigenfunctions give a finite expression.

## 3. How Boundary Conditions Select the Spectrum

### 3.1 The Four Standard Endpoint Pairs

All four cases below solve $X''+\lambda X=0$ on $0<x<\ell$. Eigenfunctions may be multiplied by any nonzero constant.

**Dirichlet-Dirichlet:** $X(0)=X(\ell)=0$ gives

$$
k_n=\frac{n\pi}{\ell},\quad \lambda_n=k_n^2,\quad
X_n=\sin(k_nx),\quad n\ge1. \tag{15}
$$

**Dirichlet-Neumann:** $X(0)=X'(\ell)=0$ gives

$$
k_n=\frac{(2n-1)\pi}{2\ell},\quad \lambda_n=k_n^2,\quad
X_n=\sin(k_nx),\quad n\ge1. \tag{16}
$$

Indeed, $X(0)=0$ removes the cosine term and $X'(\ell)=0$ requires $\cos(k\ell)=0$.

**Neumann-Dirichlet:** $X'(0)=X(\ell)=0$ gives

$$
k_n=\frac{(2n-1)\pi}{2\ell},\quad \lambda_n=k_n^2,\quad
X_n=\cos(k_nx),\quad n\ge1. \tag{17}
$$

**Neumann-Neumann:** $X'(0)=X'(\ell)=0$ gives a zero mode and positive modes:

$$
\begin{aligned}
&\lambda_0=0,\qquad X_0(x)=1,\\
&k_n=\frac{n\pi}{\ell},\quad\lambda_n=k_n^2,\quad
X_n(x)=\cos(k_nx),\quad n\ge1.
\end{aligned} \tag{18}
$$

For every nonzero mode in these four cases, the squared norm is $\ell/2$. For the constant Neumann mode, it is $\ell$.

### 3.2 Example with One Fixed and One Free End

Consider $u(0,t)=0$, $u_x(\ell,t)=0$, and initial data

$$
\varphi(x)=3\sin\frac{3\pi x}{2\ell}+6\sin\frac{5\pi x}{2\ell},
\qquad \psi(x)=0. \tag{19}
$$

These are the second and third Dirichlet-Neumann eigenfunctions. Hence

$$
\begin{aligned}
u(x,t)={}&3\cos\frac{3\pi at}{2\ell}\sin\frac{3\pi x}{2\ell}\\
&+6\cos\frac{5\pi at}{2\ell}\sin\frac{5\pi x}{2\ell}.
\end{aligned} \tag{20}
$$

### 3.3 Two Free Ends and the Zero Mode

For $u_x(0,t)=u_x(\ell,t)=0$, the wave solution has the form

$$
u(x,t)=A_0+B_0t+
\sum_{n=1}^{\infty}
\bigl[A_n\cos(\omega_nt)+B_n\sin(\omega_nt)\bigr]\cos(k_nx), \tag{21}
$$

where $k_n=n\pi/\ell$ and $\omega_n=ak_n$. The constant mode satisfies $T_0''=0$, not an oscillation equation with nonzero frequency. Its coefficients are

$$
A_0=\frac1\ell\int_0^\ell\varphi(x)\,\mathrm{d}x,
\qquad B_0=\frac1\ell\int_0^\ell\psi(x)\,\mathrm{d}x. \tag{22}
$$

For $n\ge1$,

$$
\begin{aligned}
A_n&=\frac2\ell\int_0^\ell\varphi(x)\cos(k_nx)\,\mathrm{d}x,\\
B_n&=\frac{2}{\ell\omega_n}\int_0^\ell\psi(x)\cos(k_nx)\,\mathrm{d}x.
\end{aligned} \tag{23}
$$

Physically, the mean displacement is $A_0+B_0t$. A string with free ends can translate uniformly, so this mode must not be discarded.

## 4. Heat Conduction on a Finite Interval

### 4.1 The Time Equation Changes

For $u_t-\kappa u_{xx}=0$, with $\kappa>0$, substitute $u=XT$ and use the same spatial equation $X''+\lambda X=0$. The time equation becomes

$$
T'+\kappa\lambda T=0,
\qquad T_n(t)=C_n\mathrm{e}^{-\kappa\lambda_nt}. \tag{24}
$$

Thus the boundary conditions determine the spatial eigenfunctions, while the PDE determines how their amplitudes evolve.

### 4.2 Insulated Ends

If $u_x(0,t)=u_x(\ell,t)=0$ and $u(x,0)=\varphi(x)$, the solution is

$$
u(x,t)=C_0+\sum_{n=1}^{\infty}C_n
\mathrm{e}^{-\kappa(n\pi/\ell)^2t}\cos\frac{n\pi x}{\ell}, \tag{25}
$$

with

$$
C_0=\frac1\ell\int_0^\ell\varphi(x)\,\mathrm{d}x,
\qquad
C_n=\frac2\ell\int_0^\ell\varphi(x)\cos\frac{n\pi x}{\ell}\,\mathrm{d}x. \tag{26}
$$

The zero mode is constant in time because $T_0'=0$. All nonzero modes decay. Consistently,

$$
\frac{\mathrm{d}}{\mathrm{d}t}\int_0^\ell u(x,t)\,\mathrm{d}x
=\kappa[u_x(\ell,t)-u_x(0,t)]=0. \tag{27}
$$

The long-time temperature approaches the initial spatial average, under conditions ensuring convergence of the expansion.

For endpoints held at zero temperature, replace the cosine family by $\sin(n\pi x/\ell)$ and omit the zero mode. The coefficients are the Fourier sine coefficients of $\varphi$.

## 5. Laplace's Equation in a Rectangle

### 5.1 Separation and the Zero Spatial Mode

Let $0<x<\ell$ and $0<y<b$, and consider

$$
\begin{cases}
u_{xx}+u_{yy}=0,\\
u_x(0,y)=u_x(\ell,y)=0,\\
u(x,0)=g(x),\qquad u(x,b)=h(x).
\end{cases} \tag{28}
$$

Put $u=X(x)Y(y)$. Then

$$
X''+\lambda X=0,\qquad X'(0)=X'(\ell)=0,
\qquad Y''-\lambda Y=0. \tag{29}
$$

The spatial eigenfunctions are $X_0=1$ and $X_n=\cos(k_nx)$, with $k_n=n\pi/\ell$. Their corresponding $y$ factors are

$$
Y_0(y)=\alpha_0+\beta_0y,
\qquad
Y_n(y)=\alpha_n\cosh(k_ny)+\beta_n\sinh(k_ny),\quad n\ge1. \tag{30}
$$

The zero eigenvalue again requires its own linear solution. It cannot be recovered by dividing a positive-mode formula by $k_n$ and then setting $n=0$.

### 5.2 Matching the Remaining Boundary Data

Define the cosine coefficients

$$
\begin{aligned}
g_0&=\frac1\ell\int_0^\ell g(x)\,\mathrm{d}x,&
h_0&=\frac1\ell\int_0^\ell h(x)\,\mathrm{d}x,\\
g_n&=\frac2\ell\int_0^\ell g(x)\cos(k_nx)\,\mathrm{d}x,&
h_n&=\frac2\ell\int_0^\ell h(x)\cos(k_nx)\,\mathrm{d}x.
\end{aligned} \tag{31}
$$

At $y=0$, matching coefficients gives $\alpha_0=g_0$ and $\alpha_n=g_n$. At $y=b$,

$$
\beta_0=\frac{h_0-g_0}{b},
\qquad
\beta_n=\frac{h_n-g_n\cosh(k_nb)}{\sinh(k_nb)},\quad n\ge1. \tag{32}
$$

Equivalently, the complete solution is

$$
\begin{aligned}
u(x,y)={}&g_0\left(1-\frac yb\right)+h_0\frac yb\\
&+\sum_{n=1}^{\infty}
\left[g_n\frac{\sinh(k_n(b-y))}{\sinh(k_nb)}
+h_n\frac{\sinh(k_ny)}{\sinh(k_nb)}\right]\cos(k_nx).
\end{aligned} \tag{33}
$$

Each positive mode is harmonic and has zero $x$ derivative on the vertical sides. The hyperbolic-sine factors select the required value on each horizontal side. The mean mode interpolates linearly between $g_0$ and $h_0$.

## 6. Conditions for Using the Expansions

The coefficient calculations use orthogonal expansions in $L^2(0,\ell)$. A classical solution requires enough regularity and endpoint compatibility to justify differentiation of the series and attainment of the prescribed traces. For less regular data, the expansion can instead be interpreted in the appropriate integral or weak sense; pointwise convergence at a discontinuity does not by itself establish a classical solution there.

The working procedure is:

1. Homogenize boundary data when necessary.
2. Solve the spatial eigenvalue problem and retain every admissible mode, including zero modes.
3. Solve the time or remaining-coordinate equation for each mode.
4. Determine coefficients by orthogonality and check the PDE, boundary data, and initial or remaining boundary data.

The next lecture extends this procedure to forcing terms and explains how Fourier and Laplace transforms produce integral representations.
