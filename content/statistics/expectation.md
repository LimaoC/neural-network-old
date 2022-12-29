---
title: "Expectation"
publishdate: "2022-12-10"
tags:
- "statistics"
---

## Definition
Let $X$ be a [discrete random variable](statistics/random-variable.md) with [probability mass function](statistics/probability-mass-function.md) $f_X(x)$ where $x \in S$. Then the expected value of $X$, denoted by $\mathbb{E}(X)$ and commonly shortened to $\mathbb{E}X$, is given by
$$\mathbb{E}(X) = \sum_{x \in S} xf_X(x) = \sum_{x \in S} x\mathbb{P}(X = x).$$

Let $X$ be a continuous random variable with [probability density function](statistics/probability-density-function.md) $f_X(x)$. Then the expected value of $X$ is given by
$$\mathbb{E}(X) = \int_{-\infty}^\infty uf(u)du.$$

The expected value of $X$ is also commonly denoted by $\mu_X$.

> [!tip] Tip.
> 
> Intuitively, the expectation of a random variable $X$ is a weighted average of the values that $X$ takes ($x$ in the range of $X$), where the weight is given by the probability of each value in the discrete case, and the density function $f_X$ in the continuous case.

## Properties
Let $X$ and $Y$ be two arbitrary random variables. Then
1. $\mathbb{E}(aX + b) = a\mathbb{E}X + b$ for all $a, b$
2. $\mathbb{E}(X + Y) = \mathbb{E}X + \mathbb{E}Y$
3. $X \geq Y \implies \mathbb{E}X \geq \mathbb{E}Y$

**Proof.** The first property follows from applying [LOTUS](statistics/law-of-the-unconscious-statistician.md). For the second property, first define $X: \Omega \to \mathbb{R}$, $Y: \Omega \to \mathbb{R}$ and $Z(\omega) = X(\omega) + Y(\omega)$. Then
$$\begin{align*}
\mathbb{E}Z &= \sum_{\omega\in\Omega} Z(\omega) \mathbb{P}(\lbrace\omega\rbrace) \\
&= \sum_{\omega\in\Omega} (X(\omega) + Y(\omega)) \mathbb{P}(\lbrace\omega\rbrace) \\
&= \sum_{\omega\in\Omega} X(\omega) \mathbb{P}(\lbrace\omega\rbrace) + \sum_{\omega\in\Omega} Y(\omega) \mathbb{P}(\lbrace\omega\rbrace) \\
&= \mathbb{E}X + \mathbb{E}Y,
\end{align*}$$
with the continuous case following analogously with integrals. For the third property, $X \geq Y \implies X - Y \geq 0 \implies \mathbb{E}(X - Y) \geq 0 \implies \mathbb{E}X \geq \mathbb{E}Y$, where we use the second property in the last step.