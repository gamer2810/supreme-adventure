---
title: Sieve of Eratosthenes
date: November 11, 2024 10:04 AM
categories:
  - CP Snippet
tags:
  - algorithm
  - snippet
  - leetcode
  - java
description: Find all prime number in the range [1, max]
toc: false
comments: true
---

## Goal

Find all prime number in the range [1, max]

## Plan

Create a boolean array from [1,max], marking every prime number `true` and non-prime `false`.

## Idea

1. Initialize an array with size `max`
2. Fill each element of the array with `true`
3. Mark the element at [1] as `true`
4. For each element in the range [2, sqrt(max)]:
   - If the element `j` is `true` (i.e. not touched by the algorithm yet):
     - Start from `i*i`:
       - Mark all multiplier of `j` (`2j`,`3j`,...) that is smaller than `max` as `false`

> Why starts from `i*i`?  
> Because every number less than i2 is either a prime or has a divisor less than i.  
> Reason: if it has two divisors at least i, then its value is at least i2.
> {: .prompt-info }

## Java Code

```java
        boolean[] sieve = new boolean[1001];
        Arrays.fill(sieve, true);
        sieve[1] = false;
        for (int i = 2; i <= Math.sqrt(1001); i++) {
            if (sieve[i]) {
                for (int j = i * i; j <= 1000; j += i) {
                    sieve[j] = false;
                }
            }
        }
```

## Example LeetCode problem

[Prime Subtraction Operation](https://leetcode.com/problems/prime-subtraction-operation/)
