---
title: "Law of the Unconscious Statistician"
publishdate: "2022-12-10"
tags:
- "statistics"
---

## Definition
Let $X$ be a [discrete random variable](statistics/random-variable.md) with support $S$ and with [probability mass function](statistics/probability-mass-function.md) $f_X(x)$ where $x \in S$, and let $g(X)$ be some function of $X$. Then the [expectation](statistics/expectation.md) of $g(X)$ is given by
$$\mathbb{E}(g(X)) = \sum_{x \in S} g(x)f_X(x) = \sum_{x \in S} g(x) \mathbb{P}(X = x).$$

If $X: \Omega \to \mathbb{R}$ is a continuous random variable with [probability density function](statistics/probability-density-function.md) $f_X(x)$ where $x \in \Omega$, and let $g(X)$ be some function of $X$. Then the expectation of $g(X)$ is given by
$$\mathbb{E}(g(X)) = \int_{-\infty}^\infty g(x)f_X(x) dx$$

The Law of the Unconscious Statistician is often shortened to LOTUS.
