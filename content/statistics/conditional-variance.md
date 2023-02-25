---
title: "Conditional Variance"
publishdate: "2023-02-25"
tags:
- "probability"
---

## Definition
The *[variance](statistics/variance.md) of $Y$ given $X = x$* is given by
$$\begin{align*}
\text{Var}(Y | X = x) &= \mathbb{E}[(Y - \mathbb{E}(Y|X = x))^2|X = x] \\
&= \mathbb{E}[Y^2 | X = x) - (\mathbb{E}(Y|X = x)]^2.
\end{align*}$$

> [!tip] Tip.
> 
> The variance of $Y$ given $X = x$ is just the variance of the conditional distribution of $Y$ given $X = x$.

## See Also
- [Conditional Expectation](statistics/conditional expectation.md)
- [Law of Total Expectation](statistics/law-of-total-expectation.md)
- [Law of Total Variance](statistics/law-of-total-variance.md)
