---
layout: post
title: "Modular Arithmetic and the Chinese Remainder Theorem"
subtitle: "Clock arithmetic, congruences, and a 2000-year-old algorithm"
date: 2024-02-05
categories: [learning]
math_category: number-theory
tags: [number-theory, modular-arithmetic, crt, cryptography]
reading_time: 10
tldr: Modular arithmetic is clock math generalized. The Chinese Remainder Theorem says that knowing a number mod several coprime moduli uniquely determines it mod their product.
---

**Modular arithmetic** formalizes the idea of a clock: after 12 comes 1, not 13. We write $a \equiv b \pmod{n}$ (read "$a$ is congruent to $b$ mod $n$") when $n \mid (a - b)$.

## Basic Properties

Congruences behave like equations — you can add, subtract, and multiply both sides:

$$a \equiv b,\; c \equiv d \pmod{n} \implies \begin{cases} a + c \equiv b + d \\ ac \equiv bd \end{cases} \pmod{n}$$

Division is trickier. $a \cdot x \equiv 1 \pmod{n}$ has a solution (the **modular inverse**) exactly when $\gcd(a, n) = 1$.

## Fermat's Little Theorem

If $p$ is prime and $\gcd(a, p) = 1$:

$$a^{p-1} \equiv 1 \pmod{p}$$

Equivalently, $a^p \equiv a \pmod p$ for all $a$. This is the foundation of **RSA encryption**: encrypting with exponent $e$ and decrypting with $d$ where $ed \equiv 1 \pmod{p-1}$.

## The Chinese Remainder Theorem

**Theorem.** Let $n_1, n_2, \ldots, n_k$ be pairwise coprime. Then the system:

$$x \equiv a_1 \pmod{n_1}, \quad x \equiv a_2 \pmod{n_2}, \quad \ldots, \quad x \equiv a_k \pmod{n_k}$$

has a unique solution modulo $N = n_1 n_2 \cdots n_k$.

**Construction.** Let $N_i = N/n_i$. Since $\gcd(N_i, n_i) = 1$, the inverse $M_i \equiv N_i^{-1} \pmod{n_i}$ exists. Then:

$$x = \sum_{i=1}^{k} a_i N_i M_i \pmod{N}$$

**Example.** Solve $x \equiv 2 \pmod{3}$, $x \equiv 3 \pmod{5}$, $x \equiv 2 \pmod{7}$.

$N = 105$, so $N_1 = 35$, $N_2 = 21$, $N_3 = 15$.

Inverses: $35^{-1} \equiv 2 \pmod 3$, $21^{-1} \equiv 1 \pmod 5$, $15^{-1} \equiv 1 \pmod 7$.

$$x = 2 \cdot 35 \cdot 2 + 3 \cdot 21 \cdot 1 + 2 \cdot 15 \cdot 1 = 140 + 63 + 30 = 233 \equiv 23 \pmod{105}$$

Check: $23 = 7\cdot3+2$, $23 = 4\cdot5+3$, $23 = 3\cdot7+2$. ✓

## Applications

CRT appears in: fast arithmetic on large numbers (split mod small primes, compute, reconstruct), secret sharing schemes, calendar calculations, and competitive programming.
