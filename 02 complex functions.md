# Complex Functions

$$
\newcommand{\ds}{\displaystyle}

\newcommand{\R}{\mathbb R}
\newcommand{\C}{\mathbb C}

\newcommand{\curlies}[1]{\left\{ #1\right\}}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\conj}[1]{\overline{#1}}
$$

## Linear functions

A function $T: \C \to \C$ is linear if there is some $a \in \C$ so that $T(z) = az$

These functions are a composition of a rotation and a scaling, i.e. $a = rs$ where $\abs r = 1$ (rotation) and $s \geq 0$ (scaling).

$\C$-linear functions are a subset of $\R$-linear functions:

$$
\begin{align*}
T(z) = az &= (\alpha + i \beta)(x + iy) \\
&= (\alpha x - \beta y) + i (\beta x + \alpha y)
\end{align*}
$$

so we can write $T$ as a function on $\R^2$ as

$$
T \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} \alpha & -\beta \\ \beta & \alpha \end{pmatrix}\begin{pmatrix} x \\ y \end{pmatrix}
$$

## Polynomials

## Rational functions

Rational functions have the form

$$
R(z) = \frac{P(z)}{Q(z)}
$$

where $P, Q$ are polynomial functions

Assume $P, Q$ have no common factors

Then the zeros of $Q(z)$ are called the **poles** of $R(z)$

The **order** of a pole of $R(z)$ is the order of the zero in $Q(z)$

The poles of $R'(z)$ are the same as the poles of $R(z)$, since by the quotient rule,

$$
R'(z) = \frac{P'(z) Q(z) - P(z) Q'(z)}{(Q(z))^2}
$$

We define the value at infinity as

$$
R(\infty) = \lim_{z \to \infty} R(z)
$$

This may be a pole (if $R(\infty) = \infty$) - how do we define the order of this pole?

This is more easily formulated if we consider rational functions to be from the Riemann sphere to itself

We can consider the funciton $R_1(z) = R(1/z)$ - if $R$ has a zero/pole at $\infty$ then $R_1$ has a zero/pole at $0$

$$
\begin{align*}
R(z) &= \frac{a_m z^m + ... + a_0}{b_n z^n + ... + b_0} \\
R_1(z) = R(1/z) &= \frac{a_0 z^m + ... + a_m}{b_0 z^n + ... + b_m} (z^{n-m})
\end{align*}
$$

So if $n > m$, then $R$ has a zero of order $n-m$ at $\infty$, and if $n < m$ then $R$ has a pole of order $m - n$ at $\infty$ (since those are the orders of the poles/zeroes of $R_1(z)$). If $n = m$ then $R(\infty) = \dfrac{a_m}{b_n} \neq 0$ (since $a_m \neq 0$ by assumption).

So the total number of zeroes (counting multiplicity) of $R$ in the Riemann sphere, including at infinity, is $\max(m, n)$, and the number of poles is also $\max(m, n)$. This number is called the **order** of $R$.

So if a rational function $R$ has $k$ roots (and $k$ poles), then $R(z) = a$ has $k$ solutions in the Riemann sphere.

### Examples

#### Fractional linear transformations

$$
S(z) = \frac{az + b}{cz + d},\ ad-bc \neq 0
$$

A rational function of order 1 is called a **fractional linear transformation** (or a **Möbius transformation**)

Any equation $S(z) = w$ has exactly one root

#### Translations

$$
S(z) = z + a
$$

$S(z)$ is a translation with one fixed point, $\infty$

### Partial fraction decomposition

Consider a rational function

$$
R(z) = \frac{P(z)}{Q(z)}
$$

First do long division until $\deg P(z) \leq \deg Q(z)$, so that we have $P(z) = G(z) Q(z) + \tilde H(z)$ where $G(z)$ is a polynomial and $\deg \tilde H(z) \leq \deg Q$. Define $H(z) = \dfrac{\tilde H(z)}{Q(z)}$, then

$$
R(z) = G(z) + H(z)
$$

Then $\deg G(z)$ is the order of $R$'s pole at $\infty$, and we call $G(z)$ the **singular part** of $R(z)$.

Let $\beta_1, ..., \beta_q$ be distinct finite poles of $R(z)$, i.e. for all $j$ we have $Q(\beta_j) = 0$ and $\beta_j \neq \infty$. Then for any $i$, $R \left( \beta_j + \dfrac{1}{\zeta} \right)$ is a rational function of $\zeta$, and we can write it as

$$
R\left( \beta_j + \frac{1}{\zeta} \right) = G_j(\zeta) + H_j(\zeta)
$$

Taking $z = \beta_j + \dfrac{1}{\zeta}$, we can write $\zeta = \dfrac{1}{z - \beta_j}$, so we have

$$
R(z) = G_j\left( \frac{1}{z - \beta_j} \right) + H_j\left( \frac{1}{z - \beta_j} \right)
$$

TODO: complete proof - Ahlfors 1.4

#### Real rational functions

Complex roots  of a real polynomial always occur in conjugate pairs, so when looking at poles of $R(z)$ we will have to pair the $\beta_j, \beta_k$ where $\beta_j = \conj{\beta_k}$

We can take the complex partial fraction decomposition and add the terms for conjugate roots, and we'll end up with real terms

### Classification of order-2 rational functions

Want to classify order-2 rational functions up to change of coordinates by FLTs

Let $f$ be an order 2 rational function. There are 2 cases for the poles of $f$ - 1 double pole $\beta$ or 2 distinct poles $\alpha, \beta$

Double pole case:

$f\left(1 + \dfrac{1}{\zeta}\right)$ has a double pole at $\zeta = \infty$. Since its only poles are at infinity, it must be a polynomial, so

$$
\begin{align*}
f\left(1 + \frac{1}{\zeta}\right) = w &= a\zeta^2 + b\zeta + c \\
w &= a \left(\zeta - \frac{b}{2a}\right)^2 + c - \frac{b^2}{4a} \\
\frac{w - c + \frac{b^2}{4a}}{a} &= \left(\zeta - \frac{b}{2a}\right)^2
\end{align*}
$$

Now, if we apply fractional linear transformations to both the left hand side (a function of $w$) and the right hand side (a function of $z$), we can change coordinates to $w = z^2$. So every rational function of order 2 can be transformed to look like $f(z) = z^2$.

Distinct poles case:
