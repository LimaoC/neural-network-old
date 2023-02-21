---
title: "Moment Generating Function"
publishdate: "2022-12-29"
tags:
- "statistics"
---

## Definition
Let $X$ be an arbitrary [random variable](statistics/random-variable.md). Then the *moment generating function* (MGF) of $X$ is defined as
$$M(t) = \mathbb{E}(e^{tX}), \quad t \in \mathbb{R}$$
provided the expectation exists on some open interval $I$ containing 0, where we often write $M_X(z)$ to emphasize the role of $X$ (especially with dealing with multiple MGFs).

If $X$ is a discrete random variable with range $S$,
$$M_X(t) = \sum_{x \in S} e^{tx}f_X(x), \quad t \in I$$
and if $X$ is a continuous random variable,
$$M_X(t) = \int_{-\infty}^\infty e^{tx} f_X(x) \thinspace dx, \quad t \in I.$$

> [!warning] Note.
> 
> If $X$ is a non-negative discrete random variable (that is, it takes values in the non-negative integers), then $M_X(t) = G_X(e^t)$ for $t \in I$, where $G_X$ is the [PGF](statistics/probability-generating-function.md) of $X$, in which case we would usually use PGFs over MGFs.

## Properties
Let $X$ be an arbitrary random variable with MGF $M(t)$. Then $M$ has the following properties:
1. $M$ determines the distribution of $X$ uniquely; two MGFs are the same if and only if their [cumulative distribution functions](statistics/cumulative-distribution-function.md) are the same.
2. The [expectation](statistics/expectation.md) of $X$ is given by $\mathbb{E}X = M'(0)$.
3. More generally, $\mathbb{E}(X^n) = M^{(n)}(0), n \geq 1$, i.e. $M^{(n)}(0)$ gives the n-th [moment](statistics/moment.md) of $X$.
4. From 2 and 3, we have that the [variance](statistics/variance.md) of $X$ is given by $\text{Var}(X) = M''(0) - (M'(0))^2$.