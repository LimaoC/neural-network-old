---
title: "Event"
publishdate: "2022-11-20"
tags:
- "statistics"
---

> [!abstract] Definition.
> 
> An *event* is any subset of outcomes; that is, any subset of the [sample space](statistics/sample-space.md) $\Omega$.

Let $\lbrace A_i \rbrace$ be a collection of events. \
The *union* of $\lbrace A_i \rbrace$, denoted $\cup_i A_i = A_1 \cup A_2 \cup \cdots$, is the event that $A_i$ occurs for at least one value of $i$. \
The *intersection* of $\lbrace{A_i \rbrace}$, denoted $\cap_iA_i = A_1 \cap A_2 \cap \cdots$, is the event that $A_i$ occurs for all values of $i$.

If $A$ is an event, then $A$ complement, denoted $A^c$, is the event that $A$ does not occur.

If $A$ and $B$ are two events such that $A \neq B$, and all the outcomes in $A$ are also in $B$, then $A$ is a *proper subset* of $B$, denoted $A \subset B$. If $A$ and $B$ are equal, then $A$ is a *subset* of $B$, denoted $A \subseteq B$. $A \subset B$ can also be read as "$A$ implies $B$". Note that "subset" is often said as as shorthand of "proper subset" when $A \subset B$ is used.

If $A$ and $B$ are two events such that they share no outcomes in common, they are said to be *disjoint*, that is $A \cap B = \varnothing$. More generally, $A_1, A_2, \dots$ is said to be *disjoint* if each pair of events $(A_i, A_j$) with $i \neq j$, is disjoint.

$A_1, A_2, \dots$ are said to be *exhaustive* if $A_1 \cup A_2 \cup \cdots = \Omega$, that is at least one $A_i$ must occur. If $A_1, A_2, \dots$ are exhaustive and mutually exclusive, then they are a *partition* of $\Omega$ and are said to partition the sample space.
