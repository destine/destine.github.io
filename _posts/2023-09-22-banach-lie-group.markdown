---
layout: post
title:  "The group of units of a Banach algebra."
categories: jekyll update
---
<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# Proposition 1

Let $$\mathcal{A}$$ be a Banach algebra with unit $$\mathbf{1}$$. Let $$x \in \mathcal{A}$$ be such that
$$ \lVert x - \mathbf{1} \rVert < 1. $$
Then $$x$$ is a unit.

# Proof

Our candidate inverse is
$$ \sum_{j = 0}^{\infty} (\mathbf{1} - x)^{j}. $$
Define for any integer $$n > 0$$ the partial sum
$$ S_{n} = \sum_{j = 0}^{n} (\mathbf{1} - x)^{j}. $$
First, I show the sequence of partial sums is Cauchy. Next, I verify the series actually converges to an inverse.

Fix integers $$0 < m < n$$. Then

$$ \lVert S_{n} - S_{m} \rVert \leq \sum_{j = m + 1}^{n} \lVert \mathbf{1} - x \rVert^{j} \leq \sum_{j = m + 1}^{\infty} \lVert \mathbf{1} - x \rVert^{j} = \frac{\lVert \mathbf{1} - x \rVert^{m+1}}{1 - \lVert \mathbf{1} - x \rVert}. $$

Since the rightmost quantity tends to $$0$$ as $$m$$ tends to $$\infty$$, the sequence is Cauchy. Hence, the $$S_{n}$$ converge to an element $$y \in \mathcal{A}$$.

I verify that $$xy = yx = \mathbf{1}$$. I compute:

$$ \lVert \mathbf{1} - xy \rVert = \lim_{n \to \infty} \lVert \mathbf{1} - xS_{n} \rVert $$

$$ = \lim_{n \to \infty} \lVert \mathbf{1} - (\mathbf{1} - (\mathbf{1} - x)) S_{n} \rVert $$

$$ = \lim_{n \to \infty} \lVert (\mathbf{1} - x)^{n+1} \rVert $$

$$ \leq \lim_{n \to \infty} \lVert \mathbf{1} - x \rVert^{n+1} = 0. $$

Similarly, $$\lVert \mathbf{1} - yx \rVert = 0$$.
$$\tag*{$\blacksquare$}$$

In other words, the unit ball centered at the unit $$\mathbf{1}$$ is contained in the group of units. We can generalize this to all units in Banach algebras.

# Proposition 2

Let $$\mathcal{A}$$ be a Banach algebra with unit $$\mathbf{1}$$. Let $$x,y \in \mathcal{A}$$ be such that $$x$$ is a unit and
$$ \lVert x - y \rVert < \frac{1}{\lVert x^{-1} \rVert}. $$
Then $$y$$ is a unit.

# Proof

We shall see that Proposition 1 implies both $$x^{-1}y$$ and $$yx^{-1}$$ are units. Consider the former.

$$ \lVert \mathbf{1} - x^{-1}y \rVert = \lVert x^{-1} \rVert \lVert x - y \rVert < 1. $$

Likewise, $$yx^{-1}$$ is a unit. Finally, observe

$$ \left( (x^{-1}y)^{-1}x^{-1} \right) y = y \left( x^{-1}(yx^{-1})^{-1} \right) = \mathbf{1}. $$

That is, $$y$$ admits both a left inverse and a right inverse.
$$\tag*{$\blacksquare$}$$

In sum, the group of units of a Banach algebra is a Banach manifold. Our next stop is the compatibility of this Banach manifold-structure with the group multiplication. Specifically, the hurdle is proving the continuity of taking inverses. We use the following bound.

# Lemma

Let $$\mathcal{A}$$ be a Banach algebra with unit $$\mathbf{1}$$. Let $$x,y \in A$$ be such that $$x$$ is a unit and
$$ \lVert x - y \rVert < \frac{1}{2 \lVert x^{-1} \rVert}. $$
Then
$$ \lVert y^{-1} \rVert < 2 \lVert x^{-1} \rVert. $$

# Proof

Recall the inverse $$y^{-1}$$ has the formula
$$ y^{-1} = (x^{-1}y)^{-1}x^{-1} $$
and that

$$ \lVert (x^{-1}y)^{-1} \rVert = \lVert \sum_{j = 0}^{\infty} (\mathbf{1} - x^{-1}y)^{j} \rVert \leq \frac{1}{1 - \lVert \mathbf{1} - x^{-1}y \rVert}. $$

Using

$$ \lVert \mathbf{1} - x^{-1}y \lVert \leq \lVert x^{-1} \rVert \lVert x - y \rVert < \frac{1}{2}, $$

we refine the bound on $$\lVert y^{-1} \rVert$$ to $$2 \lVert x^{-1} \rVert$$.
$$\tag*{$\blacksquare$}$$

# Proposition 3

Let $$\mathcal{A}$$ be a Banach algebra with unit $$\mathbf{1}$$. The function $$i\colon \mathcal{A}^{\times} \to \mathcal{A}^{\times}$$ from the group of invertible elements to itself is continuous.

# Proof

Fix $$x,y \in \mathcal{A}^{\times}$$. Our lemma readily yields

$$ \lVert x^{-1} - y^{-1} \rVert \leq \lVert x^{-1} \rVert \lVert y^{-1} \rVert \lVert x - y \rVert < 2 \lVert x^{-1} \rVert^{2} \lVert x - y \rVert. $$

Therefore, at any point $$x \in \mathcal{A}^{\times}$$ and for any $$\epsilon > 0$$, the image under $$i$$ of the ball of radius
$$ \frac{\epsilon}{2 \lVert x^{-1} \rVert^{2}} $$
centered at $$x$$ is contained in the ball of radius $$\epsilon$$ centered at $$x^{-1}$$.
$$\tag*{$\blacksquare$}$$

In conclusion, $$\mathcal{A}^{\times}$$ is a Banach Lie group.
