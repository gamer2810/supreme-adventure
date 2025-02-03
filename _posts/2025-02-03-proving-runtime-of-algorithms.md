---
title: Proving runtime of algorithms
date: February 2, 2025 7:40 PM
categories:
  - algorithm
tags:
  - analysis
  - runtime
  - big-o
  - proving-runtime
description: How to prove the Big-O notation, i.e. the runtime of algorithms
toc: true
math: true
comments: true
---
There are 3 major methods and 1 advanced method:

## Method 1: Subtitution

In this method, we will utilize the definition of Big-O notation and mathematical induction.

By definition, Big-O notation defines a lower bound for a function.

i.e.: 

\[ f(n) \eq O(n) \Longleftrightarrow f(n) \leq c*n, with c \gte 0 and n \gte n_{0} \]

We use mathematical induction to prove that there exists a c and $n_{0}$ that satisfies the above equation.

In another word, we will prove that the left hand side $f(n)$ is less than or equal the right hand side $c*n$.

Method 2: Iteration

Method 3: The master method (To be updated)
