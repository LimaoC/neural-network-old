---
title: "Binomial Distribution"
publishdate: "2022-12-31"
tags:
- "statistics"
---

## Definition
The *binomial distribution* with parameters $n$ (number of trials) and $p$ (success probability) is the discrete probability distribution of the number of successes in $n$ independent experiments, each taking on the value 1 with probability $p$ and the value 0 with probability $1 - p$.

The [Bernoulli distribution](statistics/bernoulli-distribution.md) is a special case of the binomial distribution with $n = 1$.

## Properties
### Probability Mass Function
Let $X$ be a binomial [random variable](statistics/random-variable.md) with $n$ trials and success probability $p$; that is, $X \sim \text{Bin}(n, p)$. Then $X$ has [pmf](statistics/probability-mass-function.md)
$$f_X(x) = \mathbb{P}(X = x) = \binom{n}{x} p^x (1 - p)^{n-x}$$
for a non-negative integer $x$ (number of successes), and $0$ otherwise. The quantity
$$\binom{n}{x} = \frac{n!}{x!(n-x)!}$$
is the *binomial coefficient* *\[link needed\]*. Note that omitting the binomial coefficient gives us the pmf of a Bernoulli random variable; the binomial coefficient gives us the number of ways in which we can arrange $x$ successes and $n - x$ failures.
$X$ has [cdf](statistics/cumulative-distribution-function.md)
$$F_X(x) = \mathbb{P}(X \leq x) = \sum_{k=0}^{\lfloor k \rfloor} \binom{n}{k} p^k (1 - p)^{n-k}.$$

### Expectation
The [expectation](statistics/expectation.md) of $X$ is given by
$$\mathbb{E}X = np,$$
which follows from applying linearity of expectation to the fact that $X$ is equivalent to the sum of $n$ Bernoulli random variables each with expectation $p$.

### Variance
The [variance](statistics/variance.md) of $X$ is given by
$$\text{Var}(X) = np(1 - p),$$
which follows from the fact that the variance of the sum of independent random variables is the sum of the variances *\[link needed\]*.
