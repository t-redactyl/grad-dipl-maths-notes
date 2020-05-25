# Introduction to Linear Algebra

## Gilbert Strang

### Chapter 4: Orthogonality

* Two vectors are orthogonal when they are at a 90° angle to each other
* In other words, when the dot product of the two vectors is equal to 0:
  * $\vec v^T\vec w = 0$
* Think of $a^2 + b^2 = c^2$ for a right triangle with sides $\vec v$ and $\vec w$
  * $||\vec v||^2 + ||\vec w||^2 = ||\vec v + \vec w||^2 = \vec v^T\vec v + \vec w^T\vec w = (\vec v + \vec w)^T(\vec v + \vec w)$
  * $(\vec v + \vec w)^T(\vec v + \vec w)$ only equals $\vec v^T\vec v + \vec w^T\vec w$ when $\vec v^T\vec w = \vec w^T\vec v = 0 $
* Two subspaces $V$ and $W$ are orthogonal if every vector $\vec v$ in $V$ is perpendicular to every vector $\vec w$ in $W$
  * $\vec v^T\vec w = 0$ for all $\vec v$ in $V$ and all $\vec w$ in $W$
* When a vector is in two orthogonal subspaces, this vector must be zero
  * The zero vector is the only vector that is orthogonal to itself
* For two subspaces to be orthogonal, they must add up to the "right" number of dimensions for an $\mathbb{R}^n$, i.e., less than or equal to $n$
  * E.g., Two planes in $\mathbb{R}^3$ cannot be orthogonal, because their dimensions add up to $2 + 2 = 4 > 3$
  * However, a plane and a line can be orthogonal, as long as the only vector they share is the zero vector
  * Two lines can also be orthogonal

#### Orthogonality of the fundamental subspaces of $A$

* The **nullspace $N(A)$ and the row space $C(A^T)$** are orthogonal, and the zero vector of $\mathbb{R}^n$ is the only point they meet

  * Every vector $x$ in the nullspace is perpendicular to every row of $A$, because $Ax = 0$
  * Every row has a dot product with $x$, which produces 0

  $Ax = \begin{bmatrix} \textrm{row 1} \\ \vdots \\ \textrm{row m} \end{bmatrix} \begin{bmatrix} x \end{bmatrix} = \begin{bmatrix} 0 \\ \vdots \\ 0 \end{bmatrix} = \begin{matrix} \textrm{(row 1)} \cdotp x = 0 \\ \vdots \\ \textrm{(row m)} \cdotp x = 0 \end{matrix}$

  * Because $A^T$ forms the basis for $C(A^T)$, then $x$ is also perpendicular to every combination of the rows
  * The whole row space $C(A^T)$ is orthogonal to $N(A)$

* Similarly, the **left nullspace $N(A^T)$ and the column space $C(A)$** are orthogonal, and the zero vector of $\mathbb{R}^m$ is the only point they meet

  * Every vector $y$ in the nullspace of $A^T$ is perpendicular to every column of $A$
  * Every row of $A^T$ has a dot product with $y$, which produces 0

  $A^Ty = \begin{bmatrix} \textrm{(column 1)}^T \\ \vdots \\ \textrm{(column m)}^T \end{bmatrix} \begin{bmatrix} y \end{bmatrix} = \begin{bmatrix} 0 \\ \vdots \\ 0 \end{bmatrix} = \begin{matrix} \textrm{(column 1)}^T \cdotp y = 0 \\ \vdots \\ \textrm{(column m)}^T \cdotp y = 0 \end{matrix}$

  * Because $A$ forms the basis for $C(A)$, then $y$ is also perpendicular to every combination of the rows
  * The whole column space $C(A)$ is orthogonal to $N(A^T)$

#### Orthogonal complements

* $N(A)$ is the orthogonal complement of the row space $C(A^T)$ in $\mathbb{R}^n$
* $N(A^T) $ is the orthogonal complement of the column space $C(A)$ in $\mathbb{R}^m$
* This means that:
  * The orthogonal complement of a subspace $V$ contains **every** vector that is perpendicular to $V$
    * This orthogonal subspace is denoted by $V^{\perp}$ (called "$V$ perp")
  * The dimensions of the complement and the subspace add up to the total dimensions of the space they divide
* **Every** $x$ that is perpendicular to the rows of $A$ satisfies $Ax = 0$, and therefore lies in the nullspace
* **Every** $y$ that is perpendicular to the columns of $A$ satisfies $A^Ty = 0$, and therefore lies in the left nullspace
* The point of complements is that every vector $x$ can be split into:
  * A row space component $x_r$
  * A nullspace component $x_n$
* When $A$ multiplies $x$, we get $Ax = Ax_r + Ax_n$
  * The nullspace complement goes to zero: $Ax_n = 0$
  * The row space complement goes to the column space: $Ax_r = Ax$
* **REMEMBER**: $x = x_p + x_n$ 
  * When the nullspace contains non-zero vectors, there are a range of possible solutions to $Ax = b$, which are found by finding $x_{particular}$ and adding all linear combinations of the basis of the nullspace
  * When the nullspace contains only the zero vector, if a solution exists for $Ax = b$ then it is given by $x_{solution}$ plus the zero vector

#### Combining bases from subspaces

* Any $n$ independent vectors in $\mathbb{R}^n$ must span $\mathbb{R}^n$, so they are a basis
* Any $n$ vectors that span $\mathbb{R}^n$ must be independent, so they are a basis
* If the $n$ columns of $A$ are independent, they span $\mathbb{R}^n$, so $Ax = b$ must be solveable
* If the $n$ columns span $\mathbb{R}^n$, they are independent, so $Ax = b$ has only one solution
* With both of these conditions met, $A$ must be invertible:
  * If there are no free variables, the solution is unique
  * There must be $n$ pivot columns
  * The solution to $Ax = b$ must be discoverable using back elimination
* With bases for the row space and the nullspace, we have these $r + (n - r) = n$ vectors
  * These $n$ vectors are independent
  * Therefore, these $n$ vectors span $\mathbb{R}^n$
* Each $x$ is the sum of $x_r + x_n$ of a row space vector $x_r$ and a nullspace vector $x_n$
* For example:

$A = \begin{bmatrix} 1 & 2 \\ 3 & 6 \end{bmatrix}$, $x = \begin{bmatrix} 4 \\ 3 \end{bmatrix}$

* As the vectors in this matrix are not independent, we have a non-zero nullspace.

$R = \begin{bmatrix} 1 & 0 \\ 0 & 0 \end{bmatrix}$

* This tells us that we have one free variable in the nullspace, which we can find by:
  * Special solution = 2 (column 1) = $\begin{bmatrix} -2 \\ 1 \end{bmatrix}$
* We can then subtract this from $x$ to get the value of $x_r$:
  * In order to make this work, we need to take $-1\begin{bmatrix} -2 \\ 1 \end{bmatrix}= \begin{bmatrix} 2 \\ -1 \end{bmatrix}$
  * $x_r = x - x_n = \begin{bmatrix} 4 \\ 3 \end{bmatrix} - \begin{bmatrix} 2 \\ -1 \end{bmatrix} = \begin{bmatrix} 2 \\ 4 \end{bmatrix}$
* Finally, we check that these are orthogonal:
  * $x_r^Tx_n = \begin{bmatrix} 2 \\ 4 \end{bmatrix} \cdotp \begin{bmatrix} 2 & -1 \end{bmatrix} = 4 - 4 = 0$





