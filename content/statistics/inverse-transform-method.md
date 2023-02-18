---
title: "Inverse Transform Method"
publishdate: "2023-02-18"
tags:
- "statistics"
---

## Definition
The *inverse-transform method* is a method of generating (one-dimensional) [random variables](statistics/random-variable.md) from a given distribution with [cdf](statistics/cumulative-distribution-function.md) $F$, which has inverse $F^{-1}$.

## Method
### Continuous Distribution
Since $U \sim \mathcal{U}[0, 1]$, the random variable $X = F^{-1}(U)$ has cdf $F$; that is,
$$\mathbb{P}(X \leq x) = \mathbb{P}(F^{-1}(U) \leq x) = \mathbb{P}(U \leq F(x)) = F(x).$$

Thus the method is as follows:
1. Generate $U \sim \mathcal{U}[0, 1]$ (see [uniform distribution](statistics/uniform-distribution.md)).
2. Return $X = F^{-1}(U)$.

### Discrete Distribution
The inverse-transform method can also be used to simulate a discrete random variable $X$ with $\mathbb{P}(X = x_i) = p_i$ for $i \in \mathbb{N}$.

1. Generate $U \sim \mathcal{U}[0, 1]$.
2. Find the smallest positive integer $k$ such that $U \leq F(X_k)$ and return $X = x_k$.

## Also See
- [Acceptance Rejection Method](statistics/acceptance-rejection-method.md)
