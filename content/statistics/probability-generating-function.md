---
title: "Probability Generating Function"
publishdate: "2022-12-29"
tags:
- "statistics"
---

## Definition
Let $X$ be a non-negative [discrete random variable](statistics/random-variable.md). Then the *probability generating function* (PGF) of $X$ is defined as
$$G(z) = \mathbb{E}(z^X) = \sum_{k=0}^\infty z^k \mathbb{P}(X = k), \quad |z| \leq 1,$$
where we often write $G_X(z)$ to emphasize the role of $X$ (especially when dealing with multiple PGFs).

Mathematically, $G$ is a *power series* *\[link needed\]* with coefficients $a_k = \mathbb{P}(X = k)$, and converges *\[link needed\]* for all $|z| \leq 1$ and often for $|z| \leq R$ where $R > 1$. As such, it can be differentiated or integrated term-wise.

## Properties
Let $X$ be a non-negative discrete random variable with PGF $G(z)$. Then $G$ has the following properties:
1. $G$ determines the distribution of $X$ uniquely with
   $$\mathbb{P}(X = k) = \frac{G^{(k)}(0)}{k!}, \quad k \geq 1.$$
2. The [expectation](statistics/expectation.md) of $X$ is given by $\mathbb{E}X = G'(1)$.
3. More generally, $\mathbb{E}(X(X - 1)\cdot(X - (k - 1))) = G^{(k)}(1), k \geq 1$, i.e. $G^{(k)}(1)$ gives the k-th [factorial moment](statistics/moment.md) of $X$.
4. From 2 and 3, we have that the [variance](statistics/variance.md) of $X$ is given by $\text{Var}(X) = G''(1) + G'(1) - (G'(1))^2$.

> [!warning] Note.
> 
> $G'(1)$ (and $G^{(k)}(1)$ etc.) may not be defined if $R = 1$, in which case we conventionally take $G(1)$ to be the limit from below, i.e. $G(1) = \lim_{z\to1^-} G(z)$.
