## 4. Introduction to Point Sets in the Complex Plane

### 4.1 Neighborhoods

The $\delta$**-neighborhood** of a point $z_0 \in \mathbb{C}$ is defined as the open disk:

$$
U(z_0, \delta) \coloneqq \{ z \in \mathbb{C} : \vert{}z - z_0\vert{} < \delta \} \tag{39}
$$

The **punctured (deleted) neighborhood** is defined as:

$$
\mathring{U}(z_0, \delta) \coloneqq \{ z \in \mathbb{C} : 0 < \vert{}z - z_0\vert{} < \delta \} \tag{40}
$$

### 4.2 Point Classification and Domains

Let $E \subset \mathbb{C}$ be a subset of the complex plane:

1. **Interior Point:** A point $z_0 \in E$ is defined as an *interior point* of $E$ if there exists $\delta > 0$ such that $U(z_0, \delta) \subset E$.

2. **Open Set:** $E$ is defined to be an *open set* if every point of $E$ is an interior point of $E$.

3. **Domain (Region):** An open set $D \subset \mathbb{C}$ is defined as a **domain** if it is connected (i.e., any two points in $D$ can be joined by a continuous polygonal path lying entirely within $D$).