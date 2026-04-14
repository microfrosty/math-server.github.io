---
layout: post
title: "Integration by Parts: The Product Rule in Reverse"
subtitle: "A systematic technique for integrating products of functions"
date: 2024-01-15
categories: [learning]
math_category: calculus
tags: [calculus, integration, techniques]
reading_time: 8
tldr: Integration by parts turns ∫u dv into uv − ∫v du, letting you trade a hard integral for an easier one.
---

The **product rule** for differentiation says:

$$\frac{\d}{\d x}[u(x)v(x)] = u'(x)v(x) + u(x)v'(x)$$

Integrate both sides:

$$u(x)v(x) = \int u'v\,\d x + \int uv'\,\d x$$

Rearrange:

$$\boxed{\int u\,\d v = uv - \int v\,\d u}$$

This is **integration by parts**.

## The LIATE Rule

Choosing $u$ and $dv$ is an art. A useful heuristic — **LIATE** — says to prefer $u$ in this order:

1. **L**ogarithms
2. **I**nverse trig
3. **A**lgebraic (polynomials)
4. **T**rigonometric
5. **E**xponential

## Worked Examples

**Example 1:** $\int x e^x\,\d x$

Let $u = x$, $\d v = e^x\,\d x$. Then $\d u = \d x$, $v = e^x$.

$$\int x e^x\,\d x = xe^x - \int e^x\,\d x = xe^x - e^x + C = e^x(x-1) + C$$

**Example 2:** $\int \ln x\,\d x$

Let $u = \ln x$, $\d v = \d x$. Then $\d u = \frac{1}{x}\d x$, $v = x$.

$$\int \ln x\,\d x = x\ln x - \int x \cdot \frac{1}{x}\,\d x = x\ln x - x + C$$

**Example 3 (applying twice):** $\int x^2 e^x\,\d x$

First pass: $u = x^2$, $\d v = e^x\,\d x$:

$$\int x^2 e^x\,\d x = x^2 e^x - 2\int x e^x\,\d x$$

Second pass: use Example 1:

$$= x^2 e^x - 2e^x(x-1) + C = e^x(x^2 - 2x + 2) + C$$

## The "Cycling" Trick

Some integrals cycle back to themselves. Consider $I = \int e^x \sin x\,\d x$.

Apply parts twice:

$$I = e^x\sin x - e^x\cos x - I$$

$$2I = e^x(\sin x - \cos x)$$

$$I = \frac{e^x(\sin x - \cos x)}{2} + C$$

This algebraic trick — the integral appearing on both sides — is one of the most satisfying moves in all of calculus.
