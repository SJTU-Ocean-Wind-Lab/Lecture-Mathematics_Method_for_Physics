# Mathematics Method for Physics -- Lecture 3
## Planar Point Sets, Extended Complex Plane, and Complex Functions

**Instructor:** Zhaolong Han, SOCE, Shanghai Jiao Tong University  
**Email:** han.arkey@sjtu.edu.cn  

---

## 1. Planar Point Sets and Domains

### 1.1 Neighborhood and Classification of Points

> **Definition 1 (Neighborhood)**  
> The point set determined by $|z - z_0| < \varepsilon$ ($\varepsilon > 0$) is called the $\varepsilon$-neighborhood of $z_0$, denoted as $N(z_0, \varepsilon)$. Geometrically, it represents an open disk centered at $z_0$ with radius $\varepsilon$ (excluding its boundary circle). The deleted neighborhood is defined by $0 < |z - z_0| < \varepsilon$ and denoted by $\mathring{N}(z_0, \varepsilon)$.

> **Definition 2 (Classification of Points)**  
> Let $E$ be a point set in the complex plane $\mathbb{C}$ and $z_0 \in \mathbb{C}$ be a point:
> * **Interior Point:** If $z_0 \in E$ and there exists a neighborhood $U = N(z_0, \varepsilon)$ such that $U \subset E$.
> * **Exterior Point:** If there exists a neighborhood $U = N(z_0, \varepsilon)$ such that $U \cap E = \emptyset$.
> * **Boundary Point:** If every neighborhood $U = N(z_0, \varepsilon)$ of $z_0$ contains both points belonging to $E$ and points not belonging to $E$. Boundary points may or may not belong to $E$.
>
> The set of all boundary points of $E$ is called the **boundary** of $E$, denoted by $\partial E$ or $\Gamma(E)$.

### 1.2 Open Sets, Closed Sets, and Domains

> **Definition 3 (Open Set, Closed Set, and Closure)**  
> For a point set $E \subset \mathbb{C}$, we define the following basic topological notions:
> * **Open Set:** A set $E$ in which all points are interior points.
> * **Closed Set:** A set $E$ whose complement $\mathbb{C} \setminus E$ is an open set (equivalently, $\partial E \subset E$).
> * **Closure ($\overline{E}$):** The union of $E$ and its boundary, $\overline{E} = E \cup \partial E$.
> * **Bounded Set:** A set $E$ that can be contained within a disk $\{z \mid |z| < R\}$ for some finite $R > 0$; otherwise, it is unbounded.

> **Definition 4 (Connected Set and Domain)**  
> Let $E$ and $D$ be point sets in the complex plane $\mathbb{C}$:
> * **Connected Set:** A set $E$ where any two points $A, B \in E$ can be connected by a polygonal line lying entirely within $E$.
> * **Domain (Region):** A non-empty, open, and connected point set $D$.
> * **Closed Domain ($\overline{D}$):** A domain $D$ plus its boundary, $\overline{D} = D \cup \partial D$.

> **Definition 5 (Simply Connected and Multiply Connected Domains)**  
> Let $D$ be a domain. If for every simple closed curve $C$ lying inside $D$, the entire interior of $C$ also belongs to $D$ (i.e., $\operatorname{Int}(C) \subset D$), then $D$ is called a **simply connected domain**. A domain that is not simply connected is called a **multiply connected domain**.

### 1.3 Positive Orientation of the Boundary
When traversing the boundary $\Gamma$ in the **positive direction**, the domain $D$ always remains on the **left-hand side**. For a multiply connected domain bounded externally by $C_0$ (counterclockwise) and internally by disjoint closed curves $C_1, \dots, C_n$ (clockwise, denoted $C_k^-$):
$$\Gamma = C_0 + C_1^- + C_2^- + \dots + C_n^-$$

### 1.4 Typical Examples from Lecture Notes
* **Example 1 (Textbook Example 1.12):** $\cos\theta < r < 2\cos\theta$ ($-\frac{\pi}{2} < \theta < \frac{\pi}{2}$) corresponds to $(x-1)^2 + y^2 < 1$ and $(x-\frac{1}{2})^2 + y^2 > \frac{1}{4}$. Bounded by two circles internally tangent at the origin, this crescent region is a **bounded, simply connected domain**.
* **Example 2 (Textbook Example 1.13):** $0 < \arg\frac{z-i}{z+i} < \frac{\pi}{4}$ corresponds to $x < 0$ and $(x+1)^2 + y^2 > 2$. Bounded by the imaginary axis rays ($x = 0, |y| > 1$) and a circular arc, this is an **unbounded, simply connected domain**.

---

## 2. Extended Complex Plane and the Point at Infinity

### 2.1 The Point at Infinity and Arithmetic Conventions

> **Definition 6 (Extended Complex Plane)**  
> The set $\mathbb{C}_\infty = \mathbb{C} \cup \{\infty\}$ is called the **extended complex plane**. For the symbol $\infty$, its modulus is defined as
> $$|\infty| = +\infty,$$
> whereas $\operatorname{Re}\infty$, $\operatorname{Im}\infty$, and $\operatorname{Arg}\infty$ are undefined.

For any finite complex number $a \in \mathbb{C}$:
1. $a \pm \infty = \infty \pm a = \infty$
2. $a \cdot \infty = \infty \cdot a = \infty \quad (a \neq 0)$
3. $\dfrac{a}{\infty} = 0, \quad \dfrac{a}{0} = \infty \quad (a \neq 0)$

Indeterminate expressions such as $\infty \pm \infty$, $0 \cdot \infty$, $\dfrac{\infty}{\infty}$, and $\dfrac{0}{0}$ have no meaning.

### 2.2 The Riemann Sphere and Stereographic Projection
* A sphere tangent to $\mathbb{C}$ at the origin $O$ (South Pole) establishes a bijection between $\mathbb{C}_\infty$ and the sphere via straight lines passing through the North Pole $N$, where $N$ corresponds to $\infty$.
* Every straight line in $\mathbb{C}$ corresponds to a circle through $N$ on the sphere (so every line in $\mathbb{C}_\infty$ passes through $\infty$), whereas no open half-plane contains $\infty$.

### 2.3 Topological Concepts in $\mathbb{C}_\infty$

> **Definition 7 (Neighborhood of $\infty$)**  
> In the extended complex plane $\mathbb{C}_\infty$, the $\varepsilon$-neighborhood of $\infty$ is defined as
> $$N(\infty, \varepsilon) = \left\{ z \in \mathbb{C}_\infty \;\middle|\; |z| > \frac{1}{\varepsilon} \right\} \quad (\text{or } \{|z| > R\}).$$

* **Boundary Orientation:** For the exterior domain $\{|z| > R\}$, the positively oriented boundary is the clockwise circle $\Gamma^- = \{|z| = R\}^-$.
* **Simply Connectedness:** In $\mathbb{C}_\infty$, a simple closed curve can shrink continuously to $\infty$ by expanding into $\{|z| > R\}$. Hence, $\{|z| > 1\}$ is **simply connected** in $\mathbb{C}_\infty$, whereas $\{1 < |z| < +\infty\}$ is **multiply connected**.

---

## 3. Functions of a Complex Variable

### 3.1 Concept of Complex Functions and Geometric Mappings

> **Definition 8 (Complex Function)**  
> Let $D$ be a point set in the complex plane $\mathbb{C}$. If for every complex number $z \in D$, there corresponds one or more complex numbers $w$ according to a rule $f$, then $w$ is called a **function of a complex variable** defined on $D$, denoted by $w = f(z) = u(x,y) + iv(x,y)$.

* **Mappings vs. Graphs:** Unlike 1D real functions $y = f(x)$ plotted in $\mathbb{R}^2$, a complex function involves four real dimensions $(x,y,u,v)$ and is visualized as a **mapping** from $D$ in the $z$-plane to $G$ in the $w$-plane (injective, surjective, or bijective).
* **Example 3 ($w = z^2$):** With $z = re^{i\theta}$ and $w = \rho e^{i\varphi}$, we have $u = x^2 - y^2$, $v = 2xy$, $\rho = r^2$, and $\varphi = 2\theta + 2k\pi$:
  * Maps the real axis ($y=0$) onto $[0, +\infty)$ (covered twice) and the imaginary axis ($x=0$) onto $(-\infty, 0]$.
  * Maps the angular sector $0 < \arg z < \alpha$ onto $0 < \arg w < 2\alpha$ (e.g., the first quadrant maps onto the upper half-plane).

### 3.2 Elementary Complex Functions (Five Major Categories)

#### 1. Exponential Function

> **Definition 9 (Complex Exponential Function)**  
> For any complex number $z = x + iy$, the exponential function is defined by
> $$w = e^z = \exp(z) = e^{x+iy} = e^x(\cos y + i\sin y).$$

* **Modulus & Argument:** $|e^z| = e^x > 0$ ($e^z \neq 0$), $\operatorname{Arg} e^z = y + 2k\pi$.
* **Conjugate & Addition:** $\overline{e^z} = e^{\overline{z}}$, and $e^{z_1} \cdot e^{z_2} = e^{z_1 + z_2}$.
* **Periodicity:** Periodic with fundamental period $T = 2\pi i$ ($e^{z + 2k\pi i} = e^z$).
* **Analyticity:** Entire on $\mathbb{C}$ with $(e^z)' = e^z$; $\lim_{z\to\infty} e^z$ does not exist.

#### 2. Logarithmic Function

> **Definition 10 (Complex Logarithmic Function)**  
> For $z \neq 0, \infty$, any complex number $w$ satisfying $e^w = z$ is called the logarithm of $z$, denoted by
> $$w = \operatorname{Ln} z = \ln|z| + i\operatorname{Arg} z = \ln z + 2k\pi i \quad (k = 0, \pm 1, \pm 2, \dots).$$

* **Principal Value:** $\ln z = \ln|z| + i\arg z$ ($-\pi < \arg z \le \pi$).
* **Example:** $\operatorname{Ln}(-1) = (2k+1)\pi i$, with principal value $\ln(-1) = \pi i$.
* **Properties:** $\operatorname{Ln}(z_1 z_2) = \operatorname{Ln} z_1 + \operatorname{Ln} z_2$ and $\operatorname{Ln}(z_1/z_2) = \operatorname{Ln} z_1 - \operatorname{Ln} z_2$ hold as set equalities, whereas $\ln(z_1 z_2) = \ln z_1 + \ln z_2$ **does not always hold** for principal values.
* **Analyticity:** Each branch is analytic on $\mathbb{C} \setminus (-\infty, 0]$ with $(\operatorname{Ln} z)' = \frac{1}{z}$.

#### 3. Power Function and General Exponential Function

> **Definition 11 (Complex Power Function)**  
> For any complex exponent $a \in \mathbb{C}$ and $z \neq 0$, the power function is defined by
> $$w = z^a = e^{a \operatorname{Ln} z} = e^{a \ln z} \cdot e^{2k\pi a i} \quad (k \in \mathbb{Z}), \qquad a^z = e^{z \operatorname{Ln} a}.$$

* **Special Cases:**
  * $a = n \in \mathbb{Z}^+$: $z^n = r^n e^{in\theta}$ (single-valued, entire).
  * $a = \frac{1}{n}$ ($n \in \mathbb{Z}^+$): $z^{1/n} = \sqrt[n]{r} e^{i\frac{\theta + 2k\pi}{n}}$ ($k = 0, 1, \dots, n-1$, $n$-valued).
  * $a = \frac{m}{n}$ (reduced fraction): $n$-valued; irrational or non-real complex $a$: infinitely many-valued.
* **Example 4:** $i^i = e^{i \operatorname{Ln} i} = e^{-\frac{\pi}{2} - 2k\pi}$ ($k \in \mathbb{Z}$), yielding infinitely many positive real values.

#### 4. Trigonometric and Hyperbolic Functions

> **Definition 12 (Complex Trigonometric Functions)**  
> Extending Euler's formula $e^{ix} = \cos x + i\sin x$ ($x \in \mathbb{R}$) to $z \in \mathbb{C}$, the sine and cosine functions are defined as
> $$\sin z = \frac{e^{iz} - e^{-iz}}{2i}, \quad \cos z = \frac{e^{iz} + e^{-iz}}{2}, \quad \tan z = \frac{\sin z}{\cos z}, \quad \cot z = \frac{\cos z}{\sin z}.$$

* Entire on $\mathbb{C}$ (for $\sin z, \cos z$), $2\pi$-periodic, satisfy Euler's formula $e^{iz} = \cos z + i\sin z$ and real trig identities, and have only real zeros ($\sin z = 0 \iff z = k\pi$; $\cos z = 0 \iff z = k\pi + \frac{\pi}{2}$).
* **Key Difference:** $|\sin z|$ and $|\cos z|$ are **unbounded** in $\mathbb{C}$.

> **Definition 13 (Complex Hyperbolic Functions)**  
> The hyperbolic sine, cosine, and tangent functions are defined for $z \in \mathbb{C}$ by
> $$\sinh z = \frac{e^z - e^{-z}}{2}, \quad \cosh z = \frac{e^z + e^{-z}}{2}, \quad \tanh z = \frac{\sinh z}{\cosh z}.$$

* Related via $\sinh z = -i\sin(iz)$, $\cosh z = \cos(iz)$, and $\cosh^2 z - \sinh^2 z = 1$.

#### 5. Inverse Trigonometric and Inverse Hyperbolic Functions
All are infinitely many-valued functions:
* $\operatorname{Arcsin} z = -i\operatorname{Ln}(iz \pm \sqrt{1 - z^2})$, $\quad \operatorname{Arccos} z = -i\operatorname{Ln}(z \pm \sqrt{z^2 - 1})$
* $\operatorname{Arctan} z = -\frac{i}{2}\operatorname{Ln}\frac{1 + iz}{1 - iz}$ ($z \neq \pm i$), $\quad \operatorname{Arccot} z = \frac{i}{2}\operatorname{Ln}\frac{z - i}{z + i}$ ($z \neq \pm i$)
* $\operatorname{Arcsinh} z = \operatorname{Ln}(z \pm \sqrt{z^2 + 1})$, $\quad \operatorname{Arccosh} z = \operatorname{Ln}(z \pm \sqrt{z^2 - 1})$

---

## Assigned Homework Reference
* **Textbook P.20 (Exercise 1):** Set A: Problems 8 (even), 9, 12; Set B: Problems 5, 6.
* **Textbook P.55 (Exercise 2):** Set A: Problem 13 (even).