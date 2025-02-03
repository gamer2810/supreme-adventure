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

### Example:

**Proving merge sort runtime is $O(n*lgn)$**

To prove that Merge Sort has a runtime of (O(n \log n)) using the substitution method, we'll follow these steps:

1. **Understand the Recurrence Relation**:\
   The time complexity of Merge Sort can be described by the recurrence relation:\

   $$T(n) = 2T\left(\frac{n}{2}\right) + O(n)$$

   This means that to sort an array of size (n), we recursively sort two subarrays each of size (\frac{n}{2}), and then merge them, which takes linear time.
2. **Assume a Form for the Solution**:\
   We aim to show that (T(n)) is bounded above by (O(n \log n)). Let's assume:\
   $$T(n) \leq k \cdot n \log n$$
   where (k) is some constant.
3. **Apply the Substitution Method**:\
   Substitute our assumed upper bound into the recurrence relation to see if it holds.
4. **Expand the Recurrence Relation**:\
   Using the assumption, substitute $(T\left(\frac{n}{2}\right))$:\

   $$T(n) = 2T\left(\frac{n}{2}\right) + O(n) \leq 2\left(k \cdot \frac{n}{2} \log \frac{n}{2}\right) + O(n)$$ 

   Simplify $(2 \cdot \frac{n}{2})$:

   $$T(n) \leq k \cdot n \log \frac{n}{2} + O(n)$$

5. **Simplify the Logarithmic Term**:\
   Use the logarithmic identity $(\log \frac{n}{2} = \log n - \log 2)$:

   $$T(n) \leq k \cdot n (\log n - \log 2) + O(n)$$ 

   Expand the terms:

   $$T(n) \leq k \cdot n \log n - k \cdot n \log 2 + O(n)$$

6. **Compare with the Assumed Bound**:\
   Our goal is to show that:

   $$k \cdot n \log n \geq k \cdot n \log n - k \cdot n \log 2 + O(n)$$ 

   Subtract (k \cdot n \log n) from both sides:

   $$0 \geq -k \cdot n \log 2 + O(n)$$ 

   Rearranging terms:

   $$k \cdot n \log 2 \geq O(n)$$

7. **Determine the Constant (k)**:\
   To satisfy the inequality, choose (k) such that:

   $$k \geq \frac{c}{\log 2}$$

   where (c) is the constant from the linear term (O(n)).
8. **Conclusion**:\
   By choosing an appropriate constant (k), the substitution method confirms that Merge Sort's runtime satisfies:

   $$T(n) = O(n \log n)$$

## Method 2: Iteration (To be updated)

## Method 3: The master method (To be updated)
