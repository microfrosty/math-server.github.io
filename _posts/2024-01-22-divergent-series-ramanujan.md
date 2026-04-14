---
layout: post
title: "Does 1 + 2 + 3 + 4 + ⋯ = −1/12?"
subtitle: "Ramanujan summation and the regularization of divergent series"
date: 2024-01-22
categories: [exploration]
tags: [series, analysis, regularization, ramanujan]
reading_time: 10
tldr: In a precise, well-defined sense — yes. Ramanujan summation assigns −1/12 to the divergent series of all natural numbers, and this value appears in physics and string theory.
---

One of the most viral equations in mathematics:

$$1 + 2 + 3 + 4 + \cdots = -\frac{1}{12}$$

Is this nonsense? Is it profound? The answer is: **both, depending on context**.

## The Standard View

In the usual sense of convergence, the partial sums $S_N = N(N+1)/2$ grow without bound. The series **diverges**. Full stop.

## Ramanujan's Approach

Srinivasa Ramanujan, working in India without access to Western mathematical literature, independently developed a summation method. For a function $f$ satisfying certain conditions:

$$\sum_{n=0}^{\infty} f(n) \overset{R}{=} -\sum_{k=1}^{\infty} \frac{B_k}{k!} f^{(k-1)}(0)$$

where $B_k$ are **Bernoulli numbers**. For $f(n) = n$, this yields $-1/12$.

## The Zeta Function Route

The Riemann zeta function:

$$\zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^s}, \quad \Re(s) > 1$$

can be analytically continued to all $s \in \C$ except $s = 1$. At $s = -1$:

$$\zeta(-1) = -\frac{1}{12}$$

Formally, $\zeta(-1) = 1 + 2 + 3 + \cdots$, but this is **not** a statement about convergence — it's a statement about the unique analytic continuation of $\zeta$.

## Why Physicists Care

In **string theory** and the **Casimir effect**, regularized sums of this type appear naturally. The Casimir effect (the measurable attraction between uncharged parallel conducting plates) is computed using a regularized sum:

$$E = \frac{\hbar c}{2} \sum_{n=1}^{\infty} n \cdot \frac{\pi}{L} \overset{\text{reg.}}{=} \frac{\hbar c \pi}{2L} \cdot \left(-\frac{1}{12}\right) = -\frac{\pi \hbar c}{24 L}$$

This is experimentally verified.

## The Moral

Mathematics has many notions of "sum." The standard one (limit of partial sums) is not the only one. Ramanujan summation, zeta regularization, and Abel summation all assign finite values to some divergent series — **consistently** across different methods — and those values are useful.

The equation $1 + 2 + 3 + \cdots = -1/12$ is not wrong. It's a statement about a different notion of sum than the one you learned in calculus. And that distinction matters enormously.
