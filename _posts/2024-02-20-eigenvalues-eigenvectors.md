---
layout: post
title: "Eigenvalues and Eigenvectors: The Skeleton of a Matrix"
subtitle: "Understanding what a linear transformation actually does"
date: 2024-02-20
categories: [learning]
math_category: linear-algebra
tags: [linear-algebra, eigenvalues, transformations]
reading_time: 11
tldr: Eigenvectors are the directions a matrix doesn't rotate — only stretches. Their eigenvalues are the stretch factors. Together they reveal a matrix's true nature.
---

A matrix $A$ represents a linear transformation: it takes vectors in and spits vectors out. Most vectors get both rotated and scaled. But some special vectors — **eigenvectors** — only get scaled.

## The Definition

A nonzero vector $\mathbf{v}$ is an **eigenvector** of $A$ with **eigenvalue** $\lambda$ if:

$$A\mathbf{v} = \lambda\mathbf{v}$$

The matrix $A$ acts on $\mathbf{v}$ exactly like scalar multiplication by $\lambda$.

## Finding Eigenvalues

Rewrite: $(A - \lambda I)\mathbf{v} = \mathbf{0}$. For nonzero solutions, the matrix $A - \lambda I$ must be singular:

$$\det(A - \lambda I) = 0$$

This is the **characteristic equation**. Its roots are the eigenvalues.

**Example:** Let $A = \begin{pmatrix} 3 & 1 \\ 0 & 2 \end{pmatrix}$.

$$\det(A - \lambda I) = (3-\lambda)(2-\lambda) = 0 \implies \lambda_1 = 3,\; \lambda_2 = 2$$

For $\lambda_1 = 3$: $(A - 3I)\mathbf{v} = \begin{pmatrix}0&1\\0&-1\end{pmatrix}\mathbf{v} = \mathbf{0}$, giving $\mathbf{v}_1 = \begin{pmatrix}1\\0\end{pmatrix}$.

For $\lambda_2 = 2$: $(A - 2I)\mathbf{v} = \begin{pmatrix}1&1\\0&0\end{pmatrix}\mathbf{v} = \mathbf{0}$, giving $\mathbf{v}_2 = \begin{pmatrix}-1\\1\end{pmatrix}$.

## Diagonalization

If $A$ has $n$ linearly independent eigenvectors, form matrix $P = [\mathbf{v}_1 \mid \cdots \mid \mathbf{v}_n]$. Then:

$$A = P D P^{-1}, \quad D = \operatorname{diag}(\lambda_1, \ldots, \lambda_n)$$

This is **diagonalization**. It's enormously useful: $A^k = P D^k P^{-1}$, and $D^k = \operatorname{diag}(\lambda_1^k, \ldots, \lambda_n^k)$.

## The Spectral Theorem

For **symmetric** matrices ($A = A^T$):
- All eigenvalues are **real**
- Eigenvectors for distinct eigenvalues are **orthogonal**
- $A$ is always diagonalizable: $A = Q D Q^T$ with $Q$ orthogonal

This is the **spectral theorem**, the cornerstone of principal component analysis (PCA), quadratic forms, and quantum mechanics.

## Geometric Intuition

The eigenvalues of the **Jacobian** of a dynamical system $\dot{\mathbf{x}} = f(\mathbf{x})$ at a fixed point tell you whether the system is stable:
- $\Re(\lambda) < 0$ for all $\lambda$: stable (attracting)
- Any $\Re(\lambda) > 0$: unstable (repelling)

Eigenvalues aren't just algebra — they're the geometry of change.
