---
title: "Order Statistic"
publishdate: "2023-02-26"
tags:
- "probability"
---

## Definition
Let $X_1, \dots, X_n$ be a collection of iid [random variables](statistics/random-variable.md), that is they are a *random sample*. We denote the in-order arrangement of these random variables by $X_{(1)}, \dots, X_{(n)}$, i.e. the minimum is given by $X_{(1)}$ and the maximum is given by $X_{(n)}$. Then $X_{(r)}$ (for $1 \leq r \leq n$) is called the *$r$-th order statistic.* 

Let $F$ be the common [cumulative distribution function](statistics/cumulative-distribution-function.md) of $X_1, \dots, X_n$. Then
$$\begin{align*}
F_{X_{(r)}}(y) &= \mathbb{P}(X_{(r)} \leq y) \\
&= \mathbb{P}(\text{at least $r$ of $X_1, \dots, X_n$ are} \leq y) \\
&= \sum_{j=r}^n \mathbb{P}(\text{exactly $j$ of $X_1, \dots, X_n$ are} \leq y) \\
&= \sum_{j=r}^n \binom{n}{j} (F(y))^j (1 - F(y))^{n-j}.
\end{align*}$$

## Example (Common Probability Density Function)
If $X_1, \dots, X_n$ are continuous random variables with common [probability density function](statistics/probability-density-function.md) $f$, then
$$f_{X_{(r)}}(y) = F_{X_{(r)}}'(y) = r \binom{n}{r} (F(y))^{r-1}(1 - F(y))^{n-r} f(y).$$

By symmetry, the order statistics have [joint pdf](statistics/joint-distribution.md) given by
$$g(y_1, \dots, y_n) = \begin{cases}
n! \prod_{i=1}^n f(y_i) & \text{if } y_1 < \cdots < y_n \\
0 & \text{otherwise.}
\end{cases}$$

> [!tip] Tip.
> 
> We can think of this as the joint pdf of $X_1, \dots, X_n$, which is $\prod_{i=1}^n f(y_i)$, multiplied by the number of arrangements of the sample,  $n!$.

For example, the minimum of the sample has distribution function
$$F_{X_{(1)}}(y) = 1 - (1 - F(y))^n,$$
and in the continuous case,
$$f_{X_{(1)}}(y) = n(1 - F(y))^{n-1}f(y).$$
The maximum of the sample has distribution function
$$F_{X_{(n)}} = (F(y))^n,$$
and in the continuous case,
$$f_{X_{(n)}}(y) = n(F(y))^{n-1}f(y).$$
