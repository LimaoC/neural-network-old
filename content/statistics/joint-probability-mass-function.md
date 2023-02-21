---
title: "Joint Probability Mass Function"
publishdate: "2023-02-19"
tags:
- "statistics"
---

## Definition
Let $X$ and $Y$ be two [discrete random variables](statistics/random-variable.md). Then the function
$$f(x, y) = \mathbb{P}(X = x, Y = y), \quad x, y \in \mathbb{R}$$
is the *joint probability (mass) function* of $X$ and $Y$. It is often denoted $f_{X, Y}(x, y)$.

If $S_X = \lbrace x_1, x_2, \dots \rbrace$ is the range of $X$ and $S_Y = \lbrace y_1, y_2, \dots \rbrace$ is the range of $Y$, then $S_{X, Y} = S_X \times S_Y$ is the range of $(X, Y)$, where $\times$ is the cross product operator, i.e. $S_{X, Y} = \lbrace (x, y) | x \in S_X, y \in S_Y \rbrace$.

## Properties
Let $X$, $Y$, and $f_{X, Y}$ be defined as above, and let $f_X$ be the marginal [pmf](statistics/probability-mass-function.md) of $X$, and $f_Y$ the marginal pmf of $Y$. Then the following properties hold:
- $f_X(x) = \sum_y f_{X, Y}(x, y)$ and $f_Y(y) = \sum_y f_{X, Y}(x, y)$
- $f_{X, Y}(x, y) > 0$ only if $(x, y) \in S_{X, Y}$
- $\sum_x \sum_y f_{X, Y}(x_i, y_j) = 1$
- $F_{X, Y}(x, y) = \sum_{u \leq x} \sum_{v \leq y} f_{X, Y}(u, v)$
