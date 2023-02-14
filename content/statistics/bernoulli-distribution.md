---
title: "Bernoulli Distribution"
publishdate: "2022-12-31"
tags:
- "statistics"
---

## Definition
The *Bernoulli distribution* is the discrete probability distribution with parameter $p$ (success probability) that takes the value 1 with probability $p$ and the value 0 with probability $1 - p$.

The Bernoulli distribution is a special case of the [binomial distribution](statistics/binomial-distribution.md) with $n = 1$.

## Properties
### Probability Mass Function
Let $X$ be a *Bernoulli [random variable](statistics/random-variable.md)* with success probability $p$; that is, $X \sim \text{Ber}(p)$. Then $X$ has [pmf](statistics/probability-mass-function.md)
$$f_X(x) = \mathbb{P}(X = x) = \begin{cases}
p, && \text{if } x = 1 \\
1 - p, && \text{if } x = 0 \\
0, && \text{otherwise}.
\end{cases}$$
and [cdf](statistics/cumulative-distribution-function.md)
$$F_X(x) = \mathbb{P}(X \leq x) = \begin{cases}
0, && \text{if } x < 0 \\
1 - p, && \text{if } 0 \leq x < 1 \\
1, && \text{if } x >= 1.
\end{cases}$$

### Expectation
The [expectation](statistics/expectation.md) of $X$ is given by
$$\mathbb{E}X = 0 \cdot (1 - p) + 1 \cdot p = p.$$

### Variance
The [variance](statistics/variance.md) of $X$ is given by
$$\begin{align*}
\text{Var}(X) &= \mathbb{E}(X^2) - (\mathbb{E}X)^2 \\
&= (0^2 \cdot (1 - p) + 1^2 \cdot p) - p^2 \\
&= p - p^2 = p(1 - p).
\end{align*}$$
