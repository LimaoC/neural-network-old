---
title: "Markov's Inequality"
publishdate: "2022-12-29"
tags:
- "statistics"
---

## Definition
Let $X$ be a non-negative [random variable](statistics/random-variable.md) (i.e. $X \geq 0$) and $a > 0$. Then
$$\mathbb{P}(X \geq a) \leq \frac{\mathbb{E}(X)}{a}.$$

## Proof
Define $A = \lbrace \omega \in \Omega : X(\omega) \geq a \rbrace$. Then the random variable $X - a \cdot \mathbb{I}_A \geq 0$, since if the outcome is in $A$, $X \geq a$ and $a - a \cdot \mathbb{I}_A = 0$ implies $X \geq a \cdot \mathbb{I}_A$, and if the outcome is not in $A$, $\mathbb{I}_A = 0$ which implies $X - a \cdot \mathbb{I}_A = X \geq 0$. Taking the [expectation](statistics/expectation.md) of this random variable yields
$$\begin{align*}
\mathbb{E}(X - a \cdot \mathbb{I}_A) &\geq 0 \\
\mathbb{E}X - a \cdot \mathbb{E}(\mathbb{I}_A) &\geq 0 \\
\mathbb{E}X - a \cdot \mathbb{P}(A) &\geq 0 \\
a \cdot \mathbb{P}(A) &\leq \mathbb{E}X \\
\therefore \mathbb{P}(A) \leq \frac{\mathbb{E}X}{a}.
\end{align*}$$
