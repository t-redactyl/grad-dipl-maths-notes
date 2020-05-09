# Introduction to Linear Algebra

## Gilbert Strang

### Chapter 3: Vector Spaces and Subspaces

* The space $R^{n}$ consists of all column vectors $\vec v$ with $n$ components
* If a vector is in a space, it means it can be multiplied by any scalar, or added to any other vector in that space, and the result will stay in that space
  * In other words, all linear combinations of vectors in that space must also remain in that space
* There are spaces other than $R^n$
  * One example is $Z$, the vector space that consists only of the zero vector for a particular $R^n$ (e.g., $Z$ for $R^2$ is $\begin{bmatrix} 0 \\ 0 \end{bmatrix}$)
  * This space is zero dimensional (a point), and is the smallest possible vector space
  * No space can exist without the zero vector as linear combinations of vectors always have the chance to equal zero

#### Subspaces

* Spaces exist _inside_ $R^n$, called subspaces. These contain a subset of all vectors in the full vector space.
* In order to be a subspace, this collection of vectors must: 
  * Contain the zero vector
  * Allow all linear combinations of its members to remain in the space
* Examples of all of the possible subspaces of $R^3$:
  * $L$: A line through $(0, 0, 0)$ (one column vector)
  * $P$: A plane through $(0, 0, 0)$ (two independent column vectors)
  * $R^3$: All of $R^3$ (three independent column vectors)
  * $Z$: The zero vector
* These rules scale to any $R^n$

#### The column space of A

* **If a $A$ matrix is not invertible, it means it is solveable for some $b$ and not others**

* If $Ax = b$ describes these matrices, these $b$'s form a subspace called the column space of $A$, $C(A)$

* In order to describe all of the members of $C(A)$, we multiply $A$ by every possible $x$ 

  * In other words, calculate all possible linear combinations of the column vectors of $A$

* **The system $Ax = b$ is solveable if and only if $b$ is in the column space of $A$**

* If we have an $m \times n$ matrix, our column vectors are in $R^m$ (the number of rows in the matrix), so the linear combinations of the columns in our vector will be a subspace in $R^m$

* For example:

  $Ax = \begin{bmatrix} 1 & 0 \\ 4 & 3 \\ 2 & 3 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} $  which is (as a linear combination of the vector columns of $A$)  $ x_1\begin{bmatrix} 1 \\ 4 \\ 2 \end{bmatrix} + x_2\begin{bmatrix} 0 \\ 3 \\ 3 \end{bmatrix}$

  * As this is a $3 \times 2$ matrix, we have a column space with two columns in $R^3$
  * As we do not have 3 (independent) column vectors in $C(A)$, this cannot represent all of $R^3$, therefore it is a plane which represents a subspace of $R^3$ 
  * As it has zero thickness, most $b$'s are not in this column space - for most $b$ there is no solution to our three equations in two unknowns

* Rather than starting with a matrix, we could start with some set of vectors $S$ in a vector space

  * $S$ is very likely _not_ a subspace
  * All linear combinations of the vectors in $S$ (called $SS$) are a subspace
  * The subspace $SS$ is the **span** of $S$, containing all combinations of vectors in $S$

#### Nullspaces

* The nullspace $N(A)$ consists of all solutions to $Ax = 0$

  * In the case of invertible matrices, this is only the zero vector $Z$
  * In the case of matrices which contain free variables, the nullspace will contain additional $x$ which solve $Ax = 0$

* The nullspace is a subspace of $R^n$, for any $m \times n$ matrix

* When we create the reduced row echelon form $R$ of any matrix $A$, we discover:

  * Which columns have pivots. The number of pivot columns represents the rank of the matrix $A$, and the dimension of the column space $C(A)$.
  * Which columns are "free" (it does not matter which value we chose for their unknown values). The number of free columns represents the dimension of the nullspace $N(A)$. 
  * The "special solutions", which are vectors in $R^n$ which represent the $x$'s for which $Ax = 0$. These special solutions are the basis of the nullspace, i.e., they are the vectors which, when multiplied by scalars and added, describe all vectors in the nullspace.

* If we start with the matrix $C$:

  $C = \begin{bmatrix} 1 & 2 & 2 & 4 \\ 3 & 8 & 6 & 16 \end{bmatrix}$

  * This matrix has columns 3 and 4 that are multiples of columns 1 and 2

  $U = \begin{bmatrix} 1 & 2 & 2 & 4 \\ 0 & 2 & 0 & 4 \end{bmatrix}$

  * We then reduce this down to $R$

  $R = \begin{bmatrix} 1 & 0 & 2 & 0 \\ 0 & 1 & 0 & 2 \end{bmatrix}$

  * We can now see the first two columns, which are pivot columns, are reduced down to the identity matrix, and the last two give the values needed for the special solutions ($F$).
  * The special solutions are now found by taking each non-zero row of $R$ and representing it in the form $\begin{bmatrix} -F \\ I \end{bmatrix}$
    * This is equivalent to chosing 1 and 0 as the "free" numbers for the special solutions
  * In our case, our special solutions are:

  $s_1 = \begin{bmatrix} 0 \\ -2 \\ 0 \\ 1 \end{bmatrix}, s_2 = \begin{bmatrix} -2 \\ 0 \\ 1 \\ 0 \end{bmatrix}$

* For non-square matrices, the column space and the nullspace lie in different $\mathbb{R}^n$:

  * The column space $C(A)$ lies in $\mathbb{R}^m$, for the number of rows in the matrix
  * The nullspace $N(A)$ lies in $\mathbb{R}^n$, for the number of columns in the matrix

* The rank of a matrix $r$ is the "true dimensionality" of a matrix:

  * It represents the number of pivot columns in the matrix
  * This in practice is the number of independent columns in the matrix
  * The rank gives an indication of the actual number of dimentions that the matrix represents, i.e., if a matrix is $3 \times 3$, but one of the columns is a linear combination of the other 2, then the matrix only has 2 pivot columns, 2 independent columns, and a rank of 2.
    * This means that this matrix will represent a plane subspace within $\mathbb{R}^3$

* Each free column is a combination of earlier pivot columns. The special solutions tell us what those combinations are:

  $A = \begin{bmatrix} 1 & 1 & 2 & 4 \\ 1 & 2 & 2 & 5 \\ 1 & 3 & 2 & 6 \end{bmatrix}, R = \begin{bmatrix} 1 & 0 & 2 & 3 \\ 0 & 1 & 0 & 1 \\ 0 & 0 & 0 & 0 \end{bmatrix}$

  * Column 3 = 2 (column 1) + 0 (column 2), $s_1 = (-2, 0, 1, 0)$
  * Column 4 = 3 (column 1) + 1 (column 2), $s_2 = (-3, -1, 0, 1)$

#### The complete solution to $Ax = b$

* We can go from solving $Ax = 0$ to $Ax = b$ for any matrix

* Remember: if a matrix is not invertible, then $Ax = b$ is not solveable for every $b$

  * It is only solveable for $b$'s that exist in the column space $C(A)$

* In order to check if $Ax = b$ is solveable for any particular $b$, we can create an augmented matrix $\begin{bmatrix} A & b \end{bmatrix} $ and apply elimination (through to the reduced row echelon form)

  * This allows us to see what the dependencies are between the rows of $A$, which the components of $b$ must also satisfy in order to be solveable

  $Ax = b = \begin{bmatrix} 1 & 3 & 0 & 2 \\ 0 & 0 & 1 & 4 \\ 1 & 3 & 1 & 6 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \\ x_3 \\ x_4 \end{bmatrix} = \begin{bmatrix} 1 \\ 6 \\ 7 \end{bmatrix} $ has the augmented matrix $\begin{bmatrix} 1 & 3 & 0 & 2 & 1 \\ 0 & 0 & 1 & 4 & 6 \\ 1 & 3 & 1 & 6 & 7 \end{bmatrix} = \begin{bmatrix} A & b \end{bmatrix}$

  * Applying elimination, we end up with:

  $ \begin{bmatrix} R & d \end{bmatrix} = \begin{bmatrix} 1 & 3 & 0 & 2 & 1 \\ 0 & 0 & 1 & 4 & 6 \\ 0 & 0 & 0 & 0 & 0 \end{bmatrix} $

  * The important part of this is the final row, which is equivalent (in the linear equation form) of saying $0 = 0$
    * This *must be true* in order for $Ax = b$ to be solveable for any particular $b$
  * This rule can be seen more clearly with a generalised form of $b$:

  $\begin{bmatrix} A & b \end{bmatrix} = \begin{bmatrix} 1 & 3 & 0 & 2 & b_1 \\ 0 & 0 & 1 & 4 & b_2 \\ 1 & 3 & 1 & 6 & b_3 \end{bmatrix}$ becomes $\begin{bmatrix} 1 & 3 & 0 & 2 & b_1 \\ 0 & 0 & 1 & 4 & b_2 \\ 0 & 0 & 0 & 0 & (b_3 - b_1 - b_2) \end{bmatrix}$

  * Because row 3 is equal to row 1 + row 2 in $A$ (on the "left-hand side" of the linear equations), $b$ can only be solveable if $b_3$ is similarly $b_1 + b_2$, hence $b_3 - b_1 - b_2 = 0$

* Once we know $Ax = b$ is solveable, we can start by finding **one particular solution $Ax = b$**

  * The easiest way to do this is assign the free variables to all equal 0, and then solve for the pivot variables using back-elimination
  * We then have one particular $x_{particular}$ or $x_p$

* The complete solution $x$ for $Ax = b$ is this $x_p$, as well as all of the vectors in the nullspace

  * This is because $A(x_p + x_n) = b + 0 = b$ (because anything plus 0 just equals itself)

* Whether there are multiple solutions for $Ax = b$ depends on the matrix

  * $r = m$ and $r = n$:
    * Full rank (full column rank and full row rank) 
    * Matrix is square and invertible 
    * $Ax = b$ has one unique solution (because nullspace only contains zero vector)
  * $r = m$ and $r < n$:
    * Full row rank
    * Matrix is short and wide
    * $Ax = b$ has $\infty$ solutions (there is always a solution, and nullspace contains non-zero vectors)
  * $r < m$ and $r = n$:
    * Full column rank
    * Matrix is tall and thin
    * $Ax = b$ has either 0 or 1 solutions (the additional rows add more constraints to $b$, meaning not all $b$ will satisfy the row relationships)
  * $r < m$ and $r < n$:
    * Not full rank
    * $Ax = b$ has either 0 or $\infty$ solutions

* When the nullspace contains non-zero vectors, this is what the complete solution is capturing:

  * Say we have 2 equations, $x + y + z = 3$ and $x + 2y - z$ 
    * These are two non-parallel planes in $xyz$ space
    * Because there are only two of them, they will intersect in a **line**, not a **point**
    * This line is what we're trying to find using the particular solution
  * Once we have the particular solution, we can travel along it to find all of the solutions by adding all of the values in the nullspace
    * In this case, the nullspace is also a line, because the rank of the matrix representing these two equations is 2, meaning there is only 1 free variable, meaning the dimension of the nullspace is 1

![complete-solution](image-20200509233506610.png)

