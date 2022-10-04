# Idk yet

$$
\newcommand{\ds}{\displaystyle}

\newcommand{\R}{\mathbb R}
\newcommand{\C}{\mathbb C}

\newcommand{\curlies}[1]{\left\{ #1\right\}}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\conj}[1]{\overline{#1}}
\newcommand{\partials}[2]{\frac{\partial #1}{\partial #2}}
\newcommand{\dpartials}[2]{\frac{\partial #1}{\partial #2}}
$$

### Mapping properties

The **tangent mapping** of $f$ at $z_0$ is $Tz = cz$ where $c = f'(z_0)$

If $c \neq 0$ then $T$ preserves angles

... show that holomorphic maps are conformal

#### Lemma: An $\R$-linear transformation from $\C$ to $\C$ which preserves angles is either $w = cz$ or $w = c \overline z$

Shown in problem set

#### Something else idk

Consider $w = f(z)$ on a connected open set $\Omega$, and assume $f$ is continuously differentiable, i.e. as if it were a function from $\R^2$ to $\R^2$. Suppose the Jacobian of $f$ is not equal to $0$ at any point in $\Omega$.

If $f$ preserves angles at every point $p \in \Omega$, then the tangent map is either $cz$ or $c\overline z$ (by the previous lemma), so either $\ds \partials{f}{z}(p) = 0$ or $\ds \partials{f}{\overline z}(p) = 0$.

Both of those partial derivatives are continuous and they cannot both be zero. Also note that
$$
U = \curlies{p \in \Omega : \partials{f}{z}(p) = 0} \text{ is closed} \\
V = \curlies{p \in \Omega : \partials{f}{\overline z}(p) = 0} \text{ is closed} \\
U \sqcup V = \Omega
$$
Since they are closed and their union is an open connected set $\Omega$, one of them must be equal to $\Omega$ and the other one must be $\emptyset$.

So either $\ds \partials{f}{\overline z} = 0$ everywhere, and thus $f$ is holomorphic, or $\partials{f}{z} = 0$ everywhere, and we call $f$ **anti-holomorphic**.

## Inverse function theorem

Suppose $f$ is holomorphic on a neighbourhood of $z_0$ and $f'(z_0) \neq 0$.

Then there are neighbourhoods $U$ around $z_0$ and $V$ around $w_0 = f(z_0)$ such that the restriction $f_U : U \to V$ is invertible, and its inverse is holomorphic.

We can compute the derivative of the inverse using the chain rule.

Let $g: V \to U$ be the inverse, then
$$
\begin{align*}
g(w) &= z \\
g(f(z)) &= z \\
g'(f(z)) f'(z) &= 1 \\
g'(f(z)) &= \frac{1}{f'(z)} \\
g'(w) &= \frac{1}{f'(g(w))}
\end{align*}
$$
**Proof:** (to be completed later)

We can prove most of this just using properties of differentiable real functions from $\R^2$ to $\R^2$

The last part is proving that the inverse is holomorphic - this is easy, as $\dfrac{1}{f'(z)}$

