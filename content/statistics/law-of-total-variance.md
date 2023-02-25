---
title: "Law of Total Variance"
publishdate: "2023-02-25"
tags:
- "probability"
---

## Definition
Let $X$ and $Y$ be arbitrary random variables. Then
$$\text{Var}(Y) = \mathbb{E}(\text{Var}(Y|X)) + \text{Var}(\mathbb{E}(Y|X)),$$
where $\text{Var}(Y|X)$ is the [conditional variance](statistics/conditional-variance.md) of $Y$ given $X$, and $\mathbb{E}(Y|X)$ is the [conditional expectation](statistics/conditional-expectation.md) of $Y$ given $X$.

## Proof
The law of total variance can be proved using the [law of total expectation](statistics/law-of-total-expectation.md). We have
$$\text{Var}(Y) = \mathbb{E}(Y^2) - (\mathbb{E}Y)^2$$
from the definition of [variance](statistics/variance.md). Then
$$\mathbb{E}(Y^2) = \mathbb{E}(\mathbb{E}(Y^2 | X)) = \mathbb{E}[\text{Var}(Y|X) + (\mathbb{E}(Y|X))^2]$$
using the law of total expectation and the definition of variance again. Then by rewriting $(\mathbb{E}Y)^2$ as $\mathbb{E}(\mathbb{E}(Y|X))^2$ using the law of total expectation, we have
$$\begin{align*}
\mathbb{E}(Y^2) - (\mathbb{E}Y)^2 &= \mathbb{E}[\text{Var}(Y|X) + \mathbb{E}(Y|X)^2] - \mathbb{E}(\mathbb{E}(Y|X))^2 \\
&= \mathbb{E}(\text{Var}(Y|X)) + (\mathbb{E}[\mathbb{E}(Y|X)^2] - \mathbb{E}(\mathbb{E}(Y|X))^2) \\
&= \mathbb{E}(\text{Var}(Y|X)) + \text{Var}(\mathbb{E}(Y|X)).
\end{align*}$$
