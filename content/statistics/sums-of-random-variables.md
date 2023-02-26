---
title: "Sums of Random Variables"
publishdate: "2023-02-26"
tags:
- "probability"
---

## Definition
### Discrete Random Variables
Let $X$ and $Y$ be two [discrete random variables](statistics/random-variable.md) with $Z := X + Y$. Then we have $f_Z(z) = \sum_x f_{Z|X}(z | x) f_X(x)$ for $z \in \mathbb{R}$ using the [law of total probability](statistics/law-of-total-probability.md) (see [conditional distribution](statistics/conditional-distribution.md)). We can then write
$$f_{Z|X}(z|x) = \mathbb{P}(Z = z | X = x) = \mathbb{P}(Y = z - x | X = x),$$
and thus $f_Z(z) = \sum_x f_{Y|X}(z - x | x) f_X(x)$ for $z \in \mathbb{R}$, or equivalently, $f_Z(z) = \sum_x f_{X, Y}(x, z - x)$ for $z \in \mathbb{R}$, where $f_{X, Y}$ is the [joint pmf](statistics/joint-distribution.md) of $X$ and $Y$. If we instead condition on $Y$, then
$$f_Z(z) = \sum_y f_{X|Y}(z - y|y) f_Y(y), \quad z \in \mathbb{R},$$
or equivalently $f_Z(z) = \sum_x f_{X, Y}( z- y, y)$ for $z \in \mathbb{R}$. If $X$ and $Y$ are also [independent](statistics/independence-(random-variable).md), then
$$f_Z(z) = \sum_x f_X(x) f_Y(z - x) = \sum_y f_X(z - y)f_Y(y). \quad (*)$$

Let $X$ and $Y$ be independent non-negative integer discrete random variables with [pmfs](statistics/probability-mass-function.md) $f_X$ and $f_Y$ respectively, and define $Z := X + Y$. Then $Z$ is also a non-negative discrete random variable, and its probability mass function is given by
$$f_Z(m) = \sum_{n=0}^m f_X(n)f_Y(m - n), \quad \text{for } m = 0, 1, \dots.$$

### Continuous Random Variables
Let $X$ and $Y$ be two continuous random variables with $Z := X + Y$. Then we have $f_Z(z) = \int_{-\infty}^\infty f_{Z|X}(z | x) f_X(x) \thinspace dx$ for $z \in \mathbb{R}$ using the law of total probability (similarly to the discrete case). Since $Z = X + Y$, the distribution of $Z$ conditional on $X = x$ is the same as the distribution of $Y + x$ condition on $X = x$. That is,
$$f_{Z|X}(z|x) = f_{Y|X}(z - x|x).$$
Hence
$$f_Z(z) = \int_{-\infty}^\infty f_{Y|X}(z - x|x) f_X(x) \thinspace dx, \quad z \in \mathbb{R},$$
or equivalently, $f_Z(z) = \int_{-\infty}^\infty f_{X, Y}(x, z - x) \thinspace dx$ for $z \in \mathbb{R}$. If we instead condition on $Y$, then
$$f_Z(z) = \int_{-\infty}^\infty f_{X|Y}(z - y | y) f_Y(y) \thinspace dy, \quad z \in \mathbb{R}$$
or equivalently, $f_Z(z) = \int_{-\infty}^\infty f_{X, Y}(z - y, y) \thinspace dx$ for $z \in \mathbb{R}$. If $X$ and $Y$ are also independent, then
$$f_Z(z) = \int_{-\infty}^\infty f_X(x) f_Y(z - x) \thinspace dx = \int_{-\infty}^\infty f_X(z - y) f_Y(y) \thinspace dy, \quad z \in \mathbb{R}.$$

Let $X$ and $Y$ be independent non-negative continuous random variables with [pdfs](statistics/probability-density-function.md) $f_X$ and $f_Y$ respectively, and define $Z := X + Y$. Then $Z$ is also a non-negative continuous random variable, and its probability density function is given by
$$f_Z(z) = \int_0^z f_X(x) f_Y(z - x) \thinspace dx, \quad \text{for } z \geq 0.$$

> [!info] Aside.
> 
> If $X$ and $Y$ are independent, the probability function of $Z$ is called the *convolution* of the probability functions of $X$ and $Y$, written $f_Z = f_X * f_Y = f_Y * f_X*$. This implies $f_{X_1 + \cdots + X_n} = f_{X_1} * \cdots * f_{X_n}$ if $X_1, \dots, X_n$ are mutually independent.

### Probability Generating Functions, Moment Generating Functions
When $X$ and $Y$ are independent non-negative discrete random variables, then
$$\mathbb{E}(z^{X+Y}) = \mathbb{E}(z^X z^Y) = \mathbb{E}(z^X)\mathbb{E}(z^Y),$$
where we use the independence of $X$ and $Y$ in the last step. That is, the [probability generating function](statistics/probability-generating-function.md) of the sum is the product of the probability generating functions. Also,
$$\mathbb{E}(e^{t(X + Y)}) = \mathbb{E}(e^{tX}e^{tY}) = \mathbb{E}(e^{tX})\mathbb{E}(e^{tY}), \quad t \in \mathbb{R},$$
that is the [moment generating function](statistics/moment-generating-function.md) of the sum is also the product of the moment generating functions.

> [!tip] Tip.
> 
> It is often easier to work with a distribution's PGF or MGF to handle sums, rather than their probability functions.
