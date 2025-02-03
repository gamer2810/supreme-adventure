---
title: Formal Languages And Automata Wiki
date: December 7, 2024 4:49 PM
categories:
  - automata
tags:
  - wiki
  - automata
  - comsci
description: A table of content for all topics covered in the Automata course
toc: true
comments: true
---

# Set Operation

L<sub>1</sub>∪L<sub>2</sub>: union

L<sub>1</sub>L<sub>2</sub>: concatenation

L<sub>1</sub>\*: Kleene's star

# String, Alphabet and Language

An alphabet is a set of letters

Σ = {a,b}

A string is a sequence of letters

e.g.: aabbb is a string

A language is a set of strings over an alphabet

e.g.: L = {a,aa,bb} is a language over Σ

# Chomsky's Hierarchy

| Language              | Automation                       |
| --------------------- | -------------------------------- |
| Regular Language      | DFA, NFA, NFA with Λ-transitions |
| Context-free Language | Push-down Automata               |
| Recursive Enumerable  | Turing Machine                   |

# Regular Language

## Definition

Given an alphabet Σ:

∅ is a regular language

{Λ} is a regular language

{a} where a ∈ Σ is a regular language

If L<sub>1</sub>, L<sub>2</sub> are two regular languages then:

L<sub>1</sub>∪L<sub>2</sub> is regular

L<sub>1</sub>L<sub>2</sub> is regular

L<sub>1</sub>\*, L<sub>2</sub>\* are regular

## Kleene's Theorem

Given a DFA, the language it accepts must be regular.

## Transformation sequence

Regular expression -> NFA with Λ-transitions -> NFA without Λ-transitions -> DFA -> Minimal DFA

## Related Knowledge

- Subset construction (NFA without Λ-transitions -> DFA)
- Minimalization algorithm (DFA -> Minimal DFA)
- Regular expression equivalence of set operations (Regular expression -> NFA with Λ-transitions)
- Tracing strings through NFAs: Replace Λ-transition with moves (NFA with Λ-transitions -> NFA without Λ-transitions)
- Combining NFAs (union, concatenation, kleene's star)
- Combining DFAs (use permutation of states and then choose accepting states)

# Context-Free Language

## Context-Free Grammar

Production rules and how to generate a string from a grammar

## Combining CFGs

Union:
`S -> A | B`

Concatenation:
`S -> AB`

Kleene's Star:
`S -> aS | Λ`

## Useful CFG

Palindrome CFG for Σ = {a,b}:

`S -> aSa | bSb | a | b | Λ`

## Push-down Automata

# Turing Machine

## Design Turing Machine

## Universal Turing Machine

A Universal Turing Machine is a machine which can execute other turing machines on different input.

### Idea:

Encode the turing machine and its input as a string of 0s and 1s and use that string as input for the Universal Turing Machine

### Encoding:

Let e() be the encoding function.

The input to the Universal Turing Machine is a string:

e(turing machine)e(input for the turing machine)

The two part is separated by the sequence `00`.

It is the only place with the sequence `00`.

#### Turing Machine:

e(initial-state)0e(move-1)0e(move-2)....0e(move-n)0

Encoded as a sequence of moves.

For a move:

p -a/b,D-> q

That means:
At state p, if the tape head is on character a, replace it by a b then move the tape head 1 square in the D direction.

That move is encoded as:
e(p)0e(a)0e(q)0e(b)0e(D)

##### State encoding:

a sequence of 1s

1 = h<sub>a</sub>

11 = h<sub>r</sub>

##### Character encoding:

a sequence of 1s

1 = blank (Λ)

##### Direction encoding:

Right = 1

Left = 11

Stay = 111

Input tape encoding:
0e(blank)0e(t1)0e(t2)...0e(t~m~)

## The Halting Problem

Given a Turing Machine **T** and a string **w**, does **T** halt and accept or halt and reject with **w**?
=> Turing Machine can not solve this problem

## Church-Turing Thesis

If there is an algorithmic problem that human can solve, there exists a Turing Machines that can solve it.
