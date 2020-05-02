---
layout: page
title: "Predicate Logic"
permalink: /predlogic/
---

## Table of Contents
{:.no_toc}

* TOC
{:toc}


## Predicates

So far we have discussed propositions and connectives, making [compound propositions](proplogic.md). Now, to further abstract this, we will introduce first-order logic, which utilizes objects, properties, and relations. A **predicate** is a declarative statement with *some terms unspecified*. It *becomes* a proposition when terms are specified. We refer to these terms as *objects*.

Take the proposition "*Dan is taller than both of his sisters, but they're the same height*." If we were to only use propositional logic, we would need 4 propositions:
* $$ p = $$ Dan is taller than his first sister
* $$ q = $$ Dan is taller than his second sister
* $$ r = $$ Dan's first sister is taller than his second sister
* $$ s = $$ Dan's second sister is taller than his first sister

We would then translate the original statement as $$ p \wedge q \wedge \neg r \wedge \neg s $$, however this isn't very clear and applicable in other situations.

<details><summary markdown='span'>Math Extension
</summary>

Why does $$ \neg r \wedge \neg s $$ mean that both sisters are the same height?

What does $$ \neg r $$ mean? Well if the original proposition means "*Dan's first sister is taller than his second sister*", then the negation of it is "*Dan's first sister is shorter than or the same height as his second sister*." We have to remember that the opposite of taller than isn't shorter than, but shorter than or equal to. Applying this negation to both propositions, we get $$ \neg r \wedge \neg s $$ meaning "*Dan's first sister's height is less than or the same as his second sister and Dan's second sister's height is less than or the same as his first sister*". The only possible option is that their heights are the same since both propositions must be true.

This is a neat trick we see a lot in mathematics in order to prove two things are equal. Sometimes, it is difficult to directly prove that two things are equal, however easy to prove that one thing is greater than or equal to another. If we perform this greater than or equal to proof two times, going in both directions ( $$ A \geq B $$ & $$ B \geq A $$ ), we can prove that $$ A = B $$. We will see this trick come in again later.
</details>

We can use predicate logic to explicitly described objects and relations to describe characteristics between objects.

{% include lib/mathjax.html %}