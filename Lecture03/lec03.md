# Mathematics Method for Physics -- Lecture 3

## Functions of a Complex Variable and Elementary Complex Functions

**Instructor:** Zhaolong Han, SOCE, Shanghai Jiao Tong University

**Email:** han.arkey@sjtu.edu.cn

## 1. Functions of a Complex Variable

### 1.1 Concept of Complex Functions and Geometric Mappings

> **Definition 1 (Complex Function)**
>
> Let $D$ be a point set in the complex plane $\mathbb{C}$. If for every complex number $z \in D$, there corresponds one or more complex numbers $w$ according to a rule $f$, then $w$ is called a **function of a complex variable** defined on $D$, denoted by $w = f(z) = u(x,y) + iv(x,y)$.

* **Single-valued vs. Multi-valued Functions:** If each $z \in D$ corresponds to a unique value $w$, $f(z)$ is called *single-valued* (e.g., $w = z^2$, $w = \vert{}z\vert{}$); if $z$ corresponds to two or more values, $f(z)$ is called *multi-valued* (e.g., $w = \operatorname{Arg} z$, $w = \sqrt[n]{z}$).

* **Inverse Function:** If for each $w \in G$ there exist one or more points $z \in D$ satisfying $w = f(z)$, this correspondence defines the inverse function $z = g(w) = f^{-1}(w)$.

* **Mappings vs. Graphs:** Unlike 1D real functions $y = f(x)$ plotted in $\mathbb{R}^2$, a complex function involves four real dimensions $(x,y,u,v)$ and is visualized as a **mapping** from $D$ in the $z$-plane to $G$ in the $w$-plane (injective, surjective, or bijective).

* **Example 1 ($w = z^2$):** With $z = re^{i\theta}$ and $w = \rho e^{i\varphi}$, we have $u = x^2 - y^2$, $v = 2xy$, $\rho = r^2$, and $\varphi = 2\theta + 2k\pi$:

  * Maps the real axis ($y=0$) onto $[0, +\infty)$ (covered twice, see Figure 1) and the imaginary axis ($x=0$) onto $(-\infty, 0]$.

  * Maps the angular sector $0 < \arg z < \alpha$ onto $0 < \arg w < 2\alpha$ (see Figure 2; e.g., the first quadrant maps onto the upper half-plane).

### 1.2 Elementary Complex Functions (Five Major Categories)

#### 1. Exponential Function

> **Definition 2 (Complex Exponential Function)**
>
> For any complex number $z = x + iy$, the exponential function is defined by
>
> $$
> w = e^z = \exp(z) = e^{x+iy} = e^x(\cos y + i\sin y).
> $$

* **Modulus & Argument:** $\vert{}e^z\vert{} = e^x > 0$ ($e^z \neq 0$), $\operatorname{Arg} e^z = y + 2k\pi$.

* **Conjugate & Addition:** $\overline{e^z} = e^{\overline{z}}$, and $e^{z_1} \cdot e^{z_2} = e^{z_1 + z_2}$.

* **Periodicity:** Periodic with fundamental period $T = 2\pi i$ ($e^{z + 2k\pi i} = e^z$).

* **Analyticity:** Entire on $\mathbb{C}$ with $(e^z)' = e^z$; $\lim_{z\to\infty} e^z$ does not exist.

#### 2. Logarithmic Function

> **Definition 3 (Complex Logarithmic Function)**
>
> For $z \neq 0, \infty$, any complex number $w$ satisfying $e^w = z$ is called the logarithm of $z$, denoted by
>
> $$
> w = \operatorname{Ln} z = \ln\vert{}z\vert{} + i\operatorname{Arg} z = \ln z + 2k\pi i \quad (k = 0, \pm 1, \pm 2, \dots).
> $$

* **Principal Value:** $\ln z = \ln\vert{}z\vert{} + i\arg z$ ($-\pi < \arg z \le \pi$).

* **Example:** $\operatorname{Ln}(-1) = (2k+1)\pi i$, with principal value $\ln(-1) = \pi i$.

* **Properties:** $\operatorname{Ln}(z_1 z_2) = \operatorname{Ln} z_1 + \operatorname{Ln} z_2$ and $\operatorname{Ln}(z_1/z_2) = \operatorname{Ln} z_1 - \operatorname{Ln} z_2$ hold as set equalities, whereas $\ln(z_1 z_2) = \ln z_1 + \ln z_2$ **does not always hold** for principal values.

* **Analyticity:** Each branch is analytic on $\mathbb{C} \setminus (-\infty, 0]$ with $(\operatorname{Ln} z)' = \frac{1}{z}$.

#### 3. Power Function and General Exponential Function

> **Definition 4 (Complex Power Function)**
>
> For any complex exponent $a \in \mathbb{C}$ and $z \neq 0$, the power function is defined by
>
> $$
> w = z^a = e^{a \operatorname{Ln} z} = e^{a \ln z} \cdot e^{2k\pi a i} \quad (k \in \mathbb{Z}), \qquad a^z = e^{z \operatorname{Ln} a}.
> $$

* **Special Cases:**

  * $a = n \in \mathbb{Z}^+$: $z^n = r^n e^{in\theta}$ (single-valued, entire).

  * $a = \frac{1}{n}$ ($n \in \mathbb{Z}^+$): $z^{1/n} = \sqrt[n]{r} e^{i\frac{\theta + 2k\pi}{n}}$ ($k = 0, 1, \dots, n-1$, $n$-valued).

  * $a = \frac{m}{n}$ (reduced fraction): $n$-valued; irrational or non-real complex $a$: infinitely many-valued.

* **Example 2:** $i^i = e^{i \operatorname{Ln} i} = e^{-\frac{\pi}{2} - 2k\pi}$ ($k \in \mathbb{Z}$), yielding infinitely many positive real values.

#### 4. Trigonometric and Hyperbolic Functions

> **Definition 5 (Complex Trigonometric Functions)**
>
> Extending Euler's formula $e^{ix} = \cos x + i\sin x$ ($x \in \mathbb{R}$) to $z \in \mathbb{C}$, the sine and cosine functions are defined as
>
> $$
> \sin z = \frac{e^{iz} - e^{-iz}}{2i}, \quad \cos z = \frac{e^{iz} + e^{-iz}}{2}, \quad \tan z = \frac{\sin z}{\cos z}, \quad \cot z = \frac{\cos z}{\sin z}.
> $$

* Entire on $\mathbb{C}$ (for $\sin z, \cos z$), $2\pi$-periodic, satisfy Euler's formula $e^{iz} = \cos z + i\sin z$ and real trig identities, and have only real zeros ($\sin z = 0 \iff z = k\pi$; $\cos z = 0 \iff z = k\pi + \frac{\pi}{2}$).

* **Key Difference:** $\vert{}\sin z\vert{}$ and $\vert{}\cos z\vert{}$ are **unbounded** in $\mathbb{C}$.

> **Definition 6 (Complex Hyperbolic Functions)**
>
> The hyperbolic sine, cosine, and tangent functions are defined for $z \in \mathbb{C}$ by
>
> $$
> \sinh z = \frac{e^z - e^{-z}}{2}, \quad \cosh z = \frac{e^z + e^{-z}}{2}, \quad \tanh z = \frac{\sinh z}{\cosh z}.
> $$

* Related via $\sinh z = -i\sin(iz)$, $\cosh z = \cos(iz)$, and $\cosh^2 z - \sinh^2 z = 1$.

#### 5. Inverse Trigonometric and Inverse Hyperbolic Functions

All are infinitely many-valued functions:

* $\operatorname{Arcsin} z = -i\operatorname{Ln}(iz \pm \sqrt{1 - z^2})$, $\quad \operatorname{Arccos} z = -i\operatorname{Ln}(z \pm \sqrt{z^2 - 1})$

* $\operatorname{Arctan} z = -\frac{i}{2}\operatorname{Ln}\frac{1 + iz}{1 - iz}$ ($z \neq \pm i$), $\quad \operatorname{Arccot} z = \frac{i}{2}\operatorname{Ln}\frac{z - i}{z + i}$ ($z \neq \pm i$)

* $\operatorname{Arcsinh} z = \operatorname{Ln}(z \pm \sqrt{z^2 + 1})$, $\quad \operatorname{Arccosh} z = \operatorname{Ln}(z \pm \sqrt{z^2 - 1})$

## Assigned Homework Reference

* **Textbook P.20 (Exercise 1):** Set A: Problems 8 (even), 9, 12; \quad Set B: Problems 5, 6.

* **Textbook P.55 (Exercise 2):** Set A: Problem 13 (even).