# Chapter 17 The Inverse Laplace Transform and Its Applications

The core of integral-transform theory can be summarized in four items:

1. **Definition and theorems**: the Fourier transform (on $(-\infty,+\infty)$) and the Laplace transform (on $[0,+\infty)$), together with their existence theorems;
2. **Common transform pairs**: elementary functions;
3. **Properties**: linearity, similarity, delay (time shift), frequency shift, differentiation, integration, periodicity — about seven or eight basic properties (here too "seven or eight" is approximate; the definitive list is the one collected in Chapter 16);
4. **Applications**: solving differential and integral equations, and evaluating certain generalized integrals.

## 17.1 The Inverse Laplace Transform

### 17.1.1 The Complex Inversion Integral Formula

Everything rests on one observation: the Laplace transform of $f(t)$ is exactly the Fourier transform of $f(t)u(t)\mathrm{e}^{-\sigma t}$, where $\sigma$ is a real constant. Indeed, $u(t)$ pulls the lower limit from $-\infty$ to $0$,

\[ \mathcal{F}\left[f(t)u(t)\mathrm{e}^{-\sigma t}\right]=\int_{-\infty}^{+\infty}f(t)u(t)\mathrm{e}^{-\sigma t}\mathrm{e}^{-\mathrm{i}\omega t}\,\mathrm{d}t=\int_{0}^{+\infty}f(t)\mathrm{e}^{-(\sigma+\mathrm{i}\omega)t}\,\mathrm{d}t=F(p),\qquad p=\sigma+\mathrm{i}\omega. \]

Applying the Fourier integral formula to $f(t)u(t)\mathrm{e}^{-\sigma t}$ gives

\[ f(t)u(t)\mathrm{e}^{-\sigma t}=\frac{1}{2\pi}\int_{-\infty}^{+\infty}F(\sigma+\mathrm{i}\omega)\,\mathrm{e}^{\mathrm{i}\omega t}\,\mathrm{d}\omega . \]

Multiply by $\mathrm{e}^{\sigma t}$ and use $u(t)=1$ for $t>0$; then substitute $p=\sigma+\mathrm{i}\omega$, so that $\mathrm{d}p=\mathrm{i}\,\mathrm{d}\omega$ and $\omega:-\infty\to+\infty$ corresponds to $p:\sigma-\mathrm{i}\infty\to\sigma+\mathrm{i}\infty$. This yields

\[ f(t)=\frac{1}{2\pi}\int_{-\infty}^{+\infty}F(\sigma+\mathrm{i}\omega)\,\mathrm{e}^{(\sigma+\mathrm{i}\omega)t}\,\mathrm{d}\omega
=\frac{1}{2\pi\mathrm{i}}\int_{\sigma-\mathrm{i}\infty}^{\sigma+\mathrm{i}\infty}F(p)\,\mathrm{e}^{pt}\,\mathrm{d}p\qquad(t>0). \tag{17.1} \]

The factor in front differs between the two forms ($1/2\pi$ versus $1/(2\pi\mathrm{i})$); the difference is precisely $\mathrm{d}p=\mathrm{i}\,\mathrm{d}\omega$. The integral on the right is called the **Bromwich integral**; its path is any line $\operatorname{Re}p=\sigma$ parallel to the imaginary axis, lying in the region of convergence.

**Theorem 17.1 (complex inversion integral)**

Let $f(t)$ be piecewise smooth on $t\ge0$ and of exponential order, $\left|f(t)\right|\le M\mathrm{e}^{\sigma_c t}$, and let $\mathcal{L}\left[f(t)\right]=F(p)$. Take $\sigma>\sigma_c$. Then for $t>0$

\[ f(t)=\frac{1}{2\pi\mathrm{i}}\int_{\sigma-\mathrm{i}\infty}^{\sigma+\mathrm{i}\infty}F(p)\,\mathrm{e}^{pt}\,\mathrm{d}p , \tag{17.2} \]

where at a discontinuity of $f$ the left-hand side is to be replaced by the mean of the one-sided limits, $\dfrac{f(t+0)+f(t-0)}{2}$.

The condition $\sigma>\sigma_c$ makes $f(t)u(t)\mathrm{e}^{-\sigma t}$ absolutely integrable on $(-\infty,+\infty)$, which is what the Fourier integral formula requires; it also puts the path inside the region of convergence $\operatorname{Re}p>\sigma_{0}$ ($\sigma_{0}$ is the abscissa of convergence, $\sigma_{0}\le\sigma_{c}$). The image function must in addition satisfy $\lim_{p\to\infty}F(p)=0$ — the necessary condition for a Laplace transform (Chapter 16, remark (1)).

### 17.1.2 Inversion by the Residue Theorem

The complex integral (17.2) is rarely evaluated directly; instead the path is closed to the left and the integral becomes a sum of residues.

Close the path with the left semicircle $C_{\rho}$ of radius $\rho$ centred at $\sigma+\mathrm{i}0$, which together with the vertical segment bounds a left half-disc. On $C_{\rho}$ write $p=\sigma+\rho\mathrm{e}^{\mathrm{i}\theta}$ with $\pi/2<\theta<3\pi/2$; then

\[ \left|\mathrm{e}^{pt}\right|=\mathrm{e}^{\sigma t}\mathrm{e}^{\rho t\cos\theta},\qquad \cos\theta<0 . \]

The exponential factor decays along the arc, and the integral over the arc is bounded by $\dfrac{\pi\mathrm{e}^{\sigma t}}{t}$ (the mechanism behind Jordan's lemma). Hence, provided $F(p)$ tends to zero uniformly on the arc — guaranteed by $\lim_{p\to\infty}F(p)=0$ — the arc integral tends to zero as $\rho\to+\infty$. For $t<0$ the exponential factor forces the path to be closed to the right, where there are no singularities, so the integral vanishes; this is why (17.2) is stated for $t>0$ only.

**Theorem 17.2 (inversion by residues)**

Let $F(p)$ have finitely many singular points $p_{1},\dots,p_{n}$, all to the left of the line $\operatorname{Re}p=\sigma$, and let $\lim_{p\to\infty}F(p)=0$. Then for $t>0$

\[ f(t)=\mathcal{L}^{-1}\left[F(p)\right]=\sum_{k=1}^{n}\operatorname{Res}\left[F(p)\,\mathrm{e}^{pt},\,p_{k}\right]. \tag{17.3} \]

Proof.

Combine the path of (17.2) with the left semicircle into a counterclockwise closed contour containing every singularity of $F(p)\mathrm{e}^{pt}$. By the residue theorem the contour integral equals $2\pi\mathrm{i}\sum_{k}\operatorname{Res}$; letting $\rho\to+\infty$, the arc integral vanishes and the vertical segment tends to the path of (17.2), which gives (17.3). $\blacksquare$

For a rational function $F(p)=\dfrac{A(p)}{B(p)}$ with $\deg B>\deg A$ all singularities are poles and $F(\infty)=0$ holds automatically, so this is the case met in practice. If every $p_{k}$ is a simple pole,

\[ f(t)=\sum_{k=1}^{n}\frac{A(p_{k})}{B'(p_{k})}\,\mathrm{e}^{p_{k}t} ; \tag{17.4} \]

if $p_{k}$ is a pole of order $m_{k}$,

\[ f(t)=\sum_{k=1}^{n}\frac{1}{(m_{k}-1)!}\lim_{p\to p_{k}}\frac{\mathrm{d}^{m_{k}-1}}{\mathrm{d}p^{m_{k}-1}}\left[(p-p_{k})^{m_{k}}\frac{A(p)}{B(p)}\,\mathrm{e}^{pt}\right]. \tag{17.5} \]

**Example 17.1**

Find $\mathcal{L}^{-1}\left[\dfrac{1}{p^{2}+1}\right]$.

Solution.

The poles $p=\pm\mathrm{i}$ are simple; by (17.4),

\[ \mathcal{L}^{-1}\left[\frac{1}{p^{2}+1}\right]=\frac{\mathrm{e}^{\mathrm{i}t}}{2\mathrm{i}}+\frac{\mathrm{e}^{-\mathrm{i}t}}{2(-\mathrm{i})}=\sin t . \]

**Example 17.2**

Solve the initial-value problem

\[ x''(t)-2x'(t)+2x(t)=2\mathrm{e}^{t}\cos t,\qquad x(0)=0,\quad x'(0)=0 . \]

Solution.

Transforming ($\mathcal{L}[x'']=p^{2}X$, $\mathcal{L}[x']=pX$, $\mathcal{L}\left[2\mathrm{e}^{t}\cos t\right]=\dfrac{2(p-1)}{(p-1)^{2}+1}$) gives

\[ X(p)=\frac{2(p-1)}{\left[(p-1)^{2}+1\right]^{2}} . \]

**Method 1 (residues).** The points $p=1\pm\mathrm{i}$ are poles of **order two**, so (17.5) applies. For $p_{0}=1+\mathrm{i}$,

\[ \operatorname{Res}\left[X(p)\mathrm{e}^{pt},1+\mathrm{i}\right]=\lim_{p\to1+\mathrm{i}}\frac{\mathrm{d}}{\mathrm{d}p}\left[\frac{2(p-1)\mathrm{e}^{pt}}{\left(p-1+\mathrm{i}\right)^{2}}\right], \]

and after differentiating, substituting $p=1+\mathrm{i}$ and adding the residue at $p=1-\mathrm{i}$, the answer is again $\mathrm{e}^{t}t\sin t$. The differentiation and substitution for a second-order pole are laborious — that is the drawback of this route.

**Method 2 (properties).** Put $q=p-1$; what has to be inverted is $\mathcal{L}^{-1}\left[\dfrac{2q}{\left(q^{2}+1\right)^{2}}\right]$. By the derivative-of-the-image property, $\dfrac{\mathrm{d}}{\mathrm{d}p}\dfrac{1}{p^{2}+1}=-\dfrac{2p}{\left(p^{2}+1\right)^{2}}$, i.e.

\[ \mathcal{L}\left[t\sin t\right]=-\left(\frac{1}{p^{2}+1}\right)'=\frac{2p}{\left(p^{2}+1\right)^{2}}, \]

so $\mathcal{L}^{-1}\left[\dfrac{2q}{\left(q^{2}+1\right)^{2}}\right]=t\sin t$. Then the shift property $\mathcal{L}^{-1}\left[F(p-p_{0})\right]=\mathrm{e}^{p_{0}t}\mathcal{L}^{-1}\left[F(p)\right]$ with $p_{0}=1$ restores $q\to p-1$:

\[ x(t)=\mathrm{e}^{t}\,t\sin t . \]

Both methods agree; whenever the properties suffice, the residues are not worth the work.

## 17.2 Applications of the Laplace Transform

Solving a linear differential (integral) equation by the Laplace transform takes three steps:

1. transform the equation, turning the differential (integral) equation into an **algebraic** equation for the image function;
2. solve that algebraic equation for $X(p)$;
3. invert $X(p)$ to obtain the solution.

Step 3 usually splits $X(p)$ into table entries by partial fractions, or uses the residue formula of §17.1.2.

### 17.2.1 Linear Differential (and Integral) Equations

**Example 17.3**

Solve the differential-integral equation

\[ x'(t)-2\int_{0}^{t}u(s)\,x(t-s)\,\mathrm{d}s+3\int_{0}^{t}x(s)\,\mathrm{d}s=u(t-1),\qquad x(0)=0 , \]

where $u(t)$ is the unit step function.

Solution.

Transform the four terms separately:

- first term: $\mathcal{L}\left[x'\right]=pX(p)-x(0)=pX$;
- second term: $\displaystyle\int_{0}^{t}u(s)x(t-s)\,\mathrm{d}s=u(t)*x(t)$ is a convolution, so by the convolution theorem $\mathcal{L}\left[u*x\right]=\dfrac{X(p)}{p}$ (since $\mathcal{L}[u]=\dfrac{1}{p}$);
- third term: by the integration property $\mathcal{L}\left[\displaystyle\int_{0}^{t}x(s)\,\mathrm{d}s\right]=\dfrac{X(p)}{p}$;
- right-hand side: $\mathcal{L}\left[u(t-1)\right]=\dfrac{\mathrm{e}^{-p}}{p}$.

Hence

\[ pX-\frac{2}{p}X+\frac{3}{p}X=\frac{\mathrm{e}^{-p}}{p}, \]

and multiplying by $p$ gives $\left(p^{2}+1\right)X=\mathrm{e}^{-p}$, i.e.

\[ X(p)=\frac{\mathrm{e}^{-p}}{p^{2}+1} . \]

By the delay property the factor $\mathrm{e}^{-p}$ simply shifts $\sin t$ to the right by 1:

\[ x(t)=u(t-1)\sin(t-1). \]

The factor $u(t-1)$ cannot be omitted: for $t<1$ both the right-hand side and the initial data vanish, so the solution must vanish too, while for $t\ge1$ it is a sine oscillation of unit amplitude.

The same three steps cover systems of constant-coefficient equations (reduced to a linear algebraic system for the images), boundary-value problems with a condition at one end only (the unknown initial value at the other end is carried as a parameter and fixed afterwards), and circuit equations such as the series $RLC$ circuit (where the inductance and capacitance contribute $LpI$ and $I/(Cp)$).

### 17.2.2 Generalized Integrals

The integration and differentiation properties of the image function yield two classes of generalized integrals.

**Type 1 (containing $1/t$).** Let $F(p)=\mathcal{L}[f(t)]$. The integration property of the image function gives $\mathcal{L}\left[\dfrac{f(t)}{t}\right]=\displaystyle\int_{p}^{+\infty}F(s)\,\mathrm{d}s$. Letting $p\to0^{+}$ along the real axis inside the region of convergence, and using the continuity of the Laplace integral at a point of convergence (Abel's theorem),

\[ \int_{0}^{+\infty}\frac{f(t)}{t}\,\mathrm{d}t=\lim_{p\to0^{+}}\int_{p}^{+\infty}F(s)\,\mathrm{d}s=\int_{0}^{+\infty}F(s)\,\mathrm{d}s . \]

Setting $\mathrm{e}^{-pt}=1$ in the integrand is not a licence taken lightly: its legitimacy is exactly Abel's theorem.

**Example 17.4**

Evaluate the Dirichlet integral $\displaystyle\int_{0}^{+\infty}\frac{\sin t}{t}\,\mathrm{d}t$.

Solution.

Take $f(t)=\sin t$, $F(p)=\dfrac{1}{p^{2}+1}$; by Type 1,

\[ \int_{0}^{+\infty}\frac{\sin t}{t}\,\mathrm{d}t=\int_{0}^{+\infty}\frac{\mathrm{d}s}{1+s^{2}}=\left.\arctan s\right|_{0}^{+\infty}=\frac{\pi}{2} . \]

**Type 2 (containing $t^{n}$).** The derivative-of-the-image property gives $F^{(n)}(p)=(-1)^{n}\displaystyle\int_{0}^{+\infty}t^{n}f(t)\mathrm{e}^{-pt}\,\mathrm{d}t$. Letting $p\to0$ (with $F$ analytic on $\operatorname{Re}p\ge0$ and the integral on the left convergent),

\[ \int_{0}^{+\infty}t^{n}f(t)\,\mathrm{d}t=(-1)^{n}F^{(n)}(0). \]

**Example 17.5**

Evaluate $\displaystyle\int_{0}^{+\infty}t^{2}\mathrm{e}^{-\alpha t}\sin\beta t\,\mathrm{d}t\quad(\alpha,\beta>0)$.

Solution.

Take $f(t)=\mathrm{e}^{-\alpha t}\sin\beta t$, $F(p)=\dfrac{\beta}{(p+\alpha)^{2}+\beta^{2}}$; by Type 2 with $n=2$,

\[ \int_{0}^{+\infty}t^{2}\mathrm{e}^{-\alpha t}\sin\beta t\,\mathrm{d}t=F''(0)=\left.\frac{-2\beta\left[\beta^{2}-3(p+\alpha)^{2}\right]}{\left[(p+\alpha)^{2}+\beta^{2}\right]^{3}}\right|_{p=0}=\frac{2\beta\left(3\alpha^{2}-\beta^{2}\right)}{\left(\alpha^{2}+\beta^{2}\right)^{3}} . \]

For $\beta>\sqrt3\,\alpha$ the result is negative: the rapid oscillation of $\sin\beta t$ makes the positive and negative parts almost cancel. This is not a computational slip.

**Complex-parameter method.** Writing $\sin\beta t=\operatorname{Im}\mathrm{e}^{\mathrm{i}\beta t}$, the integral is the image function evaluated at $p=\alpha-\mathrm{i}\beta$:

\[ \int_{0}^{+\infty}t^{2}\mathrm{e}^{-\alpha t}\mathrm{e}^{\mathrm{i}\beta t}\,\mathrm{d}t=\left.\frac{2}{p^{3}}\right|_{p=\alpha-\mathrm{i}\beta}=\frac{2}{(\alpha-\mathrm{i}\beta)^{3}}, \]

whose imaginary part reproduces the result above. In general, for real-valued $f$ and $\alpha$ inside the region of convergence,

\[ \int_{0}^{+\infty}f(t)\mathrm{e}^{-\alpha t}\sin\beta t\,\mathrm{d}t=\operatorname{Im}F(\alpha-\mathrm{i}\beta),\qquad
\int_{0}^{+\infty}f(t)\mathrm{e}^{-\alpha t}\cos\beta t\,\mathrm{d}t=\operatorname{Re}F(\alpha-\mathrm{i}\beta). \]

This is the standard way to evaluate generalized integrals carrying a damping factor $\mathrm{e}^{-\alpha t}$: evaluate the image function at a complex parameter, then take its imaginary or real part.

At this point the integral-transform part is complete: the definitions, common pairs and properties of the Fourier and Laplace transforms, together with the inversion and applications of this chapter. The next chapter begins the theory of equations of mathematical physics — the derivation and solution of the wave, heat and potential equations.
