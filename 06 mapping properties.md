# Mapping Properties of Holomorphic Functions

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



## $w=z^\alpha$

Consider $w = z^\alpha = e^{\alpha\log z}$

This is not injective if $\alpha \neq 1$
$$
\frac{dw}{dz} = \frac{\alpha w}{z}
$$
When $w = z^{1/n}$, there are multiple roots, so we have a multi-valued function. But it may be possible to find a covering space where this function lifts to a single-valued one, called a **branched covering**.

E.g. consider $w = z^{1/2}$. Let $X = \curlies{z = w^2} \subseteq \C^2$, then the function $(z, w) \mapsto w$ is a holomorphic covering that takes $X$ to $\C$.

## Conformal mapping of circular wedge onto $D$ or $\mathbb H^+$

If a circular wedge has endpoints $a, b$, then we can straighten it out into an open wedge with straight edges/a swept arc/an infinite pizza slice by transforming it through the FLT $\dfrac{z - a}{z - b}$ (this takes $a$ to $0$ and $b$ to $\infty$)