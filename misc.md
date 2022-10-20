# wauhigseiughes

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

###### 

### sdghdoiug

$$
\begin{align*}
\lim_{n \to \infty} \abs{\frac{c_n}{c_{n+1}}} &= \lim_{n \to \infty} \abs{\frac{q^{n^2}}{q^{{(n+1)}^2}}} \\
&= \lim_{n \to \infty} \abs{\frac{q^{n^2}}{q^{n^2 + 2n + 1}}} \\
&= \lim_{n \to \infty} \abs{\frac{q^{n^2}}{q^{n^2}q^{2n + 1}}} \\
&= \lim_{n \to \infty} \abs{\frac{1}{q^{2n + 1}}} \\
\end{align*}
$$

## 3rgiuhigeh

$$
\begin{align*}
(1 + z)^\alpha &= e^{\alpha \log(1 + z)} \\
&= \sum_{n=0}^\infty \frac{\alpha^n \log(1 + z)^n}{n!} \\
&= \sum_{n=0}^\infty \frac{\alpha^n}{n!} \log(1 + z)^n \\
&= \sum_{n=0}^\infty \frac{\alpha^n}{n!} \parens{\sum_{k=1}^\infty -\frac{(-z)^k}{k}}^n \\
\end{align*}
$$

# tutorial 2022-10-20

## 7

want riemann surface of $w = z - \sqrt{z^2 - 1}$

$(z, w)$ covers some subset of $\C^2$
$$
\begin{align*}
\curlies{(z, w) : w^2 - 2zw + 1 = 0}
\end{align*}
$$
riemann surface is covering space $X$

![image-20221020103401515](/Users/rikin/Library/Application Support/typora-user-images/image-20221020103401515.png)

$z^2 - 1 = (z + 1)(z - 1)$

can visualize this by considering loops centred at $-1$ and $1$

![image-20221020103943754](/Users/rikin/Library/Application Support/typora-user-images/image-20221020103943754.png)

can consider their product by adding angles from loops

end up with one big loop that circles twice ($z^2$ -> go around twice)

want to lift loops to $X$

## 2

only so many transformations that a FLT can do

solve for each "type" of transformation, then argue that each FLT is a composition of them

## General strategy for riemann surfaces

- find eqn of surface (graph in $\C^2$)
- find out how many branch points there are (how many multi valued points?)
- glue those points together across sheets
