# Chapter 8 Laplace Transform

*Conventions: $p=\sigma+\mathrm{i}\omega$; transform pairs are written function first, $\{f(t),F(p)\}$; $\mathrm{e},\mathrm{i},\mathrm{d}$ upright; formulas are numbered $(8.1)$–$(8.24)$.*

---

## 8.1 Definition

For $f(t)$ defined on $[0,+\infty)$ put

\[ F(p)=\int_{0}^{+\infty} f(t)\,\mathrm{e}^{-pt}\,\mathrm{d}t, \tag{8.1} \]

where

\[ p=\sigma+\mathrm{i}\omega \tag{8.2} \]

is a **complex variable**. Then $\{f(t),\,F(p)\}$ is a **Laplace transform pair**, written

\[ \mathcal{L}\left[f(t)\right]=F(p),\qquad\text{or}\qquad \mathcal{L}^{-1}\left[F(p)\right]=f(t). \tag{8.3} \]

**Remarks**

1. $F(p)$ is complex-valued. The imaginary part $\omega$ is exactly the Fourier frequency, the real part $\sigma$ acts as a **damping factor**: multiplying $f$ by $\mathrm{e}^{-\sigma t}$ before transforming is why the Laplace transform reaches functions of moderate growth that the Fourier transform does not.
2. The lower limit is written $0$; for a function with an impulse at $t=0$ the left limit $0^-$ is meant — with $0^-$ one gets $\mathscr{L}[\delta]=1$, with $0^+$ one gets $0$.
3. Only $t\ge 0$ enters $(8.1)$, so the values of $f(t)$ for $t<0$ do not affect $F(p)$: what is transformed is the causal part $f(t)u(t)$.

---

## 8.2 Exponential order and the existence theorem

### 8.2.1 Functions of exponential order

If there exist constants $M>0$ and $\sigma_c\ge 0$ such that

\[ \left|f(t)\right|\le M\,\mathrm{e}^{\sigma_c t},\qquad t\ge 0, \tag{8.4} \]

then $f(t)$ is said to be of **exponential order**, and $\sigma_c$ is called its **growth exponent**.

- $u(t),\ t^n,\ \mathrm{e}^{at},\ \sin\beta t,\ \cos\beta t$ are all of exponential order;
- $t^{-1/2}$ is unbounded as $t\to 0^+$ and is **not** of exponential order, yet $\int_{0}^{+\infty} t^{-1/2}\mathrm{e}^{-pt}\,\mathrm{d}t$ still converges (integrable singularity);
- $\mathrm{e}^{t^{2}}$ grows faster than any exponential function and is not of exponential order — its Laplace transform does not exist. Exponential order is therefore **sufficient, not necessary**.

### 8.2.2 Theorem 8.1 (existence theorem）

**Theorem 8.1.** Let $f(t)$ on $[0,+\infty)$ satisfy

1. the **Dirichlet conditions** (piecewise continuous on every finite interval, finitely many discontinuities of the first kind, finitely many extrema), and
2. $\left|f(t)\right|\le M\,\mathrm{e}^{\sigma_c t}$ (exponential order).

Then

\[ F(p)=\int_{0}^{+\infty} f(t)\,\mathrm{e}^{-pt}\,\mathrm{d}t \tag{8.5} \]

exists and is **analytic** on the half-plane $\mathrm{Re}\,p>\sigma_c$.

### 8.2.3 Proof

**1. Absolute convergence.** For $\sigma=\mathrm{Re}\,p>\sigma_c$, using $\left|\mathrm{e}^{-pt}\right|=\mathrm{e}^{-\sigma t}$,

\[ \int_{0}^{+\infty}\left|f(t)\,\mathrm{e}^{-pt}\right|\mathrm{d}t \le \int_{0}^{+\infty} M\,\mathrm{e}^{(\sigma_c-\sigma)t}\,\mathrm{d}t =\frac{M}{\sigma-\sigma_c}<+\infty . \tag{8.6} \]

**2. Uniform convergence and differentiability.** On $\mathrm{Re}\,p\ge\sigma_0>\sigma_c$ the integral $(8.5)$ converges uniformly, and so does the differentiated integral $\int_{0}^{+\infty} f(t)\,(-t)\,\mathrm{e}^{-pt}\,\mathrm{d}t$; differentiation under the integral sign is therefore legitimate:

\[ F'(p)=\int_{0}^{+\infty} f(t)\left(\mathrm{e}^{-pt}\right)'_{p}\mathrm{d}t =-\int_{0}^{+\infty} t\,f(t)\,\mathrm{e}^{-pt}\,\mathrm{d}t . \tag{8.7} \]

So $F$ is differentiable — hence analytic — on $\mathrm{Re}\,p>\sigma_c$. $\blacksquare$

### 8.2.4 Remarks

1. $F(p)$ is analytic for $\mathrm{Re}\,p>\sigma_c$, and

\[ \lim_{\mathrm{Re}\,p\to+\infty}F(p)=0 . \tag{8.8} \]

2. By **analytic continuation** $F(p)$ is analytic on the whole $p$-plane except at its singularities; the positions of the poles / branch points determine the structure of $f(t)$.
3. **Region of convergence.** The theorem gives the right half-plane $\mathrm{Re}\,p>\sigma_c$ (i.e. $\sigma>\sigma_c$). It differs from function to function: $\mathcal{L}[u]$ converges only for $\mathrm{Re}\,p>0$, $\mathcal{L}[\mathrm{e}^{at}]$ for $\mathrm{Re}\,p>\mathrm{Re}\,a$; for a rational image the ROC is fixed by the rightmost singularity.
4. In the $p$-plane, $\sigma$ is horizontal and $\mathrm{i}\omega$ vertical; the ROC is the half-plane $\sigma>\sigma_c$.

---

## 8.3 Common transform pairs

Every entry below is obtained by **direct integration** of $(8.1)$.

### 8.3.1 $u(t)\ \leftrightarrow\ 1/p$

With $u(t)=1$ for $t\ge 0$ and $0$ for $t<0$,

\[ \mathcal{L}\left[u(t)\right]=\int_{0}^{+\infty}\mathrm{e}^{-pt}\,\mathrm{d}t =\left.\frac{\mathrm{e}^{-pt}}{-p}\right|_{0}^{+\infty}=\frac{1}{p}, \qquad \mathrm{Re}\,p>0 . \tag{8.9} \]

### 8.3.2 Powers $t,\ t^2,\ \dots,\ t^n$

By parts ($u=t,\ \mathrm{d}v=\mathrm{e}^{-pt}\mathrm{d}t$):

\[ \mathcal{L}\left[t\right]=\int_{0}^{+\infty} t\,\mathrm{e}^{-pt}\,\mathrm{d}t =\left[t\left(-\frac{\mathrm{e}^{-pt}}{p}\right)\right]_{0}^{+\infty}+\int_{0}^{+\infty}\frac{\mathrm{e}^{-pt}}{p}\,\mathrm{d}t=\frac{1}{p^{2}}, \tag{8.10} \]

\[ \mathcal{L}\left[t^{2}\right]=\left[t^{2}\left(-\frac{\mathrm{e}^{-pt}}{p}\right)\right]_{0}^{+\infty}+\frac{2}{p}\int_{0}^{+\infty} t\,\mathrm{e}^{-pt}\,\mathrm{d}t=\frac{2!}{p^{3}}, \tag{8.11} \]

and in general (by induction)

\[ \mathcal{L}\left[t^{n}\right]=\frac{n!}{p^{\,n+1}},\qquad \mathrm{Re}\,p>0 . \tag{8.12} \]

### 8.3.3 Exponential $\mathrm{e}^{at}\ \leftrightarrow\ 1/(p-a)$

\[ \mathcal{L}\left[\mathrm{e}^{at}\right]=\int_{0}^{+\infty}\mathrm{e}^{(a-p)t}\,\mathrm{d}t =\left.\frac{\mathrm{e}^{(a-p)t}}{a-p}\right|_{0}^{+\infty}=\frac{1}{p-a}, \tag{8.13} \]

which converges for $\mathrm{Re}(a-p)<0$, i.e. $\mathrm{Re}\,p>\mathrm{Re}\,a$.

### 8.3.4 Sine and cosine (via Euler's formula)

From $\sin\beta t=\dfrac{\mathrm{e}^{\mathrm{i}\beta t}-\mathrm{e}^{-\mathrm{i}\beta t}}{2\mathrm{i}}$, and using linearity (Property 1),

\[ \mathcal{L}\left[\sin\beta t\right]=\frac{1}{2\mathrm{i}}\left(\frac{1}{p-\mathrm{i}\beta}-\frac{1}{p+\mathrm{i}\beta}\right) =\frac{1}{2\mathrm{i}}\cdot\frac{2\mathrm{i}\beta}{p^{2}+\beta^{2}} =\frac{\beta}{p^{2}+\beta^{2}} . \tag{8.14} \]

Similarly, from $\cos\beta t=\dfrac{\mathrm{e}^{\mathrm{i}\beta t}+\mathrm{e}^{-\mathrm{i}\beta t}}{2}$,

\[ \mathcal{L}\left[\cos\beta t\right]=\frac{p}{p^{2}+\beta^{2}} . \tag{8.15} \]

### 8.3.5 Hyperbolic functions

From $\operatorname{sh}\beta t=\dfrac{\mathrm{e}^{\beta t}-\mathrm{e}^{-\beta t}}{2}$, $\operatorname{ch}\beta t=\dfrac{\mathrm{e}^{\beta t}+\mathrm{e}^{-\beta t}}{2}$,

\[ \mathcal{L}\left[\operatorname{sh}\beta t\right]=\frac{\beta}{p^{2}-\beta^{2}},\qquad \mathcal{L}\left[\operatorname{ch}\beta t\right]=\frac{p}{p^{2}-\beta^{2}} . \tag{8.16} \]

### 8.3.6 Table 8.1 — pairs used in practice

| No. | $f(t)$, $t\ge0$ | $F(p)=\mathcal{L}[f(t)]$ | ROC |
| :--: | :-- | :-- | :-- |
| 1 | $u(t)$ | $\dfrac{1}{p}$ | $\mathrm{Re}\,p>0$ |
| 2 | $t$ | $\dfrac{1}{p^{2}}$ | $\mathrm{Re}\,p>0$ |
| 3 | $t^{n}$ | $\dfrac{n!}{p^{\,n+1}}$ | $\mathrm{Re}\,p>0$ |
| 4 | $\mathrm{e}^{at}$ | $\dfrac{1}{p-a}$ | $\mathrm{Re}\,p>\mathrm{Re}\,a$ |
| 5 | $\sin\beta t$ | $\dfrac{\beta}{p^{2}+\beta^{2}}$ | $\mathrm{Re}\,p>0$ |
| 6 | $\cos\beta t$ | $\dfrac{p}{p^{2}+\beta^{2}}$ | $\mathrm{Re}\,p>0$ |
| 7 | $\operatorname{sh}\beta t$ | $\dfrac{\beta}{p^{2}-\beta^{2}}$ | $\mathrm{Re}\,p>\lvert\beta\rvert$ |
| 8 | $\operatorname{ch}\beta t$ | $\dfrac{p}{p^{2}-\beta^{2}}$ | $\mathrm{Re}\,p>\lvert\beta\rvert$ |

> Entry 4 and entries 5–6 are derived with Euler's formula; the rest follow by direct integration.

---

## 8.4 Properties 1–4

Throughout, $\{f(t),F(p)\}$, $\{f_1(t),F_1(p)\}$, $\{f_2(t),F_2(p)\}$ are transform pairs.

### 8.4.1 Property 1 — linearity

For constants $a,b$,

\[ \mathcal{L}\left[a f_1+b f_2\right]=aF_1+bF_2 \tag{8.17} \]

and the inverse is linear as well:

\[ \mathcal{L}^{-1}\left[aF_1+bF_2\right]=a f_1+b f_2 . \tag{8.18} \]

**Example ( partial fractions).** Find $\mathcal{L}^{-1}\left[\dfrac{p}{(p-1)(p^{2}+4)}\right]$.

\[ \frac{p}{(p-1)(p^{2}+4)}=\frac{A}{p-1}+\frac{Bp+C}{p^{2}+4} \quad\Longrightarrow\quad A=\frac15,\qquad Bp+C=-\frac15p+\frac45, \]

so, with Table 8.1 (entries 4, 5, 6),

\[ \mathcal{L}^{-1}\left[\frac{p}{(p-1)(p^{2}+4)}\right] =\frac15\mathrm{e}^{t}-\frac15\cos 2t+\frac25\sin 2t . \tag{8.19} \]

### 8.4.2 Property 2 — similarity

For $a>0$,

\[ \mathcal{L}\left[f(at)\right]=\frac{1}{a}F\!\left(\frac{p}{a}\right), \tag{8.20} \]

equivalently (replace $a$ by $1/a$),

\[ \mathcal{L}\left[\frac{1}{a}f\!\left(\frac{t}{a}\right)\right]=F(ap). \tag{8.21} \]

*Proof (sketch).* With $\tau=at$, $\mathrm{d}t=\mathrm{d}\tau/a$,

\[ \mathcal{L}\left[f(at)\right]=\frac{1}{a}\int_{0}^{+\infty} f(\tau)\,\mathrm{e}^{-(p/a)\tau}\,\mathrm{d}\tau=\frac{1}{a}F\!\left(\frac{p}{a}\right). \]

### 8.4.3 Property 3 — delay (time shift of $f(t)u(t)$)

\[ \mathcal{L}\left[f(t-t_0)\,u(t-t_0)\right]=\mathrm{e}^{-pt_0}F(p), \tag{8.22} \]

with inverse

\[ \mathcal{L}^{-1}\left[\mathrm{e}^{-pt_0}F(p)\right]=f(t-t_0)\,u(t-t_0)\qquad(t_0>0). \tag{8.23} \]

**Note.** The shift must act on the *whole* function, i.e. $f(t-t_0)$ must carry $u(t-t_0)$; otherwise $f$ is non-zero for $t<t_0$ and the transform is wrong.

*Proof (sketch).* With $\tau=t-t_0$,

\[ \mathcal{L}\left[f(t-t_0)u(t-t_0)\right]=\int_{t_0}^{+\infty} f(t-t_0)\,\mathrm{e}^{-pt}\,\mathrm{d}t=\int_{0}^{+\infty} f(\tau)\,\mathrm{e}^{-p(\tau+t_0)}\,\mathrm{d}\tau=\mathrm{e}^{-pt_0}F(p). \]

### 8.4.4 Property 4 — frequency shift

\[ \mathcal{L}\left[\mathrm{e}^{at}f(t)\right]=F(p-a). \tag{8.24} \]

*Proof .* Substitute $p\mapsto p-a$ in the definition:

\[ F(p-a)=\int_{0}^{+\infty} f(t)\,\mathrm{e}^{-(p-a)t}\,\mathrm{d}t =\int_{0}^{+\infty}\left[\mathrm{e}^{at}f(t)\right]\mathrm{e}^{-pt}\,\mathrm{d}t =\mathcal{L}\left[\mathrm{e}^{at}f(t)\right]. \]

**Use.** Together with Property 1 and Table 8.1 this is the "table + partial fractions + shift" inversion recipe, e.g.

\[ \mathcal{L}^{-1}\left[\frac{1}{(p-a)^{2}}\right]=t\,\mathrm{e}^{at},\qquad \mathcal{L}^{-1}\left[\frac{p-a}{(p-a)^{2}+\beta^{2}}\right]=\mathrm{e}^{at}\cos\beta t . \]

### 8.4.5 Table 8.2 — the four properties at a glance

| Property | Content | No. |
| :-- | :-- | :--: |
| 1 Linearity | $\mathcal{L}[af_1+bf_2]=a\mathcal{L}[f_1]+b\mathcal{L}[f_2]$; same for $\mathcal{L}^{-1}$ | (8.17)(8.18) |
| 2 Similarity | $\mathcal{L}[f(at)]=\dfrac{1}{a}F\!\left(\dfrac{p}{a}\right)$, $a>0$ | (8.20) |
| 3 Delay | $\mathcal{L}[f(t-t_0)u(t-t_0)]=\mathrm{e}^{-pt_0}F(p)$ | (8.22) |
| 4 Frequency shift | $\mathcal{L}[\mathrm{e}^{at}f(t)]=F(p-a)$ | (8.24) |

---

## 8.5 Homework

- **A** 9, 10; **B** 1, 2, 5, 6, 8.
