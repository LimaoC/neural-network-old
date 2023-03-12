---
title: "Backward Reasoning"
publishdate: "2023-03-12"
tags:
- "reasoning about programs"
---

## Definition
Backward reasoning, or backward chaining, is one of the two main methods for reasoning about the correctness of a program (the other being [forward reasoning](computer-science/forward-reasoning.md)).

## Example
Take the following example of a method implemented in Dafny:
```
method MyMethod(x: int) returns (y: int)
	requires x >= 10
	ensures y >= 25
 {
	 var a := x + 3;
	 var b := 12;
	 y := a + b;
 }
```
Using backward reasoning, we can start from the bottom of the body with the [postcondition](computer-science/postcondition.md) and work our way up to the top of the method, stating the conditions that are required following each individual line:
```
method MyMethod(x: int) returns (y: int)
	requires x >= 10
	ensures y >= 25
 {
     // here, we want x + 3 + 12 >= 25
	 var a := x + 3;
     // here, we want a + 12 >= 25
	 var b := 12;
     // here, we want a + b >= 25
	 y := a + b;
	 // here, we want y >= 25
 }
```
The method is correct with respect to its specification if the last calculated condition is implied by the stated [precondition](computer-science/precondition.md); in other words, the precondition needs to be [stronger](mathematics/predicate.md) than the last calculated condition. In this case, we require `x >= 10` to imply `x + 3 + 12 >= 25`, which is true, so the method is indeed correct.

> [!tip] Tip.
> 
> Backward reasoning is usually easier to keep track of than forward reasoning, as you are only keeping track of the conditions that are necessary for the postcondition to hold. In forward reasoning, we conjoin every condition after each line and so we may end up with more conditions than are necessary to imply the required postcondition.
