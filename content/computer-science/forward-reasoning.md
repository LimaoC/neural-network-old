---
title: "Forward Reasoning"
publishdate: "2023-03-12"
tags:
- "reasoning about programs"
---

## Definition
Forward reasoning, or forward chaining, is one of the two main methods for reasoning about the correctness of a program (the other being [backward reasoning](computer-science/backward-reasoning.md)). It can be described logically as the repeated application of modus ponens *\[link needed\]*.

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
Using forward reasoning, we can infer the conditions that must hold before each line in the method body. For example, we know that the [precondition](computer-science/precondition.md) will hold before the first line in the body, and that the precondition AND the first line will hold before the second line in the body, and so on until we reach the end of the body:
```
method MyMethod(x: int) returns (y: int)
	requires x >= 10
	ensures y >= 25
 {
	 // here, we have x >= 10
	 var a := x + 3;
	 // here, we have x >= 10 && a == x + 3
	 var b := 12;
	 // here, we have x >= 10 && a == x + 3 && b == 12
	 y := a + b;
	 // here, we have x >= 10 && a == x + 3 && b == 12 && y == a + b
 }
```
The method is correct with respect to its specification if the last constructed condition implies the required [postcondition](computer-science/postcondition.md); in other words, the last constructed condition needs to be [stronger](mathematics/predicate.md) than the postcondition. In this case, we require `x >= 0 && a == x + 3 && b == 12 && y == a + b` to imply `y >= 25`, which is true, so the method is indeed correct.