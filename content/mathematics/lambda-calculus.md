---
title: "Lambda Calculus"
publishdate: "2023-02-21"
tags:
- "formal logic"
---

## Definition
*Lambda calculus* (also written as $\lambda$-calculus) is a formal system for expressing computations based on function abstraction (defining and expressing $\lambda$-terms, also called $\lambda$-expressions) and function application (applying functions to arguments).

## Lambda Terms ($\lambda$-terms)
A *$\lambda$-term* is a valid $\lambda$-calculus expression. The set of all lambda terms, $\Lambda$, is recursively generated as follows:
- A variable $x$ is itself a $\lambda$-term
- If $t$ is a $\lambda$-term and $x$ is a variable, then $(\lambda x.t)$ is a $\lambda$-term, also called an abstraction. $(\lambda x.t)$ denotes an anonymous function that takes an input $x$ and returns $t$.
- If $t$ and $s$ are $\lambda$-terms, then $(t \thinspace s)$ is a $\lambda$-term, also called an application. $(t \thinspace s)$ denotes the application of a function $t$ to an input $s$.

There are some rules for evaluating $\lambda$-expressions:
1. Application has higher precedence than abstraction. $\lambda x. A \thinspace B$ means $\lambda x. (A \thinspace B)$ and not $(\lambda x.A)B$
2. Application is left-associative. $A \thinspace B \thinspace C$ means $(A \thinspace B) \thinspace C$ and not $A \thinspace (B \thinspace C)$
3. Abstraction is right-associative. $\lambda x. A \thinspace \lambda y.B$ means $(\lambda x . (A \thinspace \lambda y . B))$ and not $(\lambda x . A)(\lambda y . B)$

We are only allowed to use univariate functions, but we can simulate multivariate functions by "chaining" single-variate functions like so:
$$\lambda x.(\lambda y.(\lambda z.x+y+z)),$$
which we can write in short-form notation:
$$\lambda xyz.x + y + z$$

A *free variable* in a $\lambda$-expression is one that is not bounded by an abstraction. The set of free variables $\mathcal{F}(r)$ in an expression $r \in \Lambda$ can be recursively generated as follows:
- $\mathcal{F}(x) = \lbrace x \rbrace$
- $\mathcal{F}(\lambda x.t) = \mathcal{F}(t) - \lbrace x \rbrace$
- $\mathcal{F}(s \thinspace t) = \mathcal{F}(s) \cup \mathcal{F}(t)$ for $s, t \in \Lambda$

A *combinator* is a $\lambda$-expression with no free variables; they are named as such as these expressions serve only to combine arguments.

A term that cannot be reduced any further is said to be in $\beta$-normal form. It can be thought of as a fully executed functional program. If a term cannot be reduced to a $\beta$-normal form, it is said to be divergent.

## Reduction Operations
There are two reduction operations that can be performed on $\lambda$-terms:
- An *$\alpha$-conversion*, denoted by $(\lambda x.M[ x]) \to (\lambda y.M[y])$, where we rename variables to avoid name collisions.
- A *$\beta$-reduction*, denoted by $((\lambda x.M)E) \to (M[x := E])$, where we replace bound variables with the argument expression in the body of the abstraction.

Two $\lambda$-expressions that are identical after $\alpha$-conversion are called *$\alpha$-equivalent*.

## Haskell Ordering
A *reducible expression* or *redex* is any expression to which a $\beta$-reduction can be immediately applied. When multiple reducible expressions are present, choose the left-most redex that is not in the body of a lambda abstraction, i.e. do the outermost and leftmost reduction first.

## Boolean Logic
Lambda calculus can also be used to model boolean logic. One possible formulation is listed below:
- $\text{True} := \lambda x . \lambda y . x$
- $\text{False} := \lambda x . \lambda y . y$
- $\text{And} := \lambda p . \lambda q . p \thinspace q \thinspace p$
- $\text{Or} := \lambda p . \lambda q . p \thinspace p \thinspace q$
- $\text{Not} := \lambda p . p \thinspace \text{True} \thinspace \text{False}$
