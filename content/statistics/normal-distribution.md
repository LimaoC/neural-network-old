---
title: "Normal Distribution"
publishdate: "2023-02-17"
tags:
- "statistics"
---

## Properties
### Probability Density Function
Let $X$ be a normal [random variable](statistics/random-variable.md) with parameters $\mu$ and $\sigma^2$; that is, $X \sim \mathcal{N}(\mu, \sigma^2)$. Then $X$ has [pdf](statistics/probability-density-function.md)
$$f_X(x) = \frac{1}{\sigma\sqrt{2\pi}} \text{exp}\left(-\frac{(x - \mu)^2}{2\sigma^2}\right)$$
for $x \in \mathbb{R}$. If $X \sim \mathcal{N}(0, 1)$, then $X$ is said to have a *standard* normal distribution with pdf
$$f_X(x) = \frac{1}{\sqrt{2\pi}} \text{exp}\left(-\frac{x^2}{2}\right).$$

### Expectation
The [expectation](statistics/expectation.md) of $X$ is given by $\mathbb{E}X = \mu$.

> [!info] Aside.
> 
> The median and mode of $X$ are also given by $\mu$.

### Variance
The [variance](statistics/variance.md) of $X$ is given by $\text{Var}(X) = \sigma^2$.

### Standardization
Let $X \sim \mathcal{N}(\mu, \sigma^2)$ and define $Z := (X - \mu)/\sigma$. Then
$$\mathbb{E}Z = \mathbb{E}X/\sigma - \mu/\sigma = 0$$
and
$$\text{Var}(Z) = \text{Var}(X)/\sigma^2 = 1,$$
and it can be shown that $Z \sim \mathcal{N}(0, 1)$.
