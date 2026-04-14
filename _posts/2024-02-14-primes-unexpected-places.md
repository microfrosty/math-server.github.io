---
layout: post
title: "Primes in Unexpected Places"
subtitle: "From Pascal's triangle to Ulam spirals — prime numbers hide in plain sight"
date: 2024-02-14
categories: [exploration]
tags: [primes, patterns, visualization]
reading_time: 6
tldr: Prime numbers appear in surprising structures — Pascal's triangle, spiral grids, even musical tuning systems — hinting at deep hidden order.
---

Most people meet primes as a list: $2, 3, 5, 7, 11, 13, \ldots$ But primes have a habit of appearing where nobody expected them.

## Pascal's Triangle mod 2

Color every entry in Pascal's triangle: white if even, black if odd. The pattern that emerges is **Sierpiński's triangle** — a fractal with self-similar structure at every scale.

The entry $\binom{n}{k}$ is odd if and only if $k \mathbin{\&} n = k$ (bitwise AND), a consequence of **Kummer's theorem**: the highest power of prime $p$ dividing $\binom{m+n}{m}$ equals the number of carries when adding $m$ and $n$ in base $p$.

## The Ulam Spiral

In 1963, Stanisław Ulam, bored during a meeting, started writing integers in a spiral:

```
17 16 15 14 13
18  5  4  3 12
19  6  1  2 11
20  7  8  9 10
21 22 23 24 25 ...
```

When he circled the primes, diagonal lines appeared. Primes cluster along diagonals corresponding to quadratic polynomials like $n^2 + n + 41$ — **Euler's lucky number**, which generates primes for $n = 0, 1, \ldots, 39$.

## Wilson's Theorem

A number $p$ is prime if and only if:

$$(p-1)! \equiv -1 \pmod{p}$$

This is a beautiful characterization — but practically useless for testing primality (computing $(p-1)!$ for large $p$ is infeasible). Its elegance is purely theoretical.

## Primes and Music

The 12-tone equal temperament system divides the octave into 12 equal semitones. Why 12? Partly because $2^{7/12} \approx 1.4983 \approx 3/2$ — a perfect fifth — making the tuning system work. The density of good rational approximations to $\log_2 3$ is intimately connected to the distribution of primes via the **three-distance theorem**.

## The Riemann Hypothesis

All of this hints at deeper structure. The distribution of primes is governed by the zeros of the **Riemann zeta function**:

$$\zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^s} = \prod_{p \text{ prime}} \frac{1}{1 - p^{-s}}$$

The hypothesis: all non-trivial zeros of $\zeta(s)$ lie on the line $\Re(s) = 1/2$. A million-dollar problem. Unsolved since 1859.

Primes are everywhere. We just haven't learned to see them yet.
