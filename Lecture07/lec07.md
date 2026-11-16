# Chapter 7: Applications of Cauchy's Integral Formula

## 7.1 Applications of Cauchy’s Integral Formula

### 7.1.1 Evaluation of a Contour Integral

$$
f(z) = \oint_{\vert{}\zeta\vert{} = 2}\frac{(\zeta^{3} + 2\zeta + 1)}{(\zeta - z)^{2}}d\zeta \tag{1}
$$

Find $f'(1)$ and $f'(2 + \mathrm{i})$.

By Cauchy’s integral formula:

The integrand has the form $g(\zeta)/(\zeta - z)^{2}$, where $g(\zeta) = \zeta^{3} + 2\zeta + 1$ is analytic everywhere. If $\vert{}z\vert{} < 2$, the point $z$ is inside $C$, so the generalized Cauchy integral formula with derivative order 1 applies: the integral equals $2\mathrm{\pi}\mathrm{i}g'(z)$. Since $g'(\zeta) = 3\zeta^{2} + 2$, this gives the first branch. If $\vert{}z\vert{} > 2$, the pole $\zeta = z$ lies outside $C$, so the integrand is analytic on and inside $C$; Cauchy’s theorem makes the integral zero.

$$
\oint_{\vert{}\zeta\vert{} = 2}\frac{\zeta^{3} + 2\zeta + 1}{{(\zeta - z)}^{2}}d\zeta = \begin{cases} 2\mathrm{\pi}\mathrm{i}(3z^{2} + 2)\quad & \vert{}z\vert{} < 2 \\ 0 & \vert{}z\vert{} > 2 \end{cases} \tag{2}
$$

The two cases are $\vert{}z\vert{} < 2$ and $\vert{}z\vert{} > 2$.

Differentiating on the two regions gives:

Differentiate each branch separately. For $\vert{}z\vert{} < 2$, $d[2\mathrm{\pi}\mathrm{i}(3z^{2} + 2)]/dz = 2\mathrm{\pi}\mathrm{i} \cdot 6z = 12\mathrm{\pi}\mathrm{i}z$. For $\vert{}z\vert{} > 2$, the branch is the constant 0, so its derivative is 0. Substituting $z = 1$ gives $f'(1) = 12\mathrm{\pi}\mathrm{i}$; because $\vert{}2 + \mathrm{i}\vert{} = \sqrt{5} > 2$, the exterior branch gives $f'(2 + \mathrm{i}) = 0$.

$$
f'(z) = \begin{cases} 12\mathrm{\pi}\mathrm{i}z, & \vert{}z\vert{} < 2, \\ 0, & \vert{}z\vert{} > 2, \end{cases}\quad f'(1) = 12\mathrm{\pi}\mathrm{i}, \quad f'(2 + \mathrm{i}) = 0 \tag{3}
$$

At $\vert{}z\vert{} = 2$, the pole lies on the contour, so the contour integral is not defined.

Given on the boundary $C$:

### 7.1.2 Estimate for the Derivative

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
\vert{}f(z)\vert{}/\vert{}z - 1\vert{}^{2} \le 4
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

### 7.1.3 A Parameter-Dependent Contour Integral

$$
f(z) = \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{\mathrm{e}^{\zeta^{2}}}{(\zeta^{3} - z\zeta^{2})}d\zeta, \tag{5}
$$

$$
C:\vert{}\zeta - z\vert{} = 3
$$

Find: (1) the expression for $f(z)$; (2) $f'(\mathrm{i})$, $f'(0)$, $f'(3 + \mathrm{i})$.

Solution. From

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

Factor the denominator: $\zeta^{3} - z\zeta^{2} = \zeta^{2}(\zeta - z)$. Thus, for $z \ne 0$, the integrand has a double pole at $\zeta = 0$ and a simple pole at $\zeta = z$. The contour $\vert{}\zeta - z\vert{} = 3$ contains $\zeta = z$ at its centre. The origin is inside the contour exactly when $\vert{}z\vert{} < 3$, and outside exactly when $\vert{}z\vert{} > 3$.

Using Cauchy’s integral formula, split the contour into the small contours $C_{0}$ and $C_{1}$ around the two singular points:

$$
f(z) = \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C_{0}}\frac{[\frac{\mathrm{e}^{\zeta^{2}}}{(\zeta - z)}]}{(\zeta - 0)^{2}}d\zeta + \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C_{1}}\frac{[\frac{\mathrm{e}^{\zeta^{2}}}{\zeta^{2}}]}{(\zeta - z)}d\zeta \tag{8}
$$

Double pole at $\zeta = 0$:

$$
h(\zeta)/\zeta^{2} \tag{9}
$$

$$
h(\zeta) = \mathrm{e}^{\zeta^{2}}/(\zeta - z)
$$

$$
h'(0)
$$

$$
h'(\zeta) = [(2\zeta \mathrm{e}^{\zeta^{2}})(\zeta - z) - \mathrm{e}^{\zeta^{2}}]/(\zeta - z)^{2}
$$

$$
h'(0) = -1/z^{2}
$$

Simple pole at $\zeta = z$:

$$
[\mathrm{e}^{\zeta^{2}}/\zeta^{2}]/(\zeta - z) \tag{10}
$$

$$
\mathrm{e}^{z^{2}}/z^{2}
$$

$$
= {\left[\left(\frac{\mathrm{e}^{\zeta^{2}}}{\zeta - z}\right)'\right]}_{\zeta = 0} + {\left[\frac{\mathrm{e}^{\zeta^{2}}}{\zeta^{2}}\right]}_{\zeta = z}
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
f(z) = \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{\mathrm{e}^{\zeta^{2}}}{(\zeta^{3} - z\zeta^{2})}d\zeta \tag{11}
$$

$$
= \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{[\frac{\mathrm{e}^{\zeta^{2}}}{\zeta^{2}}]}{(\zeta - z)}d\zeta
$$

When $\vert{}z\vert{} > 3$, the origin is outside $C$, so only the simple pole at $\zeta = z$ is enclosed. The generalized Cauchy formula therefore gives the numerator $\mathrm{e}^{\zeta^{2}}/\zeta^{2}$ evaluated at $\zeta = z$, which is $\mathrm{e}^{z^{2}}/z^{2}$.

$$
= {[\frac{\mathrm{e}^{\zeta^{2}}}{\zeta^{2}}]}_{\zeta = z}
$$

$$
= \frac{\mathrm{e}^{z^{2}}}{z^{2}}
$$

For the exterior case:

$$
f(z) = \begin{cases} \frac{\mathrm{e}^{z^{2}} - 1}{z^{2}} & 0 < \vert{}z\vert{} < 3 \\ 1 & z = 0 \\ \frac{\mathrm{e}^{z^{2}}}{z^{2}} & \vert{}z\vert{} > 3 \end{cases} \tag{12}
$$

[At $\vert{}z\vert{} = 3$, the point $\zeta = 0$ lies on $C$, so the contour integral is not defined.]

For (2),

$$
f'(z) = \begin{cases} ? & \vert{}z\vert{} < 3 \\ ? & \vert{}z\vert{} > 3 \end{cases} \tag{13}
$$

$$
\left[\frac{\mathrm{e}^{z^{2}} - 1}{z^{2}}\right]
$$

For $0 < \vert{}z\vert{} < 3$:

$$
(\mathrm{e}^{z^{2}} - 1)/z^{2} \tag{14}
$$

$$
2z\mathrm{e}^{z^{2}}
$$

$$
2z
$$

$$
f'(z) = [(2z\mathrm{e}^{z^{2}})z^{2} - (\mathrm{e}^{z^{2}} - 1)(2z)]/z^{4}
$$

$$
f'(z) = 2[z^{2}\mathrm{e}^{z^{2}} - (\mathrm{e}^{z^{2}} - 1)]/z^{3}
$$

$$
= \frac{{[(2z\mathrm{e}^{z^{2}})z^{2} - (\mathrm{e}^{z^{2}} - 1) \cdot 2z]}}{z^{4}}
$$

$$
= \frac{{{2z^{2}\mathrm{e}}^{z^{2}} - 2(\mathrm{e}^{z^{2}} - 1)}}{z^{3}}
$$

At $z = \mathrm{i}$:

$$
f'(\mathrm{i}) = {\left.\frac{2[z^{2}\mathrm{e}^{z^{2}} - \mathrm{e}^{z^{2}} + 1]}{z^{3}}\right\vert{}}_{z = \mathrm{i}} = 2\mathrm{i}\left(1 - \frac{2}{\mathrm{e}}\right) \tag{15}
$$

Note: $At\ z = 0:$

$$
f(0) = f(z)\vert{}_{z = 0} \tag{16}
$$

At $z = 0$, use the original integral because the two poles coincide. The contour is then $\vert{}\zeta\vert{} = 3$ and the integrand is $\mathrm{e}^{\zeta^{2}}/\zeta^{3}$. Cauchy’s derivative formula with derivative order 2 gives $f(0) = (1/2!)(d^{2}/d\zeta^{2})\mathrm{e}^{\zeta^{2}}\vert{}\zeta = 0$. Since $(\mathrm{e}^{\zeta^{2}})'= 2\zeta \mathrm{e}^{\zeta^{2}}$ and $(\mathrm{e}^{\zeta^{2}})''= 2\mathrm{e}^{\zeta^{2}} + 4\zeta^{2}\mathrm{e}^{\zeta^{2}}$, the second derivative at 0 is 2, so $f(0) = 1$.

$$
= \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{\vert{}\zeta - 0\vert{} = 3}\frac{\mathrm{e}^{\zeta^{2}}}{\zeta^{3}}d\zeta
$$

$$
= \left(\frac{1}{2!}\right)\left(\frac{d^{2}}{d\zeta^{2}}\right)\mathrm{e}^{\zeta^{2}}\vert{}_{\zeta = 0} = 1
$$

The derivatives of $\mathrm{e}^{\zeta^{2}}$ are:

$$
(\mathrm{e}^{\zeta^{2}})'= ({2\zeta \mathrm{e}}^{\zeta^{2}}) \tag{17}
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

Power series at z = 0:

$$
\mathrm{e}^{z^{2}} = 1 + z^{2} + z^{4}/2!+z^{6}/3!+\cdots \tag{18}
$$

$$
f(z) = (\mathrm{e}^{z^{2}} - 1)/z^{2} = 1 + z^{2} + z^{4}/2!+z^{6}/3!+\cdots
$$

$$
f'(0) = 0
$$

$$
f'(0) = \frac{1}{3!}{\left.\frac{d^{3}}{d\zeta^{3}}\mathrm{e}^{\zeta^{2}}\right\vert{}}_{\zeta = 0} = 0
$$

For the exterior region, differentiate the second branch of $f(z)$:

$$
f'(z) = \left(\frac{\mathrm{e}^{z^{2}}}{z^{2}}\right)'= \frac{2\mathrm{e}^{z^{2}}(z^{2} - 1)}{z^{3}}, \vert{}z\vert{} > 3 \tag{19}
$$

Hence, at the requested point:

$$
f^{'(3 + \mathrm{i})} = {\left.\frac{2\mathrm{e}^{z^{2}}(z^{2} - 1)}{z^{3}}\right\vert{}}_{z = 3 + \mathrm{i}} = \frac{2\mathrm{e}^{{(3 + \mathrm{i})}^{2}}({(3 + \mathrm{i})}^{2} - 1)}{{(3 + \mathrm{i})}^{3}} \tag{20}
$$

## 7.2 Fundamental Properties of Analytic Functions

### 7.2.1 Existence of Derivatives

If $f(z)$ is analytic, then its derivatives $f'(z)$, $f''(z)$, … of all orders exist.

### 7.2.2 Cauchy’s Inequality

Suppose $f(z)$ is analytic on and inside the circle $C$: $\vert{}z - z_{0}\vert{} = R$.

Suppose that

$$
\vert{}f(z)\vert{} \le M\quad on\ C \tag{21}
$$

Then

$$
\vert{}f^{(n)}(z_{0})\vert{} \le \ \frac{n!M}{R^{n}}, \tag{22}
$$

where

$$
M = \max_{C}\vert{}f(z)\vert{} \tag{23}
$$

*Proof.* By the generalized Cauchy integral formula:

$$
f^{(n)}(z_{0}) = \frac{n!}{(2\mathrm{\pi}\mathrm{i})}\oint_{C}\frac{f(z)}{(z - z_{0})^{(n + 1)}}dz \tag{24}
$$

$$
\vert{}f^{(n)}(z_{0})\vert{} = \left\vert{}\frac{n!}{(2\mathrm{\pi}\mathrm{i})}\oint_{C}\frac{f(z)}{(z - z_{0})^{(n + 1)}}dz\right\vert{}
$$

$$
\le \ \frac{n!}{(2\mathrm{\pi})}\oint_{C}\frac{\vert{}f(z)\vert{}}{\vert{}z - z_{0}\vert{}^{(n + 1)}}\vert{}dz\vert{}
$$

On $C$, $\vert{}z - z_{0}\vert{} = R$ and $\vert{}f(z)\vert{} \le M$. Taking absolute values in the integral formula and using $\vert{}\int g(z)dz\vert{} \le \int\vert{}g(z)\vert{}\vert{}dz\vert{}$ gives $\vert{}f^{(n)}(z_{0})\vert{} \le[n!/(2\mathrm{\pi})] \cdot[M/R^{(n + 1)}] \cdot \oint_{C}\vert{}dz\vert{}$. The contour length is $2\mathrm{\pi}R$, so the factors simplify to $n!M/R^{n}$.

$$
\le \ \frac{n!M}{(2\mathrm{\pi}R^{(n + 1)})}\oint_{C}\vert{}dz\vert{}
$$

$$
= \frac{n!M}{(2\mathrm{\pi}R^{(n + 1)})} \cdot 2\mathrm{\pi}R
$$

$$
= \frac{n!M}{R^{n}}
$$

### 7.2.3 Maximum Modulus Principle

Suppose $f(z)$ is analytic in the open disk and continuous on its closure, and let $C$ be its boundary circle.

On the boundary $C$, assume:

$$
\vert{}f(\zeta)\vert{} \le M, \quad \zeta \in C \tag{25}
$$

where

$$
M = \max_{\zeta \in C}\vert{}f(\zeta)\vert{}, \tag{26}
$$

Equivalently, the maximum-modulus conclusion is:

$$
\max_{z \in \bar{D}}\vert{}f(z)\vert{} = \max_{\zeta \in C}\vert{}f(\zeta)\vert{}. \tag{27}
$$

*Proof.* By Cauchy’s integral formula:

$$
\vert{}f(z)\vert{} = \left\vert{}\left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{f(\zeta)}{(\zeta - z)}d\zeta\right\vert{} \tag{28}
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

Here $d$ is the distance from $z$ to the contour $C$, and $L$ is the length of $C$.

Apply Cauchy’s integral formula to the function $[f(z)]^{n}$:

For a fixed interior point $z$ at distance $d$ from the boundary, $\vert{}\zeta - z\vert{} \ge d$ on $C$, and $\vert{}f(\zeta)\vert{} \le M$ on C:

$$
\vert{}[f(z)]^{n}\vert{} = \left\vert{}\left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\frac{[f(\zeta)]^{n}}{(\zeta - z)}d\zeta\right\vert{} \tag{29}
$$

$$
\le \left(\frac{L}{(2\mathrm{\pi}d)}\right)M^{n}.
$$

Take the nth root:

$$
\vert{}f(z)\vert{} \le[L/(2\mathrm{\pi}d)]^{1/n}M \tag{30}
$$

Let $n \to \infty$. Since

$$
\\sqrt[n]{\left(\frac{L}{(2\mathrm{\pi}d)}\right)} \to 1, \tag{31}
$$

we obtain

$$
\vert{}f(z)\vert{} \le M. \tag{32}
$$

### 7.2.4 Liouville’s Theorem

If $f(z)$ is analytic on the whole complex plane (entire), and $\vert{}f(z)\vert{} \le M$, then $f(z)$ is constant.

*Proof.* Take arbitrary distinct points $z_{1}$ and $z_{2}$.

Consider

$$
I = \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{f(z)}{[(z - z_{1})(z - z_{2})]}dz. \tag{33}
$$

Choose the contour $C$ to be $\vert{}z\vert{} = R$, where $R > \max(\vert{}z_{1}\vert{}, \vert{}z_{2}\vert{})$, and let $R \to \infty$.

By partial fractions:

$$
I = \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{f(z)}{[(z - z_{1})(z - z_{2})]}dz \tag{34}
$$

$$
= \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C_{1}}\frac{[\frac{f(z)}{(z - z_{2})}]}{(z - z_{1})}dz + \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C_{2}}\frac{[\frac{f(z)}{(z - z_{1})}]}{(z - z_{2})}dz
$$

Using Cauchy’s integral formula:

$$
= f(z_{1})/(z_{1} - z_{2}) + f(z_{2})/(z_{2} - z_{1})
$$

$$
= [f(z_{1}) - f(z_{2})]/(z_{1} - z_{2}).
$$

The residue calculation gives an expression independent of $R$. The estimate below shows that this same integral tends to zero as $R \to \infty$, so the residue expression must be zero:

$\vert{}I\vert{} < \varepsilon$ for every $\varepsilon > 0$.

The estimate is:

On $\vert{}z\vert{} = R$:

$$
\vert{}z - z_{1}\vert{} \ge R - \vert{}z_{1}\vert{} \tag{35}
$$

$$
\vert{}z - z_{2}\vert{} \ge R - \vert{}z_{2}\vert{}
$$

$$
\vert{}I\vert{} \le \left(\frac{1}{2\mathrm{\pi}}\right)\oint_{C}\frac{M}{(\vert{}z - z_{1}\vert{}\vert{}z - z_{2}\vert{})}\vert{}dz\vert{}.
$$

Letting $R \to \infty$ therefore gives $I = 0$.

Hence

$$
f(z_{1}) - f(z_{2}) = 0 \tag{36}
$$

and therefore $f(z_{1}) = f(z_{2})$

Since $z_{1}$ and $z_{2}$ are arbitrary, $f(z)$ is constant.

By Cauchy’s integral formula:

$$
\vert{}f'(z)\vert{} = \left\vert{}\left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{f(\zeta)}{(\zeta - z)^{2}}d\zeta\right\vert{} \tag{37}
$$

Taking absolute values and using $\vert{}f(\zeta)\vert{} \le M$ on the circle $\vert{}\zeta - z\vert{} = R$ gives $\vert{}f'(z)\vert{} \le (1/2\mathrm{\pi})(M/R^{2})(2\mathrm{\pi}R) = M/R$. The point $z$ is arbitrary, and $R$ can be made arbitrarily large because $f$ is entire. Therefore $\vert{}f'(z)\vert{} = 0$, so $f'(z) = 0$ everywhere and $f$ is constant.

where $C$: $\vert{}\zeta - z\vert{} = R$.

$$
\vert{}f'(z)\vert{} \le \left(\frac{1}{2\mathrm{\pi}}\right) \cdot\left(\frac{M}{R^{2}}\right) \cdot 2\mathrm{\pi}R = \frac{M}{R} \tag{38}
$$

Let $R \to \infty$. Then

$$
\frac{M}{R} \to 0 \tag{39}
$$

$$
f'(z) = 0
$$

### 7.2.5 Mean Value Formula

Suppose $f(z)$ is analytic in the region bounded by $C$: $\vert{}z - z_{0}\vert{} = R$, and also on $C$.

Then

$$
f(z_{0}) = \frac{1}{2\mathrm{\pi}}\int_{0}^{2\mathrm{\pi}}f(z_{0} + R\mathrm{e}^{\mathrm{i}\theta})d\theta \tag{40}
$$

*Proof.* By Cauchy’s integral formula:

$$
f(z_{0}) = \left(\frac{1}{2\mathrm{\pi}\mathrm{i}}\right)\oint_{C}\frac{f(\zeta)}{\zeta - z_{0}}d\zeta \tag{41}
$$

Let

$$
\zeta - z_{0} = R\mathrm{e}^{\mathrm{i}\theta} \tag{42}
$$

With $\zeta = z_{0} + R\mathrm{e}^{\mathrm{i}\theta}$ and $d\zeta = \mathrm{i}R\mathrm{e}^{\mathrm{i}\theta}d\theta$, the Cauchy integral formula gives $f(z_{0}) = (1/2\mathrm{\pi}\mathrm{i})\int_{0}^{2\mathrm{\pi}}f(z_{0} + R\mathrm{e}^{\mathrm{i}\theta})/(R\mathrm{e}^{\mathrm{i}\theta}) \cdot \mathrm{i}R\mathrm{e}^{\mathrm{i}\theta}d\theta$:

then

$$
d\zeta = {\mathrm{i}R\mathrm{e}}^{\mathrm{i}\theta}d\theta \tag{43}
$$

$$
f(z_{0}) = \frac{1}{2\mathrm{\pi}\mathrm{i}}\int_{0}^{2\mathrm{\pi}}\frac{f(z_{0} + R\mathrm{e}^{\mathrm{i}\theta})}{(R\mathrm{e}^{\mathrm{i}\theta})} \cdot \mathrm{i}R\mathrm{e}^{(\mathrm{i}\theta)}d\theta
$$

$$
= \frac{1}{2\mathrm{\pi}}\int_{0}^{2\mathrm{\pi}}f(z_{0} + R\mathrm{e}^{\mathrm{i}\theta})d\theta
$$

### 7.2.6 Converse of Cauchy’s Theorem

Suppose $f(z)$ is analytic in $D$. The following statements are equivalent:

1) For every closed curve $C$ in $D$:

$$
\oint_{C}f(z)dz = 0. \tag{44}
$$

2) $f(z)$ has an antiderivative in $D$.

*Proof.* Fix $z_{0} \in D$. For $z \in D$, define

$$
F(z) = \int_{z_{0}}^{z}f(\zeta)d\zeta \tag{45}
$$

The zero-integral condition makes this definition independent of the chosen path: any two paths from $z_{0}$ to $z$ form a closed curve when one is followed in reverse, and the integral around that closed curve is zero.

$$
F'(z) = f(z) \tag{46}
$$

To compute $F'(z)$, choose the short straight segment from $z$ to $z + \Delta z$. Path independence gives:

On $\zeta = z + t\Delta z$, $0 \le t \le 1$:

$$
[F(z + \Delta z) - F(z)]/\Delta z = \int_{0}^{1}f(z + t\Delta z)dt \tag{47}
$$

$$
F'(z) = f(z)
$$

Conversely, with $F'= f$:

$$
\oint_{C}f(z)dz = \oint_{C}F'(z)dz = 0 \tag{48}
$$

$$
\lim_{\Delta z \to 0}\frac{F(z + \Delta z) - F(z)}{\Delta z} = f(z)
$$

## 7.3 Applications of the Fundamental Theorems

### 7.3.1 Existence of a Zero

Suppose $f(z)$ is analytic in $D$, where $D$ is the region on and inside $\vert{}z\vert{} = R$.

On the boundary $\vert{}z\vert{} = R$, suppose

$$
\vert{}f(z)\vert{} > a > 0 \tag{49}
$$

and

$\vert{}f(0)\vert{} <$ a

Show that there exists $\zeta$ inside the region such that

$$
f(\zeta) = 0. \tag{50}
$$

*Proof.* Use proof by contradiction.

Suppose that

for every $z$ in the closed region $D$, $f(z) \ne 0$.

Then

$$
F(z) = \frac{1}{f(z)} \tag{51}
$$

is analytic in $D$.

Apply the maximum modulus principle to $F(z)$, comparing its value at the origin with its values on the boundary:

$$
\vert{}F(0)\vert{} = \frac{1}{\vert{}f(0)\vert{}} > \frac{1}{a} \tag{52}
$$

$$
\vert{}F(R\mathrm{e}^{\mathrm{i}\theta})\vert{} = \frac{1}{\vert{}f(R\mathrm{e}^{\mathrm{i}\theta})\vert{}} < \frac{1}{a}
$$

$$
F(z) = 1/f(z)
$$

$$
\vert{}F(0)\vert{} = 1/\vert{}f(0)\vert{} > 1/a
$$

$$
\vert{}f(z)\vert{} > a
$$

$$
\vert{}F(z)\vert{} = 1/\vert{}f(z)\vert{} < 1/a
$$

### 7.3.2 An Entire Function with Bounded Real Part

Suppose $f(z)$ is analytic on the whole complex plane, and there exists $M > 0$ such that

$$
R\mathrm{e}\ f(z) < M. \tag{53}
$$

Show that $f(z)$ is constant.

*Proof.* Let

$$
F(z) = \mathrm{e}^{f(z)}. \tag{54}
$$

$$
\vert{}F(z)\vert{} = \vert{}\mathrm{e}^{f(z)}\vert{} = \mathrm{e}^{R\mathrm{e}\ f(z)}.
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
\vert{}F(z)\vert{} < \mathrm{e}^{M}. \tag{55}
$$

Thus $F(z)$ is an entire bounded function.

By Liouville’s theorem,

$$
F(z) = constant. \tag{56}
$$

Therefore

$$
\mathrm{e}^{f(z)} = constant, \tag{57}
$$

Differentiate both sides:

The derivative of the left-hand side is $\mathrm{e}^{f(z)}f'(z)$ by the chain rule. The derivative of a constant is zero, so $\mathrm{e}^{f(z)}f'(z) = 0$. Since $\mathrm{e}^{f(z)} \ne 0$ for every $z$, division by this factor gives $f'(z) = 0$ everywhere; hence $f$ is constant.

$$
\mathrm{e}^{f(z)}f'(z) = 0 \tag{58}
$$

Since the exponential function never vanishes, we conclude that:

$$
f'(z) = 0 \tag{59}
$$

and therefore $f(z)$ is constant.

## 7.4 Further Contour Integral Evaluations

### 7.4.1 Applications of the Generalized Cauchy Integral Formula

Suppose $f(z)$ is analytic for $\vert{}z\vert{} < 2$, and

$$
f(0) = 1\quad f'(0) = 2 \tag{60}
$$

(1) Evaluate

$$
I_{1} = \oint_{\vert{}z\vert{} = 1}[\frac{{(z + 1)}^{2}}{z^{2}}]f(z)dz \tag{61}
$$

(2) Evaluate

$$
I_{2} = \int_{0}^{2\mathrm{\pi}}\cos^{2}\left(\frac{\theta}{2}\right)f(\mathrm{e}^{\mathrm{i}\theta}) d\theta \tag{62}
$$

(1) By the generalised Cauchy integral formula:

$$
I_{1} = \left(\frac{2\mathrm{\pi}\mathrm{i}}{1!}\right){[((z + 1)^{2}f(z)]}_{z = 0} \tag{63}
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

(2) Let

$$
z = \mathrm{e}^{\mathrm{i}\theta} \tag{64}
$$

Then

On $\vert{}z\vert{} = 1$, with $z = \mathrm{e}^{\mathrm{i}\theta}$ and $0 \le \theta \le 2\mathrm{\pi}$:

$$
\mathrm{e}^{\mathrm{i}\theta} = z \tag{65}
$$

$$
\mathrm{e}^{-\mathrm{i}\theta} = z^{-1}
$$

$$
\cos \theta = (z + z^{-1})/2
$$

$$
dz = \mathrm{i}z\ d\theta
$$

$$
d\theta = dz/(\mathrm{i}z)
$$

$$
\cos^{2}(\theta /2) = (1 + \cos \theta)/2
$$

$$
[1 + (z + z^{-1})/2]/2 = (z^{2} + 2z + 1)/(4z)
$$

$$
(z^{2} + 2z + 1)/(4\mathrm{i}z^{2})
$$

$$
I_{2} = (1/4\mathrm{i})I_{1} = (1/4\mathrm{i})(8\mathrm{\pi}\mathrm{i}) = 2\mathrm{\pi}
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

Substitute:

$$
I_{2} = \int_{0}^{2\mathrm{\pi}}[\frac{(1 + \cos \theta)}{2}]f(\mathrm{e}^{\mathrm{i}\theta})d\theta \tag{66}
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
\mathrm{e}^{\mathrm{i}\theta} = z \tag{67}
$$

**Let n be a non-negative integer. We evaluate the trigonometric integral by converting it to a contour integral.**

By Euler’s formula:

$$
\cos \theta + \mathrm{i}\ \sin \theta = \mathrm{e}^{\mathrm{i}\theta} \tag{68}
$$

$$
\cos(n\theta - \sin \theta) + \mathrm{i}\ \sin(n\theta - \sin \theta) = \mathrm{e}^{\mathrm{i}(n\theta - \sin \theta)}
$$

Taking the complex conjugate of the second Euler formula gives:

The conjugate identity is $\mathrm{e}^{-\mathrm{i}(n\theta - \sin \theta)} = \cos(n\theta - \sin \theta) - \mathrm{i}\sin(n\theta - \sin \theta)$. Multiplying by $\mathrm{e}^{\cos \theta}$ and integrating gives a complex integral $J$ whose real part is the required $I$. The exponent simplifies because $-\mathrm{i}(n\theta - \sin \theta) = -\mathrm{i}n\theta + \mathrm{i}\sin \theta$, so $\cos \theta + \mathrm{i}\sin \theta$ appears together.

$$
\mathrm{e}^{-\mathrm{i}(n\theta - \sin \theta)} = \cos(n\theta - \sin \theta) - \mathrm{i}\sin(n\theta - \sin \theta). \tag{69}
$$

The original integral $I$ is the real component of the corresponding complex integral $J$:

$$
J = \int_{0}^{2\mathrm{\pi}}\mathrm{e}^{\cos \theta}\mathrm{e}^{-\mathrm{i}(n\theta - \sin \theta)} d\theta = \int_{0}^{2\mathrm{\pi}}\mathrm{e}^{\cos \theta + \mathrm{i}\sin \theta - \mathrm{i}n\theta} d\theta . \tag{70}
$$

Using $\cos \ \theta + \mathrm{i}\sin \ \theta = \mathrm{e}^{\mathrm{i}\theta}$, we obtain:

$$
\cos \theta + \mathrm{i}\sin \theta = \mathrm{e}^{\mathrm{i}\theta} \tag{71}
$$

$$
\mathrm{e}^{\mathrm{i}\theta} - \mathrm{i}n\theta
$$

$$
z = \mathrm{e}^{\mathrm{i}\theta}
$$

$$
\mathrm{e}^{\mathrm{i}\theta} = z
$$

$$
\mathrm{e}^{-\mathrm{i}n\theta} = z^{-n}
$$

$$
\mathrm{e}^{z}z^{-n}
$$

$$
d\theta = dz/(\mathrm{i}z)
$$

$$
J = (1/\mathrm{i})\oint_{\vert{}z\vert{} = 1}\mathrm{e}^{z}z^{-n - 1}dz
$$

$$
J = \int_{0}^{2\mathrm{\pi}}\mathrm{e}^{\mathrm{e}^{\mathrm{i}\theta}}\mathrm{e}^{-\mathrm{i}n\theta} d\theta .
$$

Let $z = \mathrm{e}^{\mathrm{i}\theta}$. Then

$$
dz = \mathrm{i}z d\theta, \quad d\theta = \frac{dz}{\mathrm{i}z}. \tag{72}
$$

As $\theta$ goes from 0 to $2\mathrm{\pi}$, $z$ traverses the unit circle $C$ once counterclockwise. Hence

$$
J = \frac{1}{\mathrm{i}}\oint_{C}\mathrm{e}^{z}z^{-n - 1} dz. \tag{73}
$$

Expand the exponential:

$$
\mathrm{e}^{z} = \sum_{k = 0}^{\infty}z^{k}/k! \tag{74}
$$

$$
z^{-n - 1}
$$

$$
\sum_{k = 0}^{\infty}z^{k - n - 1}/k!
$$

$$
z^{-1}
$$

$$
2\mathrm{\pi}\mathrm{i}
$$

$$
k - n - 1 = -1
$$

$$
k = n
$$

$$
1/n!
$$

$$
J = (1/\mathrm{i})(2\mathrm{\pi}\mathrm{i})(1/n!) = 2\mathrm{\pi}/n!
$$

$$
I = 2\mathrm{\pi}/n!
$$

$$
\mathrm{e}^{z}z^{-n - 1} = \left(\sum_{k = 0}^{\infty}\frac{z^{k}}{k!}\right)z^{-n - 1} = \sum_{k = 0}^{\infty}\frac{z^{k - n - 1}}{k!}, \quad n = 0, 1, 2, \dots .
$$

Only the term with $k = n$ contributes to the contour integral. Thus

$$
J = \frac{1}{\mathrm{i}}(2\mathrm{\pi}\mathrm{i})\frac{1}{n!} = \frac{2\mathrm{\pi}}{n!}. \tag{75}
$$

This value is real. Since $I$ is the real component of $J$, it follows that

$$
I = \frac{2\mathrm{\pi}}{n!}, \quad n = 0, 1, 2, \dots . \tag{76}
$$
