## 1. November 8, Monday — Review and Questions

### 1.1 p. 118, Exercise 7 — Computing Laurent Coefficients by Integration

Show that

$$
\cosh(z+1/z)=C_0+\sum_{k=1}^{\infty}C_k(z^k+z^{-k}),
\qquad
C_k=\frac1{2\pi}\int_0^{2\pi}\cos k\varphi\,\cosh(2\cos\varphi)\,d\varphi.
$$

**Proof.** Expand $\cosh(z+1/z)$ on $0<|z|<\infty$:

$$
\cosh(z+1/z)=\sum_{k=-\infty}^{\infty}C_kz^k. \tag{1}
$$

$$
C_k=\frac1{2\pi i}\oint_C\frac{\cosh(z+1/z)}{z^{k+1}}\,dz,\qquad
k=0,\pm1,\pm2,\ldots. \tag{2}
$$

The closed contour $C$ goes once around $z=0$. Take $C:|z|=1$ and put $z=e^{i\varphi}$, $0\le\varphi\le2\pi$. By (2),

$$
\begin{aligned}
C_k&=\frac1{2\pi i}\int_0^{2\pi}
\frac{\cosh(e^{i\varphi}+e^{-i\varphi})}{(e^{i\varphi})^{k+1}}i e^{i\varphi}\,d\varphi\\
&=\frac1{2\pi}\int_0^{2\pi}\frac{\cosh(2\cos\varphi)}{\cos k\varphi+i\sin k\varphi}\,d\varphi\\
&=\frac1{2\pi}\int_0^{2\pi}
\frac{(\cos k\varphi-i\sin k\varphi)\cosh(2\cos\varphi)}
{\cos^2 k\varphi+\sin^2 k\varphi}\,d\varphi\\
&=\frac1{2\pi}\int_0^{2\pi}\cos k\varphi\,\cosh(2\cos\varphi)\,d\varphi.
\end{aligned}
$$

The sine term integrates to zero. Also, $C_{-k}=C_k$.

### 1.2 p. 119, Exercise 5 — Taylor Series and a Recurrence

Consider $f(z)=1/(1-z-z^2)$ and its Taylor series $\sum_{n=0}^{\infty}a_nz^n$ at $z=0$. (1) Find the radius of convergence $R$. (2) Find a recurrence and an explicit expression for $a_n$. (3) Explain why

$$
\frac1{2\pi i}\oint_C
\frac{(1+\xi^2)f(\xi)}{(\xi-z)^{n+1}(1-\xi)}\,d\xi
=\frac{f^{(n)}(z)}{n!},
\qquad |z|<r<R,\quad C:|\xi|=r.
$$

**(1)** Use $R=\min_{z_k\text{ singular}}|z_0-z_k|$. From $1-z-z^2=0$, or $z^2+z-1=0$,

$$
z_{1,2}=\frac{-1\pm\sqrt{1^2+4}}2=\frac{-1\pm\sqrt5}2,
\qquad z_1=\frac{-1+\sqrt5}2,\quad z_2=\frac{-1-\sqrt5}2.
$$

Since $|z_1|<|z_2|$, $R=|z_1|=|z_1-0|=(\sqrt5-1)/2$. Thus $f(z)=\sum_{n=0}^{\infty}a_nz^n$ for $|z|<R$.

**(2)** By the Laurent coefficient formula on $C:|\xi|=r<R$,

$$
\begin{aligned}
a_n&=\frac1{2\pi i}\oint_C\frac{f(\xi)}{(\xi-0)^{n+1}}\,d\xi
=\frac1{2\pi i}\oint_C\frac1{(1-\xi-\xi^2)\xi^{n+1}}\,d\xi,\\
a_{n-1}&=\frac1{2\pi i}\oint_C\frac1{(1-\xi-\xi^2)\xi^n}\,d\xi,\\
a_{n-2}&=\frac1{2\pi i}\oint_C\frac1{(1-\xi-\xi^2)\xi^{n-1}}\,d\xi.
\end{aligned}
$$

$$
\begin{aligned}
a_n&=\frac1{2\pi i}\oint_C
\frac{(1-\xi-\xi^2)+\xi+\xi^2}{(1-\xi-\xi^2)\xi^{n+1}}\,d\xi\\
&=\frac1{2\pi i}\oint_C\frac{d\xi}{\xi^{n+1}}+a_{n-1}+a_{n-2}\\
&=0+a_{n-1}+a_{n-2}\qquad(n>0).
\end{aligned}
$$

The characteristic equation is $r^2-1\cdot r-1=0$, so $r_{1,2}=(1\pm\sqrt5)/2$ with $r_1\ne r_2$. The handwritten solution line reads $a_n=C_1r_1+C_2r_2$, with $C_1,C_2$ to be determined. For the general second-order difference equation $a_n=pa_{n-1}+qa_{n-2}$, the characteristic equation is $r^2-pr-q=0$, with $r_{1,2}=(p\pm\sqrt{p^2+4q})/2$.

**Another approach.** Use partial fractions to obtain an explicit expression. The notes give $1-z-z^2=(z-z_1)(z-z_2)$ and $z_1-z_2=\sqrt5$.

$$
\begin{aligned}
f(z)&=\frac1{(z-z_1)(z-z_2)}
=\left(\frac1{z-z_1}-\frac1{z-z_2}\right)\frac1{z_1-z_2}\\
&=\frac1{\sqrt5}\left(-\frac1{z_1}\frac1{1-z/z_1}
+\frac1{z_2}\frac1{1-z/z_2}\right)\\
&=\frac1{\sqrt5}\left[-\frac1{z_1}\sum_{n=0}^\infty\left(\frac z{z_1}\right)^n
+\frac1{z_2}\sum_{n=0}^\infty\left(\frac z{z_2}\right)^n\right]\\
&=\frac1{\sqrt5}\sum_{n=0}^\infty
\left(-\frac1{z_1^{n+1}}+\frac1{z_2^{n+1}}\right)z^n,
\qquad |z|<R=|z_1|<|z_2|.
\end{aligned}
$$

$$
a_n=\frac1{\sqrt5}\left(-\frac1{z_1^{n+1}}+\frac1{z_2^{n+1}}\right)
=\frac1{\sqrt5}\left(-\frac1{\left(\frac{-1+\sqrt5}2\right)^{n+1}}
+\frac1{\left(\frac{-1-\sqrt5}2\right)^{n+1}}\right).
$$

The signs in the factorization and coefficient formula follow the source.

**(3)** The handwritten cancellation is reproduced below. The contour encloses $\xi=z$ and $|z|<r<R$. The final step invokes the higher-derivative formula.

$$
\begin{aligned}
\frac1{2\pi i}\oint_C\frac{(1+\xi^2)f(\xi)}{(\xi-z)^{n+1}(1-\xi)}\,d\xi
&=\frac1{2\pi i}\oint_C
\frac{(1+\xi^2)/(1-\xi-\xi^2)}{(\xi-z)^{n+1}(1-\xi)}\,d\xi\\
&=\frac1{2\pi i}\oint_C
\frac{1-\xi-\xi^2+\xi+\xi^2}{(1-\xi-\xi^2)(\xi-z)^{n+1}(1-\xi)}\,d\xi\\
&=\frac1{2\pi i}\oint_C
\frac{1/(1-\xi-\xi^2)}{(\xi-z)^{n+1}}\,d\xi
=\frac{f^{(n)}(z)}{n!}.
\end{aligned}
$$

### 1.3 Exercise 8 — A Pole Criterion

Suppose $f(z)\ne0$ in the punctured neighborhood and $z_0$ is an isolated singularity other than an essential singularity. The notes give the criterion

$$
z_0\text{ is a pole of order }n
\quad\Longleftrightarrow\quad
\frac1{2\pi i}\oint_C\frac{zf'(z)}{f(z)}\,dz=-nz_0.
$$

**Proof.** If $z_0$ is a pole of order $n$, write $f(z)=g(z)/(z-z_0)^n$, where $g(z_0)\ne0$ and $g$ is analytic. Then

$$
f'(z)=\frac{g'(z)(z-z_0)^n-n(z-z_0)^{n-1}g(z)}{(z-z_0)^{2n}}
=\frac{(z-z_0)g'(z)-ng(z)}{(z-z_0)^{n+1}}.
$$

$$
\begin{aligned}
\frac1{2\pi i}\oint_C\frac{zf'(z)}{f(z)}\,dz
&=\frac1{2\pi i}\oint_C z\frac{(z-z_0)g'(z)-ng(z)}{g(z)(z-z_0)}\,dz\\
&=\frac1{2\pi i}\left[\oint_C z\frac{g'(z)}{g(z)}\,dz-
\oint_C z\frac n{z-z_0}\,dz\right]\\
&=\frac1{2\pi i}\left[0-n\cdot2\pi i z_0\right]=-nz_0.
\end{aligned}
$$

The first integral vanishes by analyticity. Conversely, the notes compare the value $-nz_0$ with that for a pole of order $m$ and conclude $m=n$. The contour sketch labels $z_0,z_1,z_2$ inside $C$.

### 1.4 p. 143, Exercise 2 — Contour Integrals

Review the residue theorem:

$$
\oint_C f(z)\,dz=2\pi i\sum_{k=1}^n\operatorname{Res}[f,z_k].
$$

The exercise heading lists (1), (2), and (3). The written solutions cover (1) and (2).

**(1)** For $C:|z|=1$,

$$
\oint_C\frac{dz}{z\sin z}=2\pi i\operatorname{Res}\left[\frac1{z\sin z},0\right]
=2\pi iC_{-1}=0.
$$

The point $z=0$ is a double pole. For $0<|z|<\pi$,

$$
\frac1{z\sin z}=\frac{C_{-2}}{z^2}+\frac{C_{-1}}z+C_0+C_1z+\cdots. \tag{*}
$$

**Method 1.** Since $\sin z=z-z^3/3!+\cdots$, divide the series:

$$
\frac1{z\sin z}=\frac1{z(z-z^3/3!+\cdots)}
=\frac1{z^2}\frac{1+0+0+\cdots}{1-z^2/6+\cdots}
=\frac1{z^2}\left(1+\frac{z^2}{6}+\frac{z^4}{36}+\cdots\right).
$$

Thus $C_{-1}=0$ and $\operatorname{Res}[0]=0$. The $z^4$ coefficient follows the source.

More generally, use long division to compute the coefficients in

$$
\frac{a_0+a_1z+a_2z^2+\cdots}{b_0+b_1z+b_2z^2+\cdots}
=C_0+C_1z+C_2z^2+\cdots,\qquad |z|<R=\min\{R_1,R_2\},\quad a_0,b_0\ne0.
$$

The first quotient term is $b_0^{-1}a_0$. Subtract $a_0+b_0^{-1}a_0b_1z+b_0^{-1}a_0b_2z^2+\cdots$ from the numerator. The leading remainder term is $(a_1-b_0^{-1}a_0b_1)z$, giving the next quotient term $b_0^{-1}(a_1-b_0^{-1}a_0b_1)z$.

**Method 2.** Multiply both sides of $(*)$ by $z^2$, differentiate, and let $z\to0$:

$$
\begin{aligned}
\frac{z^2}{z\sin z}&=C_{-2}+C_{-1}z+C_0z^2+C_1z^3+\cdots,\\
\left(\frac z{\sin z}\right)'&=0+C_{-1}+C_0\cdot2z+C_1\cdot3z^2+\cdots,\\
C_{-1}&=\lim_{z\to0}\left(\frac z{\sin z}\right)'
=\lim_{z\to0}\frac{1\cdot\sin z-z\cos z}{\sin^2 z}=0.
\end{aligned}
$$

**(2)** For $C:|z|=1$, the source gives

$$
\oint_C\frac{z}{1-2\sin^2 z}\,dz
=2\pi i\{\operatorname{Res}[\pi/4]+\operatorname{Res}[-\pi/4]\}
=2\pi i\{-1/2+(-1/2)\}=-2\pi i.
$$

The denominator vanishes when

$$
1-2\sin^2 z=0\quad\Rightarrow\quad\sin^2 z=\frac12,\qquad
\sin z=\pm\sqrt{\frac12},\qquad z=\pm\frac\pi4+2k\pi.
$$

The poles inside the unit circle are $z_1=\pi/4$ and $z_2=-\pi/4$. Both are simple. To find $C_{-1}$ at $z_1$, multiply the Laurent series by $z-\pi/4$:

$$
\begin{aligned}
\frac1{1-2\sin^2 z}&=\frac{C_{-1}}{z-\pi/4}+C_0+C_1(z-\pi/4)+\cdots,\\
\frac{z-\pi/4}{1-2\sin^2 z}&=C_{-1}+C_0(z-\pi/4)+\cdots,\\
C_{-1}&=\lim_{z\to\pi/4}\frac{z-\pi/4}{1-2\sin^2 z}
=\lim_{z\to\pi/4}\frac1{-4\sin z\cos z}=-\frac12.
\end{aligned}
$$

Thus $\operatorname{Res}[\pi/4]=C_{-1}=-1/2$. The source likewise gives $\operatorname{Res}[-\pi/4]=-1/2$. The calculation and integral are transcribed as written.

## 2. Methods for Computing Residues

**Method 1 (definition).** Find $C_{-1}$, the coefficient in the Laurent series in a punctured neighborhood of $z_0$.

**Method 2 (pole formulas).** For a simple pole, a double pole, and a pole of order $n$, respectively,

$$
\begin{aligned}
\operatorname{Res}[f,z_0]&=\lim_{z\to z_0}(z-z_0)f(z),\\
\operatorname{Res}[f,z_0]&=\lim_{z\to z_0}\left[(z-z_0)^2f(z)\right]',\\
\operatorname{Res}[f,z_0]&=\frac1{(n-1)!}\lim_{z\to z_0}
\left[(z-z_0)^nf(z)\right]^{(n-1)}.
\end{aligned}
$$

**Proof.** If $z_0$ is a pole of order $n$, write its Laurent expansion as

$$
f(z)=\frac{C_{-n}}{(z-z_0)^n}+\cdots+\frac{C_{-1}}{z-z_0}+C_0+\cdots.
$$

$$
(z-z_0)^nf(z)=C_{-n}+\cdots+C_{-1}(z-z_0)^{n-1}+C_0(z-z_0)^n+\cdots.
$$

Differentiate $n-1$ times and let $z\to z_0$:

$$
[(z-z_0)^nf(z)]^{(n-1)}=0+C_{-1}(n-1)!+O(z-z_0).
$$

### 2.1 p. 121, Example 5.1

**(1)** $\operatorname{Res}[\sin z/z,0]=0$ because $C_{-1}=0$. If $z_0$ is removable, then $\operatorname{Res}[f,z_0]=0$.

**(2)**

$$
\operatorname{Res}[ze^{1/z},0]=C_{-1}=\frac1{2!}=\frac12,
\qquad ze^{1/z}=z\left(1+\frac1z+\frac1{2!}\frac1{z^2}+\cdots\right).
$$

**(3)** In a neighborhood of $z=0$,

$$
\frac1{1-z}e^{1/z}
=\left(\sum_{n=1}^{\infty}z^{n-1}\right)
\left(\sum_{n=0}^{\infty}\frac1{n!}\frac1{z^n}\right)
=\cdots+\frac{C_{-1}}z+C_0+C_1z+\cdots.
$$

$$
\operatorname{Res}\left[\frac1{1-z}e^{1/z},0\right]
=C_{-1}=\sum_{n=1}^{\infty}\frac1{n!}=e-1.
$$

The margin note gives the residue at $1$ as

$$
\operatorname{Res}[1]=\lim_{z\to1}(z-1)\frac{e^{1/z}}{1-z}=e^1=e.
$$

The sign is as written in the margin.

### 2.2 p. 126, Examples 5.5–5.7

**5.5.** At the simple pole $1$ and double pole $-1$,

$$
\begin{aligned}
\operatorname{Res}\left[\frac z{(z-1)(z+1)^2},1\right]
&=\lim_{z\to1}(z-1)\frac z{(z-1)(z+1)^2}
=\frac1{2^2}=\frac14,\\
\operatorname{Res}\left[\frac z{(z-1)(z+1)^2},-1\right]
&=\lim_{z\to-1}\left[(z+1)^2\frac z{(z-1)(z+1)^2}\right]'
=\lim_{z\to-1}\frac{-1}{(z-1)^2}=-\frac14.
\end{aligned}
$$

**5.6.** At a simple pole of $\tan z$, use the $0/0$ limit:

$$
\begin{aligned}
\operatorname{Res}[\tan z,k\pi+\pi/2]
&=\lim_{z\to k\pi+\pi/2}(z-k\pi-\pi/2)\tan z\\
&=\lim_{z\to k\pi+\pi/2}\frac{\sin z\,(z-k\pi-\pi/2)}{\cos z}\\
&=\lim_{z\to k\pi+\pi/2}\sin z\cdot
\lim_{z\to k\pi+\pi/2}\frac1{-\sin z}=-1.
\end{aligned}
$$

**5.7.** As $z\to0$, $\sin z\sim z$ and $e^z-1\sim z$, so

$$
\operatorname{Res}\left[\frac{z\sin z}{(1-e^z)^3},0\right]
=\lim_{z\to0}(z-0)\frac{z\sin z}{(1-e^z)^3}
=\lim_{z\to0}\frac{z^2\cdot z}{-z^3}=-1.
$$

Treating $z=0$ as a pole of order three in the calculation also gives

$$
\begin{aligned}
\operatorname{Res}\left[\frac{z\sin z}{(1-e^z)^3},0\right]
&=\frac1{2!}\lim_{z\to0}\left[z^3\frac{z\sin z}{(1-e^z)^3}\right]''\\
&=\frac12\lim_{z\to0}
\left[\frac{z^4(z-z^3/3!+\cdots)}{(-1)(z+z^2/2+\cdots)^3}\right]''
=\cdots=-1.
\end{aligned}
$$

## 3. Residue at Infinity

In the neighborhood $|z|>R$, write the Laurent expansion as

$$
f(z)=\left(\cdots+\frac{C_{-2}}{z^2}\right)+\frac{C_{-1}}z+(C_0+C_1z+\cdots).
$$

Integrate along the clockwise circle $C^-$:

$$
\oint_{C^-}f(z)\,dz=0-2\pi iC_{-1}+0,\qquad
-C_{-1}=\frac1{2\pi i}\oint_{C^-}f(z)\,dz.
$$

**Definition 1.** If infinity is isolated, define its residue by

$$
\operatorname{Res}[f(z),\infty]=\frac1{2\pi i}\oint_{C^-}f(z)\,dz,
\qquad C^-: |z|=R_1>R.
$$

**Definition 2.** If infinity is isolated, its residue is

$$
\operatorname{Res}[f,\infty]=-C_{-1},
$$

where $C_{-1}$ is the coefficient of $1/z$ in the Laurent expansion for $|z|>R$.

For the counterclockwise circle $C:|z|=R_1>R$,

$$
\frac1{2\pi i}\oint_{C^-}f(z)\,dz=-C_{-1}=\operatorname{Res}[f,\infty],
\qquad
\oint_C f(z)\,dz=-2\pi i\operatorname{Res}[f,\infty].
$$

**Theorem 1.** If $f(z)$ has finitely many singularities $z_1,z_2,\ldots,z_n$ in the complex plane, then

$$
\sum_{k=1}^n\operatorname{Res}[f(z),z_k]+\operatorname{Res}[f,\infty]=0.
$$

**Proof.** Take $C:|z|=R_1>R$ enclosing all the finite singularities. The definition at infinity and the residue theorem give

$$
\operatorname{Res}[f,\infty]=\frac1{2\pi i}\oint_{C^-}f(z)\,dz,\qquad
\frac1{2\pi i}\oint_C f(z)\,dz=\sum_{k=1}^n\operatorname{Res}[f,z_k].
$$

The two orientations are opposite. Consequently,

$$
\sum_{k=1}^n\operatorname{Res}[f,z_k]=-\operatorname{Res}[f,\infty],
\qquad
\operatorname{Res}[f,\infty]=-\sum_{k=1}^n\operatorname{Res}[f,z_k].
$$

**Theorem 2.** Under $\xi=1/z$,

$$
\operatorname{Res}[f(z),\infty]=-\operatorname{Res}\left[\frac1{z^2}f\left(\frac1z\right),0\right].
$$

**Proof.** Start with the Laurent expansion at infinity and set $\xi=1/z$, or $z=1/\xi$:

$$
\begin{aligned}
f(z)&=\cdots+\frac{C_{-1}}z+C_0+C_1z+\cdots && (|z|>R),\\
f(1/\xi)&=\cdots+C_{-1}\xi+C_0+\frac{C_1}{\xi}+\cdots && (0<|\xi|<1/R),\\
\frac1{\xi^2}f(1/\xi)&=\cdots+\frac{C_{-1}}{\xi}+\frac{C_0}{\xi^2}+\cdots.
\end{aligned}
$$

Therefore $\operatorname{Res}[\xi^{-2}f(1/\xi),0]=C_{-1}$.

**Corollary.** If infinity is isolated and $\lim_{z\to\infty}zf(z)=A$, then $\operatorname{Res}[f,\infty]=-A$. In the Laurent expansion

$$
f(z)=\cdots+\frac{C_{-2}}{z^2}+\frac{C_{-1}}z+C_0+C_1z+\cdots,
$$

the existence of $\lim_{z\to\infty}zf(z)$ implies $C_n=0$ for $n=0,1,2,\ldots$. The notes also state that if $\lim_{z\to\infty}f(z)=A$, then $z=\infty$ is removable.

## 4. Homework from November 8

p. 143: 1 (selected parts), 2(6), 2(7), and 3. Part B: 1, 2, and 3.

## 5. p. 123 — Examples 5.2 and 5.3

**5.2 (1).** Expand for $|z|>1$:

$$
\frac1{1-z}=\frac1{-z}\frac1{1-1/z}
=-\frac1z\left(1+\frac1z+\cdots\right).
$$

Thus $C_{-1}=-1$ and $\operatorname{Res}[1/(1-z),\infty]=-C_{-1}=1$.

**(2)** $\operatorname{Res}[\sin z-\cos z,\infty]=0$, since

$$
\sin z=z-\frac{z^3}{3!}+\cdots,\qquad
\cos z=1-\frac{z^2}{2!}+\cdots.
$$

**(3)**

$$
\operatorname{Res}\left[\frac{1-\cos z}{z^{2n+1}},\infty\right]
=-\frac{(-1)^{n+1}}{(2n)!}.
$$

$$
\cos z=1-\frac{z^2}{2!}+\cdots+\frac{(-1)^nz^{2n}}{(2n)!}+\cdots,
\qquad
\frac{1-\cos z}{z^{2n+1}}
=\cdots+\frac{-(-1)^nz^{2n}/(2n)!}{z^{2n+1}}+\cdots.
$$

Therefore $C_{-1}=(-1)^{n+1}/(2n)!$.
