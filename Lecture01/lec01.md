# Chapter 1: Complex Numbers and the Complex Plane

## 1. Fundamentals and Representations of Complex Numbers

### 1.1 Algebraic (Cartesian) Form

A **complex number** $z$ is defined as an ordered pair of real numbers $(x, y) \in \mathbb{R}^2$, expressed in the algebraic form:

$$
z \coloneqq x + \mathrm{i} y, \quad x, y \in \mathbb{R} \tag{1}
$$

where:

* $\mathrm{i}$ denotes the imaginary unit defined by $\mathrm{i}^2 \coloneqq -1$.

* $x \coloneqq \operatorname{Re}(z)$ is the **real part** of $z$.

* $y \coloneqq \operatorname{Im}(z)$ is the **imaginary part** of $z$.

#### Geometric Correspondence (The Complex Plane / Argand Plane)

There exists a canonical bijective correspondence among three entities:

1. The complex number $z = x + \mathrm{i} y \in \mathbb{C}$.

2. The point $P(x, y)$ in the Cartesian plane $\mathbb{R}^2$.

3. The position vector $\vec{OP} \coloneqq \begin{bmatrix} x \\ y \end{bmatrix} \in \mathbb{R}^2$.

The horizontal axis represents the **real axis** ($\operatorname{Re}$), and the vertical axis represents the **imaginary axis** ($\operatorname{Im}$).

### 1.2 Polar Form, Euler's Formula, and Exponential Representation

#### Polar Coordinates and Polar Form

Transforming the Cartesian coordinates $(x, y)$ into plane polar coordinates $(r, \theta)$ via:

$$
\begin{cases} x = r \cos\theta \\ y = r \sin\theta \end{cases} \tag{2}
$$

allows $z$ to be written in **trigonometric (polar) form**:

$$
z = r(\cos\theta + \mathrm{i}\sin\theta) \tag{3}
$$

#### Modulus (Absolute Value)

The **modulus** $r \coloneqq \vert{}z\vert{}$ represents the Euclidean distance from the origin to $P(x, y)$:

$$
\vert{}z\vert{} \coloneqq \sqrt{x^2 + y^2} \ge 0 \tag{4}
$$

#### Argument and Principal Argument

The angle $\theta$ is defined as an **argument** of $z$, denoted by $\operatorname{Arg}(z)$. Since the trigonometric functions are $2\mathrm{\pi}$-periodic, $\operatorname{Arg}(z)$ is a multi-valued set:

$$
\operatorname{Arg}(z) \coloneqq \arg(z) + 2k\mathrm{\pi}, \quad k \in \mathbb{Z} \tag{5}
$$

The unique representative in the interval $(-\mathrm{\pi}, \mathrm{\pi}]$ is defined as the **principal argument**, denoted by $\arg(z) \in (-\mathrm{\pi}, \mathrm{\pi}]$:

$$
\arg(z) \coloneqq \begin{cases}  \arctan\left(\frac{y}{x}\right), & x > 0 \\  \arctan\left(\frac{y}{x}\right) + \mathrm{\pi}, & x < 0, \, y \ge 0 \\  \arctan\left(\frac{y}{x}\right) - \mathrm{\pi}, & x < 0, \, y < 0 \\  \frac{\mathrm{\pi}}{2}, & x = 0, \, y > 0 \\  -\frac{\mathrm{\pi}}{2}, & x = 0, \, y < 0  \end{cases} \tag{6}
$$

*(For* $z = 0$*, the modulus is* $\vert{}0\vert{} = 0$*, and the argument* $\operatorname{Arg}(0)$ *is undefined.)*

#### Physical Meaning and Introduction of the Exponential Form

In physics and engineering (such as wave mechanics, alternating-current circuits, and quantum mechanics), complex exponentials are the natural language for describing **rotation**, **phase**, and **harmonic oscillation (phasors)**:

* **Rotation Operator:** The factor $\mathrm{e}^{\mathrm{i}\theta}$ acts as a unit rotator ($\vert{}\mathrm{e}^{\mathrm{i}\theta}\vert{} = 1$). Multiplying any vector by $\mathrm{e}^{\mathrm{i}\theta}$ preserves its magnitude while rotating it counterclockwise by an angle $\theta$.

* **Harmonic Motion:** When the phase evolves uniformly with time, $\theta(t) = \omega t$, the term $\mathrm{e}^{\mathrm{i}\omega t}$ describes uniform circular motion on the complex plane. Its projection onto the real axis yields the standard harmonic oscillator $\cos(\omega t)$.

This bridge between circular rotation and trigonometry is codified as **Euler's Formula**:

$$
\mathrm{e}^{\mathrm{i}\theta} \coloneqq \cos\theta + \mathrm{i}\sin\theta \tag{7}
$$

Substituting Euler's formula into the polar representation yields the **exponential form** of a complex number:

$$
z \coloneqq r \mathrm{e}^{\mathrm{i}\theta} \tag{8}
$$

where $r = \vert{}z\vert{}$ represents the **amplitude** (magnitude) and $\theta$ represents the **phase** (orientation).

## 2. Operations and Geometric Transformations

### 2.1 Addition and Subtraction

For $z_1 = x_1 + \mathrm{i} y_1$ and $z_2 = x_2 + \mathrm{i} y_2$:

$$
z_1 \pm z_2 \coloneqq (x_1 \pm x_2) + \mathrm{i}(y_1 \pm y_2) \tag{9}
$$

**Geometric Meaning:** Addition and subtraction correspond to vector addition and subtraction of $\begin{bmatrix} x_1 \\ y_1 \end{bmatrix}$ and $\begin{bmatrix} x_2 \\ y_2 \end{bmatrix}$ according to the parallelogram law or triangle rule.

### 2.2 Complex Conjugation

The **complex conjugate** of $z = x + \mathrm{i} y = r \mathrm{e}^{\mathrm{i}\theta}$ is defined by:

$$
\bar{z} \coloneqq x - \mathrm{i} y = r \mathrm{e}^{-\mathrm{i}\theta} \tag{10}
$$

Fundamental properties:

* $\overline{z_1 \pm z_2} = \bar{z}_1 \pm \bar{z}_2$

* $\overline{z_1 z_2} = \bar{z}_1 \bar{z}_2$

* $z \bar{z} = \vert{}z\vert{}^2 = x^2 + y^2$

* $\operatorname{Re}(z) = \frac{z + \bar{z}}{2}, \quad \operatorname{Im}(z) = \frac{z - \bar{z}}{2\mathrm{i}}$

### 2.3 Multiplication and Division

Let $z_1 = r_1 \mathrm{e}^{\mathrm{i}\theta_1}$ and $z_2 = r_2 \mathrm{e}^{\mathrm{i}\theta_2}$.

#### Multiplication:

$$
z_1 z_2 = (r_1 r_2) \mathrm{e}^{\mathrm{i}(\theta_1 + \theta_2)} \tag{11}
$$

* **Modulus:** $\vert{}z_1 z_2\vert{} = \vert{}z_1\vert{} \vert{}z_2\vert{}$

* **Argument:** $\operatorname{Arg}(z_1 z_2) = \operatorname{Arg}(z_1) + \operatorname{Arg}(z_2) \pmod{2\mathrm{\pi}}$

**Geometric Meaning:** Multiplying a vector $z$ by $z_1 = r_1 \mathrm{e}^{\mathrm{i}\theta_1}$ dilates its length by factor $r_1$ and rotates it counterclockwise by an angle of $\theta_1$.

#### Division:

$$
\frac{z_1}{z_2} \coloneqq \frac{z_1 \bar{z}_2}{\vert{}z_2\vert{}^2} = \left(\frac{r_1}{r_2}\right) \mathrm{e}^{\mathrm{i}(\theta_1 - \theta_2)}, \quad (z_2 \ne 0) \tag{12}
$$

* **Modulus:** $\left\vert{}\frac{z_1}{z_2}\right\vert{} = \frac{\vert{}z_1\vert{}}{\vert{}z_2\vert{}}$

* **Argument:** $\operatorname{Arg}\left(\frac{z_1}{z_2}\right) = \operatorname{Arg}(z_1) - \operatorname{Arg}(z_2) \pmod{2\mathrm{\pi}}$

#### Example: Division by $\mathrm{i}$

$$
\frac{z}{\mathrm{i}} = \frac{z(-\mathrm{i})}{\mathrm{i}(-\mathrm{i})} = -\mathrm{i} z = z \cdot \mathrm{e}^{-\mathrm{i}\frac{\mathrm{\pi}}{2}} \tag{13}
$$

**Geometric Meaning:** Multiplying by $-\mathrm{i}$ (or dividing by $\mathrm{i}$) rotates the vector clockwise by $\frac{\mathrm{\pi}}{2}$.

### 2.4 Powers, Binomial Expansion, and de Moivre’s Theorem

For any positive integer $n \in \mathbb{N}^+$:

$$
z^n = (r \mathrm{e}^{\mathrm{i}\theta})^n = r^n \mathrm{e}^{\mathrm{i} n\theta} = r^n (\cos(n\theta) + \mathrm{i}\sin(n\theta)) \tag{14}
$$

Setting $r = 1$ gives **de Moivre’s Theorem**:

$$
(\cos\theta + \mathrm{i}\sin\theta)^n = \cos(n\theta) + \mathrm{i}\sin(n\theta) \tag{15}
$$

In Cartesian form, $z^n$ can be expanded using the binomial theorem:

$$
z^n = (x + \mathrm{i} y)^n = \sum_{k=0}^n \binom{n}{k} x^{n-k} (\mathrm{i} y)^k \tag{16}
$$

where the **binomial coefficient** $\binom{n}{k}$ is defined by:

$$
\binom{n}{k} \coloneqq \frac{n!}{k!(n-k)!} = \frac{n(n-1)\cdots(n-k+1)}{k!} \tag{17}
$$

with $0! \coloneqq 1$.

### 2.5 Roots of Complex Numbers

If $w^n = z$ for $n \in \mathbb{N}^+$, $w$ is an $n$-th root of $z$, denoted by $\sqrt[n]{z}$.

Let $z = r \mathrm{e}^{\mathrm{i}\theta}$. There are exactly $n$ distinct complex roots given by:

$$
w_k \coloneqq \sqrt[n]{r} \exp\left(\mathrm{i} \frac{\theta + 2k\mathrm{\pi}}{n}\right) = \sqrt[n]{r}\left[\cos\left(\frac{\theta + 2k\mathrm{\pi}}{n}\right) + \mathrm{i}\sin\left(\frac{\theta + 2k\mathrm{\pi}}{n}\right)\right] \tag{18}
$$

for $k = 0, 1, 2, \dots, n-1$.

#### Special Case: Roots of Unity ($\sqrt[n]{1}$)

When $z = 1 = 1 \cdot \mathrm{e}^{\mathrm{i} 0}$, the solutions to $w^n = 1$ are:

$$
\omega_k \coloneqq \mathrm{e}^{\mathrm{i}\frac{2k\mathrm{\pi}}{n}} = \cos\left(\frac{2k\mathrm{\pi}}{n}\right) + \mathrm{i}\sin\left(\frac{2k\mathrm{\pi}}{n}\right), \quad k = 0, 1, \dots, n-1 \tag{19}
$$

**Geometric Meaning:** The $n$ roots of unity form the vertices of a regular $n$-sided polygon inscribed in the unit circle $\vert{}w\vert{} = 1$, with one vertex located at $w = 1$.

## 3. Geometric Applications in the Complex Plane

### 3.1 Distance and Modulus Identities

The Euclidean distance between two points represented by $z_1$ and $z_2$ is:

$$
\operatorname{dist} \left(z_1, \, z_2 \right) \coloneqq \vert{}z_1 - z_2\vert{} \tag{20}
$$

#### Key Identities and Inequalities:

1. **Modulus-Conjugate Relation:**

   $$
   \vert{}z\vert{}^2 = z \bar{z} \tag{21}
   $$

2. **Parallelogram Identity:**

   $$
   \vert{}z_1 + z_2\vert{}^2 + \vert{}z_1 - z_2\vert{}^2 = 2(\vert{}z_1\vert{}^2 + \vert{}z_2\vert{}^2) \tag{22}
   $$

3. **Modulus Expansion:**

   $$
   \vert{}z_1 \pm z_2\vert{}^2 = \vert{}z_1\vert{}^2 + \vert{}z_2\vert{}^2 \pm 2\operatorname{Re}(z_1 \bar{z}_2) \tag{23}
   $$

4. **Triangle Inequality:**

   $$
   \big\vert{} \vert{}z_1\vert{} - \vert{}z_2\vert{} \big\vert{} \le \vert{}z_1 \pm z_2\vert{} \le \vert{}z_1\vert{} + \vert{}z_2\vert{} \tag{24}
   $$

### 3.2 Standard Curves and Lines

#### Circle

A circle $C$ centered at $z_0$ with radius $r > 0$:

* **Implicit Form:**

  $$
  \vert{}z - z_0\vert{} = r \tag{25}
  $$

* **Parametric Form:**

  $$
  z(t) \coloneqq z_0 + r \mathrm{e}^{\mathrm{i} t}, \quad t \in [0, 2\mathrm{\pi}) \tag{26}
  $$

#### Straight Line

A straight line passing through two distinct points $z_1$ and $z_2$:

* **Parametric Form:**

  $$
  z(t) \coloneqq z_1 + t(z_2 - z_1), \quad t \in \mathbb{R} \tag{27}
  $$

### 3.3 Angle Between Vectors and Angles in a Triangle

#### Directed Angle

The directed angle $\theta$ from vector $(z_3 - z_1)$ to vector $(z_2 - z_1)$ is:

$$
\theta \coloneqq \operatorname{Arg}\left(\frac{z_2 - z_1}{z_3 - z_1}\right) \tag{28}
$$

#### Interior Angles of a Triangle

For a positively oriented (counterclockwise) triangle $\triangle ABC$ with vertices $z_1, z_2, z_3$:

$$
\begin{cases}  \angle z_1 \coloneqq \arg\left(\dfrac{z_3 - z_1}{z_2 - z_1}\right) \\  \angle z_2 \coloneqq \arg\left(\dfrac{z_1 - z_2}{z_3 - z_2}\right) \\  \angle z_3 \coloneqq \arg\left(\dfrac{z_2 - z_3}{z_1 - z_3}\right)  \end{cases} \tag{29}
$$

#### Theorem: The Sum of Interior Angles of a Triangle is $\mathrm{\pi}$

*Proof.* Consider the cyclic product:

$$
P \coloneqq \left(\frac{z_3 - z_1}{z_2 - z_1}\right) \cdot \left(\frac{z_1 - z_2}{z_3 - z_2}\right) \cdot \left(\frac{z_2 - z_3}{z_1 - z_3}\right) = -1 \tag{30}
$$

Taking arguments on both sides:

$$
\operatorname{Arg}(P) = \operatorname{Arg}\left(\frac{z_3 - z_1}{z_2 - z_1}\right) + \operatorname{Arg}\left(\frac{z_1 - z_2}{z_3 - z_2}\right) + \operatorname{Arg}\left(\frac{z_2 - z_3}{z_1 - z_3}\right) = \operatorname{Arg}(-1) = \mathrm{\pi} + 2k\mathrm{\pi}, \quad k \in \mathbb{Z} \tag{31}
$$

For interior angles of a nondegenerate triangle, each angle satisfies $0 < \angle z_i < \mathrm{\pi}$, so:

$$
0 < \angle z_1 + \angle z_2 + \angle z_3 < 3\mathrm{\pi} \tag{32}
$$

Thus, $k$ must be $0$, which proves:

$$
\angle z_1 + \angle z_2 + \angle z_3 = \mathrm{\pi} \tag{33}
$$

### 3.4 Geometric Characterization of Circles (Thales's Theorem)

**Theorem:** A point $z$ lies on the circle with diameter endpoints $z_1$ and $z_2$ (with $z \ne z_1$) if and only if:

$$
\operatorname{Re}\left(\frac{z_2 - z_1}{z - z_1}\right) = 1 \tag{34}
$$

*Proof.* Rearranging the algebraic fraction:

$$
\frac{z_2 - z_1}{z - z_1} - 1 = \frac{(z_2 - z_1) - (z - z_1)}{z - z_1} = \frac{z_2 - z}{z - z_1} \tag{35}
$$

Taking the real part of both sides yields:

$$
\operatorname{Re}\left(\frac{z_2 - z}{z - z_1}\right) = 0 \iff \frac{z_2 - z}{z - z_1} \text{ is purely imaginary} \tag{36}
$$

This is equivalent to:

$$
\arg\left(\frac{z_2 - z}{z - z_1}\right) = \pm \frac{\mathrm{\pi}}{2} \iff \angle(z_1, z, z_2) = \frac{\mathrm{\pi}}{2} \tag{37}
$$

By Thales's Theorem, the locus of points subtending a right angle across segment $[z_1, z_2]$ is the circle with diameter $[z_1, z_2]$. This also satisfies the Pythagorean theorem:

$$
\vert{}z_1 - z_2\vert{}^2 = \vert{}z - z_1\vert{}^2 + \vert{}z - z_2\vert{}^2 \tag{38}
$$

