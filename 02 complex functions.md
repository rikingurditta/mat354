$$
\newcommand{\ds}{\displaystyle}

\newcommand{\R}{\mathbb R}
\newcommand{\C}{\mathbb C}

\newcommand{\curlies}[1]{\left\{ #1\right\}}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
$$

# Complex Functions

## Linear functions

A function $T: \C \to \C$ is linear if there is some $a \in \C$ so that $T(z) = az$

These functions are a composition of a rotation (i.e. if $\abs a = 1$) and a dilation (scaling)  (since $|a| > 0$)

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
