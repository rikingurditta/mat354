# The Riemann Sphere

$$
\newcommand{\ds}{\displaystyle}

\newcommand{\R}{\mathbb R}
\newcommand{\C}{\mathbb C}

\newcommand{\curlies}[1]{\left\{ #1\right\}}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\conj}[1]{\overline{#1}}
$$

Want to extend $\C$ to $\infty$ - what properties do we want to preserve?

- $a + \infty = \infty + a = \infty$
- $a \cdot \infty = \infty \cdot a = \infty$ if $a \neq 0$
- $a / \infty = 0$ if $a \neq \infty$
- $a / 0 = \infty$ if $a \neq 0$

Can do this via stereographic projection

- any point on unit sphere $S^2$ can be written as $(x, y, t)$ where $x^2 + y^2 + t^2 = 1$
- $\mathbf n = (0, 0, 1)$ and $\mathbf s = (0, 0, -1)$ are the north and south poles of $S^2$
- can define pair of transition maps between $S^2$ and $\C$
  - project each point of $S^2 \setminus \curlies{\mathbf n}$ to a point on $\C$ by the projection $z = \dfrac{x + iy}{1 - t}$
  - project each point of $S^2 \setminus \curlies{\mathbf s}$ to a point on $\C$ by $z = \dfrac{x + iy}{1 + t}$

Can also consider the complex conjugate of stereographic projection

- $z' = \dfrac{x - iy}{1 + t}$ projects from $S^2 \setminus \curlies{\mathbf s}$ to $\C$

Considering the pair of projections $z = \dfrac{x + iy}{1 - t}$ and $z' = \dfrac{x - iy}{1 + t}$, we can multiply them to see that on $\C \setminus \curlies{\mathbf n, \mathbf s}$,
$$
\begin{align*}
z' z &= \frac{x - iy}{1 + t} \frac{x + iy}{1 - t} \\
&= \frac{x^2 - i^2 y^2}{1^2 - t^2} \\
&= \frac{x^2 + y^2}{1 - t^2}
\end{align*}
$$
TODO: not sure where this went

- under stereographic projection from $\mathbf n$
  - any straight line on $\C$ corresponds to a circle through $\mathbf n$ on $S^2$
  - any circle on $S^2$ corresponds to either a circle or straight line in $\C$

### Any circle on $S^2$ corresponds to either a circle or straight line in $\C$

Any circle in $S^2$ lies in a plane $ax + by + ct = d$

Stereographic projection from $\mathbf n$ takes $(x, y, t)$ to $z = \frac{x + iy}{1 - t}$

$$
\begin{align*}
\abs{z}^2 &= \conj z z \\
&= \frac{x + iy}{1 - t} \frac{x - iy}{1 - t} \\
&= \frac{x^2 + y^2}{(1 - t)^2} \\
&= \frac{1 - t^2}{(1 - t)^2} \tag{since $x^2 + y^2 + t^2 = 1$} \\
&= \frac{1 + t}{1 - t}
\end{align*}
$$

So

$$
\begin{align*}
t &= \frac{\abs{z}^2 - 1}{\abs{z}^2 + 1} \\
1 - t &= \frac{2}{\abs{z}^2 + 1}
\end{align*}
$$

Based on our definitions, we know that

$$
\begin{align*}
x &= \dfrac{1}{2} (z + \conj z)(1 - t) \\
y &= \dfrac{1}{2} (z - \conj z)(1 - t)
\end{align*}
$$

so considering our plane equation, we have

$$
\begin{align*}
ax + by + ct &= d \\
a \dfrac{1}{2} (z + \conj z)(1 - t) + b \dfrac{1}{2} (z - \conj z)(1 - t) + ct &= d \\
a \dfrac{1}{2} (z + \conj z) \frac{2}{\abs{z}^2 + 1} + b \dfrac{1}{2} (z - \conj z)\frac{2}{\abs{z}^2 + 1} + c\frac{\abs{z}^2 - 1}{\abs{z}^2 + 1} &= d \\
a(z + \conj z) + b(z - \conj z) + c(\abs{z}^2 - 1) &= d(\abs{z}^2 + 1)
\end{align*}
$$

TODO: umm uhh ummmm
