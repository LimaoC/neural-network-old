---
title: "Transformations of Random Variables"
publishdate: "2023-02-26"
tags:
- "probability"
---

Let $X$ be a [random variable](statistics/random-variable.md) and define $Y := g(X)$ for some function $g : \mathbb{R} \to \mathbb{R}$ with inverse $g^{-1}$. We can then obtain the distribution of $Y$ from $X$ by using the fact that $X = g^{-1}(Y)$. If $g$ is increasing, then the [cdf](statistics/cumulative-distribution-function.md) of $Y$ is given by
$$F_Y(y) = \mathbb{P}(Y \leq y) = \mathbb{P}(X \leq g^{-1}(y)) = F_X(g^{-1}(y)), \quad \forall y \in \mathbb{R},$$
and if $g$ is decreasing, then the cdf of $Y$ is given by
$$F_Y(y) = \mathbb{P}(Y \leq y) = \mathbb{P}(X \geq g^{-1}(y)) = 1 - \lim_{x\to y^{-}} F_X(g^{-1}(x)),$$
since the inverse of a decreasing function is also a decreasing function (aside: the inverse of an increasing function is also an increasing function):

> If $g$ is decreasing, then $x \leq y \implies g(x) \geq g(y)$. Define $u := g(x)$ and $v := g(y)$, so that $x = g^{-1}(u)$ and $y = g^{-1}(v)$. We then have $u \geq v$ (since $g(x) \geq g(y)$) and $g^{-1}(u) \leq g^{-1}(v)$ (since $x \leq y$). Thus $g^{-1}$ is decreasing.

And if $X$ is a continuous random variable, then $F_Y(y) = 1 - F_X(g^{-1}(y))$.

If the function $g$ is not monotone *\[link needed\]*, then we can consider separately the intervals of $g$ that are monotone.

*(Transformation Rule).* Let $X$ and $Y := g(X)$ be continuous random variables with [pdfs](statistics/probability-density-function.md)$f_X$ and $f_Y$, and suppose $g$ has inverse $g^{-1}$ and is differentiable. Then if $g$ is increasing (which implies $g^{-1}$ is also increasing),
$$F_Y(y) = \mathbb{P}(Y \leq y) = \mathbb{P}(g(X) \leq y) = \mathbb{P}(X \leq g^{-1}(y))= F_X(g^{-1}(y)).$$
Then
$$\begin{align*}
f_Y(y) &= \frac{d}{dy}F_Y(y) \\
&= \frac{d}{dy}F_X(g^{-1}(y)) \\
&= \left(\frac{d}{dy}g^{-1}(y)\right) \cdot f_X(g^{-1}(y)) \\
&= \frac{1}{g'(g^{-1}(y))} f_X(g^{-1}(y)),
\end{align*}$$
for $y$ in the range of $g$. The case in which $g$ is decreasing is similar, and we obtain a general formula for the pdf of $Y$:
$$f_Y(y) = \frac{1}{|g'(g^{-1}(y))|} f_X(g^{-1}(y)).$$

### Example (Linear Function)
Let $X$ be a random variable and define $Y := aX + b$, where $a, b \in \mathbb{R}$ and $a \neq 0$. Then for all $y \in \mathbb{R}$,
$$F_Y(y) = \begin{cases}
F_X\left(\frac{y - b}{a}\right) & \text{if } a > 0 \\
1 - \lim_{x\to y^{-}}F_X\left(\frac{x - b}{a}\right) & \text{if } a < 0.
\end{cases}$$

If $X$ is a discrete random variable, then
$$f_Y(y) = \mathbb{P}(Y = y) = \mathbb{P}\left(X = \frac{y - b}{a}\right) = f_X\left(\frac{y - b}{a}\right).$$

If $X$ is a continuous random variable, then
$$F_Y(y) = \begin{cases}
F_X\left(\frac{y - b}{a}\right) & \text{if } a > 0 \\
1 - F_X\left(\frac{x - b}{a}\right) & \text{if } a < 0,
\end{cases}$$
and if $F_X$ is differentiable at $x = (y - b)/a$, then
$$f_Y(y) = \frac{d}{dy}F_Y(y) = \frac{1}{|a|} f_X\left(\frac{y - b}{a}\right).$$
