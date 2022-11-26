---
title: "Law of Total Probability"
publishdate: "2022-11-21"
tags:
- "statistics"
---

> [!abstract] Theorem.
> 
> If $A$ and $B$ are [events](statistics/event.md) such that $0 < \mathbb{P}(B) < 1$, then
> $$\mathbb{P}(A) = \mathbb{P}(A|B)\mathbb{P}(B) + \mathbb{P}(A|B^c)\mathbb{P}(B^c).$$
> More generally, if $\lbrace B_i \rbrace$ is a collection of events that form a [partition](statistics/partition.md) of $\Omega$ such that $\mathbb{P}(B_i) > 0$ for at least one $i$,  then
> $$\mathbb{P}(A) = \sum_i \mathbb{P}(A|B_i)\mathbb{P}(B_i) = \sum_i \mathbb{P}(A \cap B_i)$$
> for any event $A$, by the definition of [conditional probability](statistics/conditional-probability.md).

> [!note] Proof.
> 
> We have
> $$A = A \cap \Omega = A \cap (B \cup B^c) = (A \cap B) \cup (A \cap B^c),$$
> where $A \cap B$ and $A \cap B^c$ are disjoint events.
> 
> Then from the [third axiom of probability](statistics/probability-measure.md) and the definition of conditional probability,
> $$\mathbb{P}(A) = \mathbb{P}(A \cap B) + \mathbb{P}(A \cap B^c) = \mathbb{P}(A|B)\mathbb{P}(B) + \mathbb{P}(A|B^c)\mathbb{P}(B^c).$$
