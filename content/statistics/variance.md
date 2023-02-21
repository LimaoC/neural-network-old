---
title: "Variance"
publishdate: "2022-12-27"
tags:
- "probability"
---

## Definition
Let $X$ be an arbitrary [random variable](statistics/random-variable.md). Then the *variance* of $X$, denoted $\text{Var}(X)$, is given by
$$\text{Var}(X) = \mathbb{E}(X - \mu_X)^2,$$ and quantities the spread of the distribution of $X$, or the variation about the mean, $\mu_X$.

The variance may also be written as:
$$\text{Var}(X) = \mathbb{E}(X - \mu_X)^2 = \mathbb{E}(X^2) - 2\mu_x\mathbb{E}X + \mu_X^2 = \mu_X^2 = \mathbb{E}(X^2) - \mu_X^2.$$

The variance of $X$ is also commonly denoted by $\sigma_X^2$, where $\sigma_X$ is the *standard deviation* of $X$.

## Properties
If $X$ is any arbitrary random variable, then $\text{Var}(aX + b) = a^2\text{Var}(X)$ for all $a$ and $b$. \
**Proof.** We have
$$\begin{align*}
\text{Var}(aX + b) &= \mathbb{E}(aX + b)^2 - (\mathbb{E}(aX + b))^2 \\
&= \mathbb{E}(a^2X^2 + 2abX + b^2) - (a\mathbb{E}X + b)^2 \\
&= \mathbb{E}(a^2X^2 + 2abX + b^2) - (a^2(\mathbb{E}X)^2 + 2ab\mathbb{E}X + b^2) \\
&= a^2(\mathbb{E}(X^2) - (\mathbb{E}X)^2) \\
&= a^2\text{Var}(X)
\end{align*}$$
