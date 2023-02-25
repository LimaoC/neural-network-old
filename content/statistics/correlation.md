---
title: "Correlation"
publishdate: "2023-02-22"
tags:
- "probability"
---

## Definition
The *correlation* (or *correlation coefficient*) of two random variables $X$ and $Y$ is given by
$$\varrho(X, Y) = \frac{\text{Cov}(X, Y)}{\sqrt{\text{Var}(X)\text{Var}(Y)}},$$
where $\text{Cov}(X, Y)$ is the [covariance](statistics/covariance.md) of $X$ and $Y$.

$X$ and $Y$ are said to be *positively correlated* if $\varrho(X, Y) > 0$, *negatively correlated* if $\varrho(X, Y) < 0$, or otherwise *uncorrelated*.

## Properties
The [variance](statistics/variance.md) of the sum of random variables $X$ and $Y$ is given by
$$\text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y) + 2\text{Cov}(X, Y).$$
**Proof.** We have
$$\begin{align*}
\text{Var}(X + Y) &= \mathbb{E}((X + Y)^2) - (\mathbb{E}(X + Y))^2 \\
&= \mathbb{E}(X^2 + 2XY + Y^2) - (\mathbb{E}X + \mathbb{E}Y)^2 \\
&= \mathbb{E}(X^2) + 2\mathbb{E}(XY) + \mathbb{E}(Y^2) - ((\mathbb{E}X)^2 + 2\mathbb{E}X\mathbb{E}Y + (\mathbb{E}Y)^2) \\
&= \mathbb{E}(X^2) - (\mathbb{E}X)^2 + \mathbb{E}(Y^2) - (\mathbb{E}Y))^2 + 2(\mathbb{E}(XY) - \mathbb{E}X\mathbb{E}Y) \\
&= \text{Var}(X) + \text{Var}(Y) + 2\text{Cov}(X, Y).
\end{align*}$$

A corollary of the Cauchy-Schwarz Inequality *\[link needed\]* is that $|\varrho(X, Y)| \leq 1$. $\varrho(X, Y) = 1$ in the case where $X$ and $Y$ are linearly dependent and have an increasing linear relation, and $\varrho(X, Y) = -1$ in the case where $X$ and $Y$ are linearly independent and have a decreasing linear relation.
