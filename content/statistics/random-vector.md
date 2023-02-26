---
title: "Random Vector"
publishdate: "2023-02-26"
tags:
- "probability"
---

## Definition
A [random vector](statistics/random-vector.md) is a vector composed of $n$ [random variables](statistics/random-variable.md):
$$\boldsymbol{X} = (X_1, \dots, X_n)^T.$$
In this case, $\boldsymbol{X}$ is said to be an $n$-dimensional random vector.

The [cdf](statistics/cumulative-distribution-function.md) of $\boldsymbol{X}$ is determined completely by the [joint cdf](statistics/joint-distribution.md) $F : \mathbb{R}^n \to [0, 1]$, given by
$$F(\boldsymbol{x}) = \mathbb{P}(X_1 \leq x_1, \dots, X_n \leq x_n),$$
for $\boldsymbol{x} = (x_1, \dots, x_n)^T \in \mathbb{R}^n.$

The marginal distributions of the $n$ individual random variables, the marginal joint distributions of subcollections of $X_1, \dots, X_n$, and the various [conditional distributions](statistics/conditional-distribution.md) of $X_1, \dots, X_n$ are all defined as well.
