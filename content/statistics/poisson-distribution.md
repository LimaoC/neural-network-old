---
title: "Poisson Distribution"
publishdate: "2023-01-01"
tags:
- "probability"
---

## Definition
The *Poisson distribution* with parameter $\lambda > 0$ (mean rate) is the discrete probability distribution of the number of events occurring in a fixed time interval where events occur independently of each other at a constant mean rate of occurrences.

## Properties
### Probability Mass Function
Let $X$ be a Poisson [random variable](statistics/random-variable.md) with parameter $\lambda > 0$; that is, $X \sim \text{Poi}(\lambda)$. Then $X$ has [pmf](statistics/probability-mass-function.md)
$$f_X(x) = \mathbb{P}(X = x) = \frac{\lambda^x e^{-\lambda}}{x!}$$
for a non-negative integer $x$ (number of occurrences), and $0$ otherwise.

### Expectation
The [expectation](statistics/expectation.md) of $X$ is given by
$$\mathbb{E}X = \lambda.$$

### Variance
The [variance](statistics/variance.md) of $X$ is given by
$$\text{Var}(X) = \lambda.$$

### Connection to binomial distribution
The Poisson $\text{Poi}(np)$ distribution is the limiting distribution of a [binomial](statistics/binomial-distribution.md) $\text{Bin}(n, p)$ distribution. To see this, suppose $X \sim \text{Bin}(n, p)$ and let $\lambda = np > 0$. Now let the number of trials $n$ tend to infinity, whilst holding the product $np$ constant. The expectation of $X$ is given by
$$\mathbb{E}X = np = \lambda,$$
and the variance of $X$ is given by
$$\text{Var}(X) = np(1 - p) = n \left(\frac{\lambda}{n}\right) \left(1 - \frac{\lambda}{n}\right) = \lambda \left(1 - \frac{\lambda}{n}\right),$$
which tends to $\lambda$ as $n \to \infty$. The pmf of $X$, for support $x \in 0, 1, 2, \dots$, is given by
$$\begin{align*}
\mathbb{P}(X = x) &= \binom{n}{x} \left(\frac{\lambda}{n}\right)^x \left(1 - \frac{\lambda}{n}\right)^{n-x} \\
&= \frac{n \times (n - 1) \times \cdots \times (n - x + 1)}{x!} \frac{\lambda^x}{n^x} \left(1 - \frac{\lambda}{n}\right)^n \left(1 - \frac{\lambda}{n}\right)^{-x},
\end{align*}$$
where we can take the limits of each component separately:
$$\lim_{n\to\infty} \left(\frac{n \times (n - 1) \times \cdots \times (n - x + 1)}{x!} \frac{\lambda^x}{n^x}\right) = \frac{\lambda^x}{x!}$$
$$\lim_{n\to\infty} \left(1 - \frac{\lambda}{n}\right)^n = e^{-\lambda}$$
$$\lim_{n\to\infty} \left(1 - \frac{\lambda}{n}\right)^{-x} = 1,$$
yielding
$$\mathbb{P}(X = x) \to \frac{\lambda^x e^{-\lambda}}{x!},$$
which is precisely the pmf of a Poisson random variable.

It follows that the Poisson $\text{Poi}(np)$ distribution approximates the binomial $\text{Bin}(n, p)$ distribution when $n$ is sufficiently large and $p$ is sufficiently small. A good rule of thumb is to have $n \geq 20$ and $p \leq 0.05$.
