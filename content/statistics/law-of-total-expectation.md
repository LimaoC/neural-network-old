---
title: "Law of Total Expectation"
publishdate: "2023-02-25"
tags:
- "probability"
---

## Definition
Let $X$ and $Y$ be arbitrary [random variables](statistics/random-variable.md). Then
$$\mathbb{E}(\mathbb{E}(Y|X)) = \mathbb{E}Y,$$
where $\mathbb{E}Y$ is the [expectation](statistics/expectation.md) of $Y$ and $\mathbb{E}(Y|X)$ is the [conditional expectation](statistics/conditional-expectation.md) of $Y$ given $X$.

## Proof
Suppose $X$ and $Y$ are [jointly continuous](statistics/joint-distribution.md). Then for $x$ such that $f_X(x) > 0$,
$$\psi(x) = \int_{-\infty}^\infty y f_{Y|X}(y|x) \thinspace dy.$$
Using [LOTUS](statistics/law-of-the-unconscious-statistician.md), it follows that
$$\begin{align*}
\mathbb{E}(\psi(X)) &= \int_{-\infty}^\infty \psi(x) f_X(x) \thinspace dx \\
&= \int_{-\infty}^\infty \left(\int_{-\infty}^\infty y f_{Y|X}(y|x) \thinspace dy \right)f_X(x) \thinspace dx \\
&= \int_{-\infty}^\infty y \left(\int_{-\infty}^\infty f_{Y|X}(y|x) f_X(x) \thinspace dx\right) \thinspace dy \\
&= \int_{-\infty^\infty} y f_Y(y) \thinspace dy \\
&= \mathbb{E}Y.
\end{align*}$$
The proof is analogous when one or both of $X$ and $Y$ are discrete; just replace the appropriate integrals with summations.

## See Also
- [Law of Total Variance](statistics/law-of-total-variance.md)