## Introduction and historical context

Residues connect local series expansions with integrals around closed curves. Cauchy's study of the calculus of residues began in 1826 and formed part of his development of complex analysis. The historical account used here is the MacTutor biography of Cauchy. [MacTutor history](https://mathshistory.st-andrews.ac.uk/Biographies/Cauchy/)

A Laurent expansion describes a function near a missing point. When we integrate once around that point, exactly one coefficient contributes. This observation turns the calculation of a contour integral into the calculation of a few coefficients. The prerequisites for this lecture are holomorphic functions, Taylor series, and Cauchy's integral theorem.

Throughout, $\mathrm{i}^2=-1$. A positive contour is traversed counterclockwise. All contours used below are piecewise continuously differentiable. The exercises and worked practice from the handwritten notes are collected in the accompanying exercises files.

## Laurent expansions and isolated singularities

### The expansion and its region

If $f$ is holomorphic on the annulus $r<|z-z_0|<R$, it has a Laurent expansion

$$
f(z)=\sum_{n=-\infty}^{\infty}C_n(z-z_0)^n,\qquad
C_n=\frac{1}{2\pi\mathrm{i}}\oint_{|\zeta-z_0|=\rho}
\frac{f(\zeta)}{(\zeta-z_0)^{n+1}}\,\mathrm{d}\zeta,
$$

where $r<\rho<R$ and the circle is positively oriented. The coefficients depend on the annulus. Expansions separated by another singularity can have different coefficients even when they have the same center.

A point $z_0$ is an isolated singularity if $f$ is holomorphic on some punctured disk $0<|z-z_0|<R$. In that disk, write

$$
f(z)=\underbrace{\sum_{n=1}^{\infty}\frac{C_{-n}}{(z-z_0)^n}}_{\text{principal part}}
+\underbrace{\sum_{n=0}^{\infty}C_n(z-z_0)^n}_{\text{holomorphic part}}.
$$

The Laurent series converges uniformly on each compact subannulus. In particular, it can be integrated term by term along a circle strictly inside the annulus.

### Classification and limits

An isolated singularity is removable when all negative-power coefficients vanish. Its remaining Taylor series extends holomorphically across $z_0$, taking the value $C_0$ there.

A pole of order $m$ has a finite principal part. Its most singular nonzero term is $C_{-m}(z-z_0)^{-m}$, with $C_{-m}\ne0$.

An essential singularity has infinitely many nonzero negative-power coefficients.

For a pole, multiplication by $(z-z_0)^m$ removes every negative power. Consequently,

$$
f(z)=\frac{g(z)}{(z-z_0)^m},\qquad
g\text{ holomorphic near }z_0,\qquad g(z_0)=C_{-m}\ne0.
$$

Taking reciprocals shows that $1/f$ extends to a function with a zero of order $m$ at $z_0$. Conversely, factoring a zero of $1/f$ in this way recovers a pole of $f$.

The limit tests, with $z_0$ assumed isolated, are

$$
\begin{aligned}
\lim_{z\to z_0}f(z)=L\in\mathbb C
&\quad\Longleftrightarrow\quad z_0\text{ is removable},\\
\lim_{z\to z_0}|f(z)|=\infty
&\quad\Longleftrightarrow\quad z_0\text{ is a pole}.
\end{aligned}
$$

An essential singularity has neither a finite limit nor a limit at infinity in the extended complex plane. The pole condition must hold along every approach to $z_0$. Growth along a single ray is insufficient.

### Accumulating singularities and branch points

If distinct singularities $z_k$ approach $z_0$, every punctured neighborhood of $z_0$ contains another singularity. Thus $z_0$ is non-isolated and there is no Laurent expansion valid on a full punctured disk about it.

A logarithmic branch point also requires care. A branch can be holomorphic on a slit domain, but a Laurent expansion around an isolated singularity requires a single-valued holomorphic function on a full punctured disk. These hypotheses must be checked before applying the classification above.

## The point at infinity

### The local coordinate at infinity

The extended complex plane is $\widehat{\mathbb C}\coloneqq\mathbb C\cup\{\infty\}$. A neighborhood of infinity has the form $|z|>R$, together with infinity itself. To study local behavior there, introduce

$$
\zeta\coloneqq\frac1z,\qquad F(\zeta)\coloneqq f(1/\zeta).
$$

Then $|z|>R$ corresponds to $0<|\zeta|<1/R$. Infinity is isolated for $f$ precisely when $f$ is holomorphic on some exterior region. It is classified by the isolated singularity of $F$ at zero. If singularities $z_k$ tend to infinity, no such exterior region exists.

### Translating the classification

Suppose $f$ is holomorphic for $|z|>R$. Its Laurent expansion there can be written as

$$
f(z)=\sum_{n=1}^{\infty}\frac{C_{-n}}{z^n}+C_0+\sum_{n=1}^{\infty}C_nz^n.
$$

Substitution gives

$$
F(\zeta)=\sum_{n=1}^{\infty}C_{-n}\zeta^n+C_0+
\sum_{n=1}^{\infty}\frac{C_n}{\zeta^n}.
$$

The positive powers of $z$ become the principal part at $\zeta=0$. Hence infinity is removable if all $C_n$ with $n\ge1$ vanish, a pole of order $m$ if $C_m\ne0$ and all higher positive-power coefficients vanish, and essential if infinitely many positive-power coefficients are nonzero.

This explains why $e^{1/z}$ is removable at infinity, a polynomial of degree $m\ge1$ has a pole of order $m$ there, and $e^z$ has an essential singularity there. The finite-limit and modulus-growth tests above apply after replacing $z\to z_0$ by $z\to\infty$.

## Residues

### Why one coefficient survives

Let $\gamma$ be the positive circle $z=z_0+\rho e^{\mathrm{i}t}$ with $0\le t\le2\pi$. Then $\mathrm{d}z=\mathrm{i}\rho e^{\mathrm{i}t}\,\mathrm{d}t$. For any integer $n$,

$$
\begin{aligned}
\oint_\gamma(z-z_0)^n\,\mathrm{d}z
&=\mathrm{i}\rho^{n+1}\int_0^{2\pi}e^{\mathrm{i}(n+1)t}\,\mathrm{d}t\\
&=\begin{cases}2\pi\mathrm{i},&n=-1,\\0,&n\ne-1.\end{cases}
\end{aligned}
$$

For $n\ne-1$, the exponential completes an integer number of periods and its integral is zero. For $n=-1$, the integrand in $t$ is the constant $\mathrm{i}$. Uniform convergence on $\gamma$ permits termwise integration of the Laurent series. Therefore,

$$
\oint_\gamma f(z)\,\mathrm{d}z=2\pi\mathrm{i}C_{-1}.
$$

### Definition and contour characterization

**Definition.** If $z_0$ is an isolated singularity of $f$, its residue is

$$
\operatorname{Res}[f,z_0]\coloneqq C_{-1}.
$$

Equivalently,

$$
\operatorname{Res}[f,z_0]=\frac1{2\pi\mathrm{i}}\oint_C f(z)\,\mathrm{d}z,
$$

provided $C$ is a positive simple closed contour, $f$ is holomorphic on $C$ and throughout its interior except at $z_0$, and $C$ encloses $z_0$. Deforming $C$ to a small circle around $z_0$ within the holomorphic region proves this equivalence.

The residue records a single coefficient even when the principal part contains infinitely many terms. A removable singularity has residue zero. A zero residue alone gives no classification of the singularity, since a double pole can also have zero residue.

## The residue theorem

**Theorem.** Let $C$ be a positive simple closed contour. Suppose $f$ is holomorphic on an open neighborhood of $C$ and its interior, except for finitely many isolated singularities $z_1,\ldots,z_N$ strictly inside $C$. Then

$$
\oint_C f(z)\,\mathrm{d}z
=2\pi\mathrm{i}\sum_{k=1}^{N}\operatorname{Res}[f,z_k].
$$

**Proof.** Choose mutually disjoint small circles $\gamma_k$ around the singularities, all lying inside $C$. Give each small circle counterclockwise orientation. Remove the disks they bound. The remaining region contains no singularities, and its positively oriented boundary consists of $C$ and the clockwise circles $-\gamma_k$. Cauchy's theorem yields

$$
0=\oint_C f(z)\,\mathrm{d}z-\sum_{k=1}^{N}\oint_{\gamma_k}f(z)\,\mathrm{d}z.
$$

Each small-circle integral equals $2\pi\mathrm{i}\operatorname{Res}[f,z_k]$. Substituting these values proves the theorem. This argument explains both the sign and the requirement that all singularities lie strictly off the contour.

For a general closed contour in a region where the usual homological form of Cauchy's theorem applies, each residue is weighted by the winding number

$$
\operatorname{Ind}(C,a)\coloneqq
\frac1{2\pi\mathrm{i}}\oint_C\frac{\mathrm{d}z}{z-a}.
$$

In the simple positive-contour case used in this lecture, every enclosed singularity has winding number one.

### Applying the theorem

First locate all singularities, then determine which lie inside the contour and check that none lies on it. Compute the residues at those points and multiply their sum by $2\pi\mathrm{i}$. Reversing the contour orientation reverses the integral. Lecture 11 develops efficient residue formulas for poles and explains how the point at infinity can simplify the sum.

## References

For the residue definition and theorem, see Mathews and Howell's open textbook. [Complex Analysis, Section 8.1](https://complexanalysis.org/web/sec_residue-thm.html)
