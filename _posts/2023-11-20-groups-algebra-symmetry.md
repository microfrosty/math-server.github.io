---
layout: post
title: "Groups: The Algebra of Symmetry"
subtitle: "Why the symmetries of a triangle and modular addition are the same thing"
date: 2023-11-20
categories: [learning]
math_category: abstract-algebra
tags: [abstract-algebra, group-theory, symmetry]
reading_time: 11
tldr: A group is a set with an associative binary operation, identity, and inverses. Groups capture the abstract structure of symmetry — the same axioms govern rotations, permutations, and clock arithmetic.
---

## The Definition

A **group** is a set $G$ with a binary operation $\cdot$ satisfying:

1. **Closure:** $a, b \in G \implies a \cdot b \in G$
2. **Associativity:** $(a \cdot b) \cdot c = a \cdot (b \cdot c)$
3. **Identity:** $\exists\, e \in G$ such that $e \cdot a = a \cdot e = a$
4. **Inverses:** $\forall\, a \in G,\; \exists\, a^{-1}$ such that $a \cdot a^{-1} = e$

If additionally $a \cdot b = b \cdot a$ for all $a, b$, the group is **abelian** (commutative).

## Examples

- $(\Z, +)$: integers under addition. Identity $0$, inverse of $n$ is $-n$. Abelian.
- $(\Z/n\Z, +)$: integers mod $n$. Finite abelian group of order $n$.
- $S_n$: **symmetric group**, all permutations of $\{1,\ldots,n\}$ under composition. Order $n!$. Non-abelian for $n \geq 3$.
- $D_n$: **dihedral group**, symmetries of a regular $n$-gon (rotations + reflections). Order $2n$.
- $\mathrm{GL}(n, \R)$: invertible $n \times n$ real matrices under multiplication. Non-abelian for $n \geq 2$.

## Subgroups and Lagrange's Theorem

A subset $H \subseteq G$ is a **subgroup** if it is itself a group under the same operation.

**Lagrange's Theorem:** If $G$ is finite and $H \leq G$, then $|H|$ divides $|G|$.

Consequence: in a group of prime order $p$, the only subgroups are $\{e\}$ and $G$ itself — such groups are **cyclic**: $G = \langle g \rangle = \{e, g, g^2, \ldots, g^{p-1}\}$.

## Homomorphisms

A **group homomorphism** $\phi: G \to H$ satisfies:

$$\phi(a \cdot b) = \phi(a) \cdot \phi(b)$$

The **kernel** $\ker\phi = \{g \in G : \phi(g) = e_H\}$ is a normal subgroup of $G$.

The **First Isomorphism Theorem**:

$$G / \ker\phi \cong \operatorname{Im}\phi$$

This is the structural heart of algebra: every homomorphism factors through a quotient.

## Why Groups?

Galois showed that the solvability of a polynomial by radicals depends entirely on the structure of its **Galois group** — the group of field automorphisms permuting its roots. Groups are also the mathematical language of particle physics: the Standard Model is built on the gauge group $\mathrm{U}(1) \times \mathrm{SU}(2) \times \mathrm{SU}(3)$.

Abstract algebra began as the study of equations. It became the study of structure itself.
