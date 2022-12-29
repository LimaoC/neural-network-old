---
title: "Probability Density Function"
publishdate: "2022-12-28"
tags:
- "statistics"
---

## Definition
If $X: \Omega \to \mathbb{R}$ is a *continuous [random variable](statistics/random-variable.md)*, then the function $f$ such that $f(x) \geq 0$ for all $x \in \Omega$ and
$$\mathbb{P}(x \leq X \leq y) = \int_x^y f(u)du$$
for all $x \leq y$, that is, the probability that $X$ takes on values in the interval $[x, y]$ is given by the area under the graph of the pdf from $x$ to $y$. It is often denoted $f_X(x).$

> [!warning] Note.
> 
> Note that $f(x)$ is *not* a probability; it should be thought of as a *probability density*. It is not true that $f(x) = \mathbb{P}(X = x)$ for all $x$. In fact, we have $\mathbb{P}(X = x) = 0$ for all $x$ in the support of $X$.

## Properties
If $X$ is a continuous random variable taking values in $\Omega$, then
1. $f_X(x) \geq 0$ for all real $x$
2. $\int_{-\infty}^\infty f_X(u) du = 1$
3. $F_X(x) = \mathbb{P}(X \leq x) = \int_{-\infty}^x f_X(u) du$, where $F_X(x)$ is the [cumulative distribution function](statistics/cumulative-distribution-function.md). Additionally, if $f_X(x)$ exists, $F'_X(x) = f_X(x)$.
