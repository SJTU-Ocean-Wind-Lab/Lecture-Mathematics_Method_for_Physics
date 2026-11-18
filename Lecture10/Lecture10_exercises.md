# Lecture10 Exercises and Worked Practice

Exercises, homework, and worked practice from the handwritten source are retained below. The original calculation lines remain available for comparison. Mathematical inconsistencies are addressed in the verification notes at the end.

## Homework from November 1

p. 117: 7(3), 7(4), 8, 11, and 12 (selected parts).


## Exercises and worked practice

### p. 117, Exercise 7

**(3)** The neighborhoods centered at $\mathrm{i}$ are $0<|z-\mathrm{i}|<1$ and $|z-\mathrm{i}|>1$.

**(4)** Expand $f(z)=e^{1/(1-z)}$ for $|z|>1$ as $\sum_{n=-\infty}^{\infty}C_nz^n$.

$$
e^{\frac1{1-z}}
=\sum_{n=0}^{\infty}\frac1{n!}\left(\frac1{1-z}\right)^n
=1+\frac1{1-z}+\frac1{2!}\left(\frac1{1-z}\right)^2
+\frac1{3!}\left(\frac1{1-z}\right)^3+\cdots. \tag{*}
$$

For $|z|>1$,

$$
\frac1{1-z}=-\frac1z\frac1{1-\frac1z}
=-\frac1z\sum_{n=0}^{\infty}\frac1{z^n}
=-\sum_{n=0}^{\infty}\frac1{z^{n+1}}.
$$

$$
\left(\frac1{1-z}\right)^2
=\left(\frac1{1-z}\right)'
=\sum_{n=0}^{\infty}\frac{n+1}{z^{n+2}}.
$$

Substitute these expressions into $(*)$ to obtain the Laurent expansion.

**Another solution.** Put $\xi=1/z$. The exterior $|z|>1$ maps to the punctured disk $0<|\xi|<1$.

$$
f=e^{\frac1{1-z}}=e^{\frac1{1-\frac1\xi}}=e^{\frac{\xi}{\xi-1}}.
$$

Define the value at $\xi=0$ by $f|_{\xi=0}=e^0=1$. The singularity is removable. Treat $\xi=0$ as an ordinary point. Since $|\xi|<1$ is a disk, use Taylor coefficients $C_n=f^{(n)}(0)/n!$.

$$
\begin{aligned}
f&=e^{\frac{\xi}{\xi-1}}\quad\Rightarrow\quad f(0)=1,\\
f'&=e^{\frac{\xi}{\xi-1}}\left(\frac{\xi}{\xi-1}\right)'
=e^{\frac{\xi}{\xi-1}}\frac{-1}{(\xi-1)^2}\quad\Rightarrow\quad f'(0)=-1,\\
f''&=(f')'=e^{\frac{\xi}{\xi-1}}\left(\frac{-1}{(\xi-1)^2}\right)^2+
e^{\frac{\xi}{\xi-1}}\frac{2}{(\xi-1)^3}
\quad\Rightarrow\quad f''(0)=1-2=-1,\\
f'''&=e^{\frac{\xi}{\xi-1}}\left(\frac{-1}{(\xi-1)^2}\right)^3
+e^{\frac{\xi}{\xi-1}}\frac{-4}{(\xi-1)^5}
+e^{\frac{\xi}{\xi-1}}\frac{-1}{(\xi-1)^2}\frac{2}{(\xi-1)^3}
+e^{\frac{\xi}{\xi-1}}\frac{-8}{(\xi-1)^4},\\
f'''(0)&=-1+4+2-8=-3.
\end{aligned}
$$

$$
f=C_0+C_1\xi+C_2\xi^2+C_3\xi^3+\cdots,
\qquad
e^{\frac{\xi}{\xi-1}}=1+\frac{-1}{1!}\xi+\frac{-1}{2!}\xi^2+\frac{-3}{3!}\xi^3+\cdots
\quad (|\xi|<1).
$$

Substituting $\xi=1/z$ gives

$$
f(z)=e^{\frac1{1-z}}=1-\frac1z-\frac12\frac1{z^2}-\frac12\frac1{z^3}+\cdots
\qquad (|z|>1).
$$


### Exercise 8

1. In $|a|<|z|<|b|$, use $\sum_{n=-\infty}^{\infty}C_nz^n$.
2. A neighborhood of infinity is $|z|>R=\max\{|a|,|b|\}=|b|$.
3. A neighborhood of $a$ is $0<|z-a|<r$, where $r=|b-a|$.

For (2), in the neighborhood $|z|>|b|>|a|$,

$$
\begin{aligned}
\frac1{z-a}\frac1{z-b}
&=\left(\frac1{z-a}-\frac1{z-b}\right)\frac1{a-b}\\
&=\left(\frac1z\frac1{1-a/z}-\frac1z\frac1{1-b/z}\right)\frac1{a-b}\\
&=\left(\frac1z\sum\left(\frac az\right)^n-\frac1z\sum\left(\frac bz\right)^n\right)\frac1{a-b}\\
&=\sum_{n=0}^\infty\frac{a^n-b^n}{a-b}z^{-n-1}.
\end{aligned}
$$

Here $C_{-1}=(1-1)/(a-b)=0$ ($n=0$).


### p. 118, Exercise 12

**(2)** For $1/(z^2+\mathrm{i})^2$,

$$
z^2=-\mathrm{i},\qquad z=\sqrt{-\mathrm{i}}=e^{\mathrm{i}\frac{-\pi/2+2k\pi}{2}}\quad(k=0,1).
$$

The roots $z_0=e^{-\mathrm{i}\pi/4}$ and $z_1=e^{\mathrm{i}3\pi/4}$ are poles of order two. The notes recall $\sqrt[n]{z}=\sqrt[n]{r}\,e^{\mathrm{i}(\theta+2k\pi)/n}$.

**(6)** For $\frac1{e^z-1}e^{1/(z-1)}$, the singularities are $z=0,1,2k\pi \mathrm{i}$. The points $z=0,2k\pi \mathrm{i}$ are simple poles. The point $z=1$ is essential because $\lim_{z\to1}e^{1/(z-1)}$ does not exist. The expression $e^\infty$ is undefined here.

**(10)** For $\frac1{1+z^2}+\cos\frac1{z+\mathrm{i}}$, the singularities are $z=\pm \mathrm{i}$. The point $z=-\mathrm{i}$ is essential because $\lim_{z\to-\mathrm{i}}\cos\frac1{z+\mathrm{i}}$ does not exist. The point $z=\mathrm{i}$ is a simple pole. The notes remark that $\sin(\infty)$ and $\cos(\infty)$ are undefined.

**(12)** For $f(z)=1/[z\ln(1-z)]$, the singularities are $z=0$ and $z=1$. The latter is a branch point and a non-isolated singularity. For example, $\ln z$ cannot be analytic in a neighborhood of $z=0$.

$$
\begin{aligned}
g(z)&\coloneqq z\ln(1-z)=\frac1{f(z)},\\
g'(z)&=1\cdot\ln(1-z)+z\cdot\frac1{1-z},\\
g''&=\frac1{1-z}+\left(\frac z{1-z}\right)'
=\frac1{1-z}+\frac{1-z-(-1)z}{(1-z)^2}
=\frac1{1-z}+\frac1{(1-z)^2},\\
g(0)&=0,\qquad g'(0)=0,\qquad g''(0)=1+1=2\ne0.
\end{aligned}
$$

Thus $z=0$ is a double zero of $g(z)=1/f(z)$ and a double pole of $f(z)$. The derivative signs above follow the handwritten notes.


### p. 116, Example 4.28

The extended complex plane is the complex plane together with $\{\infty\}$. For $f(z)=\cot z-1/z$, the singularities are $z=0$, $z_k=k\pi$ ($k=\pm1,\pm2,\ldots$), and $z=\infty$.

$$
\begin{aligned}
\lim_{z\to0}f(z)
&=\lim_{z\to0}\left(\cot z-\frac1z\right)
=\lim_{z\to0}\frac{z\cos z-\sin z}{z\sin z}
=\lim_{z\to0}\frac{(z\cos z-\sin z)'}{(z^2)'}\\
&=\lim_{z\to0}\frac{1\cdot\cos z+z(-\sin z)-\cos z}{2z}
=-\frac12\lim_{z\to0}\sin z.
\end{aligned}
$$

Thus $z=0$ is removable. For $k\ne0$,

$$
f(z)=\frac{z\cos z-\sin z}{z\sin z}=\frac{g(z)}{h(z)},\qquad
h(k\pi)=0,\quad h'(k\pi)\ne0,\quad g(k\pi)\ne0.
$$

Hence $z=k\pi$ is a simple pole. Since $z_k=k\pi\to\infty$, infinity is a non-isolated singularity.

**Example.**

$$
\oint_{|z|=1}e^{1/z}\,\mathrm{d}z
=\oint_{|z|=1}\left(1+\frac1z+\frac1{2!}\frac1{z^2}+\cdots\right)\mathrm{d}z
=0+2\pi \mathrm{i}+0=2\pi \mathrm{i}.
$$

The constant term integrates to zero. See p. 62, (2)–(4), for

$$
\oint_{|z|=1}\frac{\mathrm{d}z}{z^k}=
\begin{cases}2\pi \mathrm{i},& k=1,\\0,& k\ne1.\end{cases}
$$


## Homework from November 3

- p. 118, A: 13 (selected parts), 14. B: 7, 8.
- p. 143: 2(1), 2(2), 2(3).

## Additional worked practice

### p. 118, Exercise 11

**p. 118, Exercise 11.** For $f(z)=\tan(1/(z-1))$, can a Laurent series be obtained in a punctured neighborhood of $z=1$? No, because $z=1$ is non-isolated.

$$
\frac1{z-1}=k\pi+\frac\pi2
\quad\Rightarrow\quad z_k=\frac1{k\pi+\frac\pi2}+1,
\qquad z_k\to1.
$$


### Worked practice with two singularities

**Example.**

$$
I=\oint_{|z|=2}\frac{e^{1/z}}{z-1}\,\mathrm{d}z
=2\pi \mathrm{i}\{\operatorname{Res}[0]+\operatorname{Res}[1]\}
=2\pi \mathrm{i}\{-(e-1)+e\}=2\pi \mathrm{i}.
$$

1. In the punctured neighborhood $0<|z|<1$ of $z=0$, use the Laurent expansion

$$
\begin{aligned}
\frac{e^{1/z}}{z-1}&=e^{1/z}\frac1{z-1}
=\left(\sum_{n=0}^{\infty}\frac1{n!}\frac1{z^n}\right)
\left(-\sum_{n=0}^{\infty}z^{n-1}\right)\\
&=\cdots+\frac{-1}{z}(?)\cdots,\\
C_{-1}&=\sum_{n=1}^{\infty}\frac1{n!}=-(e-1).
\end{aligned}
$$

The series exponent and the sign in the coefficient line are transcribed as written.

2. In the punctured neighborhood $0<|z-1|<1$ of $z=1$, expand as $\sum C_n(z-1)^n$. Let $g(z)=e^{1/z}$. Then

$$
\frac{e^{1/z}}{z-1}=\frac1{z-1}(g(1)+g'(1)(z-1)+\cdots)
=\frac1{z-1}[e+\cdots]\quad\Rightarrow\quad C_{-1}=e.
$$



## Verification notes for the preserved calculations

The preceding practice material preserves the earlier transcription, with notation standardized. The following notes resolve mathematical inconsistencies so that the preserved lines can be checked against valid derivations.

### Exterior expansion in Exercise 7(4)

For $F(\xi)=e^{\xi/(\xi-1)}$, the derivative of $2(\xi-1)^{-3}$ is $-6(\xi-1)^{-4}$. Thus the last term in the displayed third derivative has coefficient $-6$, giving

$$
F'''(0)=-1+4+2-6=-1.
$$

The beginning of the expansion is consequently

$$
e^{1/(1-z)}
=1-\frac1z-\frac1{2z^2}-\frac1{6z^3}+O(z^{-4}),\qquad |z|>1.
$$

This also follows by expanding $e^{-\xi-\xi^2-\xi^3-\cdots}$ through degree three.

### The logarithm in Exercise 12(12)

Choose the branch of $\ln(1-z)$ analytic near zero, with value zero there. For $g(z)\coloneqq z\ln(1-z)$,

$$
g'(z)=\ln(1-z)-\frac z{1-z},\qquad
g''(z)=-\frac1{1-z}-\frac1{(1-z)^2}.
$$

Hence $g''(0)=-2$. The conclusion that $1/g$ has a double pole at zero remains valid. The point $1$ is a logarithmic branch point, outside the hypotheses of the isolated-singularity Laurent classification.

### The removable point of cotangent

The denominator $z\sin z$ cannot be replaced by $z^2$ as an equality before differentiation. A valid local expansion gives

$$
\cot z-\frac1z
=\frac{z\cos z-\sin z}{z\sin z}
=\frac{-z^3/3+O(z^5)}{z^2+O(z^4)}
=-\frac z3+O(z^3)\longrightarrow0.
$$

This establishes the removable singularity directly.

### The two residues of the final integral

For $0<|z|<1$, the geometric series is $1/(z-1)=-\sum_{m=0}^{\infty}z^m$. Therefore,

$$
\begin{aligned}
\operatorname{Res}\left[\frac{e^{1/z}}{z-1},0\right]
&=-\sum_{m=0}^{\infty}\frac1{(m+1)!}=-(e-1),\\
\operatorname{Res}\left[\frac{e^{1/z}}{z-1},1\right]&=e.
\end{aligned}
$$

The contour $|z|=2$ encloses both points, so the stated integral $2\pi\mathrm{i}$ is correct. The corrected coefficient sum includes the minus sign.
