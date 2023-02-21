---
title: "Independence (Event)"
publishdate: "2022-11-21"
tags:
- "probability"
---

## Definition
Two [events](statistics/event.md) $A$ and $B$ are said to be *independent* if $\mathbb{P}(A \cap B) = \mathbb{P}(A)\mathbb{P}(B)$.

A collection of events $A_1, A_2, \dots$ is said to be *pairwise independent* if, for all $i \neq j$, $A_i$ and $A_j$ are independent; that is, $\mathbb{P}(A_i \cap A_j) = \mathbb{P}(A_i)\mathbb{P}(A_j)$. \
They are said to be *triplewise independent* if, for all distinct $i, j, k$, we have $\mathbb{P}(A_i \cap A_j \cap A_k) = \mathbb{P}(A_i)\mathbb{P}(A_j)\mathbb{P}(A_k)$.

Generally, they are said to be *mutually independent* if each event is independent of any combination of other events in the collection; that is, $$\mathbb{P}\left(\bigcap_i A_i \right) = \prod_i \mathbb{P}(A_i).$$

## Properties

If $A$ and $B$ are independent events, then $A^c$ and $B^c$ are independent, i.e. $\mathbb{P}(A^c \cap B^c) = \mathbb{P}(A^c)\mathbb{P}(B^c)$. \
**Proof.** Using [De Morgan's Law](statistics/de-morgans-laws.md), we have $\mathbb{P}(A^c \cap B^c) = \mathbb{P}((A \cup B)^c)$. Then
$$\begin{align*}
\mathbb{P}(A^c \cap B^c) &= 1 - \mathbb{P}(A \cup B) \\
&= 1 - [\mathbb{P}(A) + \mathbb{P}(B) - \mathbb{P}(A \cap B)] \\
&= 1 - [\mathbb{P}(A) + \mathbb{P}(B) - \mathbb{P}(A)\mathbb{P}(B)] && A, B \text{ independent} \\
&= 1 - \mathbb{P}(A) - \mathbb{P}(B) + \mathbb{P}(A)\mathbb{P}(B) \\
&= (1 - \mathbb{P}(A))(1 - \mathbb{P}(B)) \\
&= \mathbb{P}(A^c)\mathbb{P}(B^c).
\end{align*}$$

## See Also
- [Independence (Random Variable)](statistics/independence-(random-variable).md)
