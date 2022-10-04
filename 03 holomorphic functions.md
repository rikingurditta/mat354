# Holomorphic Functions

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

If $\Omega \subset \C$ is open and $f : \Omega \to \C$, $f$ is **holomorphic** at $z \in \C$ if

$$
f'(z) = \lim_{h \to 0} \frac{f(z + h) - f(z)}{h} \text{ exists}
$$

We can rewrite this as

$$
\begin{align*}
\lim_{h \to 0} \frac{f(z + h) - f(h)}{h} &= c \\
f(z + h) - f(z) = hc + h\varphi(h)
\end{align*}
$$

where $\ds \lim_{h \to 0} \varphi(h) = 0$

The derivative is a linear transformation $h \mapsto ch$ for some $c \in \C$. Writing this as a vector equation in terms of the real and imaginary parts of $h = \zeta + i \eta$ and $c = a + ib$,

$$
\begin{pmatrix} \zeta \\ \eta \end{pmatrix} \mapsto \begin{pmatrix} a\zeta - b\eta \\ ia\eta + ib\zeta \end{pmatrix} = \begin{pmatrix} a & -b \\ b & a \end{pmatrix} \begin{pmatrix} \zeta \\ \eta \end{pmatrix}
$$

So if we take $f(z) = f(x + iy) = u + iv$ as a function on $\R^2$, this tells us that its derivative satisfies $\dfrac{\partial u}{\partial x} = \dfrac{\partial v}{\partial y}$ and $\dfrac{\partial u}{\partial y} = - \dfrac{\partial v}{\partial x}$.

i.e.,

$$
\frac{\partial f}{\partial x} + i \frac{\partial f}{\partial y} = 0
$$

These are the Cauchy-Riemann equations

Considering the jacobian determinant,

$$
\det \frac{\partial (u, v)}{ \partial (x, y)} = \abs{f'(z)}^2
$$

Considering $f : \R^2 \to \C$, the differential is

$$
df = \frac{\partial f}{\partial x} dx + \frac{\partial f}{\partial y} dy
$$

We define

$$
\begin{align*}
\frac{\partial f}{\partial z} &= \frac{1}{2} \left( \frac{\partial f}{\partial x} - i \frac{\partial f}{\partial y} \right) \\
\frac{\partial f}{\partial \conj z} &= \frac{1}{2} \left( \frac{\partial f}{\partial x} + i \frac{\partial f}{\partial y} \right)
\end{align*}
$$

so we can also rewrite the Cauchy-Riemann equations as

$$
\frac{\partial f}{\partial \conj z} = 0
$$

## Harmonic Functions

$f$ is **harmonic** if $f$ is $C^2$ and

$$
\frac{\partial^2 f}{\partial x} + i \frac{\partial^2 f}{\partial y} = 0
$$

i.e. if

$$
\frac{\partial^2 f}{\partial z \partial \conj z} = 0
$$

## Remark about holomorphic functions

Note that the condition $\dfrac{\partial f}{\partial \conj z} = 0$ is equivalent to $\dfrac{\partial \conj f}{\partial z} = 0$:

$$
\begin{align*}
\partials{f}{\conj z} &= \frac{1}{2} \left( \partials{f}{x} + i \partials{f}{y} \right) \\
\conj{\left(\partials{f}{\conj z}\right)} &= \conj{\frac{1}{2} \left( \partials{f}{x} + i \partials{f}{y} \right)} \\
&= \frac{1}{2} \left( \partials{\conj f}{x} + i \partials{\conj f}{y} \right) \\
&= \partials{\conj f}{z}
\end{align*}
$$

## If $f$ is holomorphic and $f' = 0$, then $f$ is constant

(consider one connected component of the domain of $f$)

$$
df = \partials{f}{z} dz + \partials{f}{\conj z} d\conj z
$$

## If $f$ is holomorphic on a connected open set $\Omega$ and $\abs{f}$ is constant then $f$ is constant

Suppose $\abs{f(z)} = c \in \R$ for all $z$, then
$$
\begin{align*}
c^2 &= \abs{f(z)}^2 \\
c^2 &= f(z) \conj{f(z)} \\
\partials{(c^2)}{z} &= \partials{f}{z} \conj{f(z)} + f(z) \partials{\conj f}{z} \\
0 &= \partials{f}{z} \conj{f(z)} + f(z) \partials{f}{\conj z} \\
0 &= \partials{f}{z} \conj{f(z)} + f(z) (0) \tag{since $f$ is holomorphic} \\
0 &= \partials{f}{z} \conj{f(z)}
\end{align*}
$$
If $c = 0$ then $f = 0$, so $f$ is constant. If $c \neq 0$, then $f(z) \neq 0$, so $\conj{f(z)} \neq 0$ for any $z$, so we must have $\ds \partials{f}{z} = 0$.
