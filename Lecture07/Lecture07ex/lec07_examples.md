# Lecture 07: Applications of Cauchy's Integral Formula
## Example 1

*Theory reference: §1 Existence of Derivatives.*

$$
f(z) = \oint_{\vert{}\zeta\vert{} = 2}\frac{(\zeta^{3} + 2\zeta + 1)}{(\zeta - z)^{2}}d\zeta \tag{1}
$$

Find $f'(1)$ and $f'(2 + \mathrm{i})$.

By Cauchy’s integral formula:

The integrand has the form $\frac{g(\zeta)}{(\zeta - z)^{2}}$, where $g(\zeta) = \zeta^{3} + 2\zeta + 1$ is analytic everywhere.

If $\vert{}z\vert{} < 2$, the point $z$ is inside $C$, so the generalized Cauchy integral formula with derivative order 1 applies: the integral equals $2\mathrm{\pi}\mathrm{i}g'(z)$.

Since $g'(\zeta) = 3\zeta^{2} + 2$, this gives the first branch.

If $\vert{}z\vert{} > 2$, the pole $\zeta = z$ lies outside $C$, so the integrand is analytic on and inside $C$; Cauchy’s theorem makes the integral zero.

$$
\oint_{\vert{}\zeta\vert{} = 2}\frac{\zeta^{3} + 2\zeta + 1}{{(\zeta - z)}^{2}}d\zeta = \begin{cases} 2\mathrm{\pi}\mathrm{i}(3z^{2} + 2)\quad & \vert{}z\vert{} < 2 \\ 0 & \vert{}z\vert{} > 2 \end{cases} \tag{2}
$$

The two cases are $\vert{}z\vert{} < 2$ and $\vert{}z\vert{} > 2$.

Differentiate each branch separately.

For $\vert{}z\vert{} < 2$

$$
\frac{d}{dz}\left[2\mathrm{\pi}\mathrm{i}(3z^{2} + 2)\right] = 2\mathrm{\pi}\mathrm{i} \cdot 6z = 12\mathrm{\pi}\mathrm{i}z
$$

For $\vert{}z\vert{} > 2$, the branch is the constant 0, so its derivative is 0.

Substituting $z = 1$ gives $f'(1) = 12\mathrm{\pi}\mathrm{i}$; because $\vert{}2 + \mathrm{i}\vert{} = \sqrt{5} > 2$, the exterior branch gives $f'(2 + \mathrm{i}) = 0$.

$$
f'(z) = \begin{cases} 12\mathrm{\pi}\mathrm{i}z, & \vert{}z\vert{} < 2, \\ 0, & \vert{}z\vert{} > 2, \end{cases}\quad f'(1) = 12\mathrm{\pi}\mathrm{i}, \quad f'(2 + \mathrm{i}) = 0 \tag{3}
$$

At $\vert{}z\vert{} = 2$, the pole lies on the contour, so the contour integral is not defined.

Given on the boundary $C$:

## Example 2

*Theory reference: §2 Cauchy's Inequality.*

When $\vert{}z\vert{} = 2$, $\vert{}f(z) - z\vert{} \le \vert{}z\vert{}$.

Prove that $\vert{}f'(1)\vert{} \le 8$

$$
\vert{}f'(1)\vert{} = \left\vert{}\left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{\vert{}z\vert{} = 2}\frac{f(z)}{(z - 1)^{2}}dz\right\vert{} \tag{4}
$$

$$
= \left\vert{}\left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{\vert{}z\vert{} = 2}\frac{[f(z) - z + z]}{(z - 1)^{2}}dz\right\vert{}
$$

$$
f(z) = [f(z) - z] + z
$$

$$
\vert{}f(z)\vert{} \le \vert{}f(z) - z\vert{} + \vert{}z\vert{}
$$

$$
\vert{}f(z)\vert{} \le 2\vert{}z\vert{} = 4
$$

$$
\vert{}z - 1\vert{} \ge \vert{}\vert{}z\vert{} - 1\vert{} = 1
$$

$$
\frac{\vert{}f(z)\vert{}}{\vert{}z - 1\vert{}^{2}} \le 4
$$

$$
\le \left(\frac{1}{2\mathrm{\pi}}\right)\oint_{\vert{}z\vert{} = 2}\frac{(\vert{}f(z) - z\vert{} + \vert{}z\vert{})}{\vert{}z - 1\vert{}^{2}}\vert{}dz\vert{}
$$

$$
\le \left(\frac{1}{2\mathrm{\pi}}\right)\oint_{\vert{}z\vert{} = 2}2\frac{\vert{}z\vert{}}{\vert{}z - 1\vert{}^{2}}\vert{}dz\vert{}
$$

$$
= \left(\frac{1}{2\mathrm{\pi}}\right) \cdot[2 \cdot \frac{2}{(2 - 1)^{2}}] \cdot \oint_{\vert{}z\vert{} = 2}\vert{}dz\vert{}
$$

$$
= \left(\frac{1}{2\mathrm{\pi}}\right) \cdot 4 \cdot 2\mathrm{\pi} \cdot 2 = 8
$$

## Example 3

*Theory reference: §1 Existence of Derivatives.*

$$
f(z) = \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{\mathrm{e}^{\zeta^{2}}}{(\zeta^{3} - z\zeta^{2})}d\zeta \tag{5}
$$

$$
C:\vert{}\zeta - z\vert{} = 3
$$

Find: (1) the expression for $f(z)$; (2) $f'(\mathrm{i})$, $f'(0)$, $f'(3 + \mathrm{i})$.

**(1) Find the expression for $f(z)$.**

From

$$
\zeta^{3} - z\zeta^{2} = 0 \tag{6}
$$

For $z \ne 0$, the roots are $\zeta = 0$ (a double root) and $\zeta = z$ (a simple root). When $z = 0$, the roots coincide; that case is treated separately below.

The contour is $C$: $\vert{}\zeta - z\vert{} = 3$. The sketch marks the centre $z$ and radius 3, with 0 also marked.

Discuss the cases separately.

(i) If $\vert{}z\vert{} < 3$, then the point 0 lies inside $C$.

$$
f(z) = \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{\mathrm{e}^{\zeta^{2}}}{(\zeta^{3} - z\zeta^{2})}d\zeta \tag{7}
$$

$$
= \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{\mathrm{e}^{\zeta^{2}}}{[\zeta^{2}(\zeta - z)]}d\zeta
$$

Factor the denominator: $\zeta^{3} - z\zeta^{2} = \zeta^{2}(\zeta - z)$.

Thus, for $z \ne 0$, the integrand has a double pole at $\zeta = 0$ and a simple pole at $\zeta = z$.

The contour $\vert{}\zeta - z\vert{} = 3$ contains $\zeta = z$ at its centre.

The origin is inside the contour exactly when $\vert{}z\vert{} < 3$, and outside exactly when $\vert{}z\vert{} > 3$.

Using Cauchy’s integral formula, split the contour into the small contours $C_{0}$ and $C_{1}$ around the two singular points

$$
f(z) = \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C_{0}}\frac{[\frac{\mathrm{e}^{\zeta^{2}}}{(\zeta - z)}]}{(\zeta - 0)^{2}}d\zeta + \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C_{1}}\frac{[\frac{\mathrm{e}^{\zeta^{2}}}{\zeta^{2}}]}{(\zeta - z)}d\zeta \tag{8}
$$

**Double pole at** $\zeta = 0$. Write $h(\zeta) = \frac{\mathrm{e}^{\zeta^{2}}}{\zeta - z}$, so that the integrand is $\frac{h(\zeta)}{\zeta^{2}}$



$$
h'(\zeta) = \frac{2\zeta\mathrm{e}^{\zeta^{2}}(\zeta - z) - \mathrm{e}^{\zeta^{2}}}{(\zeta - z)^{2}}, \qquad h'(0) = -\frac{1}{z^{2}}
$$



**Simple pole at** $\zeta = z$. The residue is



$$
\left.\frac{\mathrm{e}^{\zeta^{2}}}{\zeta^{2}}\right|_{\zeta = z} = \frac{\mathrm{e}^{z^{2}}}{z^{2}}
$$



Combining both contributions

$$
f(z) = {\left[\left(\frac{\mathrm{e}^{\zeta^{2}}}{\zeta - z}\right)'\right]}_{\zeta = 0} + {\left[\frac{\mathrm{e}^{\zeta^{2}}}{\zeta^{2}}\right]}_{\zeta = z}
$$

$$
= {[\frac{({2\zeta \mathrm{e}}^{\zeta^{2}}(\zeta - z) - \mathrm{e}^{\zeta^{2}})}{(\zeta - z)^{2}}]}_{\zeta = 0} + \frac{\mathrm{e}^{z^{2}}}{z^{2}}
$$

$$
= \frac{(-1)}{z^{2}} + \frac{\mathrm{e}^{z^{2}}}{z^{2}}
$$

$$
= \frac{(\mathrm{e}^{z^{2}} - 1)}{z^{2}}
$$

(ii) If $\vert{}z\vert{} > 3$, the point 0 is outside $C$.

$$
f(z) = \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{\mathrm{e}^{\zeta^{2}}}{(\zeta^{3} - z\zeta^{2})}d\zeta \tag{9}
$$

$$
= \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{[\frac{\mathrm{e}^{\zeta^{2}}}{\zeta^{2}}]}{(\zeta - z)}d\zeta
$$

When $\vert{}z\vert{} > 3$, the origin is outside $C$, so only the simple pole at $\zeta = z$ is enclosed.

The generalized Cauchy formula therefore gives the numerator $\frac{\mathrm{e}^{\zeta^{2}}}{\zeta^{2}}$ evaluated at $\zeta = z$, which is $\frac{\mathrm{e}^{z^{2}}}{z^{2}}$.

$$
= {[\frac{\mathrm{e}^{\zeta^{2}}}{\zeta^{2}}]}_{\zeta = z}
$$

$$
= \frac{\mathrm{e}^{z^{2}}}{z^{2}}
$$

For the exterior case

$$
f(z) = \begin{cases} \frac{\mathrm{e}^{z^{2}} - 1}{z^{2}} & 0 < \vert{}z\vert{} < 3 \\ 1 & z = 0 \\ \frac{\mathrm{e}^{z^{2}}}{z^{2}} & \vert{}z\vert{} > 3 \end{cases} \tag{10}
$$

At $\vert{}z\vert{} = 3$ the point $\zeta = 0$ lies on $C$, so the contour integral is not defined.

**(2) Find $f'(i)$, $f'(0)$ and $f'(3 + \mathrm{i})$.**

*Find $f'(i)$.* Differentiate the branch that contains $z = \mathrm{i}$, the one for $0 < \vert{}z\vert{} < 3$:

For $0 < \vert{}z\vert{} < 3$, with numerator $u = \mathrm{e}^{z^{2}} - 1$ and denominator $v = z^{2}$



$$ f'(z) = \frac{u'v - uv'}{v^{2}} = \frac{(2z\mathrm{e}^{z^{2}})z^{2} - (\mathrm{e}^{z^{2}} - 1)(2z)}{z^{4}} = \frac{2[z^{2}\mathrm{e}^{z^{2}} - (\mathrm{e}^{z^{2}} - 1)]}{z^{3}}$$

At $z = \mathrm{i}$

$$
f'(\mathrm{i}) = {\left.\frac{2[z^{2}\mathrm{e}^{z^{2}} - \mathrm{e}^{z^{2}} + 1]}{z^{3}}\right\vert{}}_{z = \mathrm{i}} = 2\mathrm{i}\left(1 - \frac{2}{\mathrm{e}}\right) \tag{11}
$$

*Find $f'(0)$.*

At $z = 0$, use the original integral because the two poles coincide.

The contour is then $\vert{}\zeta\vert{} = 3$ and the integrand is $\frac{\mathrm{e}^{\zeta^{2}}}{\zeta^{3}}$.

Cauchy’s derivative formula with derivative order 2 gives $f(0) = \left(\frac{1}{2!}\right)\left(\frac{d^{2}}{d\zeta^{2}}\right)\mathrm{e}^{\zeta^{2}}\vert{}\zeta = 0$.

Since $(\mathrm{e}^{\zeta^{2}})'= 2\zeta \mathrm{e}^{\zeta^{2}}$ and $(\mathrm{e}^{\zeta^{2}})''= 2\mathrm{e}^{\zeta^{2}} + 4\zeta^{2}\mathrm{e}^{\zeta^{2}}$, the second derivative at 0 is 2, so $f(0) = 1$. This agrees with the limit of the interior branch, $\lim_{z \to 0}(\mathrm{e}^{z^{2}} - 1)/z^{2} = 1$, so $f$ is continuous at the origin.

$$
= \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{\vert{}\zeta - 0\vert{} = 3}\frac{\mathrm{e}^{\zeta^{2}}}{\zeta^{3}}d\zeta
$$

$$
= \left(\frac{1}{2!}\right)\left(\frac{d^{2}}{d\zeta^{2}}\right)\mathrm{e}^{\zeta^{2}}\vert{}_{\zeta = 0} = 1
$$

The derivatives of $\mathrm{e}^{\zeta^{2}}$ are

$$
(\mathrm{e}^{\zeta^{2}})'= ({2\zeta \mathrm{e}}^{\zeta^{2}}) \tag{12}
$$

$$
(\mathrm{e}^{\zeta^{2}})''= ({2\zeta \mathrm{e}}^{\zeta^{2}})'
$$

$$
= (2\zeta){'\mathrm{e}}^{\zeta^{2}} + 2\zeta(\mathrm{e}^{\zeta^{2}})'
$$

$$
= {2\mathrm{e}}^{\zeta^{2}} + {4\zeta^{2}\mathrm{e}}^{\zeta^{2}} \vert{}\zeta = 0
$$

Power series at z = 0

$$
\mathrm{e}^{z^{2}} = 1 + z^{2} + \frac{z^{4}}{2!} + \frac{z^{6}}{3!} + \cdots \tag{13}
$$

$$
f(z) = \frac{\mathrm{e}^{z^{2}} - 1}{z^{2}} = 1 + z^{2} + \frac{z^{4}}{2!} + \frac{z^{6}}{3!} + \cdots
$$

$$
f'(0) = 0
$$

*Find $f'(3 + \mathrm{i})$.* For $\vert{}z\vert{} > 3$ the branch is $f(z) = \mathrm{e}^{z^{2}}/z^{2}$, so

$$
f(z) = \frac{\mathrm{e}^{z^{2}}}{z^{2}}, \qquad
f'(z) = \frac{2z\mathrm{e}^{z^{2}}z^{2} - \mathrm{e}^{z^{2}}(2z)}{z^{4}}
= \frac{2\mathrm{e}^{z^{2}}(z^{2} - 1)}{z^{3}}
$$

At $z = 3 + \mathrm{i}$, where $z^{2} = 8 + 6\mathrm{i}$, $z^{2} - 1 = 7 + 6\mathrm{i}$ and $z^{3} = 18 + 26\mathrm{i}$

$$
f'(3 + \mathrm{i}) = \frac{2\mathrm{e}^{8 + 6\mathrm{i}}(7 + 6\mathrm{i})}{18 + 26\mathrm{i}}
= \frac{\mathrm{e}^{8 + 6\mathrm{i}}(141 - 37\mathrm{i})}{250}
$$

## Example 4

*Theory reference: §3 Maximum Modulus Principle.*

Suppose $f(z)$ is analytic in $D$, where $D$ is the region on and inside $\vert{}z\vert{} = R$.

On the boundary $\vert{}z\vert{} = R$, suppose

$$
\vert{}f(z)\vert{} > a > 0 \tag{14}
$$

and

$\vert{}f(0)\vert{} <$ a

Show that there exists $\zeta$ inside the region such that

$$
f(\zeta) = 0 \tag{15}
$$

*Proof.* Use proof by contradiction.

Suppose that

for every $z$ in the closed region $D$, $f(z) \ne 0$.

Then

$$
F(z) = \frac{1}{f(z)} \tag{16}
$$

is analytic in $D$.

Apply the maximum modulus principle to $F(z)$, comparing its value at the origin with its values on the boundary

$$
\vert{}F(0)\vert{} = \frac{1}{\vert{}f(0)\vert{}} > \frac{1}{a} \tag{17}
$$

$$
\vert{}F(R\mathrm{e}^{\mathrm{i}\theta})\vert{} = \frac{1}{\vert{}f(R\mathrm{e}^{\mathrm{i}\theta})\vert{}} < \frac{1}{a}
$$

$$
F(z) = \frac{1}{f(z)}
$$

$$
\vert{}F(0)\vert{} = \frac{1}{\vert{}f(0)\vert{}} > \frac{1}{a}
$$

$$
\vert{}f(z)\vert{} > a
$$

$$
\vert{}F(z)\vert{} = \frac{1}{\vert{}f(z)\vert{}} < \frac{1}{a}
$$

## Example 5

*Theory reference: §4 Liouville's Theorem.*

Suppose $f(z)$ is analytic on the whole complex plane, and there exists $M > 0$ such that

$$
R\mathrm{e}\ f(z) < M \tag{18}
$$

Show that $f(z)$ is constant.

*Proof.* Let

$$
F(z) = \mathrm{e}^{f(z)} \tag{19}
$$

$$
\vert{}F(z)\vert{} = \vert{}\mathrm{e}^{f(z)}\vert{} = \mathrm{e}^{R\mathrm{e}\ f(z)}
$$

$$
\vert{}\mathrm{e}^{w}\vert{} = \mathrm{e}^{\operatorname{Re}(w)}
$$

$$
w = f(z)
$$

$$
\vert{}F(z)\vert{} = \mathrm{e}^{\operatorname{Re}f(z)}
$$

$$
\operatorname{Re}f(z) < M
$$

$$
\vert{}F(z)\vert{} < \mathrm{e}^{M}
$$

Since $\operatorname{Re}f(z) < M$,

$$
\vert{}F(z)\vert{} < \mathrm{e}^{M} \tag{20}
$$

Thus $F(z)$ is an entire bounded function.

By Liouville’s theorem,

$$
F(z) = constant \tag{21}
$$

Therefore

$$
\mathrm{e}^{f(z)} = constant \tag{22}
$$

Differentiate both sides:

The derivative of the left-hand side is $\mathrm{e}^{f(z)}f'(z)$ by the chain rule.

The derivative of a constant is zero, so $\mathrm{e}^{f(z)}f'(z) = 0$.

Since $\mathrm{e}^{f(z)} \ne 0$ for every $z$, division by this factor gives $f'(z) = 0$ everywhere; hence $f$ is constant.

$$
\mathrm{e}^{f(z)}f'(z) = 0 \tag{23}
$$

Since the exponential function never vanishes, we conclude that

$$
f'(z) = 0 \tag{24}
$$

and therefore $f(z)$ is constant.

## Example 6

*Theory reference: §1 Existence of Derivatives.*

Suppose $f(z)$ is analytic for $\vert{}z\vert{} < 2$, and

$$
f(0) = 1\quad f'(0) = 2 \tag{25}
$$

(1) Evaluate

$$
I_{1} = \oint_{\vert{}z\vert{} = 1}[\frac{{(z + 1)}^{2}}{z^{2}}]f(z)dz \tag{26}
$$

(2) Evaluate

$$
I_{2} = \int_{0}^{2\mathrm{\pi}}\cos^{2}\left(\frac{\theta}{2}\right)f(\mathrm{e}^{\mathrm{i}\theta}) d\theta \tag{27}
$$

(1) Find $I_{1}$.

By the generalised Cauchy integral formula

$$
I_{1} = \left(\frac{2\mathrm{\pi}\mathrm{i}}{1!}\right){[((z + 1)^{2}f(z)]}_{z = 0} \tag{28}
$$

Set $g(z) = (z + 1)^{2}f(z)$. The generalized Cauchy integral formula gives $I_{1} = 2\mathrm{\pi}\mathrm{i}g'(0)$. By the product rule, $g'(z) = 2(z + 1)f(z) + (z + 1)^{2}f'(z)$.

$$
= 2\mathrm{\pi}\mathrm{i}{[2(z + 1)f(z) + (z + 1)^{2}f'(z)]}_{z = 0}
$$

$$
= 2\mathrm{\pi}\mathrm{i}[2f(0) + f'(0)]
$$

$$
= 2\mathrm{\pi}\mathrm{i}(2 + 2) = 8\mathrm{\pi}\mathrm{i}
$$

(2) Find $I_{2}$.

Let $z = \mathrm{e}^{\mathrm{i}\theta}$

$$
z = \mathrm{e}^{\mathrm{i}\theta} \tag{29}
$$

Then

On $\vert{}z\vert{} = 1$, with $z = \mathrm{e}^{\mathrm{i}\theta}$ and $0 \le \theta \le 2\mathrm{\pi}$

$$
\mathrm{e}^{\mathrm{i}\theta} = z \tag{30}
$$

$$
\mathrm{e}^{-\mathrm{i}\theta} = z^{-1}
$$

$$
\cos \theta = \frac{z + z^{-1}}{2}
$$

$$
dz = \mathrm{i}z\ d\theta
$$

$$
d\theta = \frac{dz}{\mathrm{i}z}
$$

$$
\cos^{2}\left(\frac{\theta}{2}\right) = \frac{1 + \cos \theta}{2}
$$

$$
\frac{2 + z + z^{-1}}{4} = \frac{z^{2} + 2z + 1}{4z}
$$

$$
\frac{z^{2} + 2z + 1}{4\mathrm{i}z^{2}}
$$

$$
I_{2} = \left(\frac{1}{4\mathrm{i}}\right)I_{1} = \left(\frac{1}{4\mathrm{i}}\right)(8\mathrm{\pi}\mathrm{i}) = 2\mathrm{\pi}
$$

$$
\cos \theta = \frac{(\mathrm{e}^{\mathrm{i}\theta} + \mathrm{e}^{-\mathrm{i}\theta})}{2} = \frac{(z + z^{-1})}{2}
$$

$$
dz = {\mathrm{i}\mathrm{e}}^{\mathrm{i}\theta}d\theta = \mathrm{i}z\ d\theta
$$

$$
d\theta = \frac{dz}{(\mathrm{i}z)}
$$

Substitute

$$
I_{2} = \int_{0}^{2\mathrm{\pi}}[\frac{(1 + \cos \theta)}{2}]f(\mathrm{e}^{\mathrm{i}\theta})d\theta \tag{31}
$$

$$
= \oint_{\vert{}z\vert{} = 1}\frac{[1 + \frac{(z + z^{-1})}{2}]}{2} \cdot f(z) \cdot \ \frac{dz}{(\mathrm{i}z)}
$$

$$
= \left(\frac{1}{4\mathrm{i}}\right)\oint_{\vert{}z\vert{} = 1}[\frac{(z^{2} + 2z + 1)}{z^{2}}]f(z)dz
$$

$$
= \left(\frac{1}{4\mathrm{i}}\right)I_{1}
$$

$$
= 2\mathrm{\pi}
$$

$$
I = \int_{0}^{2\mathrm{\pi}}\mathrm{e}^{\cos \theta}\cos(n\theta - \sin \theta)d\theta
$$

Let

$$
\mathrm{e}^{\mathrm{i}\theta} = z \tag{32}
$$

**Let n be a non-negative integer. We evaluate the trigonometric integral by converting it to a contour integral.**

By Euler’s formula

$$
\cos \theta + \mathrm{i}\ \sin \theta = \mathrm{e}^{\mathrm{i}\theta} \tag{33}
$$

$$
\cos(n\theta - \sin \theta) + \mathrm{i}\ \sin(n\theta - \sin \theta) = \mathrm{e}^{\mathrm{i}(n\theta - \sin \theta)}
$$

Taking the complex conjugate of the second Euler formula gives:

The conjugate identity is $\mathrm{e}^{-\mathrm{i}(n\theta - \sin \theta)} = \cos(n\theta - \sin \theta) - \mathrm{i}\sin(n\theta - \sin \theta)$.

Multiplying by $\mathrm{e}^{\cos \theta}$ and integrating gives a complex integral $J$ whose real part is the required $I$.

The exponent simplifies because $-\mathrm{i}(n\theta - \sin \theta) = -\mathrm{i}n\theta + \mathrm{i}\sin \theta$, so $\cos \theta + \mathrm{i}\sin \theta$ appears together.

$$
\mathrm{e}^{-\mathrm{i}(n\theta - \sin \theta)} = \cos(n\theta - \sin \theta) - \mathrm{i}\sin(n\theta - \sin \theta) \tag{34}
$$

The original integral $I$ is the real component of the corresponding complex integral $J$

$$
J = \int_{0}^{2\mathrm{\pi}}\mathrm{e}^{\cos \theta}\mathrm{e}^{-\mathrm{i}(n\theta - \sin \theta)} d\theta = \int_{0}^{2\mathrm{\pi}}\mathrm{e}^{\cos \theta + \mathrm{i}\sin \theta - \mathrm{i}n\theta} d\theta \tag{35}
$$

Using $\cos \ \theta + \mathrm{i}\sin \ \theta = \mathrm{e}^{\mathrm{i}\theta}$, we obtain

$$
\cos \theta + \mathrm{i}\sin \theta = \mathrm{e}^{\mathrm{i}\theta} \tag{36}
$$

With $z = \mathrm{e}^{\mathrm{i}\theta}$ one has $\mathrm{e}^{\mathrm{i}\theta} = z$, $\mathrm{e}^{-\mathrm{i}n\theta} = z^{-n}$, $\mathrm{e}^{\mathrm{e}^{\mathrm{i}\theta}} = \mathrm{e}^{z}$ and $d\theta = \frac{dz}{\mathrm{i}z}$, hence



$$
J = \left(\frac{1}{\mathrm{i}}\right)\oint_{\vert{}z\vert{} = 1}\mathrm{e}^{z}z^{-n - 1}dz
$$

$$
J = \int_{0}^{2\mathrm{\pi}}\mathrm{e}^{\mathrm{e}^{\mathrm{i}\theta}}\mathrm{e}^{-\mathrm{i}n\theta} d\theta
$$

Let $z = \mathrm{e}^{\mathrm{i}\theta}$. Then

$$
dz = \mathrm{i}z d\theta, \quad d\theta = \frac{dz}{\mathrm{i}z} \tag{37}
$$

As $\theta$ goes from 0 to $2\mathrm{\pi}$, $z$ traverses the unit circle $C$ once counterclockwise. Hence

$$
J = \frac{1}{\mathrm{i}}\oint_{C}\mathrm{e}^{z}z^{-n - 1} dz \tag{38}
$$

Expand the exponential

$$
\mathrm{e}^{z} = \sum_{k = 0}^{\infty}\frac{z^{k}}{k!} \tag{39}
$$

$$
z^{-n - 1}\sum_{k = 0}^{\infty}\frac{z^{k}}{k!} = \sum_{k = 0}^{\infty}\frac{z^{k - n - 1}}{k!}
$$



whose $z^{-1}$ term occurs at $k - n - 1 = -1$, that is $k = n$, with coefficient $\frac{1}{n!}$.

Only the term with $k = n$ contributes to the contour integral. Thus

$$
J = \frac{1}{\mathrm{i}}(2\mathrm{\pi}\mathrm{i})\frac{1}{n!} = \frac{2\mathrm{\pi}}{n!} \tag{40}
$$

This value is real. Since $I$ is the real component of $J$, it follows that

$$
I = \frac{2\mathrm{\pi}}{n!}, \quad n = 0, 1, 2, \dots \tag{41}
$$
