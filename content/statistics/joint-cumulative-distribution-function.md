---
title: "Joint Cumulative Distribution Function"
publishdate: "2023-02-18"
tags:
- "statistics"
---

## Definition
Let $X$ and $Y$ be two [random variables](statistics/random-variable.md). Then the function
$$F_{X, Y}(x, y) = \mathbb{P}(X \leq x, Y \leq y)$$
is the *joint cumulative distribution function* of $X$ and $Y$.

We have
$$\mathbb{P}(X \leq x) = F_X(x) = \lim_{y\to\infty} F_{X, Y}(x, y)$$
and
$$\mathbb{P}(Y \leq y) = F_Y(y) = \lim_{x\to\infty} F_{X, Y}(x, y).$$

$F_X$ and $F_Y$ are referred to as *marginal* cumulative distribution functions.

## See Also
- [Cumulative Distribution Function](statistics/cumulative-distribution-function.md)
