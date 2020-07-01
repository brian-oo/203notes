---
layout: page
title: "Algorithms"
permalink: /algorithm/
---

## Table of Contents
{:.no_toc}

* TOC
{:toc}

## Basics of Algorithms

In computer science, we often talk in terms of code, projects, and programs. However, behind all the code, all programs are at the heart an **algorithm**. Wikipedia defines an algorithm as 
> a finite sequence of well-defined, computer implementable instructions, typically to solve a class of problems or to perform a computation. 

### Pseudocode

These can range in complexity and topic from anywhere between a recipe for baking bread to running a reverse Image Google search. One key about algorithms in discrete math is that they should be described in pseudocode. Pseudocode should be 
* unambigious and much clearer than code
* slightly informal compared to standard code
* avoid specific language conventions (C++, Python, et cetera)
  * because of this, pseudocode is typically 1 indexed, uses `:=` to represent assignments, and is dependent on spacing


For example, look at the following pseudocode for a `linear_search`

```
procedure linear_search(x, a1, a2, ... , an: objects of some kind)
    i := 1
    while (i <= n and x != ai)
        i := i + 1
    if i <= n then location := i
    else location := 0
    return location
```
<details><summary markdown='span'>Notes from the Author
</summary>

Due to restrictions with various builds of this blog, such as Jekyll, Mathjax, and Markdown, I have taken some liberties with this pseudocode. I would call this less of true pseudocode and more of a hybrid between C and pseudocode. Overall it should not hurt with understanding and analysis as most of the notation stuff is intuitively alternative, however I do want to note that this is not a true representation of pseudocode in its purest form.
</details>


This algorithm takes in input `x` which is the element we want to search for. It then loops through every element `a` until it either reaches the last element or finds the element we are looking for. It will then set location to either the index we are looking for, or return 0 to show that the element is not in the list of objects.

### Algorithm Properties

There are some key properties that we (and all programmers) need to consider when analyzing algorithms
* Definiteness: each step must be defined precisely, with no undefined behavior at any step
* Correctness: an algorithm should produce the correct output values for each set of input; what is considered correct is based on the intention of the algorithm
* Finiteness: an algorithm should produce the desired output after a finite (perhaps large) number of steps for any input in the set.
* Effectiveness: it must be possible to perform each step of an algorithm exactly and in a finite amount of time
* Generality: the procedure should be applicable for all problems of the desired form, not just for a particular set of input values.


* * *

#### Sample Problem 1
{:.no_toc}

Each of the following algorithms breaks a fundamental property of algorithms, determine a property the algorithm breaks and why. *Note:* The definitions for each property are very loose and overlap, such that there is no one correct answer and multiple answers are valid.

1. 
```
procedure double (n: positive integer)
    while n > 0
        n := 2n
    return n
```
2. 
```
procedure divide (n: positive integer)
    while n >= 0
        m := 1 / n
        n := n - 1
    return m
```
3. 
```
procedure sum (n: positive integer)
    sum := 0
    while i < 10
        sum = sum + i
        i := i + 1
    return sum
```

<details><summary markdown='span'>Solution
</summary>

1. This algorithm breaks finiteness as `n` will never be less than 0.
2. This algorithm breaks definiteness as it is undefined behavior what `1 / n` is when `n = 0`.
3. This algorithm breaks definiteness as `i` is undefined.
</details>

* * *

Fully understanding how to prove an algorithm is correct is beyond the scope of the basics in discrete math, however it fundamentally uses proof by [induction](induction.md) and invariants. Induction can take us far, however for elements unique to algorithms like loops, with no real mathematical equivalant, invariants help fill in the logical gaps. A loop invariant is a logic statement that is always true. In our inductive step, we would utilize the loop invariant, proving it among our inductive hypothesis.


## Greedy Algorithms



{% include lib/mathjax.html %}