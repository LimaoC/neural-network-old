---
title: "Gamma Distribution"
publishdate: "2023-02-17"
tags:
- "statistics"
---

## Definition
The *gamma distribution* is a family of continuous probability distributions with 2 parameters; a shape parameter $\alpha$, and a rate parameter $\beta$. 

The [exponential distribution](statistics/exponential-distribution.md) is a special case of the gamma distribution. An $\text{Exp}(\lambda)$ distribution is precisely the $\text{Gamma}(1, \lambda)$ distribution.

> [!info] Aside.
> 
> Another common parametrization for the distribution uses the same shape parameter $\alpha$ and a scale parameter $\theta = 1/\beta$.

## Properties
### Probability Density Function
Let $X$ be a gamma [random variable](statistics/random-variable.md) with shape parameter $\alpha$ and rate parameter $\beta$; that is, $X \sim \text{Gamma}(\alpha, \beta)$. Then $X$ has [pdf](statistics/probability-density-function.md)
$$f_X(x) = \frac{x^{\alpha-1}\beta^\alpha e^{-\beta x}}{\Gamma(\alpha)},$$
where $\Gamma(\alpha)$ is the [gamma function](mathematics/gamma-function.md).

### Expectation
The [expectation](statistics/expectation.md) of $X$ is given by $\mathbb{E}X = \alpha/\beta$.

### Variance
The [variance](statistics/variance.md) of $X$ is given by $\text{Var}(X) = \alpha/\beta^2$.
