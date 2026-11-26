# Mathematics Method for Physics -- Lecture 4

## Limits, Continuity, and Differentiability of Complex Functions

**Instructor:** Zhaolong Han, SOCE, Shanghai Jiao Tong University | **Email:** han.arkey@sjtu.edu.cn

*Overview: These lecture notes cover limits and continuity of complex functions, differentiability and differentials, and the Cauchy--Riemann conditions.*

---

## 1. Limits and Continuity of Complex Functions

### 1.1 Limit of a Complex Function

**Definition 1 (Limit at a Point).**
Let $w = f(z)$ be defined in a deleted neighborhood of $z_0$, and let $A \in \mathbb{C}$ be a complex constant. If for every $\varepsilon > 0$, there exists a $\delta > 0$ such that
$$
0 < \lvert z - z_0 \rvert < \delta \implies \lvert f(z) - A \rvert < \varepsilon,
$$
then $A$ is called the **limit** of $f(z)$ as $z$ approaches $z_0$, denoted by
$$
\lim_{z \to z_0} f(z) = A \quad (\text{or } f(z) \to A \text{ as } z \to z_0).
$$

**Geometric Remark:** In one-dimensional real calculus, $x \to x_0$ can only occur from two directions ($x \to x_0^+$ or $x \to x_0^-$). In the complex plane, however, $z \to z_0$ corresponds to $(x, y) \to (x_0, y_0)$ in $\mathbb{R}^2$, which can happen along **infinitely many arbitrary paths and directions**. For $\lim_{z \to z_0} f(z) = A$ to exist, $f(z)$ must approach $A$ regardless of the path taken by $z \to z_0$.

**Theorem 1 (Reduction to Real Two-Variable Limits).**
Let $z = x + iy$, $z_0 = x_0 + iy_0$, $w = f(z) = u(x, y) + iv(x, y)$, and $A = a + bi$. Then
$$
\lim_{z \to z_0} f(z) = A \iff \lim_{(x,y) \to (x_0,y_0)} u(x, y) = a \quad \text{and} \quad \lim_{(x,y) \to (x_0,y_0)} v(x, y) = b.
$$

**Algebraic Properties of Limits:** If $\lim_{z \to z_0} f(z) = A$ and $\lim_{z \to z_0} g(z) = B$, then:
$$
\lim_{z \to z_0} [f(z) \pm g(z)] = A \pm B, \quad \lim_{z \to z_0} [f(z)g(z)] = AB, \quad \lim_{z \to z_0} \frac{f(z)}{g(z)} = \frac{A}{B} \quad (B \neq 0).
$$

---

### 1.2 Continuity of a Complex Function

**Definition 2 (Continuity).**
Let $w = f(z)$ be a complex function defined in a neighborhood of $z_0$ or a domain $D$:
1. **Continuity at a Point:** $f(z)$ is said to be **continuous at $z_0$** if
   $$
   \lim_{z \to z_0} f(z) = f(z_0).
   $$
2. **Continuity in a Domain:** $f(z)$ is said to be **continuous in a domain $D$** if it is continuous at every point $z_0 \in D$.

**Theorem 2 (Continuity via Real and Imaginary Parts).**
A function $f(z) = u(x, y) + iv(x, y)$ is continuous at $z_0 = x_0 + iy_0$ if and only if both real functions $u(x, y)$ and $v(x, y)$ are continuous at $(x_0, y_0)$.

Sums, differences, products, quotients (with non-zero denominators), and compositions of continuous complex functions remain continuous. Furthermore, if $f(z)$ is continuous on a bounded closed domain $\overline{D}$, then $\lvert f(z) \rvert$ is bounded on $\overline{D}$ and attains its maximum and minimum values.

**Example 1 (Continuity Analysis of $w = \arg z$).**
Discuss the continuity of the principal argument function $w = \arg z \in (-\pi, \pi]$ on the complex plane.

*Solution:* For $z = x + iy \neq 0$, $\arg z$ is given explicitly by
$$
\arg z = \begin{cases}
    \arctan\dfrac{y}{x}, & x > 0, \\[0.9em]
    \pi + \arctan\dfrac{y}{x}, & x < 0, \, y \ge 0, \\[0.9em]
    -\pi + \arctan\dfrac{y}{x}, & x < 0, \, y < 0, \\[0.9em]
    \pm\dfrac{\pi}{2}, & x = 0, \, y \gtrless 0.
\end{cases}
$$
* At $z = 0$, $\arg z$ is undefined, so it is discontinuous at the origin.
* Let $z_0 = x_0 < 0$ be any point on the negative real axis. Approaching $x_0$ from the upper half-plane ($\operatorname{Im} z > 0$) versus the lower half-plane ($\operatorname{Im} z < 0$) yields different directional limits:
  $$
  \lim_{\substack{z \to x_0 \\ \operatorname{Im} z > 0}} \arg z = \pi, \qquad \lim_{\substack{z \to x_0 \\ \operatorname{Im} z < 0}} \arg z = -\pi.
  $$
* Since these limits do not agree, $\lim_{z \to x_0} \arg z$ does not exist, proving that $\arg z$ is discontinuous at every point on the negative real axis.

*Conclusion:* $w = \arg z$ is continuous everywhere on the **slit complex plane** $\mathbb{C} \setminus (-\infty, 0]$ (the complex plane cut along the non-positive real axis).

---

## 2. Differentiability and Cauchy--Riemann Conditions

### 2.1 Derivative and Differential of a Complex Function

**Definition 3 (Derivative of a Complex Function).**
Let $w = f(z)$ be defined in a neighborhood of $z_0$. If the limit
$$
\lim_{\Delta z \to 0} \frac{f(z_0 + \Delta z) - f(z_0)}{\Delta z} = \lim_{z \to z_0} \frac{f(z) - f(z_0)}{z - z_0}
$$
exists, then $f(z)$ is said to be **differentiable at $z_0$**, and this limit is called the **derivative** of $f(z)$ at $z_0$, denoted by $f'(z_0)$ or $\left.\frac{dw}{dz}\right\rvert_{z=z_0}$.

**Definition 4 (Differential of a Complex Function).**
A function $f(z)$ is differentiable at $z_0$ if and only if its increment $\Delta f(z_0) = f(z_0 + \Delta z) - f(z_0)$ can be expressed as
$$
\Delta f(z_0) = A \Delta z + o(\Delta z), \qquad \text{where } \lim_{\Delta z \to 0} \frac{o(\Delta z)}{\Delta z} = 0.
$$
Here $A = f'(z_0)$, and the principal linear part $df = A \Delta z = f'(z_0)\Delta z = f'(z_0)dz$ is called the **differential** of $f(z)$ at $z_0$.

**Remarks:**
* Because $\Delta z \to 0$ must yield the same limit along *all* paths in $\mathbb{C}$, complex differentiability is far more restrictive than real differentiability.
* If $f(z)$ is differentiable at $z_0$, it is necessarily continuous at $z_0$; the converse is false (e.g., $f(z) = \overline{z}$ and $f(z) = \operatorname{Im} z$ are continuous everywhere but differentiable nowhere; $f(z) = \lvert z \rvert^2$ is differentiable only at $z = 0$).
* Standard differentiation rules (linearity, product rule, quotient rule, chain rule, and inverse function rule) hold identically to real calculus.

---

### 2.2 Necessary Condition: The Cauchy--Riemann Equations

**Theorem 3 (Necessary Condition for Differentiability).**
Suppose $f(z) = u(x, y) + iv(x, y)$ is differentiable at $z_0 = x_0 + iy_0$. Then the first-order partial derivatives $u_x, u_y, v_x, v_y$ exist at $(x_0, y_0)$ and satisfy the **Cauchy--Riemann (C--R) equations**:
$$
\begin{cases}
    u_x = v_y, \\
    u_y = -v_x,
\end{cases}
\qquad \text{i.e.,} \qquad
\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y}, \quad \frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}.
$$
Furthermore, the derivative at $z_0$ is given by
$$
f'(z_0) = \frac{\partial u}{\partial x} + i\frac{\partial v}{\partial x} = \frac{\partial v}{\partial y} - i\frac{\partial u}{\partial y}.
$$

**Proof:**
Let $\Delta z = z - z_0 = \Delta x + i\Delta y$ and $\Delta w = f(z) - f(z_0) = \Delta u + i\Delta v$, where
$$
\Delta u = u(x_0 + \Delta x, y_0 + \Delta y) - u(x_0, y_0), \qquad \Delta v = v(x_0 + \Delta x, y_0 + \Delta y) - v(x_0, y_0).
$$
Since $f'(z_0)$ exists, the limit
$$
f'(z_0) = \lim_{\Delta z \to 0} \frac{\Delta u + i\Delta v}{\Delta x + i\Delta y}
$$
is independent of how $\Delta z \to 0$:
1. **Horizontal path** ($\Delta y = 0$, $\Delta x \to 0$):
   $$
   f'(z_0) = \lim_{\Delta x \to 0} \frac{\Delta u + i\Delta v}{\Delta x + i\cdot 0} = \lim_{\Delta x \to 0} \left(\frac{\Delta u}{\Delta x} + i\frac{\Delta v}{\Delta x}\right) = \frac{\partial u}{\partial x} + i\frac{\partial v}{\partial x}.
   $$
2. **Vertical path** ($\Delta x = 0$, $\Delta y \to 0$):
   $$
   f'(z_0) = \lim_{\Delta y \to 0} \frac{\Delta u + i\Delta v}{0 + i\Delta y} = \lim_{\Delta y \to 0} \left(\frac{\Delta v}{\Delta y} - i\frac{\Delta u}{\Delta y}\right) = \frac{\partial v}{\partial y} - i\frac{\partial u}{\partial y}.
   $$
Equating the real and imaginary parts of these two expressions yields $u_x = v_y$ and $u_y = -v_x$ at $(x_0, y_0)$. $\blacksquare$

*Remark (Polar Form):* In polar coordinates $z = re^{i\theta}$, the Cauchy--Riemann equations take the form
$$
\frac{\partial u}{\partial r} = \frac{1}{r}\frac{\partial v}{\partial \theta}, \qquad \frac{\partial v}{\partial r} = -\frac{1}{r}\frac{\partial u}{\partial \theta}, \qquad f'(z) = e^{-i\theta}\left(\frac{\partial u}{\partial r} + i\frac{\partial v}{\partial r}\right).
$$

---

### 2.3 Counterexample: C--R Equations Alone Are Not Sufficient

**Example 2 (Non-differentiable Function Satisfying C--R Equations).**
Examine the differentiability of $f(z) = \sqrt{\lvert xy \rvert}$ at the origin $z_0 = 0$.

*Solution:* Here $u(x, y) = \sqrt{\lvert xy \rvert}$ and $v(x, y) = 0$. Computing the first-order partial derivatives at $(0, 0)$ by definition:
$$
\begin{aligned}
u_x(0, 0) &= \lim_{\Delta x \to 0} \frac{u(\Delta x, 0) - u(0, 0)}{\Delta x} = \lim_{\Delta x \to 0} \frac{0 - 0}{\Delta x} = 0, \\
u_y(0, 0) &= \lim_{\Delta y \to 0} \frac{u(0, \Delta y) - u(0, 0)}{\Delta y} = \lim_{\Delta y \to 0} \frac{0 - 0}{\Delta y} = 0, \\
v_x(0, 0) &= 0, \qquad v_y(0, 0) = 0.
\end{aligned}
$$
Thus, $u_x = v_y = 0$ and $u_y = -v_x = 0$ at $(0, 0)$, so the Cauchy--Riemann equations are satisfied. However, evaluating the difference quotient along the straight line $y = kx$ as $x \to 0$ gives
$$
\lim_{\Delta z \to 0} \frac{f(z) - f(0)}{z - 0} = \lim_{x \to 0} \frac{\sqrt{\lvert kx^2 \rvert}}{x + ikx} = \lim_{x \to 0} \frac{\lvert x \rvert\sqrt{\lvert k \rvert}}{x(1 + ik)},
$$
which depends on the slope $k$ (and the sign of $x$). Therefore, $\lim_{\Delta z \to 0} \frac{\Delta f}{\Delta z}$ does not exist, and $f(z) = \sqrt{\lvert xy \rvert}$ is **not differentiable** at $z = 0$.

---

### 2.4 Necessary and Sufficient Condition for Differentiability

**Theorem 4 (Necessary and Sufficient Condition for Differentiability).**
A complex function $w = f(z) = u(x, y) + iv(x, y)$ defined in a domain $D$ is differentiable at $z = x + iy \in D$ if and only if:
1. $u(x, y)$ and $v(x, y)$ are **differentiable** (as real functions of two variables) at $(x, y)$; and
2. $u(x, y)$ and $v(x, y)$ satisfy the **Cauchy--Riemann equations** ($u_x = v_y$, $u_y = -v_x$) at $(x, y)$.

**Proof:**
Let $\Delta z = \Delta x + i\Delta y$, $\Delta w = \Delta u + i\Delta v$, $A = \alpha + i\beta$, and $o(\Delta z) = \varepsilon_1 + i\varepsilon_2$ (where $\varepsilon_1, \varepsilon_2 = o(\lvert \Delta z \rvert)$). By definition, $w = f(z)$ is differentiable at $z$ if and only if
$$
\Delta w = A\Delta z + o(\Delta z) \iff \Delta u + i\Delta v = (\alpha + i\beta)(\Delta x + i\Delta y) + \varepsilon_1 + i\varepsilon_2,
$$
which is equivalent to the real system
$$
\begin{cases}
    \Delta u = \alpha \Delta x - \beta \Delta y + \varepsilon_1, \\
    \Delta v = \beta \Delta x + \alpha \Delta y + \varepsilon_2,
\end{cases}
\qquad \text{with } \varepsilon_1, \varepsilon_2 = o\left(\sqrt{\Delta x^2 + \Delta y^2}\right).
$$
This holds if and only if $u(x, y)$ and $v(x, y)$ are real-differentiable at $(x, y)$ with partial derivatives $\alpha = u_x = v_y$ and $-\beta = u_y = -v_x$, i.e., $u$ and $v$ satisfy the Cauchy--Riemann equations at $(x, y)$, in which case $f'(z) = \alpha + i\beta = u_x + iv_x$. $\blacksquare$

**Corollary 1 (Sufficient Condition for Differentiability).**
If $u(x, y)$ and $v(x, y)$ have **continuous** first-order partial derivatives at $(x, y)$ and satisfy the Cauchy--Riemann equations there, then $f(z) = u(x, y) + iv(x, y)$ is differentiable at $z = x + iy$.