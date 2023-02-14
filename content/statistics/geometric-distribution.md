---
title: "Geometric Distribution"
publishdate: "2023-01-15"
tags:
- "statistics"
---

## Definition
The *geometric distribution* with parameter $p$ (success probability) is the discrete probability distribution of the number of [Bernoulli trials](statistics/bernoulli-distribution.md) needed before a success is achieved, taking on the positive integers ($1, 2, 3, \dots$). Alternatively, it may also be the probability distribution of the number of failures before a success is achieved, taking on the non-negative integers ($0, 1, 2, \dots$).

> [!warning] Note.
> 
> The two probability distributions described above are *not* the same (note the difference in supports). Here we will take the first distribution described as convention.

## Properties
### Probability Mass Function
Let $X$ be a geometric [random variable](statistics/random-variable.md) with parameter $p$ where $0 < p < 1$; that is, $X \sim \text{Geo}(p)$. Then $X$ has [pmf](statistics/probability-mass-function.md)
$$f_X(x) = \mathbb{P}(X = x) = p(1 - p)^{x-1}$$
for a positive integer $x$ (number of trials needed before success), and $0$ otherwise. Also, $X$ has [cdf](statistics/cumulative-distribution-function.md)
$$F_X(x) = \mathbb{P}(X \leq x) = 1 - (1 - p)^{\lfloor x \rfloor}$$
for $x \geq 1$, and $0$ otherwise.

### Expectation
The [expectation](statistics/expectation.md) of $X$ is given by
$$\mathbb{E}X = \frac{1}{p}.$$

### Variance
The [variance](statistics/variance.md) of $X$ is given by
$$\text{Var}(X) = \frac{1 - p}{p^2}.$$

### Memoryless Property
The geometric distribution is memoryless; that is, if no success has been observed yet, the number of failures that has occurred does not affect the number of additional trials required to obtain the next success. Mathematically, this is described as
$$\mathbb{P}(X > m + n | X > n) = \mathbb{P}(X > m).$$
This can be seen by evaluating the conditional probability on the left:
$$\begin{align*}
\mathbb{P}(X > m + n | X > n) &= \frac{\mathbb{P}(\lbrace X > m + n \rbrace \cap \lbrace X > n\rbrace)}{\mathbb{P}(X > n)} \\
&= \frac{\mathbb{P}(X > m + n)}{\mathbb{P}(X > n)} \\
&= \frac{(1 - p)^{m+n}}{(1 - p)^n} \\
&= (1 - p)^m \\
&= \mathbb{P}(X > m).
\end{align*}$$


> [!info] Aside.
> 
> The geometric distribution is the only discrete probability distribution with the memoryless property; the only continuous probability distribution with the memoryless property is the exponential distribution *\[link needed\]*.
