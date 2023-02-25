---
title: "Conditional Expectation"
publishdate: "2023-02-25"
tags:
- "probability"
---

## Definition
Let $X$ be a [random variable](statistics/random-variable.md) with [pdf](statistics/probability-density-function.md) or [pmf](statistics/probability-mass-function.md) $f_X$. If $Y$ is a discrete random variable, then the *[expected value](statistics/expectation.md) of $Y$ given $X = x$* is given by
$$\mathbb{E}(Y|X = x) = \sum_y y f_{Y|X}(y|x),$$
where $f_{Y|X}(y|x)$ is the [conditional pmf](statistics/conditional-distribution.md) of $Y$ given $X = x$, where $x$ must satisfy $f_X(x) > 0$.

If $Y$ is a continuous random variable, then the *expected value of $Y$ given $X = x$* is given by
$$\mathbb{E}(Y | X = x) = \int_{-\infty}^\infty y f_{Y|X}(y|x) \thinspace dy,$$
where $f_{Y|X}(y|x)$ is the conditional pdf of $Y$ given $X = x$, where $x$ must again satisfy $f_X(x) > 0$.

> [!tip] Tip.
> 
> The expected value of $Y$ given $X = x$ is just the expected value of the conditional distribution of $Y$ given $X = x$.

Now let $X$ and $Y$ be two arbitrary random variables. The function $\psi$, given by
$$\psi(x) = \mathbb{E}(Y | X = x), \quad x \in \mathbb{R},$$
is called the *regression curve of $Y$ on $X$*. The *conditional expectation of $Y$ given $X$* is given by $\mathbb{E}(Y|X) = \psi(X)$.

> [!warning] Note.
> 
> The conditional expectation of $Y$ given $X$ is a random variable, as it is a function of $X$. The expected value of $Y$ given $X = x$ is not a random variable.

## Properties
Let $X$, $Y$, and $Z$ be arbitrary random variables. Then the following basic properties hold:
- $\mathbb{E}(Y|Y) = Y$
- $\mathbb{E}(aY|X) = a\mathbb{E}(Y|X)$ for all $a \in \mathbb{R}$; i.e. conditional expectation is linear.
- $\mathbb{E}(X + Y | Z) = \mathbb{E}(X|Z) + \mathbb{E}(Y|Z)$
- $\mathbb{E}(Y \cdot g(Z) | Z) = g(Z)\mathbb{E}(Y|Z)$
- If $Y$ is non-negative, then $\mathbb{E}(Y|Z) \geq 0$. More generally, if $Y \geq X$, then $\mathbb{E}(Y|Z) \geq \mathbb{E}(X|Z)$.
- *(Tower Property).* $\mathbb{E}[\mathbb{E}(Y|(X, Z))|Z] = \mathbb{E}(Y|Z)$
- If $X$ and $Y$ are [independent](statistics/independence-(random-variable).md), then $\mathbb{E}(Y|X)$ is almost surely constant, and $\mathbb{E}(Y|X) = \mathbb{E}Y$ almost surely.

Let $Y$ be an arbitrary random variable. If $X$ is a discrete random variable, then
$$\mathbb{E}Y = \sum_x \mathbb{E}(Y | X = x) f_X(x),$$
and if $X$ is a continuous random variable, then
$$\mathbb{E}Y = \int_{-\infty}^\infty \mathbb{E}(Y|X = x) f_X(x) \thinspace dx.$$


## See Also
- [Conditional Variance](statistics/conditional-variance.md)
- [Law of Total Expectation](statistics/law-of-total-expectation.md)
- [Law of Total Variance](statistics/law-of-total-variance.md)
