# Power Series

$$
\newcommand{\ds}{\displaystyle}

\newcommand{\R}{\mathbb R}
\newcommand{\C}{\mathbb C}

\newcommand{\curlies}[1]{\left\{ #1\right\}}
\newcommand{\parens}[1]{\left( #1\right)}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\conj}[1]{\overline{#1}}
\newcommand{\partials}[2]{\frac{\partial #1}{\partial #2}}
\newcommand{\dpartials}[2]{\frac{\partial #1}{\partial #2}}
\DeclareMathOperator{\Arg}{Arg}
\DeclareMathOperator{\id}{id}
$$



### Power series operations

Consider complex power series $\ds f(w) = \sum_{n=0}^\infty a_n w^n$ and $\ds g(z) = \sum_{p=0}^\infty b_p z^p$

Note that $w$ and $z$ do not represent complex numbers, they are *indeterminates*. i.e., they are just notation to represent the formal power series

We can see the composition is
$$
\begin{align*}
f(g(z)) = a_0 + a_1(b_0 + b_1 z + \dots) + a_2(b_0 + b_1 z + \dots)^2 + \dots
\end{align*}
$$
So each coefficient is a series as well. If $b_0 = 0$, then each coefficient is a finite series, so this is well defined.

We "already know" that every formal power series is the power series of a $C^\infty$ function, and that their power series should compose the same way the functions compose... how do we make this work?

Consider the composition of Taylor series:

Suppose $w_0 = g(z_0)$, the series for $f$ around $w_0$ is $\ds \sum_{n=0}^\infty a_n (w - w_0)$, and the series for $g$ around $z_0$ is $\ds \sum_{p=0}^\infty b_p(z - z_0)$

### Formal inverse function theorem

Given formal power series $\ds f(w) = \sum_{n=0}^\infty a_n w^n$, if $f(0) = a_0 = 0$ and $f'(0) \neq 0$, then there is a unique power series $\ds g(z) = \sum_{p=0}^\infty b_p z^p$ with $b_0 = 0$ such that $f \circ g = \id$ and $g \circ f = \id$

(note that the power series for $\id$ is $\id(z) = z$)

**Proof.** (by method of undetermined coefficients)

We want to solve the equation
$$
a_0 + a_1 (b_1 z + b_2 z^2 + \dots) + a_2 (b_1 z + b_2 z^2 + \dots)^2  + \dots = z
$$
We know right away that $a_0 = 0$, and that the coefficient of $z$ is 1 so $a_1 b_1 = 1$ (this reveals our hypotheses $f(0) = 0$ and $f'(0) \neq 0$)

These are sufficient to solve uniquely for every $b_i$

Note that the cofficient of $z^n$ in the left hand side of the equation is the same as its coefficient in
$$
a_0 + a_1 g(z) + \dots + a_n g(z)^n
$$
since $g(z)$ has no constant term $b_0$ so all terms after $g(z)^n$ have degree at least $n+1$.

The $z^n$ term's coefficient is
$$
a_1 b_n + P(a_2, ..., a_n, b_1, ..., b_{n-1})
$$
where $P$ is some polynomial, which is linear in $a_2, ..., a_n$ (this polynomial doesn't depend on $a_1$ or $b_n$). We already know that $b_1 = \dfrac{1}{a_1}$, so by induction we can calculate $b_n$ recursively.

### Convergence of composition of power series

$$
f(w) = \sum_{n=0}^\infty a_n w^n, \quad g(z) = \sum_{p=1}^\infty b_p z^p
$$

If $f$ and $g$ are convergent, then so is $f \circ g$

Take $r > 0$ such that $\ds \sum_{p=1}^\infty \abs{b_p} r^p < R(f)$ (we know that $r$ exists because $\ds \lim_{z \to 0}g(z) = 0$). We will show that:

1. $r \leq R(f \circ g)$
2. $\abs{g(z)} < R(f)$
3. $f(g(z)) = (f \circ g)(z)$ (where $f(g(z))$ is composition of functions and $(f \circ g)(z)$ is composition of power series)

**Proof of 1.**

Define a new power series $\Gamma$
$$
\Gamma(r) = \sum_{k=0}^\infty \gamma_k r^k = \sum_{n=0}^\infty \abs{a_n} \parens{\sum_{p=1}^\infty \abs{b_p} r^p} < \infty
$$
$\Gamma(r) < \infty$ since both $f$ and $g$ converge

Suppose $\ds (f \circ g)(z) = \sum_{k=0}^\infty c_k z^k$, then by the triangle inequality we know $\abs{c_k} \leq \gamma_k$ for each $k$.

### Reciprocal of a power series

Define $\ds f(z) = \sum_{n=0}^\infty a_n z^n$

If $f(0) \neq 0$ then there is a unique power series $g(z)$ so that $f(z) g(z) = 1$

If $f$ has positive radius of convergence then so does $g$

**Proof.**

Assume without loss of generality that $a_0 = 1$. Define $h(z) = 1 - f(z)$, so $h(0) = 0$. Then
$$
\frac{1}{f(z)} = \frac{1}{1 - h(z)}
$$
The function $\dfrac{1}{1 - w}$ has power series $\ds 1 + \sum_{n=1}^\infty w^n$, and we can compose this with $w = h(z)$ since $h(0) = 0$.

### Inverse function theorem for convergent power series

According to previous statement, if $f(w)$ has positive radius of convergence, then so does $g(z)$.

Can prove this by direct estimate, or by IFT for holomorphic functions once we know that holomorphic functions have convergent infinite Taylor series

## Principal branch of $\log z$

Consider $\Omega = \C \setminus (-\infty, 0]$, in $\Omega$ there is a unique way to take the angle of a point within the range $(-\pi, \pi)$. We can call this angle the **principal branch of $\Arg(z)$**, and it is continuous.

If we show that $\Arg$ is continuous on $S^1 \setminus \{-1\}$ then we also know that it is continuous on $\Omega$. Also note that $\Arg$ is invertible on $S^1 \setminus \{-1\}$, and its inverse is $e^{iw}$

We define the **principal branch of $\log z$**  as $\log \abs z + i \Arg z$. This is the principal branch because it coincides with $\log : \R \to \R$ on $(0, \infty)$.

#### Power series

The power series of the principal branch of $\log(z + 1)$ is $\ds f(z) = \sum_{n=1}^\infty (-1)^{n+1} \frac{z^n}{n}$ and it converged if $\abs z < 1$

**Proof.**

The inverse of the power series $f(z)$ is $\ds g(w) = \sum_{n=1}^\infty \frac{w^n}{n!}$ ($= e^w - 1$)

(proved in first year calculus)

We can check that this is the principal branch by computing it at one point and comparing

## Complex exponents

If $\alpha, z \in \C$ and $z \neq 0$, then we define $z^\alpha = e^{\alpha \log z}$. Note that this is a many-valued function of $z$

This has a branch on any domain $\Omega$ where $\log$ has a branch

(in complex analysis, *domain* usually refers to a connected open subset of $\C$)

#### Binomial series

This shows us the binomial series
$$
(1 + z)^\alpha = e^{\alpha \log(1 + z)} = \sum_{n=0}^\infty \binom{\alpha}{n} z^n
$$
