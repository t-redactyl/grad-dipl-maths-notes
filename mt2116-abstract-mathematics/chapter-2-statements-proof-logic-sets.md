# Chapter 2 

# Mathematical statements, proof, logic and sets

## Miscellaneous definitions in this chapter

- **Natural numbers**: positive integers

## Mathematical statements and proof

### Types of mathematical statements

- **Propositions:** statements that solve for a specific value, and are either true or false.
  - E.g., 20 is divisible by 4
- **Compound statements: ** statements that involve multiple conditions that are joined by 'and', 'or', etc. Whether the statement is true or false depends on whether each of the statements are true, and what the relationship between them is.
  - E.g., 21 is divisible by 3 or 5
- **Predicate:** a statement that does not specify the value of the number $n$, and whether the statement is true or false will depend on the so-called 'free variable' $n$.
  - E.g., $n^2$ is even
- **Universal statement:** assertions about whole groups of things, for example, all natural numbers
  - E.g., For every natural number $n$, the number $n^2 + n$ is even.
- **Existential statement:** a statement that asserts the existence of a particular number.
  - E.g., There is a natural number $n$ such that $2n = 2^n$
- **Implication:** a statement that implies that if one thing is true or false, than another is true or false
  - E.g., If $n$ is even, then $n^2$ is even
- **If and only if statement:** a statement that asserts that something can only be true or false when another thing is true or false
  - E.g., For all natural numbers $n$, $n^2$ is even if and only if $n$ is even
- **Non-existence statement:** a statement that asserts that something doesn't exists (the non-existence of that thing).
  - E.g., There are no natural numbers $m$ and $n$ such that $\sqrt 2 = m/n$

### Introduction to proving statements

- **Proposition example:** 20 is divisible by 4

  - Divisible means mathematically that when we divide 20 by 4 we get no remainder. For natural numbers $n$ and $d$, to say that $n$ is divisible by $d$ is the equivalent of saying that $n$ is a multiple of $d$, or that there is some natural number $m$ for which $n$ = $md$. Since $20 = 5 \times 4$, then the statement is true.

- **Compound statement example:** 21 is divisible by 3 or 5

  - This is a compound statement that will be true if one or both of the statements are true (because of the $or$ statement). Looking at these separately:
    - 21 is divisible by 3 is true, because $21 = 7 \times 3$
    - 21 is divisible by 5 is false, because $21 / 4 = 5.25$ 
  - As at least one of the statements is true, the compound statement is also true.

- **Predicate example:** $n^2$ is even

  - Whether this is true or false depends on the value of $n$. Unlike the other statements, this is a predicate $P(n)$. This becomes a proposition once we assign a value to $n$, at which time the truth or falsity of the statement can be established. For example, if $n = 2$, then $n^2 = 4$, which is even, and therefore the statement is true. However, if $n = 3$, then $n^2 = 9$ which is odd, and therefore the statement is false.

- **Universal statement example:** For every natural number $n$, the number $n^2 + n$ is even.

  - Suppose $n$ is even. This means that for some integer $k$, $n = 2k$ (to ensure it is even).

    - We can also transform the statement $n^2 + n$ into $n(n + 1)$.
    - In that case, $n + 1 = 2k + 1$, hence:

    $$
    n(n + 1) = 2k(2k + 1) = 2(k(2k + 1))
    $$

    - $k(2k + 1)$ is an integer and divisible by 2; that is, even.

  - However, $n$ might be odd, in which case our integer is $n = 2k + 1$. Then
    $$
    n(n + 1) = (2k + 1)(2k + 2) = 2((2k + 1)(k + 1))
    $$

    - This is again even, because $(2k + 1)(k + 1)$ is an integer.

- **Existential statement example:** There is a natural number $n$ such that $2n = 2^n$

  - If an existential statement is true, it is relatively simple to prove (we only need to find that it is true for some particular value of $n$)
  - If it is false, we need to show that for _no_ value of $n$ does it hold true
    - We would need to find a general argument as in the previous example
  - In this case of this statement, we can show that for $n = 1$ it is true, therefore it is true:

  $$
  2n = 2 = 2^1 = 2^n
  $$

- **Implication example:** If $n$ is even, then $n^2$ is even

  - Most straightforward way to prove this is to assume that $n$ is any even number and then show that $n^2$ is even.
    - If $n$ is even, then $n = 2k$ for some integer $k$
    - Hence $n^2 = (2k)^2 = 4k^2 = 2(2k^2)$ 
    - This is even because $2k^2$ is an integer and because it is multiplied by 2 it is even

- **Implication example 2:** For all odd numbers $n$, $n^2$ is odd

  - Again, we assume that $n$ is any odd number and that $n^2$ is also odd
    - If $n$ is odd, then $n = 2k + 1$
    - Hence $n^2 = (2k + 1)^2 = 4k^2 + 4k + 1$
    - This can be rewritten as $4k^2 + 4k + 1 = 2(2k^2 + 2k) + 1$
    - As $2k^2 + 2k$ is an integer, our result is in the form of $2K + 1$, which means it is odd

- **If and only if statement example:** For natural numbers, $n^2$ is even if an only if $n$ is not even

  - By proving the two implication statements above, we have proven this one
    - The first statement demonstates that _if_ $n$ is even, then $n^2$ is even
    - The second statement demonstrates that $n^2$ is even _only_ when $n$ is even (because otherwise $n^2$ produces an odd number)

- **Non-existence statement example:** There are no natural numbers $m$ and $n$ such that $\sqrt 2 = m/n$ 

  - This will be explained later

## Some basic logic

- We can explore logic using 'truth tables', with _true_ denoted using T and _false_ denoted using F

### Negation

- Most simple way to form another statement is to take a statement and negate it
- Negation of a statement $P$ is written as either $\neg P$ or 'not $P$'
- Truth table looks like below:

| $P$  | $\neg P$ |
| ---- | -------- |
| T    | F        |
| F    | T        |

- Indicates that when $P$ is true $\neg P$ is false, and if $P$ is false then $\neg P$ is true
  - E.g., If $P$ is '20 is divisible by 3' then $\neg P$ is '20 is not divisible by 3'. Here $P$ is false and $\neg P$ is true.
- The negation of a universal statement is an existential statement
  - To disprove a statement that covers a group, you only need to provide an example where it fails. This is called a **counterexample**.
  - The negation of the universal statement, 'for all $n$, property $p(n)$ holds' is the existential statement 'there is $n$ such that property that $p(n)$ does not hold'
- The negation of an existential statement is a universal statement
  - That is, if you disprove an existential statement, you prove a formal one
  - The negation of the existential statement 'there is $n$ such that property $p(n)$ holds' is the universal statement 'for all $n$, property $p(n)$ does not hold'
- The negation of the predicate $p(n)$ can also be defined as $\neg p(n)$:
  - The negation of the universal statement 'for all $n$, $p(n)$ is true' is the existential statement 'there is $n$ such that $\neg p(n)$ is true'
  - The negation of the existential statement 'there is $n$ such that $p(n)$ is true' is the universal statement 'for all $n$, $\neg p(n)$ is true'

### Conjunction and disjunction

- Two basic ways of combining propositions:
  - **and** (conjunction)
  - **or** (disjunction)
- If $P$ and $Q$ are two mathematical statements, then the conjunction of $P$ and $Q$ is '$P$ and $Q$':
  - This can be denoted as $P \wedge Q$
  - It means that this statement is true precisely when _both_ $P$ and $Q$ are true
  - For example, the statement
    - 50 is divisible by 2 and 5
  - is the conjunction of 2 statements:
    - 50 is divisible by 2
    - 50 is divisible by 5
  - The truth table is below. This indicates that $P \wedge Q$ is true only when $P$ and $Q$ are both true:

| $P$    $Q$ | $P \wedge Q$ |
| ---------- | ------------ |
| T     T    | T            |
| T     F    | F            |
| F     T    | F            |
| F     F    | F            |

- Similarly, the disjunction of $P$ and $Q$ is '$P$ or $Q$':
  - This can be denoted as $P \vee Q$
  - It is means that the statement can be true precisely when $P$, or $Q$, or both are true. This means that 'or' is always used in the 'inclusive-or' sense, where both is an option.
  - For example, the statement:
    - 21 is divisible by 3 or 5
  - is the disjunction of 2 statements:
    - 21 is divisible by 3
    - 21 is divisible by 5
  - The truth table is below. This essential says that $P \vee Q$ is true precisely when _at least one_ of $P$ and $Q$ is true.

| $P$    $Q$ | $P \vee Q$ |
| ---------- | ---------- |
| T    T     | T          |
| T    F     | T          |
| F    T     | T          |
| F    F     | F          |

### If-then statements

- If-then statements in mathematics only tell you about what follows _if_ something particular happens, but does not indicate what will happen if it doesn't
- If-then statements are also known as implications
- If-then statements are made up of 2 mathematical statements which can be true or false. Therefore, if we have 2 mathematic statements $P$ and $Q$, we can denote it as:
  - $P \Rightarrow Q$, that is, '$P$ implies $Q$', or 'if $P$, then $Q$'
- The truth table is below

| $P$    $Q$ | $P \Rightarrow Q$ |
| ---------- | ----------------- |
| T     F    | T                 |
| T     F    | F                 |
| F     T    | T                 |
| F     F    | T                 |

### Contrapositive statements

- The contrapositive of the implication $P \Rightarrow Q$ is the statement $\neg Q \Rightarrow \neg P$ 
- The contrapositive is logically equivalent to the implication:
- Truth table:

| $P$     $Q$ | $P \Rightarrow Q$ | $\neg P$      $\neg Q$ | $\neg Q \Rightarrow \neg P$ |
| ----------- | ----------------- | ---------------------- | --------------------------- |
| T      T    | T                 | F           F          | T                           |
| T      F    | F                 | F           T          | F                           |
| F      T    | T                 | T           F          | T                           |
| F      F    | T                 | T           T          | T                           |

## Working backwards to obtain a proof

-  Some statements can be proved directly: for example, for a universal finding a single value of $n$ for which $P(n)$ is false is sufficient to prove it
- However, some statements are difficult to prove correctly, and it can be easier to "work backwards" from some that is simplified, expanded or rewritten in some way
- For example: Prove the statement that 'if $a,b$ are real numbers and $a \neq b$, then $ab < (a^2 + b^2)/2$'
  - We can rewrite the equation as $a^2 + b^2 - 2ab > 0$
  - We can now simply reverse the quadratic equation and rewrite this as $(a - b)^2 > 0$
  - Because $a \neq b$, this means the number inside the parentheses cannot be zero, and because this number is squared, it must be positive.
  - We can write this proof like so:

**Proof**

Since $a \neq b$ and hence, $(a - b)^2 > 0$. But $(a - b)^2 = a^2 + b^2 - 2ab$. So we have $a^2 + b^2 > 2ab$ and, therefore, $ab < (a^2 + b^2)/2$, as required. $\square$ 

## Sets

### Basics

- A set is a collection of objects
- Usually described by describing its **members** in curly brackets
- For example, $A = \{1,2,3\}$
  - Means that the objects belonging to the set $A$ are the numbers 1,2,3
  - Equivalently, the set $A$ consists of the numbers 1,2 and 3
- We could also describe the members of the set using the notations:

$A$ = $\{n$  $|$  $n$ is a whole number and $1 \leq n \leq 3  \}$

$A$ = $\{n$ $:$ $n$ is a whole number and $1 \leq n \leq 3 \}$

- In the notation, both $|$ and $:$ stand for 'such that'

- When $x$ is an object in a set $A$, we write $x \in A$ and say '$x$ belongs to $A$' or '$x$ is a member of $A$'. If $x$ does not belong to $A$, we write $x \notin A$.
- Another example: $B = \{x \in \mathbb{N}$ $|$ $x$ is even$\}$
  - This set has as its members all positive even integers
- A constructional description of a set of natural numbers known as the 'perfect squares'
  - $C = \{n^2$ $|$ $n \in \mathbb{N} \}$
- The empty set is denoted as $\emptyset$

### Subsets

- A set is a subset of another set when every single one of it's members belongs to the other set.
  - For example: $\{1,2,5\} \subseteq \{1,2,4,5,6,40 \}$
  -  Subset can also be written as $\subset$ 
- A few statements are true from this:
  - $x \subseteq S \Rightarrow x \subseteq T$ (if $x$ is a member of set $S$, then $x$ is a member of set $T$)
  - Given two sets $A$ and $B$, $A = B$ only if $A \subseteq B$ and $B \subset A$
  - For any set $A$, $\emptyset \subseteq A$ 

### Unions and intersections

- A **union** of two sets is when its members belong to $A$, $B$, or both
  - Written as $A \cup B$ 
- To formally define a union:
  - $A \cup B = \{x$ $|$ $x \subseteq A$ or $x \subseteq B \}$
- Using the notation we've already learned, we can write:
  - $x \in A \cup B \iff (x \in A) \vee (x \in B)$ 
  - That is, $x$ is a member of the union of $A$ and $B$, which is equivalent to saying that $x$ is in $A$, $B$, or both $A$ and $B$ 
- The **intersection** of two sets is a set whose members belong to both sets:
  - Written as $A \cap B$ 
- To formally define an intersection:
  - $A \cap B = \{x$ $|$ $x \in A$ and $x \in B\}$
- So,
  - $x \in A \cap B \iff (x \in A) \wedge (x \in B)$ 
  - That is, x is a member of the intersection of $A$ and $B$, which is equivalent to saying that $x$ is in both $A$ and $B$

### Universal sets and complements

- In order to define the possible members of a set, we need the context
  - This is defined as the universal set $E$ 
  - For example, if we're thinking about sets of natural numbers, the universal set would be the set $\mathbb{N}$ of all natural numbers
    - If set $A$ in this context contains all even natural numbers, than what is _not_ in set $A$ is all natural odd numbers
    - Without this context, what does not belong to set $A$ is _everything else that exists_
- Given a universal set $E$ and a subset $A$ of $E$, the **complement** of $A$ (or the complement of A in E) is denoted by $E$ \ $A$ and is:
  - $E$ \ $A = \{x \in E$ | $x \notin A \}$
  - That is, the members of the complement of $A$ are all those members of the universal set $E$ that are not members of subset $A$ 
  - The complement can also be denoted by $\bar A$ or $A^c$ 
- This statement is also true:
  - If $A$ is any subset of $E$, and each member of $E$ is either a member of $A$ or not a member of $A$, it follows that:
    - $A \cup (E$ \ $A) = E$ 
    - That is, the union of $A$ and $E$ \ $A$ is $E$ 

### Sets and logic

- Negation, conjunction and disjunction behave the same way on statements as they do on sets
- For example, the statement $(A \cap B)^c$ = $A^c \cup B^c$ can be proven using these (Demorgan's law): see pp.25-6 in the course guide

### Cartesian products

- For sets $A$ and $B$, the **Cartesian product** $A \times B$ is the set of all ordered pairs ($a,b$), where $a \in A$ and $b \in B$.
  - If $A = B = \mathbb{R}$ 
  - Then $A \times B = \mathbb{R} \times \mathbb{R}$ is the set of all ordered pairs of real numbers
  - Usually denoted by $\mathbb{R}^2$ 
- Cartesian product represents the set of a 2-dimensional plane

### Power sets

- Set $A$ can have a range of possible subsets
- The set of all subsets is called the **power set** of $A$
  - Denoted as $\mathcal{P}(A)$
  - Is a set of sets

### Quantifiers















