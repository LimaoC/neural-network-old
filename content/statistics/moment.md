---
title: "Moment"
publishdate: "2022-12-27"
tags:
- "statistics"
---

## Definition
Let $X$ be an arbitrary [random variable](statistics/random-variable.md). Then the n-th *moment* of $X$ is given by $\mathbb{E}(X^n)$.

For example, the [expectation](statistics/expectation.md) of $X$ is the first moment of $X$, and the [variance](statistics/variance.md) of $X$ is the second moment of $X$ minus the square of the first moment of $X$.

> [!info] Aside.
> 
> There are also other types of moments. For an arbitrary random variable $X$,
> - $\mathbb{E}((X - \mu_X)^n)$ is called the n-th *central moment* of $X$. For example, the variance of $X$ is the second central moment of $X$.
> - $\mathbb{E}(((X - \mu_X)/\sigma_X)^n)$ is called the n-th *standardized moment* of $X$. For example, the third standardized moment of $X$ is called the *skewness* of $X$.
> - $\mathbb{E}(X(X - 1)\cdots(X - (n - 1)))$ is called the n-th *factorial moment* of $X$.
