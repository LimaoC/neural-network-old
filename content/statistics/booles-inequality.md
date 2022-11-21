---
title: "Boole's Inequality"
publishdate: "2022-11-20"
tags:
- "statistics"
---

For any [events](statistics/event.md) $A_1, A_2, \dots$, we have
$$\mathbb{P}\left(\bigcup_i A_i\right) \leq \sum_i \mathbb{P}(A_i).$$
That is, the probability that at least one of the events occurs is less than or equal to the sum of the probabilities of the individual events.

> [!note] Proof.
> 
> We proceed by induction. The $n = 1$ case holds, since $\mathbb{P}(A_1) \leq \mathbb{P}(A_1)$. \
> Assume the $n = k$ case holds; that is,
> $$\mathbb{P}\left(\bigcup_{i=1}^k A_i\right) \leq \sum_{i=1}^k \mathbb{P}(A_i).$$
> Then, using $\mathbb{P}(A \cup B) = \mathbb{P}(A) + \mathbb{P}(B) - \mathbb{P}(A \cap B)$, 
> $$\mathbb{P}\left(\bigcup_{i=1}^{k+1} A_i \right) = \mathbb{P}\left(\bigcup_{i=1}^k A_i \right) + \mathbb{P}(A_{k+1}) - \mathbb{P}\left(\left(\bigcup_{i=1}^n A_i \right) \bigcap A_{k+1} \right),$$
> and since $\mathbb{P}(E) \geq 0$ for any event $E$ (from the [probability axioms](statistics/probability-measure.md)),
> $$\begin{align*}
\mathbb{P}\left(\bigcup_{i=1}^{k+1} A_i \right) &\leq \mathbb{P}\left(\bigcup_{i=1}^k A_i \right) + \mathbb{P}(A_{k+1}) \\
&\leq \sum_{i=1}^k \mathbb{P}(A_i) + \mathbb{P}(A_{k+1}) \\
&= \sum_{i=1}^{k+1} \mathbb{P}(A_i).
\end{align*}$$
