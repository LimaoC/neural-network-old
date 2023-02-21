---
title: "Cumulative Distribution Function"
publishdate: "2022-11-27"
tags:
- "probability"
---

## Definition
If $X$ is an arbitrary [random variable](statistics/random-variable.md), then the function
$$F(x) = \mathbb{P}(X \leq x)$$
is the *(cumulative) distribution function* of $X$. It is often denoted $F_X(x)$.

## Properties
Let $X$ be a random variable. Then the distribution function $F$ has the following properties:
1. $F(x) \to 0$ as $x \to -\infty$.
2. $F(x) \to 1$ as $x \to \infty$.
3. $F$ is an increasing function; that is $x > y \implies F(x) \geq F(y)$.
4. $F$ is continuous from the right; that is, for all $x$, $F(x + h) \to F(x)$ as $h \downarrow 0$ (limit from above).
