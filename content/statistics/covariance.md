---
title: "Covariance"
publishdate: "2023-02-22"
tags:
- "probability"
---

## Definition
Let $X$ and $Y$ be two [random variables](statistics/random-variable.md). The *covariance* of $X$ and $Y$ is given by
$$\text{Cov}(X, Y) = \mathbb{E}[(X - \mathbb{E}X)(Y - \mathbb{E}Y)] = \mathbb{E}(XY) - \mathbb{E}X\mathbb{E}Y.$$

We can apply [LOTUS](statistics/law-of-the-unconscious-statistician.md) to evaluate $\mathbb{E}(XY)$. In the case that $X$ and $Y$ are jointly discrete, we have
$$\mathbb{E}XY = \sum_i \sum_j x_i y_j f_{X, Y}(x_i, y_j),$$
where $f_{X, Y}$ is the [joint pmf](statistics/joint-distribution.md) of $X$ and $Y$.
In the case that $X$ and $Y$ are jointly continuous, we have
$$\mathbb{E}XY = \int_{-\infty}^\infty \int_{-\infty}^\infty xy f_{X, Y}(x, y) \thinspace dxdy,$$
where $f_{X, Y}$ is the [joint pdf](statistics/joint-distribution.md) of $X$ and $Y$.

If $\boldsymbol{X} = (X_1, \dots, X_n)^T$ is an $n$-dimensional [random vector](statistics/random-vector.md), then the *covariance matrix*, denoted $\text{Cov}(\boldsymbol{X})$, is the $n \times n$ matrix $\boldsymbol{V} = (v_{ij})$ with elements $v_ij = \text{Cov}(X_i, X_j)$. It follows that $v_{ii} = \text{Var}(X_i)$, that is the main diagonal of entries gives the variances of the random variables $\text{Var}(X_i)$.

## Properties
The covariance of $X$ and $X$ is equivalent to the [variance](statistics/variance.md) of $X$, i.e. $\text{Cov}(X, X) = \text{Var}(X)$.

For any $a, b, c, d \in \mathbb{R}$, we have $\text{Cov}(aX + b, cY + d) = ac\text{Cov}(X, Y)$. It follows that if either $X$ or $Y$ is constant, then $\text{Cov}(X, Y) = 0$.

- For any collection of random variables $X_1, \dots, X_n$, we have
  $$\text{Var}\left(\sum_{i=1}^n X_i\right) = \sum_{i=1}^n \sum_{j=1}^n \text{Cov}(X_i, X_j) = \sum_i \text{Var}(X_i) + \sum_i \sum_{j\neq i}\text{Cov}(X_i, X_j).$$
- More generally, for any collections of random variables $X_1, \dots, X_n$ and $Y_1, \dots, Y_m$, we have
  $$\text{Cov}(\sum_{i=1}^n X_i, \sum_{j=1}^m Y_j) = \sum_{i=1}^n\sum_{j=1}^m \text{Cov}(X_i, Y_j).$$

Let $\boldsymbol{X} = (X_1, \dots, X_n)^T$ be an $n$-dimensional random vector. Then the following basic properties hold:
- If $\boldsymbol{\mu} = \mathbb{E}\boldsymbol{X}$ is the corresponding vector of expected values, then $\text{Cov}(\boldsymbol{X}) = \mathbb{E}(\boldsymbol{XX}^T) - \boldsymbol{\mu\mu}^T = \mathbb{E}((\boldsymbol{X} - \mathbb{E}\boldsymbol{X})(\boldsymbol{X} - \mathbb{E}\boldsymbol{X})^T)$.
- $\text{Cov}(\boldsymbol{X})$ is a symmetric matrix. *\[link needed\]*
- $\text{Cov}(\mathbf{X})$ is positive semi-definite *\[link needed\]*, that is
  $$\boldsymbol{x}^T \text{Cov}(\boldsymbol{X})\boldsymbol{x} \geq 0, \quad \forall \boldsymbol{x} \in \mathbb{R}^n.$$
- Let $\boldsymbol{Y} = (Y_1, \dots, Y_n)^T$ be another $n$-dimensional random vector. Then $\text{Cov}(\boldsymbol{X} + \boldsymbol{Y}) = \text{Cov}(\boldsymbol{X}) + \text{Cov}(\boldsymbol{Y})$ if and only if $X_i$ and $y-j$ are [uncorrelated](statistics/correlation.md) (recall that independent random variables are uncorrelated). In general,
  $$(\text{Cov}(\boldsymbol{X} + \boldsymbol{Y}))\_{ij} = (\text{Cov}(\boldsymbol{X}))\_{ij} + (\text{Cov}(\boldsymbol{Y}))\_{ij} + \text{Cov}(X_i, Y_j) + \text{Cov}(Y_i, X_j).$$
- If $\boldsymbol{c} = (c_1, \dots, c_n)$ is a vector of constants, then $\text{Cov}(\boldsymbol{X} + \boldsymbol{c}) = \text{Cov}(\boldsymbol{X}).$
- Let $A$ be an $m \times n$ matrix. Define $\boldsymbol{Y} = (Y_1, \dots, Y_m)^T$ by the linear transformation $\boldsymbol{Y} = A\boldsymbol{X}$. Then $\text{Cov}(\boldsymbol{Y}) = A\text{Cov}(\boldsymbol{X})A^T$:
  $$\begin{align*}
  \text{Cov}(\boldsymbol{Y}) &= \mathbb{E}((\boldsymbol{Y} - \mathbb{E}\boldsymbol{Y})(\boldsymbol{Y} - \mathbb{E}\boldsymbol{Y})^T) \\
  &= \mathbb{E}((A\boldsymbol{X} - A\mathbb{E}\boldsymbol{X})(A\boldsymbol{X} - A\mathbb{E}\boldsymbol{X})^T) \\
  &= \mathbb{E}(A(\boldsymbol{X} - \mathbb{E}\boldsymbol{X})(A(\boldsymbol{X} - \mathbb{E}\boldsymbol{X}))^T) \\
  &= \mathbb{E}(A(\boldsymbol{X} - \mathbb{E}\boldsymbol{X})(\boldsymbol{X} - \mathbb{E}\boldsymbol{X})^TA^T) \\
  &= A\mathbb{E}((\boldsymbol{X} - \mathbb{E}\boldsymbol{X})(\boldsymbol{X} - \mathbb{E}\boldsymbol{X})^T)A^T \\
  &= A\text{Cov}(\boldsymbol{X})A^T.
  \end{align*}$$
  An example of this is $\text{Cov}(a\boldsymbol{X}) = a^2\text{Cov}(\boldsymbol{X})$ for $a \in \mathbb{R}$.

## See Also
- [Correlation](statistics/correlation.md)
- [Independence (Random Variable)](statistics/independence-(random-variable).md)
