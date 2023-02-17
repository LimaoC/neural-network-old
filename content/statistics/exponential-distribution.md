---
title: "Exponential Distribution"
publishdate: "2023-02-14"
tags:
- "statistics"
---

## Definition
The *exponential distribution* is the continuous probability distribution of the time between events that follow a [Poisson process](statistics/poisson-distribution.md); that is, events occur independently of each other at a constant mean rate of occurrences.

It is a specific case of the Gamma distribution *\[link needed\]*.

## Properties
### Probability Density Function
Let $X$ be an exponential [random variable](statistics/random-variable.md) with parameter $\lambda > 0$; that is, $X \sim \text{Exp}(\lambda)$. Then $X$ has [pdf](statistics/probability-density-function.md)
$$f_X(x) = \begin{cases}
0, & \text{if } x < 0 \\
\lambda e^{-\lambda x}, & \text{if } x \geq 0
\end{cases}$$
and [cdf](statistics/cumulative-distribution-function.md)
$$F_X(x) = \mathbb{P}(X \leq x) = \begin{cases}
0, & \text{if } x < 0 \\
1 - e^{-\lambda x}, & \text{if } x \geq 0.
\end{cases}$$

## Expectation
The [expectation](statistics/expectation.md) of $X$ is given by
$$\mathbb{E}X = \lambda \int_0^\infty xe^{-\lambda x}dx = \int_0^\infty e^{-\lambda x} = \frac{1}{\lambda},$$
where we can use integration by parts to solve the integral.

### Variance
We have
$$\mathbb{E}(X^2) = \int_0^\infty x^2 \lambda e^{-\lambda x} = \int_0^\infty 2xe^{-\lambda x} = \frac{2}{\lambda}\mathbb{E}X = \frac{2}{\lambda^2},$$
so the [variance](statistics/variance.md) of $X$ is given by
$$\text{Var}(X) = \mathbb{E}(X^2) - (\mathbb{E}X)^2 = \frac{2}{\lambda^2} - \left(\frac{1}{\lambda}\right)^2 = \frac{1}{\lambda^2}.$$

### Memoryless Property
The exponential distribution has the memoryless property. That is, the probability distribution of the waiting time for an event to occur, given we have waited for some initial time period, is independent of this initial time period.

For example, if an event is yet to occur after 5 minutes, the probability of requiring 1 more minute is equal to the probability of requiring 1 minute (without having waited the initial 5 minutes). In other words, there is no "memory" of the initial time period.

Mathematically, this is described as
$$\mathbb{P}(X > t + s | X > s) = \mathbb{P}(X > t).$$
This can be seen by evaluating the conditional probability on the left:
$$\begin{align*}
\mathbb{P}(X > t + s | X > s) &= \frac{\mathbb{P}(\lbrace X > t + s \rbrace \cap \lbrace X > s\rbrace)}{\mathbb{P}(X > s)} \\
&= \frac{\mathbb{P}(X > t + s)}{\mathbb{P}(X > s)} \\
&= \frac{e^{-\lambda(t + s)}}{e^{-\lambda s}} \\
&= e^{-\lambda t} \\
&= \mathbb{P}(X > t).
\end{align*}$$

> [!info] Aside.
> 
> The only *continuous* probability distribution with the memoryless property is the exponential distribution. The only *discrete* probability distribution with the memoryless property is the [geometric distribution](statistics/geometric-distribution.md).
