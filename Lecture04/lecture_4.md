# Mathematics Method for Physics -- Lecture 04
## Trigonometric/Inverse Trigonometric Functions, Limits, Continuity, and Differentiability

**Instructor:** Zhaolong Han, SOCE, Shanghai Jiao Tong University  
**Email:** han.arkey@sjtu.edu.cn  

---

## 1. Elementary Complex Functions (Continued)

### 1.1 Trigonometric Functions

**Definition 1 (Complex Sine and Cosine Functions).**  
Extending Euler's formula $e^{ix} = \cos x + i\sin x$ ($x \in \mathbb{R}$) to $z \in \mathbb{C}$:
$$\sin z = \frac{e^{iz} - e^{-iz}}{2i}, \qquad \cos z = \frac{e^{iz} + e^{-iz}}{2}$$
$$\tan z = \frac{\sin z}{\cos z}, \quad \cot z = \frac{\cos z}{\sin z}, \quad \sec z = \frac{1}{\cos z}, \quad \csc z = \frac{1}{\sin z}$$

**Key Properties:**
1. **Periodicity and Parity:** $\sin z$ and $\cos z$ are $2\pi$-periodic; $\sin(-z) = -\sin z$ (odd) and $\cos(-z) = \cos z$ (even).
2. **Trigonometric Identities:** Euler's formula $e^{iz} = \cos z + i\sin z$, $\sin^2 z + \cos^2 z = 1$, and sum/difference formulas remain valid for all $z \in \mathbb{C}$.
3. **Zeros:** All zeros lie on the real axis: $\sin z = 0 \iff z = k\pi$ and $\cos z = 0 \iff z = k\pi + \frac{\pi}{2}$ ($k \in \mathbb{Z}$).
4. **Failure of Boundedness:** Unlike real sine and cosine, $|\sin z| \le 1$ and $|\cos z| \le 1$ **no longer hold** in $\mathbb{C}$ (e.g., $|\cos(iy)| = \cosh y \to +\infty$ as $|y| \to \infty$).

**Example 1 (Solving $\sin z = 2$).**  
$$\sin z = \frac{e^{iz} - e^{-iz}}{2i} = 2 \implies (e^{iz})^2 - 4i(e^{iz}) - 1 = 0$$
Using the quadratic formula ($a = 1, b = -4i, c = -1$):
$$e^{iz} = \frac{4i \pm \sqrt{(-4i)^2 - 4(-1)}}{2} = \frac{4i \pm \sqrt{-12}}{2} = (2 \pm \sqrt{3})i$$
Taking the complex logarithm:
$$iz = \operatorname{Ln}\bigl[(2 \pm \sqrt{3})i\bigr] = \ln(2 \pm \sqrt{3}) + i\left(\frac{\pi}{2} + 2k\pi\right)$$
$$z = \frac{\pi}{2} + 2k\pi - i\ln(2 \pm \sqrt{3}) = \frac{\pi}{2} + 2k\pi \mp i\ln(2 + \sqrt{3}) \quad (k = 0, \pm 1, \pm 2, \dots)$$

### 1.2 Inverse Trigonometric Functions

**Definition 2 (Inverse Trigonometric Functions).**  
Defined as the inverse relations of the complex trigonometric functions, all are infinitely many-valued:
* $w = \operatorname{Arcsin} z = -i\operatorname{Ln}\left(iz \pm \sqrt{1 - z^2}\right)$
* $w = \operatorname{Arccos} z = -i\operatorname{Ln}\left(z \pm \sqrt{z^2 - 1}\right)$
* $w = \operatorname{Arctan} z = -\dfrac{i}{2}\operatorname{Ln}\dfrac{1 + iz}{1 - iz} \quad (z \neq \pm i)$
* $w = \operatorname{Arccot} z = \dfrac{i}{2}\operatorname{Ln}\dfrac{z - i}{z + i} \quad (z \neq \pm i)$

---

## 2. Limits and Continuity of Complex Functions

### 2.1 Limit of a Complex Function

**Definition 3 (Limit at a Point).**  
Let $w = f(z)$ be defined in a deleted neighborhood of $z_0$, and let $A \in \mathbb{C}$. We write $\lim_{z \to z_0} f(z) = A$ if $\forall \varepsilon > 0$, $\exists \delta > 0$ such that whenever $0 < |z - z_0| < \delta$, $|f(z) - A| < \varepsilon$.

* **Geometric Meaning:** Unlike 1D real limits ($x \to x_0^+$ or $x \to x_0^-$), $z \to z_0$ in $\mathbb{C}$ means $(x, y) \to (x_0, y_0)$ along **infinitely many arbitrary paths** in the plane.
* **Theorem 1 (Reduction to Real Limits):** For $z = x + iy$, $z_0 = x_0 + iy_0$, $f(z) = u(x,y) + iv(x,y)$, and $A = a + bi$:
  $$\lim_{z \to z_0} f(z) = A \iff \lim_{(x,y) \to (x_0,y_0)} u(x,y) = a \quad \text{and} \quad \lim_{(x,y) \to (x_0,y_0)} v(x,y) = b$$
* **Algebraic Rules:** Sum, difference, product, and quotient (with non-zero denominator) rules hold just as in real calculus.

### 2.2 Continuity of a Complex Function

**Definition 4 (Continuity).**  
Let $w = f(z)$ be a complex function defined in a neighborhood of $z_0$ or a domain $D$:
1. **Pointwise Continuity:** $f(z)$ is continuous at $z_0 \iff \lim_{z \to z_0} f(z) = f(z_0)$.
2. **Domain Continuity:** $f(z)$ is continuous in a domain $D$ if it is continuous at every point of $D$.

**Theorem 2 (Continuity via Real and Imaginary Parts).**  
$f(z) = u(x,y) + iv(x,y)$ is continuous at $z_0 = x_0 + iy_0 \iff u(x,y)$ and $v(x,y)$ are both continuous at $(x_0, y_0)$.

**Example 2 (Continuity of $w = \arg z$).**  
For $z = x + iy \neq 0$, $\arg z \in (-\pi, \pi]$ is given by:
$$\arg z = \begin{cases} \arctan\dfrac{y}{x}, & x > 0, \\ \pi + \arctan\dfrac{y}{x}, & x < 0, \, y \ge 0, \\ -\pi + \arctan\dfrac{y}{x}, & x < 0, \, y < 0, \\ \pm\dfrac{\pi}{2}, & x = 0, \, y \gtrless 0. \end{cases}$$
* At $z = 0$, $\arg z$ is undefined (hence discontinuous).
* For any point $x_0 < 0$ on the negative real axis:
  $$\lim_{\substack{z \to x_0 \\ \operatorname{Im} z > 0}} \arg z = \pi, \qquad \lim_{\substack{z \to x_0 \\ \operatorname{Im} z < 0}} \arg z = -\pi$$
* Because these limits differ, $\lim_{z \to x_0} \arg z$ does not exist. Thus, $\arg z$ is continuous everywhere on the **slit complex plane** $\mathbb{C} \setminus (-\infty, 0]$.

---

## 3. Differentiability and Cauchy--Riemann Conditions

### 3.1 Derivative and Differential

**Definition 5 (Derivative of a Complex Function).**  
Let $w = f(z)$ be defined in a neighborhood of $z_0$. If the limit below exists, $f(z)$ is differentiable at $z_0$ with derivative:
$$f'(z_0) = \lim_{\Delta z \to 0} \frac{f(z_0 + \Delta z) - f(z_0)}{\Delta z} = \lim_{z \to z_0} \frac{f(z) - f(z_0)}{z - z_0}$$

**Definition 6 (Differential of a Complex Function).**  
$f(z)$ is differentiable at $z_0 \iff \Delta f(z_0) = A\Delta z + o(\Delta z)$ where $\lim_{\Delta z \to 0} \frac{o(\Delta z)}{\Delta z} = 0$. Here $A = f'(z_0)$, and $df = f'(z_0)\Delta z = f'(z_0)dz$.

* Differentiability at $z_0$ implies continuity at $z_0$ (converse is false). Standard differentiation rules (product, quotient, chain rule, inverse rule) apply.

### 3.2 Necessary Condition: Cauchy--Riemann (C--R) Equations

**Theorem 3 (Necessary Condition for Differentiability).**  
If $f(z) = u(x,y) + iv(x,y)$ is differentiable at $z_0 = x_0 + iy_0$, then $u_x, u_y, v_x, v_y$ exist at $(x_0, y_0)$ and satisfy the **Cauchy--Riemann equations**:
$$\begin{cases} u_x = v_y, \\ u_y = -v_x, \end{cases} \qquad f'(z_0) = \frac{\partial u}{\partial x} + i\frac{\partial v}{\partial x} = \frac{\partial v}{\partial y} - i\frac{\partial u}{\partial y}$$

**Proof Outline:**
1. Along the horizontal path ($\Delta y = 0, \Delta x \to 0$): $f'(z_0) = \lim_{\Delta x \to 0} \frac{\Delta u + i\Delta v}{\Delta x} = u_x + iv_x$.
2. Along the vertical path ($\Delta x = 0, \Delta y \to 0$): $f'(z_0) = \lim_{\Delta y \to 0} \frac{\Delta u + i\Delta v}{i\Delta y} = v_y - iu_y$.
3. Equating real and imaginary parts yields $u_x = v_y$ and $u_y = -v_x$.

*(Polar form: $u_r = \frac{1}{r} v_\theta$, $v_r = -\frac{1}{r} u_\theta$.)*

### 3.3 Counterexample: C--R Equations Alone Are Not Sufficient

**Example 3 (Non-differentiable Function Satisfying C--R Equations).**  
Consider $f(z) = \sqrt{|xy|}$ at $z_0 = (0,0)$, where $u(x,y) = \sqrt{|xy|}$ and $v(x,y) = 0$:
* Partial derivatives at $(0,0)$: $u_x(0,0) = u_y(0,0) = v_x(0,0) = v_y(0,0) = 0$, so the C--R equations hold at $(0,0)$.
* However, along $y = kx$ as $x \to 0$:
  $$\lim_{z \to 0} \frac{f(z) - f(0)}{z - 0} = \lim_{x \to 0} \frac{|x|\sqrt{|k|}}{x(1 + ik)}$$
  which depends on $k$ (and the sign of $x$). Thus $\lim_{\Delta z \to 0} \frac{\Delta f}{\Delta z}$ does not exist, and $f(z)$ is **not differentiable** at $z = 0$.

### 3.4 Necessary and Sufficient Condition for Differentiability

**Theorem 4 (Necessary and Sufficient Condition for Differentiability).**  
A complex function $w = f(z) = u(x,y) + iv(x,y)$ defined in a domain $D$ is differentiable at $z = x + iy \in D$ **if and only if**:
1. $u(x,y)$ and $v(x,y)$ are **differentiable** (as real two-variable functions) at $(x,y)$; and
2. $u(x,y)$ and $v(x,y)$ satisfy the **Cauchy--Riemann equations** ($u_x = v_y$, $u_y = -v_x$) at $(x,y)$.

**Corollary 1 (Sufficient Condition).**  
If $u(x,y)$ and $v(x,y)$ have **continuous** first-order partial derivatives at $(x,y)$ and satisfy the C--R equations there, then $f(z)$ is differentiable at $z = x + iy$.

---

## Assigned Homework Reference
* **Textbook P.53 (Exercise 2):** Set A: Problems 1 (even), 2, 3, 4, 13 (even), 15.