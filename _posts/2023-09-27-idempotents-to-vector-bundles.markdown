---
layout: post
title:  "From idempotent matrices arise vector bundles."
categories: jekyll update
---
<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# Lemma 1

Let $$\mathcal{A}$$ be a Banach algebra with unit $$\mathbf{1}$$.
Suppose $$x$$ and $$y$$ are idempotent and

$$ \lVert x - y \rVert < \frac{1}{\lVert 2x - \mathbf{1} \rVert}. $$

Then $$x$$ and $$y$$ are conjugate, i.e., $$x = aya^{-1}$$ for some $$a \in \mathcal{A}$$.

In other words, conjugacy classes partition the set of idempotent elements into open subsets.

# Proof

Displayed below is our candidate $$a$$.
$$ a = \mathbf{1} - x - y + 2xy. $$
Observe

$$ xa = x - x^{2} - xy + 2x^{2}y = xy $$

and

$$ ay = y - xy - y^{2} + 2xy^{2} = xy. $$

If $$a$$ is invertible, then
$$ x = aya^{-1}. $$
It therefore remains only to prove the invertibility of $$a$$, and we do so by invoking Proposition 1 of the previous post.

I compute:

$$ \mathbf{1} - a = x + y - 2xy = (x - y)(2x - \mathbf{1}). $$

This readily implies

$$ \lVert a - \mathbf{1} \rVert \leq \lVert x - y \rVert \lVert 2x - \mathbf{1} \rVert < 1. $$

Now apply Proposition 1 as planned.
$$\tag*{$\blacksquare$}$$

Note that $$\lVert 2x - \mathbf{1} \rVert$$ is nonzero for idempotent $$x$$, since
$$ x = (2x - \mathbf{1})x $$
implies
$$ 1 \leq \lVert 2x - \mathbf{1} \rVert. $$

I now specialize to the following case.
Let $$X$$ be a compact Hausdorff space.
Let $$M(n,C(X))$$ be the Banach algebra of $$n \times n$$ matrices with entries in the ring of continuous $$\mathbf{C}$$-valued functions on $$X$$ equipped with the supremum norm.

# Lemma 2

Elements $$E$$ of $$M(n,C(X))$$ determine continuous functions $$E\colon X \to M(n,\mathbf{C})$$.

# Proof

Fix $$A \in M(n,\mathbf{C})$$ and $$\epsilon > 0$$. Consider the open ball $$U_{\epsilon}(A)$$. I claim $$E^{-1}(U_{\epsilon}(A))$$ is open in $$X$$. To this end, fix $$p \in E^{-1}(U_{\epsilon}(A))$$.

$$ \lVert E(p) - A \lVert < \epsilon. $$

Define

$$ \delta(p) = \frac{\epsilon - \lVert E(p) - A \lVert}{n^{2}}. $$

I claim that

$$ V(p) = \bigcap_{1 \leq i,j \leq n} E_{ij}^{-1}(U_{\delta(p)}(E_{ij}(p))) $$

is an open neighborhood of $$p$$ contained within $$E^{-1}(U_{\epsilon}(A))$$.

Certainly $$p$$ lies in $$V(p)$$. Suppose $$q \in X$$ too lies in $$V(p)$$. For any vector $$v \in \mathbf{C}^{n}$$ of unit length,

$$ \left| (E(q) - E(p))v \right| \leq n \max_{1 \leq i \leq n} \left| \sum_{j=1}^{n} (E_{ij}(q) - E_{ij}(p))v_{j} \right| $$

$$ \leq n \max_{1 \leq i \leq n} \sum_{j=1}^{n} \left| E_{ij}(q) - E_{ij}(p) \right| |v_{j}| $$

$$ < n \max_{1 \leq i \leq n} \sum_{j=1}^{n} \delta(p) |v_{j}| $$

$$ \leq \epsilon - \lVert E(p) - A \rVert. $$

This computation reveals

$$ \lVert E(q) - A \rVert \leq \lVert E(q) - E(p) \rVert + \lVert E(p) - A \rVert < \epsilon. $$

That is, $$q \in E^{-1}(U_{\epsilon}(A))$$.
$$\tag*{$\blacksquare$}$$

# Proposition 1

Let $$E\colon X \to \operatorname{M}(n,\mathbf{C})$$ be an idempotent element of $$\operatorname{M}(n,C(X))$$.
Then $$\operatorname{Ran} E$$ is a subbundle of $$\Theta^{n}(X)$$.

# Proof

Fix $$x \in X$$. Define

$$ V = \left\{ F \in \operatorname{M}(n,\mathbf{C}) : \lVert E(x) - F \rVert < \frac{1}{\lVert 2E(x) - I_{n} \rVert} \right\}. $$

Define $$U = E^{-1}(V)$$.
By Lemma 2, $$U$$ is an open subset of $$X$$.
We prove $$U$$ is a trivial neighborhood of $$x$$.

Define $$S\colon U \to \operatorname{GL}(n,\mathbf{C})$$ by the formula below.

$$ S(y) = I_{n} - E(x) - E(y) + E(x)E(y). $$

By Lemma 1,
$$ E(y) = S(y)^{-1}E(x)S(y). $$
Hence, the function $$S(y)\colon (\operatorname{Ran} E)_{y} \to (\operatorname{Ran} E)_{x}$$ is an isomorphism.
$$\tag*{$\blacksquare$}$$

The obvious generalization to endomorphisms of vector bundles does not hold. Consider for instance the trivial bundle over the unit interval together with the endomorphism

$$ (t,\lambda) \mapsto (t,t\lambda), $$

where $$(t,\lambda) \in [0,1] \times \mathbf{R}$$. The stalk at $$0$$ is zero-dimensional.
