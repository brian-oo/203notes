---
layout: page
title: "Propositional Logic"
permalink: /proplogic/
---

## Table of Contents
{:.no_toc}

* TOC
{:toc}

## Propositions

In order to begin our journey in any proof-based math class, we must start with the building block: propositions. If logic and proofs were a house, propositions are the bricks. A **proposition** is a declarative statement that is either *true* or *false*. Propositions must be true or false, and can not be neither true nor false, nor be both true and false. Propositions are strictly binary and must maintain only one truth value at a time.

<details><summary markdown='span'>EECS Extension
</summary>

Requiring propositions be either true or false, not neither or both, is more than a math principle. Propositions in the coding world can be considered as `boolean` where at any given point your `boolean` is true/false, but never nothing nor both. This extends even further, down to the hardware. On a circuitry level, wires and transistors can either be on or off. This is determined through voltage levels. Most transistors have a threshold voltage, such that once a particular wire reaches a threshold voltage, the transistor turns on. Gather thousands of silicon transistors together, and you just made a microprocessor.
</details>

The other major component of a proposition is that it be a declarative statement. Exclamatory statements, such as "Wow!" have no truth value, nor do questions, such as "Is it raining?" It may seem natural to think the answer to the question represents the truth value, however the question itself does not have a truth value. The statement "It is raining right now" does maintain an active truth value, and is therefore a proposition.  

Note that we do not have to know the truth value of a proposition to consider it a proposition. "Aliens exist" is a proposition, however we do not know its truth value. Nonetheless we can still use propositional logic on this proposition, despite not knowing its exact truth value. **Axioms** are propositions, that we assume to be true and are assumed to be true at all times, such as $$ 1 + 1 = 2 $$.

#### Sample Problem 1
{:.no_toc}

Which of the following are propositions:
1. A square has 4 sides.
2. All rectangles are squares.
3. Is a rectangle a square?
4. This statement is false.
5.  $$ 8 \cdot 2 = 16 $$.
6.  $$ 8 \cdot x = 16 $$.

<details><summary markdown='span'>Solution
</summary>

1. Proposition, its truth value is true.  
2. Proposition, its truth value is false.
3. Not a Proposition, questions do not have a truth value.
4. Not a Proposition, paradoxes do not have a definite truth value.
5. Proposition, its truth value is true.
6. Not a Proposition.
</details>

Number 6 from the [Sample Problem](#sample-problem-1) is tricky. $$ 8 \cdot x = 16 $$ is a proposition only if we have a value for $$ x $$. At the moment, it is a predicate because we are unsure of what $$ x $$ is. If $$ x $$ was a sandwich, then the proposition $$ 8 \cdot x = 16 $$ is not a proposition because it makes no sense: what is the truth value of eight times sandwich? Once we define possible values (domain) for $$ x $$, then we make the claim there is a truth value. "Given that $$ x $$ is a real number, $$ 8 \cdot x = 16 $$", this is a proposition, since although we do not know if the value of $$ x $$ and thus the truth value of the proposition, we know that the statement is either true or false, thus making it a proposition.

## Compound Propositions

In order to simplify logical expressions, we can use letters: such as $$ p, q, r $$ to represent propositions. Let's say we have propositions: $$ p = $$ *It rained today* and $$ q = $$ *I brought my umbrella today*. How could we express the logical statement: "*It rained today and I brought my umbrella.*" We could define a new proposition, $$ r $$ to represent this statement, however this will get tedious the more and more expressions we have. The way to combine propositions is with logical operators.

### Logical Operators

If we want to express both the logical expression of both $$ p $$ and $$ q $$, we use the *and* operator: $$ \wedge $$. Therefore, to represent the statement "*It rained today and I brought my umbrella*": $$ p \wedge q $$. A full table of logical operators is below: 

Compound Proposition | Expression in English
:---: | :---:
$$ \neg p $$ | "Not $$ p $$"
$$ p \wedge q $$ | "$$ p $$ and $$ q $$"
$$ p \vee q $$ | "$$ p $$ or $$ q $$ (or both)"
$$ p \oplus q $$ | "$$ p $$ or $$ q $$ (not both)"
$$ p \rightarrow q $$ | "If $$ p $$ then $$ q $$"
$$ p \leftrightarrow q $$ | "$$ p $$ if and only if $$ q $$"

Note that these are not the only translations between logic and English. Translating between logic and English at times can be unclear and ambigious and so we can use **truth tables** to clearly define the meaning of a compound proposition. Below is a truth table for all of the logical operators defined above:

$$ p $$ | $$ q $$ | $$ \neg p $$ | $$ p \wedge q $$ | $$ p \vee q $$ | $$ p \oplus q $$ | $$ p \rightarrow q $$ | $$ p \leftrightarrow q $$ |
:---: | :---: | :---: | :---: | :---: | :---: | :---: | :---:
T | T | F | T | T | F | T | T


#### Or vs. Xor

In logic we have two ways to express the English word "*or*". This is because there are some instances where we need an inclusive-or or an exclusive-or (xor). For example, the or in "*Today or tomorrow is her birthday*" is an exclusive-or since both situations can not both be true. Meanwhile the or in "*Would you like cream or sugar*" is inclusive because wanting cream, sugar, or both would all be valid responses.




{% include lib/mathjax.html %}