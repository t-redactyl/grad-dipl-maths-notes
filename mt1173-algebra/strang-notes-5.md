# Introduction to Linear Algebra

## Gilbert Strang

### Chapter 5: Determinants

#### Properties of determinants

* Only square matrices have determinants
  * The determinant is a single number that contains quite a lot of information about its matrix
  * It is written in two ways, $\det A$ and $|A|$ 
* The determinant has three core properties, and 7 other properties that flow on from this one
* When $A$ is a $2 \times 2$ matrix:

$$
A = \begin{bmatrix} a & b \\ c & d \end{bmatrix} \\
\det A = \begin{vmatrix} a & b \\ c & d \end{vmatrix} = ad - bc
$$

* **Property 1**: The determinant of the $n$ by $n$ identity matrix is $1$:

$$
\det I = \begin{vmatrix} 1 & 0 \\ 0 & 1 \end{vmatrix} = \begin{vmatrix} 1 & & \\ & \ddots & \\ & & 1 \end{vmatrix} = 1
$$

* **Property 2**: The determinant changes sign when two rows are exchanged:

  * This is equivalent to multiplying the matrix by the relevant permutation matrix
  * Even numbers of row exchanges (including 0) give a positive determinant, odd numbers give a negative determinant

* **Property 3**: The determinant is a linear function of each row separately (addition and scalar multiplication)

  * **3a**: If any row is multiplied by some number $t$, then this number can be factored out of the determinant

    * In other words, the determinant is multiplied by this number
    * Multipliers can be factored out of every row. These multiply the determinant individually:

    $$
    \begin{aligned}
    A_1 &= \begin{bmatrix} 3 & 1 \\ 4 & 5 \end{bmatrix}, \quad A_2 = \begin{bmatrix} 3(3) & 3(1) \\ 4 & 5 \end{bmatrix}, \quad A_3 = \begin{bmatrix} 3 & 1 \\ 2(4) & 2(5) \end{bmatrix}, \quad A_4 = \begin{bmatrix} 3(3) & 3(1) \\ 2(4) & 2(5) \end{bmatrix} \\ \\
    \det A_1 &= 3 \cdotp 5 - 1 \cdotp 4 \\
    &= 15 - 4 \\
    &= 11 \\ \\
    \det A_2 &= 3(3) \cdotp 5 - 3(1) \cdotp 4 \\
    &= 9 \cdotp 5 - 3 \cdotp 4 \\
    &= 45 - 12 \\
    &= 33 = 3(11) = 3|A_1| \\ \\
    \det A_3 &= 3 \cdotp 2(5) - 1 \cdotp 2(4) \\
    &= 3 \cdotp 10 - 1 \cdotp 8 \\
    &= 30 - 8 \\
    &= 22 = 2(11) = 2|A_1| \\\\
    \det A_4 &= 3(3) \cdotp 2(5) - 3(1) \cdotp 2(4) \\
    &= 9 \cdotp 10 - 3 \cdotp 8 \\
    &= 90 - 24 \\
    &= 66 = 6(11) = 3 \cdotp 2|A_1|
    \end{aligned}
    $$

    

  * **3b**: If we add values to any row of $A$, then we add the determinant of those values to the determinant of A:

  $$
  A_1 = \begin{bmatrix} 3 & 5 \\ 1 & 4 \end{bmatrix}, \quad A_2 = \begin{bmatrix} (3 + 1) & (5 + 2) \\ 1 & 4 \end{bmatrix} \\ \\
  $$

  $$
  \begin{aligned}
  \det A_1 &= \begin{vmatrix} 3 & 5 \\ 1 & 4 \end{vmatrix} \\
  &= 3 \cdotp 4 - 5 \cdotp 1 \\
  &= 7 \\ \\
  
  \det A_2 &= \begin{vmatrix} 3 & 5 \\ 1 & 4 \end{vmatrix} + \begin{vmatrix} 1 & 2 \\ 1 & 4 \end{vmatrix} \\
  &= 3 \cdotp 4 + 1 \cdotp 4 - 5 \cdotp 1 - 2 \cdotp 1 \\
  &= 12 + 4 - 5 - 2 \\
  &= 9
  \end{aligned}
  $$

  * If we combine multiplication and addition, we get any linear combination in one row
  * $\det 2I \neq 2 \det I$:
    * $2I$ indicates that all values of $I$ are multipled by $2$, but in order to that we must multiply _each_ row by $2$
    * For a $2 \times 2$ matrix, this means we get $\begin{bmatrix} 2 & 0 \\ 0 & 2 \end{bmatrix}$
    * Because we have multiplied _each_ row by $2$, it factors out of each row: $\begin{vmatrix} 2 & 0 \\ 0 & 2 \end{vmatrix} = 2 \cdotp 2\begin{vmatrix} 1 & 0 \\ 0 & 1 \end{vmatrix} = 2^2\begin{vmatrix} 1 & 0 \\ 0 & 1 \end{vmatrix}$

* **Property 4**: If two rows of $A$ are equal, then $\det A = 0$

  * Say we have a matrix like so: $\begin{bmatrix} a & b \\\ a & b \end{bmatrix}$
  * According to **property 2**, if we swap the top and bottom row of this matrix, the sign of the determinant should change. 
  * However, the exchanged matrix is identical to the original matrix, so the determinant should not change
  * The only number with $-D = D$ is $D = 0$, so $0$ must be the determinant
  * A matrix with two equal rows has no inverse

* **Property 5**: Subtracting a multiple of one row from another row leaves $\det A$ unchanged

  * If we subtract a mutliple of one row from another, we can represent the determinant like so:

  $$
  \begin{aligned}
  A &= \begin{vmatrix} a & b \\ c - \ell a & d - \ell b \end{vmatrix} \\
  &= \begin{vmatrix} a & b \\ c & d \end{vmatrix} - \begin{vmatrix} a & b \\ \ell a & \ell b \end{vmatrix} \\
  &= \begin{vmatrix} a & b \\ c & d \end{vmatrix} - \ell \begin{vmatrix} a & b \\ a & b \end{vmatrix} \\
  &= \begin{vmatrix} a & b \\ c & d \end{vmatrix} - \ell \cdotp 0 \\
  &= \begin{vmatrix} a & b \\ c & d \end{vmatrix}
  \end{aligned}
  $$

  * We can conclude that (because elimination is a series of subtraction of row multiples) that the determinant is not changed by the usual elimination steps from $A$ to $U$
    * Thus, $\det A = \pm \det U$ (taking into account that elimination may involve row exchanges)

* **Property 6**: A matrix with a row of zeros has $\det A = 0$

  * Take this matrix $A$ with a zero row:

  $$ \det A = \begin{vmatrix} a & b \\ 0 & 0 \end{vmatrix} $$

  * If we add the top row to the zero row, we get:

  $$ \det A = \begin{vmatrix} a & b \\ 0 + a & 0 + b \end{vmatrix} = \begin{vmatrix} a & b \\ a & b \end{vmatrix} $$

  * According to **property 5**, adding this row to the zero row does not change the determinant
  * However, we now have a matrix with two equal rows, so by **property 4**, the determinant of this matrix is $0$

* **Property 7**: If $A$ is triangular, then $\det A = a_{11}a_{22} \ldots a_{nn} = $ product of diagonal entries

  * Reminder: a triangular matrix is one that has all zeros in the bottom half (upper triangular) or in the top half (lower triangular) 
  * If we have a triangular matrix, we can convert this into a diagonal matrix using elimination (as per the steps from $U$ to $R$)
  * By **property 5**, the determinant of our triangular matrix is not changed
  * Diagonal matrix:

  $$\det A = \begin{vmatrix} a_{11} & & & 0 \\ & a_{22} & & \\ & & \ddots & \\ 0 & & & a_{nn}  \end{vmatrix}$$

  * By **property 3**, we can factor out first $a_{11}$ from the first row:
    * Imagine that the first row is $\begin{bmatrix} 5 & 0 & 0 & 0 \end{bmatrix}$
    * We can make the assumption that each entry is multiplied by 5, as all entries other than $a_{11}$ are $0$
  * We can then repeat this for each row, getting:

  $$\det A = a_{11}a_{22} \ldots a_{nn}\begin{vmatrix} 1 & & & 0 \\ & 1 & & \\ & & \ddots & \\ 0 & & & 1\end{vmatrix}$$

  * We now have all of the values on the diagonals as a product of the identity matrix. Applying **property 1**, we can simplify $\det I = 1$, meaning that the above simplifies to:

  $$\det A = a_{11}a_{22} \ldots a_{nn} \cdotp 1 = a_{11}a_{22} \ldots a_{nn}$$

  * Therefore we can get the determinant of a diagonal matrix as a product of all of its diagonal entries.
    * As these entries are not changed during the elimination steps, and **property 5** shows that elimination does not alter the determinant (except for its sign), the determinant of a triangular matrix can also be found as a product of its diagonal entries
      * Elimination does not affect the diagonal entries as they always contain $0$'s in the row below, meaning elimination is always subtracting some multiple of $0$ from the diagonal entry.
  * This also shows that if we have a $0$ in a diagonal entry (i.e., in a pivot position), the determinant must be $0$, as we are now multiplying all other diagonal entries by $0$

* **Property 8**: If $A$ is singular, then $\det A = 0$. If $A$ is invertible, then $\det A \neq 0$

  * By **property 7**, the upper triangular matrix $U$, obtained from elimination on $A$, has a determinant given by the product of it's diagonal entries
  * If $A$ is invertible, we will have pivots along each of the diagonal entries of $U$
  * $\det A = \pm \det U = \pm $ product of the pivots

* **Property 9**: The determinant of $AB$ is $\det A$ times $\det B$: $|AB| = |A||B|$

  * When the matrix $B$ is $A^{-1}$, this rule says that the determinant of $A^{-1}$ is $\frac{1}{\det A}$

* **Property 10**: The transpose $A^T$ has the same determinant as $A$
  $$
  \det A = \begin{vmatrix} a & b \\ c & d \end{vmatrix}, \quad \det A^T = \begin{vmatrix} a & c \\ b & d \end{vmatrix}
  $$
   

  * As can be seen in the $2 \times 2$ case, the determinant is unchanged
  * This is because in square matrices, transposing the matrix does not move the pivots
  * The implication of this is that all properties that apply to the rows of a matrix can also apply to the columns of that transposed matrix







