---
media_subpath: assets/img/uploads/
title: Prefix Sum
date: November 11, 2024 10:04 AM
categories:
  - CP Snippet
tags:
  - algorithm
  - snippet
  - leetcode
  - java
description: Pre-calculate and store the sum of elements from the start of the
  array to the current element.
toc: false
comments: true
---
## Goal
Pre-calculate and store the sum of elements from the start of the array to the current element.
## Plan
Create an integer array with the same size `n`, storing the sum at each element.
## Idea
1. Initialize an array `prefix` with size `n`
2. Initialize `sum = 0`
4. For each element of index `i` in the range [0, n-1]:
    * Add the element to `sum`.
    * Store `sum` into the `prefix` array at index `i`

## Java Code
```java
        int sum = 0;
        int[] prefix = new integer[n];
        for (int i = 0; i < n; i++) {
            sum += nums[i];
            prefix[i] = sum;
        }
```

## Recommended reads
https://usaco.guide/silver/prefix-sums?lang=cpp

## Interesting properties
1. If two prefix sum have the same remainder when divided by `k`, then the subarray between them is divisible by `k`.

## Problems
https://www.hackerrank.com/challenges/k-subarrays/problem
