---
title: "Acceptance Rejection Method"
publishdate: "2023-02-18"
tags:
- "probability"
---

## Definition
The *acceptance-rejection method* is a method of generating [random variables](statistics/random-variable.md) from a given distribution with [pdf](statistics/probability-density-function.md) $f$.

## Method
First, pick a *proposal* pdf $g$ such that:
- $g$ is easy to sample from,
- there is a constant $C$ such that $Cg(x) \geq f(x)$ for all $x$; that is, $Cg(x)$ "encloses" the pdf $f$.

Then the method is as follows:
1. Generate $X \sim g$.
2. Generate $Y \sim \mathcal{U}(0, Cg(X))$.
3. If $Y \leq f(X)$, return $Z = X$. Otherwise, return to step 1.

The random variable $X$ returned by the algorithm has pdf $f$.

## Efficiency
The *efficiency* of an acceptance-rejection method is defined as
$$\mathbb{P}((X, Y) \text{ is accepted}) = \frac{\text{Area under } f}{\text{Area under } Cg} = \frac{1}{C}.$$
We would like to maximize the efficiency $1/C$ (i.e. $C$ should be close to $1$), which means choosing a proposal $g$ that is close to $f$. This is to minimize the number of rejections we have, which results in fewer iterations of the algorithm.

## See Also
- [Inverse Transform Method](statistics/inverse-transform-method.md)
