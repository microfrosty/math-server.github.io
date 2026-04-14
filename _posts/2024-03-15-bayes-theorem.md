---
layout: post
title: "Bayes' Theorem and Bayesian Reasoning"
subtitle: "How to update beliefs rationally in the face of new evidence"
date: 2024-03-15
categories: [learning]
math_category: probability-statistics
tags: [probability, bayes, statistics, inference]
reading_time: 10
tldr: Bayes' theorem tells you how to update a prior probability given new evidence. It's the mathematical foundation of rational belief revision.
---

## The Theorem

$$P(A \mid B) = \frac{P(B \mid A)\,P(A)}{P(B)}$$

In words: the probability of $A$ given $B$ equals the likelihood of $B$ under $A$, times the prior probability of $A$, divided by the total probability of $B$.

The terms have names in Bayesian inference:
- $P(A)$: **prior** — belief before seeing evidence
- $P(B \mid A)$: **likelihood** — how probable is the evidence if $A$ is true?
- $P(A \mid B)$: **posterior** — updated belief after evidence
- $P(B)$: **marginal likelihood** (normalizing constant)

## The Medical Test Example

A disease affects 1% of the population. A test is 99% sensitive (true positive rate) and 99% specific (true negative rate). You test positive. What's the probability you have the disease?

Let $D$ = "has disease", $T$ = "tests positive."

$$P(D \mid T) = \frac{P(T \mid D)\,P(D)}{P(T)}$$

$$P(T) = P(T \mid D)P(D) + P(T \mid D^c)P(D^c) = 0.99 \cdot 0.01 + 0.01 \cdot 0.99 = 0.0198$$

$$P(D \mid T) = \frac{0.99 \cdot 0.01}{0.0198} = \frac{0.0099}{0.0198} = 0.5$$

Only **50%**, despite a 99% accurate test! The low prior (1%) dilutes the evidence.

## Sequential Updating

Bayes' power shows when you update repeatedly. After each new piece of evidence $e_i$, the posterior becomes the new prior:

$$P(\theta \mid e_1, \ldots, e_n) \propto P(\theta)\prod_{i=1}^{n} P(e_i \mid \theta)$$

(assuming evidence is conditionally independent given $\theta$).

## The Law of Total Probability

The denominator in Bayes' theorem uses:

$$P(B) = \sum_{i} P(B \mid A_i)\,P(A_i)$$

where $\{A_i\}$ partition the sample space. This is the **law of total probability**.

## Conjugate Priors

Some prior-likelihood pairs produce posteriors of the same family — **conjugate pairs**. The most famous:

| Prior | Likelihood | Posterior |
|---|---|---|
| Beta$(α, β)$ | Binomial | Beta$(α+k, β+n-k)$ |
| Normal$(\mu_0, \sigma_0^2)$ | Normal (known $\sigma$) | Normal |
| Gamma$(α, β)$ | Poisson | Gamma |

Conjugate priors make Bayesian updating analytically tractable — no numerical integration needed.

## Bayesian vs. Frequentist

The philosophical divide:
- **Frequentist:** Probability is the long-run frequency of events. Parameters are fixed unknowns; data is random.
- **Bayesian:** Probability quantifies degree of belief. Parameters have distributions; data updates beliefs.

Both frameworks are useful. The Bayesian approach shines when prior knowledge is meaningful and sample sizes are small.
