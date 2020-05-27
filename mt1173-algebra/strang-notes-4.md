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

#### Projection onto a line

* Imagine we have a line through the origin in the direction of $a$, and we have another vector $b$ which we want to **project** onto $a$

  * This means we need to find the point on $a$, called $p$, which is closest to $p$
  * The key to this is to find the line between $b$ and $a$ which is orthogonal
  * This line from $b$ to $p$ is perpendicular to the vector $a$

* This projection of $p$ is some multiple of $a$:

  * $p = \hat xa$ 

* In order to find the projection of $b$ onto $a$, we:

  * Find $\hat x$
  * Find the vector $p$ 
  * Find the projection matrix $P$

* Finding $\hat x$:

  * We start with the fact that we know this point $p$ that we want to discover is $\hat xa$ 
  * We also have our line between $b$ and $p$, which represents the amount of "error" between our vector $b$ and our line $a$
  * This line $e = b - p$, and with substitution, $e = b - \hat xa$
  * Because $e$ is perpendicular to $a$, their dot product is 0: $a \cdotp e = 0$
  * With substitution, we get $a \cdot (b - \hat x a) = 0$
  * We can now rework this formula:

  $a \cdot (b - \hat x a) = 0$ (expand the brackets)

  $a \cdot b - a \cdotp \hat x a = 0$ (subtract by $a \cdotp b$ and multiply by $-1$)

  $a \cdotp \hat x a = a \cdot b$ (divide by $a \cdot a$ to solve for $\hat x$)

  $\hat x = \frac{a \cdot b}{a \cdot a} = \frac{a^Tb}{a^Ta}$

*  Finding $p$:

  * We start again with the fact that $p = \hat x a$, but this time, we have $\hat x$
  * We can then simply substitute in $\hat x$:

  $p = \hat xa$

  $p = \frac{a^Tb}{a^Ta}a$

* Once we have $p$, we can calculate $e$, which is simply the difference between $b$ and $p$:
  * $e = b - p$
  * This value will be perpendicular to $a$, so that $a \cdotp e = 0$
* We now have the value of $p$ for any specific $b$. However, we can generalise this by finding the projection matrix $P$
  * $Pb = p$ for any specific $p$
  * We can get this by rearranging $p$ so we can isolate $b$
  * $p = \frac{a^Tb}{a^Ta}a = \frac{a}{1} \cdotp \frac{a^Tb}{a^Ta} = \frac{aa^T}{a^Ta} \cdotp \frac{b}{1} = \frac{aa^T}{a^Ta}b = Pb$
  * The projection matrix projects any vector $b$ onto line $a$
  * $P^2 = P$, because the projection is still going from a vector to the same line $a$

* We can also create a projection matrix to capture $e$:
  * This matrix is $(I - P)$
  * $(I - P)b = b - p$ for any specific $b$
  * While $P$ projects onto one subspace, $(I - P)$ projects onto its perpendicular subspace
  * In the case that $a$ is the column space of any $A$, $P$ projects a vector $b$ onto $C(A) = a$, and $(I - P)$ projects $b$ onto the left nullspace $N(A^T)$ 
    * In other words, it breaks any vector $b$ that is not in the column space into two vectors which form its "column space part" (its best approximation in the column space) and its "nullspace part" (the difference between the vector and its column space part, or the error in its column space approximation).

#### Projection onto a subspace

* For any column space $C(A)$ in $\mathbb{R}^m$, its component vectors are of the form $Ax$
* If we have a vector $b$ in $\mathbb{R}^m$ that is not in the column space, we can project it onto the column space by finding the closest $A\hat x$ in $C(A)$, which is of the form $p = \hat x_1a_1 + \ldots +  \hat x_na_n$, which gives us a vector 
* The use of $\hat x$ instead of $x$ indicates that this is the _best choice_ of $x$ to give us the closest $b = A\hat x$ in $C(A)$
* We still have the error vector $e$ in this calculation as well, which now has the form $b - A^T$, where $A^T(b - A\hat x) = 0$:

$A^T(b - A\hat x) = \begin{bmatrix} a^T_1 \\ \vdots \\ a^T_n \end{bmatrix} \begin{bmatrix} b - A\hat x \end{bmatrix} = \begin{bmatrix} 0 \end{bmatrix}$

* We can rewrite $A^T(b - A\hat x) = 0$ as $A^Tb - A^TA\hat x = 0$ and then rearrange this to $A^TA\hat x = A^Tb$ 
* Finding $\hat x$:
  * When finding $\hat x$ for a line, we used $\frac{1}{a^Ta}$ (or in other words, divided by $a^Ta$)
  * We cannot divide by matrices, but we _can_ multiply by an inverse, which is equivalent
  * Generalising from $a^Ta$, we will multiply by the inverse of $A^TA$ (or $(A^TA)^{-1}$), which is invertible because it is the product of a matrix with independent columns and its transpose
  * Therefore, $\hat x = \frac{a^Tb}{a^Ta}$ for a line becomes $\hat x = (A^TA)^{-1}A^Tb$ for a subspace
* Finding $p$:
  * Once we have $\hat x$, we can again substitute it in to get $p$
  * $p = A\hat x$
  * Therefore, $p = A(A^TA)^{-1}A^Tb$

* Finding $P$:
  * In the above format, finding $P$ is trivial
  * As $p = Pb$, then $P = A(A^TA)^{-1}A^T$
* Some notes on projections:
  * Our subspace is the column space of $A$
  * The error vector $b - A\hat x$ is perpendicular to that column space
  * Therefore $b - A\hat x$ is in the nullspace of $A^T$, meaning that $A^T(b - A\hat x) = 0$
* Some notes on $(A^TA)^{-1}$:
  * Unless $A$ is invertible, we cannot separate out $(A^TA)^{-1}$ into $A{-1}$ times $(A^T)^{-1}$ 
  * _If_ $A$ is invertible, it means that the column space is the whole of $\mathbb{R}^m$, and therefore any vector $b$ in $\mathbb{R}^m$ is also in the column space. In that case, we can rewrite $P$ as $(AA^{-1})((A^T)^{-1}A^T) = (I)(I) = I$
    * This makes total sense, as the best approximation for any $b$ in $\mathbb{R}^m$ within $\mathbb{R}^m$ is, of course, itself!
    * The projection matrix is then the identity matrix
  * If $A$ is not invertible, but all of its columns are, then $A^TA$ is invertible and symmetric
    * $A$ will always have independent columns if it is the basis for $C(A)$

