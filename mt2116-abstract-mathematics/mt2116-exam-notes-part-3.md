# MT2116: Exam notes

## Part 3: Chapter 12-14 (groups)

## Chapter 12: groups

**Binary operations: **A binary operation $\star$ on a set $G$ is a function defined on the set of ordered pairs $G \times G$. This is just a generalisation of any operation that takes two elements of $G$ and returns a single object, which may or may not belong to $G$. $\star$ can be a bunch of different types of operators, e.g., multiplication, addition, function composition, etc. For example:

Multiplication is a binary operation on the set $\R$ of real numbers, where the binary operation is denoted $x \times y$, or more commonly, $xy$.

**Closure property:** Closure is a property that a binary operation can have. It means that all outputs of the binary operation on $G$ also belong to $G$. In other words, $G$ is **closed under $\star$** if for all $x,y \in G$, $x \star y$ is an element of $G$, or $\forall x,y \in G, x \star y \in G$. In order for closure to not to hold, it only requires a single case to fall outside of $G$, that is, $\exists  x,y \in G, x \star y \notin G$.  

**Associativity property:** The operation is said to be associative if for all $x,y,z \in G$, $(x \star y) \star z = x \star (y \star z)$. 

**Identity property:** Groups can also have the existence of an **identity**. We say that there is an identity element $e \in G$ (for the operation $\star$) if $e \star x = x \star e = x$, $\forall x \in G$. 

**Inverse property:**  We say that $G$ possesses **inverses** for $\star$ if for all $x \in G$ there is some element $b$ of $G$ such that $x \star b = b \star x = e$. This is denoted by $x^{-1}$. 

**Commutative property:** Operation $\star$ is commutative on $G$ if $x \star y = y \star x$ for all $x, y \in G$.

**Definition of a group:** We say that $G$ is a group under the binary operation $\star$ (or ($G, \star$) is a group) if it has the closure, associativity, identity and inverse properties on $G$. It does not have to have the communtative property, but when it does it is a special type of group called a **commutative group** or **Abelian group**.

Explicitly, let $G$ be a set and $\star$ be a binary operation on $G$. Then ($G, \star$) is a group if:

* $\forall x,y \in G, x \star y \in G$
* $\forall x,y,z \in G, (x \star y) \star z = x \star (y \star z)$
* $\exists e \in G \textrm{ such that } \forall x \in G, e \star x = x \star e = x$
* $\forall x \in G, \exists x^{-1} \in G \textrm{ such that } x \star x^{-1} = x^{-1} \star x = e$

$(G, \star)$ is an Abelian group if, additionally, $x \star y = y \star x$ for all $x,y \in G$.

If the group $G$ is finite (a finite set), we call the cardinality (length) $|G|$ of $G$ the order of $G$.

**Group tables:** A group $(G, \star)$ can be completely described by its group table. This indicates, for all $x,y \in G$, the elements $x \star y$, where $x$ corresponds to the row and $y$ to the column. This is familar from the multiplication and addition tables in modular arithmetic. For example, this is the multiplication table for ($\mathbb{Z}^*_5, \otimes$).

| \otimes | 1    | 2    | 3    | 4    |
| ------- | ---- | ---- | ---- | ---- |
| 1       | 1    | 2    | 3    | 4    |
| 2       | 2    | 4    | 1    | 3    |
| 3       | 3    | 1    | 4    | 2    |
| 4       | 4    | 3    | 2    | 1    |

This table is symmetric because the group is Abelian.

**Algebraic manipulations using properties of a group:** One shorthand we can use is to represent operations on groups is writing $xy$ instead of $x \star y$. Note that the order must be respected, as not all groups are Abelian. 

Suppose that $G$ is a group (written multiplicatively). Then denoting the identity element by $e$:

* If $xy = xz$ then $y = z$ (i.e., we can cancel)
* If $xy = e$, then $y = x^{-1}$ (i.e., inverses are unique)
* If $xy = x$, then $y = e$ (i.e., identity is unique)
* The equation $ax = b$ has a unique solution for all $a,b \in G$ (as does the equation $xa = b$)

## Chapter 13: subgroups

**Subgroups of groups:**

**Determining whether a subset is a subgroup:**

**Order of a group element:**

**Subgroup generated by a group element:**

**Cyclic groups:**

## Chapter 14: homomorphisms and Lagrange's theorem

**Homomorphisms:**

**Standard properties of homomorphisms:**

**Isomorphisms:**

**Cosets:**

**Lagrange's theorem:**




