---
title: "Geometric Distribution"
publishdate: "2023-01-15"
tags:
- "probability"
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

### Probability Generating Function
The [probability generating function](statistics/probability-generating-function.md) of $X$ is given by
$$\begin{align*}
G_X(z) &= \mathbb{E}(z^X) \\
&= \sum_{x=1}^\infty z^x p (1 - p)^{x-1} \\
&= zp \sum_{x=0}^\infty z^x (1 - p)^x \\
&= \frac{zp}{1 - z(1 - p)},
\end{align*}$$
using the fact that
$$\sum_{k=0}^\infty r^k = \frac{1}{1 - r}, \quad |r| < 1.$$

### Memoryless Property
The geometric distribution has the memoryless property. That is, the probability distribution of observing the next (or the first) success, given we have already observed some number of failures, is independent of the number of failures observed.

For example, if we have already observed 20 failures, the probability of requiring 5 more failures is equal to the probability of requiring 5 failures (without having observed the initial 20 failures). In other words, there is no "memory" of the additional failures.

Mathematically, this is described as
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
> The only *discrete* probability distribution with the memoryless property is the geometric distribution. The only *continuous* probability distribution with the memoryless property is the [exponential distribution](statistics/exponential-distribution.md).
