---
title: "Uniform Distribution"
publishdate: "2023-01-19"
tags:
- "probability"
---

## Definition
The *uniform distribution* is the continuous probability distribution that takes on values in the support $[a, b]$ (or $(a, b)$ for an open interval) such that all intervals (contained in the support) of the same length have equal probability. A random variable $X$ that is uniformly distributed on $[a, b]$ satisfies
$$\mathbb{P}(x \leq X \leq y) = \frac{y - x}{b - a}, a \leq x \leq y \leq b,$$
that is the probability of taking on a value in a particular interval is directly proportional to the interval's length.

## Properties
### Probability Density Function
Let $X$ be a uniform [random variable](statistics/random-variable.md) on $[a, b]$; that is, $X \sim \mathcal{U}[a, b]$. Then $X$ has [pdf](statistics/probability-density-function.md)
$$f_X(x) = \begin{cases}
\frac{1}{b-a}, & \text{if } a \leq x \leq b \\
0, & \text{otherwise.}
\end{cases}$$
and [cdf](statistics/cumulative-distribution-function.md)
$$F_X(x) = \mathbb{P}(X \leq x) = \begin{cases}
0, & \text{if } x < a \\
\frac{x - a}{b - a}, & \text{if } a \leq x \leq b \\
1, & \text{if } x > b.
\end{cases}$$

## Expectation
The [expectation](statistics/expectation.md) of $X$ is given by
$$\mathbb{E}X = \frac{1}{b-a} \int_a^b x \thinspace dx = \frac{b^2 - a^2}{2(b - a)} = \frac{a + b}{2},$$
which intuitively makes sense as it is the mean of the bounds $a$ and $b$.

## Variance
The [variance](statistics/variance.md) of $X$ is given by
$$\begin{align*}
\text{Var}(X) &= \mathbb{E}(X^2) - (\mathbb{E}X)^2 \\
&= \frac{1}{b - a}\int_a^b x^2 \thinspace dx - \left(\frac{a + b}{2}\right)^2 \\
&= \frac{a^2 + ab + b^2}{3} - \frac{a^2 + 2ab + b^2}{4} \\
&= \frac{(b - a)^2}{12},
\end{align*}$$
where we use difference of cubes in the third step.
