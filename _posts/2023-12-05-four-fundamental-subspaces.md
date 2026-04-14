---
layout: post
title: "The Four Fundamental Subspaces"
subtitle: "Gilbert Strang's organizing principle for all of linear algebra"
date: 2023-12-05
categories: [learning]
math_category: linear-algebra
tags: [linear-algebra, subspaces, rank, null-space]
reading_time: 9
tldr: Every m×n matrix gives rise to four subspaces — column space, null space, row space, left null space — and their dimensions are linked by the rank-nullity theorem.
---

Gilbert Strang argues that all of linear algebra — Gaussian elimination, least squares, the SVD — flows from understanding four subspaces associated with any matrix $A \in \R^{m \times n}$.

## The Four Subspaces

| Subspace | Lives in | Definition |
|---|---|---|
| Column space $C(A)$ | $\R^m$ | $\{A\mathbf{x} : \mathbf{x} \in \R^n\}$ |
| Null space $N(A)$ | $\R^n$ | $\{\mathbf{x} : A\mathbf{x} = \mathbf{0}\}$ |
| Row space $C(A^T)$ | $\R^n$ | $\{A^T\mathbf{y} : \mathbf{y} \in \R^m\}$ |
| Left null space $N(A^T)$ | $\R^m$ | $\{\mathbf{y} : A^T\mathbf{y} = \mathbf{0}\}$ |

## The Rank-Nullity Theorem

Let $r = \operatorname{rank}(A)$. Then:

$$\dim C(A) = r, \quad \dim N(A) = n - r$$
$$\dim C(A^T) = r, \quad \dim N(A^T) = m - r$$

The dimensions add up perfectly: $r + (n-r) = n$ in $\R^n$, and $r + (m-r) = m$ in $\R^m$.

## Orthogonality

The deep fact: **the row space and null space are orthogonal complements in $\R^n$**:

$$C(A^T) \perp N(A) \quad \text{and} \quad C(A^T) \oplus N(A) = \R^n$$

Similarly, $C(A) \perp N(A^T)$ in $\R^m$.

This is why the equation $A\mathbf{x} = \mathbf{b}$ has a solution exactly when $\mathbf{b} \perp N(A^T)$ — the solvability condition.

## Solving $A\mathbf{x} = \mathbf{b}$

The complete solution decomposes as:

$$\mathbf{x} = \mathbf{x}_{\text{particular}} + \mathbf{x}_{\text{null}}$$

where $\mathbf{x}_{\text{null}} \in N(A)$. The particular solution lives in $C(A^T)$ (minimum norm), and the null space component is the freedom we have in the solution.

Understanding these four subspaces turns solving linear systems from mechanical row reduction into genuine geometric insight.
