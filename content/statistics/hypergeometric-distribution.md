---
title: "Hypergeometric Distribution"
publishdate: "2023-01-19"
tags:
- "probability"
---

## Definition
The *hypergeometric distribution* with parameters $N$, $n$, and $r$ is the discrete probability distribution of the number of successes (where a success is defined as drawing an object with some certain feature) in $n$ repetitions of drawing without replacement from some population of size $N$ where $r$ objects have the desired feature.

A similar distribution is the [binomial distribution](statistics/binomial-distribution.md), which describes the probability distribution of the number of successes in $n$ repetitions of drawing *with* replacement.

## Properties
### Probability Mass Function
Let $X$ be a hypergeometric [random variable](statistics/random-variable.md) with parameters $N, n$, and $r$; that is, $X \sim \text{Hyp}(n, r, N)$. Then $X$ has [pmf](statistics/probability-mass-function.md)
$$f_X(x) = \mathbb{P}(X = x) = \frac{\binom{r}{x} \binom{N - r}{n - x}}{\binom{N}{n}},$$
for $\max \lbrace 0, r + n - N \rbrace \leq x \leq \min \lbrace n, r \rbrace$, and $0$ otherwise.

> [!tip] Tip.
> 
> To reason about the form of this pmf, consider that there are $\binom{N}{n}$ total possible outcomes, each of which are equally likely. For each number $x$ of successes, there are $\binom{r}{x}$ ways of choosing $x$ objects (with the desired feature) from $r$ and $\binom{N-r}{n-x}$ ways of choosing $n - x$ objects (without the desired feature) from $N - r$.

### Expectation
The [expectation](statistics/expectation.md) of $X$ is given by
$$\mathbb{E}X = n \frac{r}{N}.$$
Compare this with the expectation of a $\text{Bin}(n, p)$ random variable, $np$.

### Variance
The [variance](statistics/variance.md) of $X$ is given by
$$\text{Var}(X) = n\frac{r}{N}\left(1 - \frac{r}{N}\right)\frac{N - n}{N - 1}.$$
Compare this with the variance of a $\text{Bin}(n, p)$ random variable, $np(1 - p)$.
