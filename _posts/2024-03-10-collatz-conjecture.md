---
layout: post
title: "The Collatz Conjecture: Simple to State, Impossible to Prove"
subtitle: "One of the most deceptively simple open problems in all of mathematics"
date: 2024-03-10
categories: [exploration]
tags: [number-theory, open-problems, sequences]
reading_time: 8
tldr: Pick any positive integer. If even, halve it. If odd, multiply by 3 and add 1. Repeat. The conjecture says you always reach 1 — and nobody can prove it.
---

Take any positive integer $n$. Apply this rule:

$$
f(n) = \begin{cases} n/2 & \text{if } n \equiv 0 \pmod{2} \\ 3n + 1 & \text{if } n \equiv 1 \pmod{2} \end{cases}
$$

Repeat indefinitely. The **Collatz conjecture** states that for every positive integer $n$, this process eventually reaches $1$.

## A Few Examples

Starting from $n = 6$:

$$6 \to 3 \to 10 \to 5 \to 16 \to 8 \to 4 \to 2 \to 1$$

Starting from $n = 27$, the sequence takes a wild ride — it climbs to $9232$ before finally descending to $1$ after 111 steps.

## Why Is This Hard?

The problem has a fractal-like resistance to analysis. Each step multiplies the odd numbers by roughly $3/2$ (since multiply by 3, add 1, then divide by 2), suggesting divergence — yet empirically every number tested collapses to 1.

The density of odd numbers encountered is approximately $1/2$ of steps, so heuristically:

$$\mathbb{E}\left[\log f(n)\right] \approx \frac{1}{2}\log\frac{1}{2} + \frac{1}{2}\log\frac{3}{2} \approx -0.059$$

This negative expected log-drift suggests convergence — but heuristics are not proofs.

## What We Do Know

Mathematicians have verified the conjecture computationally for all $n < 2^{68}$ (roughly $2.95 \times 10^{20}$). Yet as Paul Erdős reportedly said:

> Mathematics is not yet ready for such problems.

The conjecture resists tools from ergodic theory, $p$-adic analysis, and analytic number theory alike. Terence Tao made significant progress in 2019, showing that "almost all" Collatz sequences (in a logarithmic density sense) eventually reach a value below any given function $f(n) \to \infty$ — the closest anyone has come.

## An Invitation

Try writing code to visualize the "stopping time" (number of steps to reach 1) as a function of $n$. Plot it. You'll find a beautiful, chaotic fractal structure that makes the problem feel even more mysterious.

$$\sigma(n) = \min\{k \geq 0 : f^k(n) = 1\}$$

Where $f^k$ means $f$ applied $k$ times. The graph of $\sigma(n)$ is one of the most beautiful objects in elementary number theory.
