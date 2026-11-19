# Mathematics Method for Physics - Lecture 9 Exercises

**Laurent Series and Singularities: Exercises**

Instructor: Zhaolong Han, SOCE, Shanghai Jiao Tong University

Email: han.arkey@sjtu.edu.cn

These worked exercises accompany the notes on Laurent series and singularities. Every expansion is stated together with its center and convergence region. The logarithm example also specifies a branch.

## 1. Taylor Expansions

### 1.1 Direct differentiation and indirect expansion

For $f(z)=1/z^2$ about $z_0=1$, either differentiate $f$ repeatedly or use

$$
\frac1{z^2}=-\left(\frac1z\right)'
 =-\left[\sum_{n=0}^{\infty}(-1)^n(z-1)^n\right]'.
\tag{1}
$$

Reindexing gives

$$
\boxed{\frac1{z^2}
 =\sum_{n=0}^{\infty}(-1)^n(n+1)(z-1)^n,\quad |z-1|<1.}
\tag{2}
$$

The pole at $0$ fixes the radius $1$.

For $1/[z^2(z+1)]$, the poles are $0,-1$, so the radius about $1$ is again $1$. For example, writing $w=z-1$ gives

$$
\frac1{z^2(z+1)}
 =\left[\sum_{k=0}^{\infty}(-1)^k(k+1)w^k\right]
  \left[\frac12\sum_{j=0}^{\infty}\left(-\frac w2\right)^j\right],
 \qquad |w|<1.
\tag{3}
$$

For $1/[z^2(z^2+1)]$, the poles are $0,\pm \mathrm{i}$; their distances from
$1$ are $1,\sqrt2,\sqrt2$, respectively. Its Taylor radius about $1$
is also $1$.

## 2. Review: Laurent Expansions in a Specified Region

### 2.1 An exponential in the exterior of the unit circle

Find the Laurent expansion about $0$ of

$$
f(z)=\exp\left(\frac1{1-z}\right),\qquad |z|>1.
\tag{4}
$$

Although

$$
f(z)=\sum_{k=0}^{\infty}\frac1{k!}\left(\frac1{1-z}\right)^k,
\tag{5}
$$

this is not yet a Laurent series in powers of $z$. For the specified region, begin with

$$
\frac1{1-z}=-\sum_{m=1}^{\infty}z^{-m},\qquad |z|>1.
\tag{6}
$$

One can expand the powers and collect coefficients. A more systematic method sets $w=1/z$, so the exterior becomes $0<|w|<1$:

$$
F(w)\coloneqq f(1/w)=\exp\left(\frac w{w-1}\right).
\tag{7}
$$

The apparent puncture at $w=0$ is removable; define $F(0)=1$. Then $F$ is holomorphic on $|w|<1$ and can be expanded by Taylor's theorem.

Write $F(w)=\sum_{n=0}^{\infty}a_nw^n$. Since

$$
(1-w)^2 F'(w)+F(w)=0,
\tag{8}
$$

coefficient comparison gives $a_0=1$, $a_1=-1$, and

$$
(n+1)a_{n+1}+(1-2n)a_n+(n-1)a_{n-1}=0,\qquad n\geq1.
\tag{9}
$$

Thus $a_2=-1/2$, $a_3=-1/6$, $a_4=1/24$, and

$$
\boxed{e^{1/(1-z)}
   =1-\frac1z-\frac1{2z^2}-\frac1{6z^3}
        +\frac1{24z^4}+\cdots,\qquad |z|>1.}
\tag{10}
$$

For a direct coefficient formula, expand
$F(w)=\exp[-w/(1-w)]$ to obtain, for $m\geq1$,

$$
a_m=\sum_{k=1}^{m}\frac{(-1)^k}{k!}\binom{m-1}{k-1}.
\tag{11}
$$

### 2.2 A rational function on three regions

Assume $|a|<|b|$ and let

$$
g(z)=\frac1{(z-a)(z-b)}
     =\frac1{a-b}\left(\frac1{z-a}-\frac1{z-b}\right).
\tag{12}
$$

The center and convergence region determine which geometric expansion is appropriate.

**About $0$, for $|a|<|z|<|b|$:**

$$
\boxed{g(z)=\frac1{a-b}\left[
       \sum_{n=0}^{\infty}a^nz^{-n-1}
       +\sum_{n=0}^{\infty}\frac{z^n}{b^{n+1}}\right].}
\tag{13}
$$

Here $1/(z-a)$ is expanded in $a/z$, whereas $1/(z-b)$ is expanded in $z/b$.

**About $0$, in a neighborhood of infinity, $|z|>|b|$:**

$$
\boxed{g(z)=\sum_{n=0}^{\infty}
               \frac{a^n-b^n}{a-b}\,z^{-n-1}.}
\tag{14}
$$

The coefficient of $z^{-1}$ is zero because $a^0-b^0=0$. The leading term is $z^{-2}$.

**About $a$, for $0<|z-a|<|a-b|$:** writing $u=z-a$ gives

$$
\boxed{g(z)=\sum_{n=0}^{\infty}
             \frac{(-1)^n}{(a-b)^{n+1}}u^{n-1}.}
\tag{15}
$$

This time the principal part is $1/[(a-b)(z-a)]$.

## 3. Classification Exercises

### 3.1 Double poles of a rational function: 12(2)

For

$$
f(z)=\frac1{(z^2+\mathrm{i})^2},
\tag{16}
$$

the roots of $z^2=-\mathrm{i}$ are

$$
z_0=e^{-\mathrm{i}\pi/4},\qquad z_1=e^{3\mathrm{i}\pi/4}.
\tag{17}
$$

Each is a simple zero of $z^2+\mathrm{i}$ and hence a double pole of $f$. At infinity, $f(z)\sim z^{-4}$, so infinity is removable with value $0$.

### 3.2 An essential singularity and simple poles: 12(6)

Let

$$
f(z)=\frac{e^{1/(z-1)}}{e^z-1}.
\tag{18}
$$

At $z=2k\pi \mathrm{i}$, the denominator has a simple zero, and the numerator is holomorphic and nonzero. Thus every such point, including $0$, is a simple pole. At $1$, the denominator is nonzero and holomorphic. The numerator has an essential singularity, so $1$ remains essential. Infinity is nonisolated because the simple poles are unbounded.

### 3.3 A sum with different types at $\pm \mathrm{i}$: 12(10)

For

$$
f(z)=\frac1{1+z^2}+\cos\left(\frac1{z+\mathrm{i}}\right),
\tag{19}
$$

$\mathrm{i}$ is a simple pole: the cosine term is holomorphic there.
At $-\mathrm{i}$, put $u=z+\mathrm{i}$. The cosine contributes

$$
\cos(1/u)=\sum_{n=0}^{\infty}\frac{(-1)^n}{(2n)!}\,u^{-2n}.
\tag{20}
$$

The rational term has only a simple pole at $-\mathrm{i}$, so it cannot cancel infinitely many negative-power terms. Thus $-\mathrm{i}$ is essential. At infinity the function has removable value $1$.

### 3.4 A logarithm requires a branch choice: 12(12)

Consider

$$
f(z)=\frac1{z\log(1-z)}.
\tag{21}
$$

Near $0$, take the holomorphic branch with $\log1=0$. Then

$$
q(z)\coloneqq \frac1{f(z)}
      =z\log(1-z)=-z^2-\frac{z^3}{2}-\cdots .
\tag{22}
$$

Hence $q$ has a zero of order $2$ at $0$, and $f$ has a double pole. In particular,

$$
f(z)=-\frac1{z^2}+\frac1{2z}+\frac1{12}+O(z).
\tag{23}
$$

One may also check

$$
q'(z)=\log(1-z)-\frac z{1-z},\qquad q''(0)=-2\neq0.
\tag{24}
$$

At $1$, the logarithm has a branch point. There is no single-valued holomorphic logarithm on a full punctured disk about $1$, so this point does not fall under the removable/pole/essential classification. The branch normalized at $0$ can, for example, be continued on
$\mathbb{C}\setminus[1,\infty)$.

### 3.5 The extended plane: $\cot z-1/z$

Let

$$
f(z)=\cot z-\frac1z
     =\frac{z\cos z-\sin z}{z\sin z}.
\tag{25}
$$

At $0$, use Taylor expansions:

$$
z\cos z-\sin z=-\frac{z^3}{3}+O(z^5),\qquad
 z\sin z=z^2+O(z^4).
\tag{26}
$$

Thus

$$
f(z)=-\frac z3+O(z^3)\longrightarrow0.
\tag{27}
$$

The origin is removable, with extension $f(0)=0$. At $k\pi$, $k\neq0$, $\sin z$ has a simple zero while $\cos(k\pi)$ is nonzero. Hence these points are simple poles of $\cot z$; subtracting $1/z$, which is holomorphic there, does not remove them. Their unbounded sequence makes infinity nonisolated.

## 4. Assigned Exercises

Textbook p. 117: 7(3), 7(4), 8, 11 and the assigned subitems of 12.

## 5. Checks on the Calculations

-  Differentiating the geometric series gives
$(1+w)^{-2}=\sum_{n\geq0}(-1)^n(n+1)w^n$ for $|w|<1$.
The factor $n+1$ is needed in the expansion of $1/[z^2(z-1)]$.

-  The three-region example in the main notes uses the numerator $4$
throughout. Its exterior expansion starts with $4(z-2)^{-2}$.

-  For $F(w)=\exp[w/(w-1)]$, $F^{(3)}(0)=-1$, so the coefficient of
$z^{-3}$ in the exterior expansion is $-1/6$.

-  The derivative of $\log(1-z)$ is $-1/(1-z)$. On the branch with
$\log1=0$, $1/[z\log(1-z)]$ has a double pole at $0$.

-  The expansion $\cot z-1/z=-z/3+O(z^3)$ gives the removable value
$0$ at the origin.
