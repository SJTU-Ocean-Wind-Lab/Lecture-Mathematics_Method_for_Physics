# Lecture 07: Applications of Cauchy's Integral Formula

## 1 Existence of Derivatives

If $f(z)$ is analytic in a region, then its derivatives $f'(z)$, $f''(z)$, … of
all orders exist, and each of them is again analytic in that region.

For a point $z_{0}$ inside a simple closed contour $C$ on which $f$ is analytic,

$$
f^{(n)}(z_{0}) = \frac{n!}{2\mathrm{\pi}\mathrm{i}}\oint_{C}\frac{f(z)}{(z - z_{0})^{n + 1}}dz
$$

The formula comes from Cauchy's integral formula by differentiating under the
integral sign $n$ times.

For $n = 0$ it reduces to Cauchy's integral formula itself.

## 2 Cauchy's Inequality

Suppose $f(z)$ is analytic on and inside the circle $C$: $\vert{}z - z_{0}\vert{} = R$.

Suppose that

$$
\vert{}f(z)\vert{} \le M\quad on\ C \tag{1}
$$

Then

$$
\vert{}f^{(n)}(z_{0})\vert{} \le \ \frac{n!M}{R^{n}} \tag{2}
$$

where

$$
M = \max_{C}\vert{}f(z)\vert{} \tag{3}
$$

*Proof.* By the generalized Cauchy integral formula

$$
\vert{}f^{(n)}(z_{0})\vert{} = \left\vert{}\frac{n!}{(2\mathrm{\pi}\mathrm{i})}\oint_{C}\frac{f(z)}{(z - z_{0})^{(n + 1)}}dz\right\vert{}
$$

$$
\le \ \frac{n!}{(2\mathrm{\pi})}\oint_{C}\frac{\vert{}f(z)\vert{}}{\vert{}z - z_{0}\vert{}^{(n + 1)}}\vert{}dz\vert{}
$$

On $C$, $\vert{}z - z_{0}\vert{} = R$ and $\vert{}f(z)\vert{} \le M$.

Taking absolute values in the integral formula, and using $\vert{}\int g(z)dz\vert{} \le \int\vert{}g(z)\vert{}\vert{}dz\vert{}$

$$
\vert{}f^{(n)}(z_{0})\vert{} \le \frac{n!}{2\mathrm{\pi}} \cdot \frac{M}{R^{(n + 1)}} \cdot \oint_{C}\vert{}dz\vert{}
$$

The contour length is $2\mathrm{\pi}R$, so

$$
= \frac{n!M}{(2\mathrm{\pi}R^{(n + 1)})} \cdot 2\mathrm{\pi}R = \frac{n!M}{R^{n}}
$$

## 3 Maximum Modulus Principle

Suppose $f(z)$ is analytic in the open disk and continuous on its closure, and let $C$ be its boundary circle.

Write

$$
M = \max_{\zeta \in C}\vert{}f(\zeta)\vert{} \tag{4}
$$

so that $\vert{}f(\zeta)\vert{} \le M$ for every $\zeta$ on $C$. The maximum-modulus
principle says that no interior point exceeds this boundary maximum

$$
\max_{z \in \bar{D}}\vert{}f(z)\vert{} = \max_{\zeta \in C}\vert{}f(\zeta)\vert{} \tag{5}
$$

*Proof.* By Cauchy’s integral formula

$$
\vert{}f(z)\vert{} = \left\vert{}\left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{f(\zeta)}{(\zeta - z)}d\zeta\right\vert{} \tag{6}
$$

$$
\le \left(\frac{1}{2\mathrm{\pi}}\right)\oint_{C}\frac{M}{\vert{}\zeta - z\vert{}}\vert{}d\zeta\vert{}
$$

$$
\le \left(\frac{1}{2\mathrm{\pi}}\right) \cdot\left(\frac{M}{d}\right)\oint_{C}\vert{}d\zeta\vert{}
$$

$$
= \left(\frac{1}{2\mathrm{\pi}}\right) \cdot\left(\frac{M}{d}\right) \cdot L
$$

$$
= \left(\frac{L}{(2\mathrm{\pi}d)}\right)M
$$

Here $d$ is the distance from $z$ to the contour $C$ and $L$ is its length; for the circle $L = 2\mathrm{\pi}R$, so the bound reads $\vert{}f(z)\vert{} \le (R/d)M$.

Apply Cauchy’s integral formula to the function $[f(z)]^{n}$:

For a fixed interior point $z$ at distance $d$ from the boundary, $\vert{}\zeta - z\vert{} \ge d$ on $C$, and $\vert{}f(\zeta)\vert{} \le M$ on C

$$
\vert{}[f(z)]^{n}\vert{} = \left\vert{}\left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\frac{[f(\zeta)]^{n}}{(\zeta - z)}d\zeta\right\vert{} \tag{7}
$$

$$
\le \left(\frac{L}{(2\mathrm{\pi}d)}\right)M^{n}
$$

Take the nth root

$$
\vert{}f(z)\vert{} \le \sqrt[n]{\frac{L}{2\mathrm{\pi}d}}\,M \tag{8}
$$

Let $n \to \infty$. Since

$$
\sqrt[n]{\left(\frac{L}{(2\mathrm{\pi}d)}\right)} \to 1 \tag{9}
$$

we obtain

$$
\vert{}f(z)\vert{} \le M \tag{10}
$$

## 4 Liouville's Theorem

If $f(z)$ is analytic on the whole complex plane (entire), and $\vert{}f(z)\vert{} \le M$, then $f(z)$ is constant.

*Proof.* Take arbitrary distinct points $z_{1}$ and $z_{2}$.

Consider

$$
I = \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{f(z)}{[(z - z_{1})(z - z_{2})]}dz \tag{11}
$$

Choose the contour $C$ to be $\vert{}z\vert{} = R$, where $R > \max(\vert{}z_{1}\vert{}, \vert{}z_{2}\vert{})$, and let $R \to \infty$.

By partial fractions

$$
I = \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{f(z)}{[(z - z_{1})(z - z_{2})]}dz \tag{12}
$$

$$
= \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C_{1}}\frac{[\frac{f(z)}{(z - z_{2})}]}{(z - z_{1})}dz + \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C_{2}}\frac{[\frac{f(z)}{(z - z_{1})}]}{(z - z_{2})}dz
$$

By Cauchy's integral formula

$$
I = \frac{f(z_{1})}{z_{1} - z_{2}} + \frac{f(z_{2})}{z_{2} - z_{1}}
= \frac{f(z_{1}) - f(z_{2})}{z_{1} - z_{2}} \tag{13}
$$

an expression independent of $R$.

On $\vert{}z\vert{} = R$ the distances to the two points satisfy

$$
\vert{}z - z_{1}\vert{} \ge R - \vert{}z_{1}\vert{}, \qquad
\vert{}z - z_{2}\vert{} \ge R - \vert{}z_{2}\vert{} \tag{14}
$$

With $\vert{}f\vert{} \le M$ on $C$ and contour length $2\mathrm{\pi}R$, the same integral is
bounded by

$$
\vert{}I\vert{} \le \frac{1}{2\mathrm{\pi}}\oint_{C}\frac{M}{\vert{}z - z_{1}\vert{}\vert{}z - z_{2}\vert{}}\vert{}dz\vert{}
\le \frac{MR}{(R - \vert{}z_{1}\vert{})(R - \vert{}z_{2}\vert{})} \tag{15}
$$

and the right-hand side tends to $0$ as $R \to \infty$. Hence $I = 0$ for every
pair $z_{1} \ne z_{2}$, so

$$
f(z_{1}) - f(z_{2}) = 0 \tag{16}
$$

Since $z_{1}$ and $z_{2}$ are arbitrary, $f$ is constant.

*Alternatively*, differentiating Cauchy's formula for $f'$ and letting
$R \to \infty$ gives the same conclusion directly

$$
\vert{}f'(z)\vert{} = \left\vert{}\left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{\vert{}\zeta - z\vert{} = R}\frac{f(\zeta)}{(\zeta - z)^{2}}d\zeta\right\vert{}
\le \left(\frac{1}{2\mathrm{\pi}}\right)\cdot\left(\frac{M}{R^{2}}\right)\cdot 2\mathrm{\pi}R = \frac{M}{R} \to 0 \tag{17}
$$

so $f'(z) \equiv 0$ everywhere, and $f$ is constant.

## 5 Mean Value Formula

Suppose $f(z)$ is analytic in the region bounded by $C$: $\vert{}z - z_{0}\vert{} = R$, and also on $C$.

Then

$$
f(z_{0}) = \frac{1}{2\mathrm{\pi}}\int_{0}^{2\mathrm{\pi}}f(z_{0} + R\mathrm{e}^{\mathrm{i}\theta})d\theta \tag{18}
$$

so $f(z_{0})$ is the average of $f$ over the circle $\vert{}z - z_{0}\vert{} = R$.

*Proof.* By Cauchy’s integral formula

$$
f(z_{0}) = \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{f(\zeta)}{\zeta - z_{0}}d\zeta \tag{19}
$$

With

$$
\zeta = z_{0} + R\mathrm{e}^{\mathrm{i}\theta}, \qquad
d\zeta = \mathrm{i}R\mathrm{e}^{\mathrm{i}\theta} d\theta \tag{20}
$$

the integral becomes

$$
f(z_{0}) = \frac{1}{2\mathrm{\pi}\mathrm{i}} \int_{0}^{2\mathrm{\pi}}
\frac{f(z_{0} + R\mathrm{e}^{\mathrm{i}\theta})}{R\mathrm{e}^{\mathrm{i}\theta}}
\cdot \mathrm{i}R\mathrm{e}^{\mathrm{i}\theta} d\theta
= \frac{1}{2\mathrm{\pi}} \int_{0}^{2\mathrm{\pi}} f(z_{0} + R\mathrm{e}^{\mathrm{i}\theta}) d\theta \tag{21}
$$

## 6 Converse of Cauchy's Theorem

Suppose $f(z)$ is analytic in $D$. The following statements are equivalent:

1) For every closed curve $C$ in $D$

$$
\oint_{C}f(z)dz = 0 \tag{22}
$$

2) $f(z)$ has an antiderivative in $D$.

*Proof.* Fix $z_{0} \in D$. For $z \in D$, define

$$
F(z) = \int_{z_{0}}^{z}f(\zeta)d\zeta \tag{23}
$$

The zero-integral condition makes this definition independent of the chosen path: any two paths from $z_{0}$ to $z$ form a closed curve when one is followed in reverse, and the integral around that closed curve is zero.

$$
F'(z) = f(z) \tag{24}
$$

To compute $F'(z)$, choose the short straight segment from $z$ to $z + \Delta z$. Path independence gives:

On $\zeta = z + t\Delta z$, $0 \le t \le 1$

$$
\frac{F(z + \Delta z) - F(z)}{\Delta z} = \int_{0}^{1}f(z + t\Delta z)dt \tag{25}
$$

$$
F'(z) = f(z)
$$

Conversely, with $F'= f$

$$
\oint_{C}f(z)dz = \oint_{C}F'(z)dz = 0 \tag{26}
$$

$$
\lim_{\Delta z \to 0}\frac{F(z + \Delta z) - F(z)}{\Delta z} = f(z)
$$
