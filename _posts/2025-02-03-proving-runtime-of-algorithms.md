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
comments: true
math: true
---
There are 3 major methods and 1 advanced method:

## Method 1: Substitution

In this method, we will utilize the **definition of Big-O notation** and **mathematical induction**.

By definition, Big-O notation defines a lower bound for a function:



$$f(n) = O(n) \Longleftrightarrow f(n) \le c*n, with \ c \ge 0\ and\ n \ge n_{0}$$

i.e. $f(n) = O(n)$ if there exist $c$ and $n_{0}$ such that $c*n$ is always larger than $f(n)$.



Notice that i am using $O(n)$ as an example, you can use the above equation to prove $O(n^{2}), O(n*lgn)...$ as well.



We will use mathematical induction to prove that there exists a c and $n_{0}$ that satisfies the above equation.



In another word, we want to show that the left hand side $f(n)$ is less than or equal the right hand side $c*n$.



Method 2: Iteration

Method 3: The master method (To be updated)
