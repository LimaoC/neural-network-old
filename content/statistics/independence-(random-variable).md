---
title: "Independence (Random Variable)"
publishdate: "2023-02-18"
tags:
- "probability"
---

## Definition
Two [random variables](statistics/random-variable.md) $X$ and $Y$ are said to be *independent* if and only if the product of their marginal [cdfs](statistics/cumulative-distribution-function.md) is equal to their [joint cdf](statistics/joint-distribution.md). That is, $F_{X, Y} = F_XF_Y$, or
$$\mathbb{P}(X \leq x, Y \leq y) = \mathbb{P}(X \leq x)\mathbb{P}(Y \leq y)$$
for all $x, y \in \mathbb{R}$.

Equivalently, $X$ and $Y$ are independent if and only if the product of their marginal [pdfs](statistics/probability-density-function.md) is equal to their joint pdf. That is, $f_{X, Y} = f_X f_Y$.

## Properties
### Correlation and covariance
For any pair of random variables $X$ and $Y$, $\mathbb{E}XY = \mathbb{E}X\mathbb{E}Y$, i.e. the [expectation](statistics/expectation.md) of the product of $X$ and $Y$ is equivalent to the product of the expectations of $X$ and $Y$. This also implies that the [covariance](statistics/covariance.md) of $X$ and $Y$ is 0, and thus $X$ and $Y$ are [uncorrelated](statistics/correlation.md). In short, independent variables are uncorrelated.
**Proof.** Suppose $X$ and $Y$ are jointly continuous. Since $X$ and $Y$ are independent, $f_{X, Y} = f_Xf_Y$, so
$$\begin{align*}
\mathbb{E}XY &= \int_{-\infty}^\infty \int_{-\infty}^\infty xy f_{X, Y}(x, y) \thinspace dxdy \\
&= \int_{-\infty}^\infty \int_{-\infty}^\infty xy f_X(x) f_Y(y) \thinspace dxdy \\
&= \int_{-\infty}^\infty xf_X(x) \thinspace dx \int_{-\infty}^\infty yf_Y(y) \thinspace dy \\
&= \mathbb{E}X\mathbb{E}Y.
\end{align*}$$
Replace the integrals with sums in the discrete case.

> [!warning] Note.
> 
> The converse is not true; uncorrelated random variables are not necessarily independent.

## See Also
- [Independence (Event)](statistics/independence-(event).md)
