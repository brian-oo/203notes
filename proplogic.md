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

* * *

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

* * *

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
T | F | F | F | T | T | F | F
F | T | T | F | T | T | T | F
F | F | T | F | F | F | T | T


#### Or vs. Xor

In logic we have two ways to express the English word "*or*". This is because there are some instances where we need an inclusive-or or an exclusive-or (xor). For example, the or in "*Today or tomorrow is her birthday*" is an exclusive-or since both situations can not both be true. Meanwhile the or in "*Would you like cream or sugar*" is inclusive because wanting cream, sugar, or both would all be valid responses.

#### Implication

Implication is naturally unintuitive. Saying that if $$ p $$ then $$ q $$ suggests that there is a causal relationship between $$ p $$ and $$ q $$, however we must obey the truth table. The proposition "$$ (0 = 1) \rightarrow $$ *pigs can fly*" is true. This is because the $$ (0 = 1) $$ is false and "*pigs can fly*" is false, however according to the truth table $$ F \rightarrow F = T $$. It takes practice to intuitively understand how implications work. 

* If $$ p $$ is true, then the truth value of $$ p \rightarrow q $$ depends on $$ q $$.
* If $$ p $$ is false, then the truth value of $$ p \rightarrow q $$ is true, no matter what $$ q $$ is.
* It may help to look from the false perspective: $$ p \rightarrow q $$ is false **only** if $$ p $$ is true and $$ q $$ is false.

* * *

#### Sample Problem 2
{:.no_toc}

Let $$p, q, $$ and $$ r $$ be the propositions
* $$p$$: You get an A on the final exam.
* $$q$$: You do every problem in the book.
* $$r$$: You get an A in the class.

Represent each of the following statements into compound propositions:
1. You did not do every problem in the book.
2. You get an A in the class, but you do not do every problem in the book.
3. Getting an A on the final exam and doing every exercise in the book is sufficient for getting an A in the class.

<details><summary markdown='span'>Solution
</summary>

1. $$ \neg q $$.
2. $$ r \wedge \neg q $$.
3. $$ (p \wedge q) \rightarrow r $$.
</details>

* * *

## Logical Equivalences
Two propositions are considered the same if they are **logically equivalent**, meaning that they mean the exact same thing in terms of logic. This means that given an input of propositions with truth values, the two propositions will always result in the same truth value. **Tautologies** are propositions that are always true, while **contradictions** are tautologies that are always false. Take the proposition $$ \neg p \vee p $$. Either $$ p $$ is true or false, meaning that one side of this or statement is true at any given time, meaning the entire compound proposition will equate to true. This means that this proposition is a tautology and is logically equivalent to true. The proposition $$ \neg p \wedge p $$ is a contradiction, since there is no scenario with $$ p $$ is true *and* false.

Some propositions are very complex, yet we still need to see if they are logical equivalences. To do so, we can either use truth tables or logical identities to prove logical equivalance.

### Truth Tables
Two compound propositions are logically equivalent if and only if they have the same truth table. Let's try to see if these two statements are logically equivalent: 
* $$ p $$ = "*If my nose is cold, then I am unhappy*"
* $$ q $$ = "*My nose is not cold or I'm unhappy*"
* Let $$ c $$ = "*My nose is cold*"
* Let $$ u $$ = "*I am unhappy*"

We can translate these statements into compound propositions:
* $$ p = c \rightarrow u $$.
* $$ q = \neg c \vee u $$.

Now we can use a truth table to see if these result in the same output for every input:

$$ c $$ | $$ u $$ | $$ p = c \rightarrow u $$ | $$ q = \neg c \vee u $$ |
:---: | :---: | :---: | :---:
T | T | T | T
T | F | F | F
F | T | T | T
F | F | F | F

Since the $$ p $$ and $$ q $$ columns are identical, the propositions are logically equivalent.

### Logical Identities
A truth table works great for small compound propositions without many different elementary propositions; however, as these propositions get larger, it will require larger and more complex truth tables to fully prove logical equivalance. The other method we use to prove logical equivalances is with **logical identities** (equivalance laws). Just as in algebra, you can use distributive, communiative, associative, and many other laws to simplify equations, we can use equivalance laws to simplify propositions. A list of equvalance laws are below:

Name | Equivalence |
:---: | :---
Identity Laws | $$ p \wedge \bold{T} = p$$<br>$$ p \vee \bold{F} = p$$
Domination Laws | $$ p \vee \bold{T} =  \bold{T}$$<br>$$ p \wedge \bold{F} = \bold{F}$$


{% include lib/mathjax.html %}