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

This is a neat trick we see a lot in mathematics in order to prove two things are equal. Sometimes, it is difficult to directly prove that two things are equal, however easy to prove that one thing is greater-than-or-equal-to another. If we perform this greater-than-or-equal-to proof two times, going in both directions ( $$ A \geq B $$ & $$ B \geq A $$ ), we can prove that $$ A = B $$. We will see this trick come in again later.
</details>

We can use predicate logic to explicitly described objects and relations to describe characteristics between objects.
* Objects: D = Dan, S1 = First Sister, S2 = Second Sister
* Relations: $$ T(x,y) $$ = " $$ x $$ *is taller than* $$ y $$ ".

Then we can represent the the proposition as $$ T(D,S1) \wedge T(D,S2) \wedge \neg T(S1, S2) \wedge \neg T(S2, S1) $$. When the variables in a relation are bound to objects, the relation becomes a proposition with a true/false value.

## Quantification

A relation can have just a single arguement; we can call this a property of the object. For example, let $$ P(x) $$ be "$$ x $$ *will buy an umbrella*". The statement, "*If you buy an umbrella, then I'll buy an umbrella*" can be represented as $$ P(\text{You}) \rightarrow P(\text{Me}) $$. 

How can we represent the phrase "*Everyone will buy an umbrella*". We run into the issue where there may be an infinite number of things to account for or we do not know everyone in the list. Nonetheless, we need to represent the fact that everyone will buy an umbrella. 

To do so, we can use quantifiers.

### Universal Quantifier

The universal quantifier, represented by the symbol $$ \forall $$, spoken as "*for all*" represents every element. $$ \forall x P(x) $$ represents "*Everyone will buy an umbrella*". This can be conceptualized as $$ P(x_1) \wedge P(x_2) \wedge P(x_3) \wedge ... $$ , since for every element $$ x $$, they must buy an umbrella. 

Whenever we say for all $$ x $$, we must define the **domain of discourse** (also called the universe of discourse). [Wikipedia](https://en.wikipedia.org/wiki/Domain_of_discourse) defines the domain of discourse as
> the set of entities over which certain variables of interest in some formal treatment may range. In first-order logic, the domain of discourse is the set of individuals over which the quantifiers range.

Without defining the domain of discourse, predicates are ambigious. In $$ \forall x P(x) $$, $$ x $$ itself be anything, however by specifying the domain of discourse, we can specify our domain as all people, people in this class, pets of people in this class. 

### Existential Quantifier

The existential quantifier, represented by the symbol $$ \exists $$, spoken as "*there exists*" represents some element. In other words, it means at least one element has this property. Again, we must specify to domain of discourse to know what pool of elements we are choosing from.

Under the existential quantifier, anywhere from one to every element in the domain of discourse has the property. The existential quantifier can be conceptualized as $$ P(x_1) \vee P(x_2) \vee P(x_3) \vee ... $$ .

The table below defines the conditions for when both quantifiers are true or false

 True/False | $$ \forall P(x) $$ | $$ \exists P(x) $$
 :---: | :---: | :---:
 True when... | $$ P(x) $$ true for every $$ x $$ | $$ P(x) $$ true for at least one $$ x $$
 False when... | $$ P(x) $$ false for at least one $$ x $$ | $$ P(x) $$ false for every $$ x $$

## Nested Quantiifiers

When using multiple instances of an element or multiple different quantifiers, we be careful with the scope and ordering of these elements

Let $$ B(x, y) $$ mean $$ x $$ buys $$ y $$.

"*Everyone will buy an umbrella or a raincoat*."

$$ \forall x \underline{(B(x, \text{Umbrella}) \vee B(x, \text{Raincoat} ) )} $$.

In this example there is only one quantified variable, $$ x $$, and the scope of this variable is the entire underlined statement. 



"*Everyone will buy an umbrella or everyone will buy a raincoat*."

$$ \forall x \underline{B(x, \text{Umbrella})} \vee \forall x \underline{B(x, \text{Raincoat} ) } $$.

In this example there are two quantified variable, and for each variable, there is a unique scope for the variable. This has to potential to cause confusion, so we try to avoid it by having two unique variables representing the two different quantifications. $$ \forall x \underline{B(x, \text{Umbrella})} \vee \forall y \underline{B(y, \text{Raincoat} ) } $$.


When using multiple variables and quantifiers, the understanding the order is essential to understanding the statement:

* Let the domain of $$ x $$ be people and let the domain of $$ y $$ be items in a shop 
* $$ \forall x \exists y B(x,y) $$ means for every person, they must buy some item. It does not have to be the same item for everyone, but for each person they must buy some item.
* $$ \exists y \forall x B(x,y) $$ means for some specific item, every person must buy it. This item is the same for every person. 

* * *

#### Sample Problem 1
{:.no_toc}

Using the same predicates and domains as before, translate the following statements into English.

1. $$ \forall x \forall y B(x,y) $$.
2. $$ \exists x \exists y B(x,y) $$.
3. $$ \forall y \exists x B(x,y) $$.
4. $$ \exists x \forall y B(x,y) $$.

<details><summary markdown='span'>Solution
</summary>

1. Every person bought every item in the shop.
2. There exists a person who bought some item in the shop.
3. For every item in the shop, there exists someone who bought it.
4. There exists a person who bought every item in the shop.
</details>

* * *


{% include lib/mathjax.html %}