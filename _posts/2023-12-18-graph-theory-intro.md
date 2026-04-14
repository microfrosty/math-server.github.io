---
layout: post
title: "Graph Theory: The Mathematics of Networks"
subtitle: "From bridges in Königsberg to social networks and circuit boards"
date: 2023-12-18
categories: [learning]
math_category: discrete-mathematics
tags: [discrete-math, graph-theory, networks, algorithms]
reading_time: 10
tldr: A graph is a set of vertices connected by edges. Graph theory answers questions about paths, connectivity, coloring, and flow — with applications everywhere from logistics to biology.
---

## What Is a Graph?

A **graph** $G = (V, E)$ consists of a set $V$ of **vertices** and a set $E \subseteq \binom{V}{2}$ of **edges**. Two vertices connected by an edge are **adjacent**.

Variations:
- **Directed graph (digraph):** Edges have direction, $E \subseteq V \times V$
- **Weighted graph:** Each edge carries a numerical weight
- **Multigraph:** Multiple edges between the same pair of vertices allowed

## The Seven Bridges of Königsberg

In 1736, Euler asked: can you walk through Königsberg crossing each of its seven bridges exactly once? He proved it's impossible — and in doing so, founded graph theory.

**Key insight:** Model land masses as vertices, bridges as edges. An **Eulerian path** (traversing every edge exactly once) exists iff the graph has exactly 0 or 2 vertices of odd degree.

Königsberg has four vertices of odd degree. No Eulerian path exists.

## Basic Theorems

**Handshaking Lemma:** For any graph $G$:

$$\sum_{v \in V} \deg(v) = 2|E|$$

*Proof:* Each edge contributes 2 to the total degree count. $\square$

Corollary: every graph has an even number of odd-degree vertices.

**Euler's Formula:** For any connected planar graph:

$$V - E + F = 2$$

where $F$ is the number of faces (including the outer face). Consequence: $K_5$ (complete graph on 5 vertices) and $K_{3,3}$ (complete bipartite on $3+3$ vertices) are non-planar — **Kuratowski's theorem** says these are the only obstructions.

## Trees

A **tree** is a connected acyclic graph. For a tree on $n$ vertices:
- Exactly $n - 1$ edges
- Unique path between any two vertices
- Removing any edge disconnects it

**Cayley's Formula:** The number of labeled trees on $n$ vertices is $n^{n-2}$.

For $n = 3$: $3^1 = 3$ trees. For $n = 4$: $4^2 = 16$.

## Graph Coloring

A **proper $k$-coloring** assigns colors from $\{1, \ldots, k\}$ to vertices so no two adjacent vertices share a color. The **chromatic number** $\chi(G)$ is the minimum $k$ needed.

**Four Color Theorem (Appel–Haken, 1976):** Every planar graph satisfies $\chi(G) \leq 4$.

This was the first major theorem proved with computer assistance — and remains controversial among mathematicians who prefer human-checkable proofs.

## Shortest Paths

**Dijkstra's algorithm** finds the shortest path from a source vertex to all others in $O((V + E)\log V)$ time (with a priority queue), assuming non-negative weights.

The algorithm maintains a set $S$ of "settled" vertices and greedily adds the nearest unsettled vertex:

```
dist[s] = 0; dist[v] = ∞ for v ≠ s
while unsettled vertices remain:
    u = unsettled vertex with minimum dist[u]
    for each neighbor v of u:
        dist[v] = min(dist[v], dist[u] + w(u,v))
```

Graph theory is where discrete mathematics touches the real world most directly — every network, from the internet to protein interactions, is a graph.
