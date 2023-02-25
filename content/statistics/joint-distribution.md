---
title: "Joint Distribution"
publishdate: "2023-02-19"
tags:
- "probability"
---

## Definition
### Joint Probability Mass Function
Let $X$ and $Y$ be two [discrete random variables](statistics/random-variable.md). Then the function
$$f_{X, Y}(x, y) = \mathbb{P}(X = x, Y = y), \quad x, y \in \mathbb{R}$$
is the *joint probability (mass) function* of $X$ and $Y$.

If $S_X = \lbrace x_1, x_2, \dots \rbrace$ is the range of $X$ and $S_Y = \lbrace y_1, y_2, \dots \rbrace$ is the range of $Y$, then $S_{X, Y} = S_X \times S_Y$ is the range of $(X, Y)$, where $\times$ is the Cartesian product, i.e. $S_{X, Y} = \lbrace (x, y) | x \in S_X, y \in S_Y \rbrace$.

### Joint Probability Density Function
Let $X$ and $Y$ be two continuous random variables. Then $X$ and $Y$ are said to be *jointly continuous* with *joint [probability density function](statistics/probability-density-function.md)* $f_{X, Y}$ if
$$F_{X, Y}(x, y) = \int_{-\infty}^y\int_{-\infty}^x f_{X, Y}(u, v) \thinspace dudv, \quad x, y \in \mathbb{R},$$
where $F_{X, Y}$ is the joint [cdf](statistics/cumulative-distribution-function.md) of $X$ and $Y$.

If both the partial derivatives *\[link needed\]* of $F_{X, Y}$ exist at the point $(x, y)$, then the function
$$f_{X, Y}(x, y) = \frac{\partial^2 F_{X, Y}(x, y)}{\partial x \partial y}$$
is the joint probability density function of $X$ and $Y$. The definition can also be extended for joint distributions with more than 2 variables.

Also,
$$f_{X, Y}(x, y) = f_{Y|X}(y | x)f_X(x) = f_{X|Y}(x | y)f_Y(y),$$
where $f_{Y|X}(y|x)$ and $f_{X|Y}(x|y)$ are the conditional distributions *\[link needed\]* of $Y$ given $X = x$ and $X$ given $Y = y$ respectively, and $f_X(x)$ and $f_Y(y)$ are the marginal pdfs of $X$ and $Y$ respectively.

The marginal cdfs $F_X$ and $F_Y$ can be expressed in terms of $f_{X, Y}$:
$$F_X(x) = \int_{-\infty}^x \int_{-\infty}^\infty f_{X, Y}(u, v) \thinspace dvdu, \quad x \in \mathbb{R}$$
$$F_Y(y) = \int_{-\infty}^y \int_{-\infty}^\infty f_{X, Y}(u, v) \thinspace dudv, \quad y \in \mathbb{R}$$
Similarly, the marginal pdfs $f_X$ and $f_Y$ can be expressed in terms of $f_{X, Y}$:
$$f_X(x) = \int_{-\infty}^\infty f_{X, Y}(x, y) \thinspace dy, \quad x \in \mathbb{R}$$
$$f_Y(y) = \int_{-\infty}^\infty f_{X, Y}(x, y) \thinspace dx, \quad y \in \mathbb{R}$$

### Joint Cumulative Distribution Function
Let $X$ and $Y$ be two random variables. Then the function
$$F_{X, Y}(x, y) = \mathbb{P}(X \leq x, Y \leq y)$$
is the *joint [cumulative distribution function](statistics/cumulative-distribution-function.md)* of $X$ and $Y$.

We have
$$\mathbb{P}(X \leq x) = F_X(x) = \lim_{y\to\infty} F_{X, Y}(x, y)$$
and
$$\mathbb{P}(Y \leq y) = F_Y(y) = \lim_{x\to\infty} F_{X, Y}(x, y).$$

$F_X$ and $F_Y$ are referred to as the *marginal* cumulative distribution functions.

## Properties
### Joint Probability Mass Function
Let $X$ and $Y$ be two discrete random variables, and let $f_X$ and $f_Y$ be the marginal pmfs of $X$ and $Y$ respectively. Then the following basic properties hold:
- $f_X(x) = \sum_y f_{X, Y}(x, y)$ and $f_Y(y) = \sum_y f_{X, Y}(x, y)$
- $f_{X, Y}(x, y) > 0$ only if $(x, y) \in S_{X, Y}$
- $\sum_x \sum_y f_{X, Y}(x_i, y_j) = 1$
- $F_{X, Y}(x, y) = \sum_{u \leq x} \sum_{v \leq y} f_{X, Y}(u, v)$

### Joint Probability Density Function
Let $X$ and $Y$ be jointly continuous random variables with joint pdf $f_{X, Y}$. Then the following basic properties hold:
- $f_{X, Y}(x, y) \geq 0$ for all $x, y \in \mathbb{R}$
- $\int_{-\infty}^\infty \int_{-\infty}^\infty f_{X, Y}(x, y) \thinspace dxdy = 1$
- $\mathbb{P}(a \leq X \leq b, c \leq Y \leq d) = \int_a^b \int_c^d f_{X, Y}(x, y) \thinspace dydx$ where $a, c$ can be $-\infty$ and $b, d$ can be $+\infty$, and any of the inequalities can be replaced with strict inequalities
- More generally, if $A$ is a subset of $\mathbb{R}^2$ (though technically not every subset is allowed), then
  $$\mathbb{P}((X, Y) \in A) = \iint_A f_{X, Y}(x, y) \thinspace dxdy$$
