---
layout: post
title: "The Real Numbers: Completeness and Why It Matters"
subtitle: "Plugging the holes that the rationals leave behind"
date: 2023-10-30
categories: [learning]
math_category: real-analysis
tags: [real-analysis, completeness, sequences, cauchy]
reading_time: 12
tldr: The real numbers are the unique complete ordered field. Completeness — no gaps — is what makes limits, integrals, and the intermediate value theorem actually work.
---

The rational numbers $\Q$ have a problem: they have **holes**. The sequence $1, 1.4, 1.41, 1.414, \ldots$ of rational approximations to $\sqrt{2}$ converges to something — but that something ($\sqrt{2}$) is not rational.

Real analysis is the project of building calculus on a foundation without holes.

## Completeness

An ordered field $F$ is **complete** (or satisfies the **least upper bound property**) if every nonempty subset of $F$ that is bounded above has a **supremum** (least upper bound) in $F$.

$\Q$ fails this: the set $\{q \in \Q : q^2 < 2\}$ is bounded above, but its supremum ($\sqrt{2}$) is not in $\Q$.

$\R$ satisfies it. This is the defining property of the reals — not any construction.

## Cauchy Sequences

A sequence $(a_n)$ is **Cauchy** if:

$$\forall\, \eps > 0,\; \exists\, N \text{ s.t. } m, n > N \implies |a_m - a_n| < \eps$$

In $\R$: a sequence converges $\iff$ it is Cauchy. (In $\Q$, Cauchy sequences may not converge.)

This equivalence — **Cauchy completeness** — is equivalent to the least upper bound property for ordered fields.

## Key Theorems That Need Completeness

**Bolzano-Weierstrass:** Every bounded sequence in $\R$ has a convergent subsequence.

*Proof sketch:* Use repeated bisection to extract a Cauchy subsequence; invoke completeness.

**Intermediate Value Theorem:** If $f: [a,b] \to \R$ is continuous and $f(a) < 0 < f(b)$, then $\exists\, c \in (a,b)$ with $f(c) = 0$.

*Proof sketch:* Let $S = \{x \in [a,b] : f(x) < 0\}$. By completeness, $c = \sup S$ exists. By continuity, $f(c) = 0$.

**Extreme Value Theorem:** A continuous function on a closed bounded interval attains its maximum and minimum.

All three fail on $\Q$. They are theorems about $\R$, not analysis in general.

## Constructing $\R$ from $\Q$

There are two standard constructions:

1. **Dedekind cuts:** A cut is a partition $\Q = A \mid B$ with $A$ having no maximum. Each cut represents a real number.
2. **Cauchy completion:** Take all Cauchy sequences in $\Q$, quotient by the equivalence relation $(a_n) \sim (b_n) \iff |a_n - b_n| \to 0$.

Both yield the same object (up to isomorphism) — the unique complete ordered field.

## The Nested Interval Property

Equivalent to completeness: if $[a_1, b_1] \supset [a_2, b_2] \supset \cdots$ is a nested sequence of closed bounded intervals, then $\bigcap_{n=1}^\infty [a_n, b_n] \neq \emptyset$.

This is the engine behind many existence proofs in analysis. Completeness is not a technical nicety — it is the reason calculus works.
