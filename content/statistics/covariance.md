---
title: "Covariance"
publishdate: "2023-02-22"
tags:
- "probability"
---

## Definition
Let $X$ and $Y$ be two [random variables](statistics/random-variable.md). The *covariance* of $X$ and $Y$ is given by
$$\text{Cov}(X, Y) = \mathbb{E}[(X - \mathbb{E}X)(Y - \mathbb{E}Y)] = \mathbb{E}(XY) - \mathbb{E}X\mathbb{E}Y.$$

We can apply [LOTUS](statistics/law-of-the-unconscious-statistician.md) to evaluate $\mathbb{E}(XY)$. In the case that $X$ and $Y$ are jointly discrete, we have
$$\mathbb{E}XY = \sum_i \sum_j x_i y_j f_{X, Y}(x_i, y_j),$$
where $f_{X, Y}$ is the [joint pmf](statistics/joint-distribution.md) of $X$ and $Y$.
In the case that $X$ and $Y$ are jointly continuous, we have
$$\mathbb{E}XY = \int_{-\infty}^\infty \int_{-\infty}^\infty xy f_{X, Y}(x, y) \thinspace dxdy,$$
where $f_{X, Y}$ is the [joint pdf](statistics/joint-distribution.md) of $X$ and $Y$.

## Properties
The covariance of $X$ and $X$ is equivalent to the [variance](statistics/variance.md) of $X$, i.e. $\text{Cov}(X, X) = \text{Var}(X)$.

For any $a, b, c, d \in \mathbb{R}$, we have $\text{Cov}(aX + b, cY + d) = ac\text{Cov}(X, Y)$. It follows that if either $X$ or $Y$ is constant, then $\text{Cov}(X, Y) = 0$.

- For any collection of random variables $X_1, \dots, X_n$, we have
  $$\text{Var}\left(\sum_{i=1}^n X_i\right) = \sum_{i=1}^n \sum_{j=1}^n \text{Cov}(X_i, X_j) = \sum_i \text{Var}(X_i) + \sum_i \sum_{j\neq i}\text{Cov}(X_i, X_j).$$
- More generally, for any collections of random variables $X_1, \dots, X_n$ and $Y_1, \dots, Y_m$, we have
  $$\text{Cov}(\sum_{i=1}^n X_i, \sum_{j=1}^m Y_j) = \sum_{i=1}^n\sum_{j=1}^m \text{Cov}(X_i, Y_j).$$
## See Also
- [Correlation](statistics/correlation.md)
