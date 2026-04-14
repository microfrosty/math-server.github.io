---
layout: post
title: "Introduction to Topological Spaces"
subtitle: "What remains when you throw away distance but keep the notion of nearness"
date: 2024-01-08
categories: [learning]
math_category: topology
tags: [topology, open-sets, continuity, metric-spaces]
reading_time: 13
tldr: A topology on a set captures 'nearness' without needing a metric. Open sets are the primitive notion; continuity, compactness, and connectedness all follow.
---

In metric spaces, we measure distances. But many important properties — continuity, convergence, connectedness — only need to know *which* sets are "open," not how far apart points are. **Topology** abstracts away the metric.

## Topological Spaces

A **topology** on a set $X$ is a collection $\mathcal{T}$ of subsets (called **open sets**) satisfying:

1. $\emptyset, X \in \mathcal{T}$
2. Arbitrary unions of open sets are open: $\{U_\alpha\} \subset \mathcal{T} \implies \bigcup_\alpha U_\alpha \in \mathcal{T}$
3. Finite intersections of open sets are open: $U, V \in \mathcal{T} \implies U \cap V \in \mathcal{T}$

The pair $(X, \mathcal{T})$ is a **topological space**.

## Examples

- **Discrete topology:** $\mathcal{T} = \mathcal{P}(X)$ (every subset is open). Every function out of $X$ is continuous.
- **Indiscrete topology:** $\mathcal{T} = \{\emptyset, X\}$. Only constant functions into $X$ are continuous.
- **Standard topology on $\R$:** Open sets are arbitrary unions of open intervals $(a,b)$. This is the topology calculus lives in.
- **Zariski topology:** Used in algebraic geometry. Closed sets are zero sets of polynomials.

## Continuity Redefined

A function $f: X \to Y$ is **continuous** if the preimage of every open set is open:

$$V \in \mathcal{T}_Y \implies f^{-1}(V) \in \mathcal{T}_X$$

This generalizes the $\eps$-$\delta$ definition — and works even when there's no distance function.

## Homeomorphism

A **homeomorphism** is a continuous bijection with continuous inverse. Two spaces are **homeomorphic** ($X \cong Y$) if one can be continuously deformed into the other.

The classic joke: a topologist cannot tell a coffee mug from a donut — both are homeomorphic to a torus $T^2 = S^1 \times S^1$.

Formally, topological properties are those preserved under homeomorphism: connectedness, compactness, genus, fundamental group.

## Compactness

A space $X$ is **compact** if every open cover has a finite subcover:

$$X \subset \bigcup_\alpha U_\alpha \implies X \subset U_{\alpha_1} \cup \cdots \cup U_{\alpha_n}$$

In $\R^n$: compact $\iff$ closed and bounded (**Heine-Borel**). The closed interval $[0,1]$ is compact; $(0,1)$ is not.

Compactness is what makes continuous functions on $[a,b]$ achieve their maximum — the **extreme value theorem**.

## Why Topology?

Topology is the language of modern geometry, analysis, and mathematical physics. Manifolds (the stage for general relativity), fiber bundles (the language of gauge theory), and algebraic varieties all live in topological spaces. Learning topology is learning the grammar of geometric thought.
