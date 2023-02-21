---
title: "Probability Mass Function"
publishdate: "2022-11-27"
tags:
- "statistics"
---

## Definition
If $X$ is a *[discrete random variable](statistics/random-variable.md)*, then the function
$$f(x) = \mathbb{P}(X = x), \quad x \in \mathbb{R}$$
is the *probability (mass) function* of $X$. It is often denoted $f_X(x)$.

## Properties
If $X$ is a discrete random variable taking values in $S$, then
1. $f_X(x) \geq 0$ for all real $x$
2. $\sum_{x\in S} f_X(x) = 1$.
3. $F_X(x) = \mathbb{P}(X \leq x) = \sum_{y \in S | y \leq x} f_X(y)$, where $F_X(x)$ is the [cumulative distribution function](statistics/cumulative-distribution-function.md).

## See Also
- [Probability Density Function](statistics/probability-density-function.md)
