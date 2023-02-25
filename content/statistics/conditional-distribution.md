---
title: "Conditional Distribution"
publishdate: "2023-02-25"
tags:
- "probability"
---

## Definition
### Conditional Probability Function
Let $X$ and $Y$ be arbitrary [random variables](statistics/random-variable.md) (i.e., any combination of discrete or continuous random variables). Then the *conditional probability function* of $Y$ given $X$ is given by
$$f_{Y|X}(y|x) = f_{X, Y}(x, y)/f_X(x)$$
whenever $f_X(x) > 0$, where $f_{X, Y}$ is the [joint probability function](statistics/joint-distribution.md) of $X$ and $Y$.

The marginal probability function ([mass](statistics/probability-mass-function.md) or [density](statistics/probability-density-function.md)) of $Y$ is given by
$$f_Y(y) = \sum_{\text{all } x} f_{Y|X}(y|x)f_X(x), \quad y \in \mathbb{R}$$
when $X$ is a discrete random variable (and thus $f_X$ is the probability mass function of $X$), and
$$f_Y(y) = \int_{\text{all } x}f_{Y|X}(y|x) f_X(x) \thinspace dx, \quad y \in \mathbb{R}$$
when $X$ is a continuous random variable (and thus $f_X$ is the probability density function of $X$).

### Conditional Cumulative Distribution Function
Let $Y$ be an arbitrary random variable with [cdf](statistics/cumulative-distribution-function.md) $F_Y$ and let $X$ be a discrete random variable with pmf $f_X$. The *conditional cumulative distribution function* of $Y$ given $X = x$ is given by
$$F_{Y|X}(y|x) = \mathbb{P}(Y \leq y | X = x), \quad y \in \mathbb{R},$$
where $x$ must satisfy $\mathbb{P}(X = x) > 0$.

Let $X$ and $Y$ be discrete random variables. By the [Law of Total Probability](statistics/law-of-total-probability.md), we have
$$\mathbb{P}(Y \leq y) = \sum_i \mathbb{P}(Y \leq y | X = x_i)\mathbb{P}(X = x_i),$$
where $\mathbb{P}(Y \leq y|X = x_i)$ is the conditional cdf of $Y$ given $X = x_i$. Similarly,
$$\mathbb{P}(Y = y) = \sum_i \mathbb{P}(Y = y|X = x_i)\mathbb{P}(X = x_i),$$
that is,
$$f_Y(y) = \sum_i f_{Y|X}(y|x_i) f_X(x_i).$$

With $Y$ defined the same as above, let $X$ now be a continuous random variable with pdf $f_X$. Then, under mild conditions, there exists a function $F_{Y|X}$, the conditional cdf of $Y$ given $X$, such that
$$F_Y(y) = \int_{-\infty}^\infty F_{Y|X}(y|x) f_X(x) \thinspace dx, \quad \forall y \in \mathbb{R},$$
by the [Law of Total Probability](statistics/law-of-total-probability.md). We can also interpret $F_{Y|X}$ as such:
$$F_{Y|X}(y|x) = \lim_{h\to0^+} \mathbb{P}(Y \leq y | x \leq X \leq x + h).$$

If both $X$ and $Y$ are jointly continuous random variables, then there exists a function $f_{Y|X}$, the *conditional probability density function* of $Y$ given $X$, such that
$$F_{Y|X}(y|x) = \int_{-\infty}^y f_{Y|X}(u|x) \thinspace du, \quad y \in \mathbb{R},$$
satisfying $f_{Y|X}(y|x) = f_{X, Y}(x, y) / f_X(x)$ whenever $f_X(x) > 0$, where $f_{X, Y}$ is the joint pdf of $X$ and $Y$.

> [!tip] Tip.
> 
> The notation $y|x$ is used to emphasize that $F_{Y|X}(y|x)$ and $f_{Y|X}(y|x)$ depend on $x$. Instead of thinking about them as functions of two variables, we can instead think about varying $x$ to obtain a *family* of functions of just one variable, $y$. This can be useful when dealing with two unknowns, where we may want to condition on one unknown and effectively treat it as a constant.
