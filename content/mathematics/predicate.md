---
title: "Predicate"
publishdate: "2023-03-12"
tags:
- "formal logic"
---

## Definition
In logic, a *predicate* is a mathematical statement or assertion that may be either true or false.

## Properties
### Weaker and Stronger Predicates
Let $P$ and $Q$ be two predicates. If $P \implies Q$, then $P$ is said to be *stronger* than $Q$, and $Q$ is said to be *weaker* than $P$. The following properties hold for all predicates $P, Q$:
- $P \land Q$ is stronger than $P$, since $P \land Q \implies P$.
- $P \lor Q$ is weaker than $P$, since $P \implies P \lor Q$.
- $\text{False}$ is the strongest predicate, since $\text{False} \implies P$.
- $\text{True}$ is the weakest predicate, since $P \implies \text{True}$.