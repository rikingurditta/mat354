# ???

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

\DeclareMathOperator{\diam}{diam}
\DeclareMathOperator{\perim}{perim}
$$

$\omega$ is closed if $\ds \int_\gamma \omega = 0$ whenever $\gamma$ is the boundary of a sufficiently small rectangle in $\Omega$

in an open disc, this is equivalent to $\omega$ haing a primitive

but in general a closed differential form in a domain $\Omega$ may not have a primitive

e.g.
$$
\omega = \frac{dz}{z}
$$
$\omega$ is closed because $\log z$ is locally a primitive of $\omega$ at every point

however it does not have a primitive:

if $\gamma : [0,2\pi] \to S^1, \gamma(t) = e^{it}$, then
$$
\begin{align*}
\int_{\gamma} \omega &= \int_0^{2\pi} \frac{ie^{it} dt}{e^{it}} \\
&= \int_0^{2\pi} idt \\
&= 2\pi i \neq 0
\end{align*}
$$
(doing the same thing in $\R^2$, our integral is $2\pi$)

## Cauchy's theorem

If $f(z)$ is a holomorphic function in a domain $\Omega \subseteq \C$, then the differential form $f(z)dz$ is closed

### Aside

> "I don't want you think this has anything to do with the theorem"
>
> \- Edward Bierstone

Assume $P, Q$ continuous with continuous partial derivatives $\ds \partials{P}{y}, \partials{Q}{x}$ in a neighbourhood of a closed rectangle $A$ with corners $(a_1, b_1), (a_2, b_2)$ (with $\gamma$ tracing $\partial A$)

Green's theorem says
$$
\int_\gamma P dx + Q dy = \iint_A \parens{\partials{Q}{x} - \partials{P}{y}} dx dy
$$
Proof.
$$
\begin{align*}
\iint_A \parens{\partials{Q}{x} - \partials{P}{y}} dx dy
&= \int_{b_1}^{b_2} \int_{a_1}^{a_2} \partials{Q}{x} dx dy - \int_{a_1}^{a_2} \int_{b_1}^{b_2} \partials{P}{y} dy dx \\
&= \int_{b_1}^{b_2} (Q(a_2, y) - Q(a_1, y)) dy - \int_{a_1}^{a_2} (P(x, b_2) - P(x, b_1)) dx \\
&= \int_\gamma P dx + Q dy
\end{align*}
$$
Applying this to a differential form $\omega$, the statement $\ds \int_\gamma \omega = 0$ ($\gamma$ is the boundary of a sufficiently small rectangle) is equivalent to ...

### Proof of Cauchy's theorem under additional assumption $\partials{f}{x}, \partials{f}{y}$ exist and are continuous

$$
f(z) dz = f(z) dx + if(z) dy
$$

The Cauchy-Riemann equation tells us that $\ds \partials{f}{y} = i\partials{f}{x}$. Then, considering $P = f(z)$ and $Q = if(z)$, we see that $\ds \partials{P}{y} = \partials{Q}{x}$, so we can apply Green's theorem to find that $f(z)dz$ is closed.

### Proof of Cauchy's theorem

It is enough to show that
$$
\int_\gamma f(z) dz = 0
$$
when $y$ traces the boundary of any rectangle $R$ in $\Omega$

Divide $R$ into 4 equal parts $R_i$, each with their own oriented boundary $\gamma_i$. Then
$$
\int_\gamma f(z) dz = \sum_{i=1}^4 \int_{\gamma_i} f(z)dz
$$
Since the coincident parts of the $\gamma_i$'s cancel out

We know that for at least one $i$,
$$
\frac{1}{4} \abs{\int_\gamma f(z) dz} \leq \abs{\int_{\gamma_i} f(z)dz}
$$
Let's consider this rectangle to be called $R^{(1)}$ with its boundary $\gamma^{(1)}$

We can apply the same process of subdividing to $R^{(1)}$ to get $R^{(2)}$ whose absolute value of integral over boundary is $\geq$ 1/4 the absolute value of the integral over the boundary of $R^{(1)}$, and etc

There exists one point $z_0$ at the intersection of all $R^{(k)}$, and $f$ is holomorphic at this $z_0$. Then in a neighbourhood around $z_0$,
$$
f(z) = f(z_0) + f'(z_0) (z - z_0) + \phi(z)\abs{z - z_0}
$$
where
$$
\lim_{z \to 0} \phi(z) = 0
$$
Then
$$
\int_{\gamma^{(k)}} f(z) dz = \int_{\gamma^{(k)}} f(z_0) dz + \int_{\gamma^{(k)}} f'(z_0) (z - z_0) + \int_{\gamma^{(k)}} \phi(z) \abs{z - z_0}
$$
We know that $\ds \int_{\gamma^{(k)}} f(z_0) dz = 0$ since we are integrating a constant along a closed curve.

$f'(z_0)(z - z_0)$ has a primitive $\dfrac{f'(z_0)}{2} (z - z_0)^2$, so we know that $\ds \int_{\gamma^{(k)}} f'(z_0) (z - z_0) = 0$

So now we know that
$$
\int_{\gamma^{(k)}} f(z) dz = \int_{\gamma^{(k)}} \phi(z) \abs{z - z_0}
$$
Lastly, given $\epsilon > 0$, if $\abs{z - z_0} < \delta$, then
$$
\begin{align*}
\abs{\int_{\gamma^{(k)}} \phi(z) \abs{z - z_0} dz}
&\leq \epsilon \abs{\int_{\gamma^{(k)}} \abs{z - z_0}} \\
&\leq \epsilon (\diam R^{(k)}) (\perim R^{(k)}) \\
&\leq \parens{\frac{1}{2^k} \diam R} \parens{\frac{1}{2^k} \perim R} \\
&\leq \epsilon \frac{1}{4^k} (\diam R) (\perim R)
\end{align*}
$$
Putting this in the context of our original integral over $\partial R$,
$$
\abs{\int_\gamma f(z) dz} \leq 4^k \abs{\int_{\gamma^{(k)}} f(z)dz} = 4^k \abs{\int_{\gamma^{(k)}} \phi(z) \abs{z - z_0}} \leq \epsilon (\diam R) (\perim R)
$$
This holds for any $\epsilon$, so $\ds \abs{\int_\gamma f(z) dz} = 0$

### Corollary 1

Consider a holomorphic function $f(z)$ on a domain $\Omega \subseteq \C$

Then $f(z)$ locally has a primitive $F(z)$ which is *holomorphic*
$$
f(z) dz = dF = \partials{F}{z} dz + \partials{F}{\conj z} d\conj z
$$
There is no $d\conj z$ term on the left hand side, so $\ds \partials{F}{\conj z} = 0$, so $F$ satisfies the Cauchy-Riemann equation

### Corollary 2 (generalization)

It is enough to assume that $f$ is continuous in $\Omega$ and holomorphic outside of a line (wlog could say outside of x-axis)

## A closed differential form in a simply connected open subset $\Omega \subseteq \R^2$ has a global primitive
