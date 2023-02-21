---
title: "Independence (Random Variable)"
publishdate: "2023-02-18"
tags:
- "statistics"
---

## Definition
Two [random variables](statistics/random-variable.md) $X$ and $Y$ are said to be *independent* if and only if the product of their marginal [cdfs](statistics/cumulative-distribution-function.md) is equal to their [joint cdf](statistics/joint-cumulative-distribution-function.md). That is, $F_{X, Y} = F_XF_Y$, or
$$\mathbb{P}(X \leq x, Y \leq y) = \mathbb{P}(X \leq x)\mathbb{P}(Y \leq y)$$
for all $x, y \in \mathbb{R}$.

Equivalently, $X$ and $Y$ are independent if and only if the product of their marginal [pdfs](statistics/probability-density-function.md) is equal to their joint pdf *\[link needed\]*. That is, $f_{X, Y} = f_X f_Y$.

## See Also
- [Independence (Event)](statistics/independence-(event).md)
