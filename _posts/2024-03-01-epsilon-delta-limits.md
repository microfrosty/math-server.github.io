---
layout: post
title: "The Epsilon-Delta Definition of a Limit"
subtitle: "Making the intuitive notion of 'approaching' mathematically precise"
date: 2024-03-01
categories: [learning]
math_category: calculus
tags: [calculus, limits, real-analysis, foundations]
reading_time: 12
tldr: The ε-δ definition pins down exactly what it means for f(x) to approach L as x approaches a, removing all hand-waving from calculus.
---

Calculus rests on the concept of a **limit**. Informally, we say $\lim_{x \to a} f(x) = L$ when $f(x)$ gets arbitrarily close to $L$ as $x$ approaches $a$. But "arbitrarily close" and "approaches" are not mathematics — they're metaphors. The epsilon-delta definition replaces the metaphors with logic.

## The Definition

$$\lim_{x \to a} f(x) = L \iff \forall\, \eps > 0,\; \exists\, \delta > 0 \text{ s.t. } 0 < |x - a| < \delta \implies |f(x) - L| < \eps$$

Read aloud: "For every challenge $\eps$ (how close you want $f(x)$ to be to $L$), I can find a response $\delta$ (how close $x$ must be to $a$) that meets the challenge."

## A Worked Example

**Claim:** $\lim_{x \to 3} (2x + 1) = 7$.

**Proof:** Let $\eps > 0$ be given. We need $|f(x) - 7| < \eps$, i.e., $|(2x+1) - 7| = |2x - 6| = 2|x-3| < \eps$.

This holds when $|x - 3| < \eps/2$. So choose $\delta = \eps/2$.

Then $0 < |x - 3| < \delta \implies |f(x) - 7| = 2|x-3| < 2\delta = \eps$. $\square$

## Why the $0 < |x - a|$ Condition?

Notice we require $0 < |x - a|$, meaning $x \neq a$. Limits describe behavior **near** a point, not **at** it. The function need not even be defined at $a$.

For example, $\lim_{x \to 0} \frac{\sin x}{x} = 1$ even though $\frac{\sin 0}{0}$ is undefined.

## The Squeeze Theorem

If $g(x) \leq f(x) \leq h(x)$ near $a$, and $\lim_{x\to a} g(x) = \lim_{x\to a} h(x) = L$, then:

$$\lim_{x \to a} f(x) = L$$

**Proof of $\lim_{x \to 0} \frac{\sin x}{x} = 1$:** For $0 < x < \pi/2$:

$$\cos x \leq \frac{\sin x}{x} \leq 1$$

Since $\lim_{x\to 0}\cos x = 1$ and $\lim_{x\to 0} 1 = 1$, the Squeeze Theorem gives the result.

## Continuity

A function $f$ is **continuous at $a$** if:

$$\lim_{x \to a} f(x) = f(a)$$

Three things must hold: $f(a)$ is defined, the limit exists, and they're equal. Continuity is what makes calculus "work" — the intermediate value theorem, the extreme value theorem, and differentiability all build on it.
