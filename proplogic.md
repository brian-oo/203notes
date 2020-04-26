---
layout: page
title: "Propositional Logic"
permalink: /proplogic/
---

# Table of Contents
{:.no_toc}

* TOC
{:toc}

# Propositions
In order to begin our journey in any proof-based math class, we must start with the building block: propositions. If logic and proofs were a house, propositions are the bricks. A **proposition** is a declarative statement that is either *true* or *false*. Propositions must be true or false, and can not be neither true nor false, nor be both true and false. Propositions are strictly binary and must maintain only one truth value at a time.

<details>
    <summary>EECS Extension</summary>

Requiring propositions be either true or false, not neither or both, is more than a math principle. Propositions in the coding world can be considered as `boolean` where at any given point your `boolean` is true/false, but never nothing nor both. This extends even further, down to the hardware. On a circuitry level, wires and transistors can either be on or off. This is determined through voltage levels. Most transistors have a threshold voltage, such that once a particular wire reaches a threshold voltage, the transistor turns on. Gather thousands of silicon transistors together, and you just made a microprocessor.
</details>

The other major component of a proposition is that it be a declarative statement. Exclamatory statements, such as "Wow!" have no truth value, nor do questions, such as "Is it raining?" It may seem natural to think the answer to the question represents the truth value, however the question itself does not have a truth value. The statement "It is raining right now" does maintain an active truth value, and is therefore a proposition. Note that we do not have to know the truth value of a proposition to consider it a proposition. "Aliens exist" is a proposition, however we do not know its truth value. Nonetheless we can still use propositional logic on this proposition, despite not knowing its exact truth value. **Axioms** are propositions, that we assume to be true and are assumed to be true at all times, such as $$ 1 + 1 = 2 $$.

### Sample Problem 1
{:.no_toc}

Which of the following are propositions:
1. A square has 4 sides.
2. All rectangles are squares.
3. Is a rectangle a square?
4. This statement is false.
5.  $$ 8 \cdot 2 = 16 $$
6.  $$ 8 \cdot x = 16 $$

<details>
    <summary>Solution</summary>

1. Proposition, its truth value is true.
2. Proposition, its truth value is false.
3. Not a Proposition, questions do not have a truth value.
4. Not a Proposition, paradoxes do not have a definite truth value.
5. Proposition, its truth value is true.
6. Not a Proposition.
</details>
<p>&nbsp;</p>

Number 6 from the [Sample Problem](#sample-problem-1) is tricky. $$ 8 \cdot x = 16 $$ is a proposition only if we have a value for $$ x $$. At the moment, it is a predicate because we are unsure of what $$ x $$ is. If $$ x $$ was a sandwich, then the proposition $$ 8 \cdot x = 16 $$ is not a proposition because it makes no sense: what is the truth value of eight times sandwich? Once we define possible values (domain) for $$ x $$, then we make the claim there is a truth value. "Given that $$ x $$ is a real number, $$ 8 \cdot x = 16 $$", this is a proposition, since although we do not know if the value of $$ x $$ and thus the truth value of the proposition, we know that the statement is either true or false, thus making it a proposition.

{% include lib/mathjax.html %}