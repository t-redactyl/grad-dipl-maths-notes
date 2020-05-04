# Introduction to Linear Algebra

## Gilbert Strang

### Chapter 2: Solving Linear Equations

* Solving systems of linear equations means:
  * Discovering values for the unknowns which satisfy the right hand side
  * This also implies finding the unique **point** where all values meet in $\mathbb{R}^n$ (including in spaces of greater dimension than $\mathbb{R}^2$)
  * E.g., the equations $x - 2y = 1$ and $3x + 2y = 11$, the unknowns are the point $\begin{bmatrix} x \\ y \end{bmatrix}$ in $\mathbb{R}^2$, and the solution is the point where the lines intersect $\begin{bmatrix} 3 \\ 1 \end{bmatrix}$  

* Linear equations can also be represented as in their vector form:
  * The above equation becomes  $x\begin{bmatrix} 1 \\ 3 \end{bmatrix} + y\begin{bmatrix} -2 \\ 2 \end{bmatrix} = \begin{bmatrix} 1 \\ 11 \end{bmatrix}$
  * This left-side represents a linear combination of the columns of $Ax$
  * This vector form can be generalised in the form $Ax = b$

$$ A = \begin{bmatrix} 1 & -2 \\ 3 & 2 \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} 1 \\ 11 \end{bmatrix}$$

* Matrix by vector multiplication:

  * The row form:

  $$ Ax = \begin{bmatrix} (row 1) \cdot \vec x \\  (row 2) \cdot \vec x \\ (row 3) \cdot \vec x \end{bmatrix} $$

  * The column form:

​	$$ Ax = x(column 1) + y(column 2) + z(column 3) $$

* Matrix notation:
  * Entries in matrices are denoted by their **row number**, then their **column number** as a subscript:
    * The first entry on the first row of matrix $A$ is $a_{11}$, the second entry on the first row is $a_{12}$
  * Matrix size is denoted as _m_ by _n_, where _m_ is the number of rows and _n_ is the number of columns
  * Row indices run from _i_ to _m_, and column indices run from _j_ to _n_
  * A matrix contains _mn_ entries

#### Elimination

* Elimination is a systematic way of solving linear equations
* The purpose is to eliminate each of the unknowns from the matrix to form an upper triangular matrix $U$, which can then be used to find the unknowns using back substitution
* Each of the diagonals in this matrix is known as a **pivot**
  * The pivot is the first non-zero in the row that does the elimination
  * The pivot is used to create a **multiplier** for each entry we want to eliminate
  * The multiplier $\ell = $ (entry to eliminate) divided by the pivot
* The goal of elimination is to create all zeros below the diagonal, hence the result being an upper triangular matrix
* Because we divide by the pivot, zero can never be used as one
  * We can use row substitution to change the order in which we solve the equations, and try to get non-zeros in every pivot
  * However, when we cannot get zeros in the pivot, elimination fails and the matrix is not invertible
  * E.g., $x - 2y = 1$ and $3x - 6y = 11$  are dependent (the linear equations are parallel). Elimination gives $ \begin{bmatrix} x - 2y = 1 \\ 0y = 8 \end{bmatrix} $ meaning that the system has no solution (as $0y = 8$ is false)
  * E.g., $x - 2y = 1$ and $3x - 6y = 3$ are dependent (the linear equations represent the same line). Elimination gives $ \begin{bmatrix} x - 2y = 1 \\ 0y = 0 \end{bmatrix} $. This forms $y$ into a **free variable**, meaning that ever value of $y$ will solve the equation. Hence, instead of having one unique solution, we now have infinitely many.
* Elimination in action:

$$ 2x + 4y - 2z = 2$$

$$ 4x + 9y - 3z = 8 $$

$$ -2x - 3y + 7z = 10 $$

* The first step is to make the $4x$ in the second equation into $0x$. We do this by multiplying the equation above by an amount that will mean the $2x$ above it gets rid of it when we subtract equation 1 from equation 2.
  * This is where the pivot and multiplier come in:
    * 2 is the first pivot
    * $\ell_{21} = \frac{4}{2} = 2$ 
  * We multiply equation 1 by 2 and subtract it from equation 2:

$$ 2x + 4y - 2z = 2$$

$$  y + 1z = 4  $$ 

$$ -2x - 3y + 7z = 10 $$

* Now we need to get rid of the $-2x$ in equation 3:
  * $\ell_{31} = \frac{-2}{2} = -1$
  * We multiply equation 1 by $-1$ and subtract it from equation 3

$$ 2x + 4y - 2z = 2$$

$$  y + 1z = 4  $$ 

$$ y + 5z = 12 $$

* We have one further unknown to eliminate, which is the $y$ in equation 3. Getting rid of this will allow us to have a solution for $z$, which means we can start back-substitution.
  * Our second pivot is the first non-zero element in equation 2, which is $1$
  * As such, $\ell_{32} = \frac{1}{1} = 1 $
  * As this multiplier is 1, we can simply subtract equation 2 from equation 3:

$$ 2x + 4y - 2z = 2$$

$$  y + 1z = 4  $$ 

$$ 4z = 8 $$

* We can now use back-subtitution to solve this equation:

$$z = 2$$

$$y + 2 = 4 = y = 2$$

$$2x + 4(2) - 2(2) = 2 = 2x + 4 = 2 = x = -1 $$

#### Elimination using matrices

* The above example can be represented using matrices, in the form $Ax = b$

$$\begin{bmatrix} 2 & 4 & -2 \\ 4 & 9 & -3 \\ -2 & -3 & 7 \end{bmatrix} \begin{bmatrix} x \\ y \\ z \end{bmatrix} = \begin{bmatrix} 2 \\ 8 \\ 10\end{bmatrix}  $$

* Applying the same elimination steps, we get the matrices Ux = c:

$$\begin{bmatrix} 2 & 4 & -2 \\  & 1 & -1 \\  &  & 4 \end{bmatrix} \begin{bmatrix} x \\ y \\ z \end{bmatrix} = \begin{bmatrix} 2 \\ 4 \\ 8\end{bmatrix}  $$

* We can also create matrices for each of the elimination steps, by putting the negative of each the multipliers in the position of the entry we want to eliminate. For example:

$$ E_{21} = \begin{bmatrix} 1 & 0 & 0 \\ -2 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix} $$

* The purpose of each $E_{ij}$ is to produce a zero in the position of the target entry

* This can be seen by the rule of matrix multiplication:

  * When multiplying $AB$, if $B$ has several columns $b_1, b_2, b_3$, then:

  $$AB = A\begin{bmatrix} \vec b_1 & \vec b_2 & \vec b_3 \end{bmatrix} = \begin{bmatrix} A\vec b_1 & A\vec b_2 & A\vec b_3 \end{bmatrix} $$

  * Note that this is done at the **column** level, with each column of $A$ multiplied by each element of each column of $B$
  * Multiplying $E_{21}A$ gives us the first column of $EA$:

  $$ E_{21}\vec a_{1} = 2\begin{bmatrix} 1 \\ -2 \\ 0 \end{bmatrix} + 4\begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix} - 2\begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}   $$ 

* This essentially says:
  * The first and third components of $Ea_{12}$ remain the same as in A
  * The second component is made up of $-2$ components of the first component as well as the second component. These add to give a final value of 0.
* Permutation matrix:
  * Is a "reshuffling" of the identity matrix which reorders rows when multiplied  
  * E.g., $P = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 0 & 1 \\ 0 & 1 & 1 \end{bmatrix} $ exchanges rows 2 and 3, so $P = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 0 & 1 \\ 0 & 1 & 1 \end{bmatrix}\begin{bmatrix} 2 & 4 & 1 \\ 0 & 0 & 3 \\ 0 & 6 & 5 \end{bmatrix} = \begin{bmatrix} 2 & 4 & 1 \\ 0 & 6 & 5 \\ 0 & 0 & 3 \end{bmatrix} $

* In order to incorporate the right-hand side (i.e., $b$) into the elimination matrix, we can create an **augmented matrix** $\begin{bmatrix} A & b \end{bmatrix}$, which is essentially a normal $n \times n+1$ matrix.
  * All operations we do to the rows of $A$ we now do to the rows of $b$ 

* Laws of matrix operations:
  * Commutative law is **usually broken**: $AB \neq BA$
  * Distributative law holds: 
    * $A(B + C) = AB + AC$
    * $(A + B)C = AC + BC$
  * Associative law holds: $A(BC) = (AB)C$
  * Powers of matrices: $A^p = AAA \ldots A$ ($p$ factors)
    * $(A^p)(A^q) = A^{p+q}$
    * $(A^p)^q = A^{pq}$

#### Inverse matrices

* A matrix is invertible if there exists a matrix $A^{-1}$ for which $A^{-1}A = I$ and $AA^{-1} = 1$
* A square matrix may or may not have an inverse
* A few notes about matrix inversion:
  * The inverse exists if and only if (iff) elimination procedures produce _n_ pivots
  * If a matrix is invertible, it has only one unique inverse
  * If a matrix $A$ is invertible, there is only one solution to $Ax = b$
  * If there is a non-zero vector such that $Ax = 0$, then $A$ cannot have an inverse as no matrix can bring $0$ back to $x$
  * A matrix is invertible only if its determinant is not zero
  * A diagonal matrix has an inverse only if no diagonal entries are zero, because:

$$ A = \begin{bmatrix} d_1 & 0 & 0 \\ 0 & d_2 & 0 \\ 0 & 0 & d_3 \end{bmatrix}, A^{-1} = \begin{bmatrix} \frac{1}{d_1} & 0 & 0 \\ 0 & \frac{1}{d_2} & 0 \\ 0 & 0 & \frac{1}{d_3} \end{bmatrix} $$

* The product of two invertible matrices is invertible:
  * The inversion is done in the reverse order of the product: $(AB)^{-1} = B^{-1}A^{-1}$
  * This is because:
    * $(AB)(B^{-1}A^{-1}) = A(BB^{-1})A^{-1} = AIA^{-1} = AA^{-1} = I$
* The inverse of an elimination matrix simply reverses the sign of the value being subtracted/added:

$$ E = \begin{bmatrix} 1 & 0 & 0 \\ -5 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}, E^{-1} = \begin{bmatrix} 1 & 0 & 0 \\ 5 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix} $$

* If we have two elimination matrices, then multiplying them together gives us unwanted extra products:
  * E.g., taking $E$ above, and multiplying it by $F$, a second elimination matrix (let's say that $E = E_{21}$ and $F = E_{32}$)

$$ F = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & -4 & 1 \end{bmatrix}, FE = \begin{bmatrix} 1 & 0 & 0 \\ -5 & 1 & 0 \\ 20 & -4 & 1 \end{bmatrix} $$

* However, if we take the multiplication of the _inverses_ of these elimination matrices, we end up with only the multipliers we need to do the elimination:

$$F^{-1} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 4 & 1 \end{bmatrix}$$

$$ E^{-1}F^{-1} = \begin{bmatrix} 1 & 0 & 0 \\ 5 & 1 & 0 \\ 0 & 4 & 1 \end{bmatrix} $$

#### Gauss-Jordan elimination

* Idea is to solve $AA^{-1} = I$ by finding each column of $A^{-1}$

  * We do this by multiplying $\begin{bmatrix} A & I \end{bmatrix} $ by $A^{-1}$ to get $\begin{bmatrix} I & A^{-1} \end{bmatrix} $
  * This is done in several steps, as below

* Step 1: find $U$

  * Add the identity matrix to your invertible matrix

  $$ \begin{bmatrix} K & e_1 & e_2 & e_3 \end{bmatrix} =  \begin{bmatrix} 2 & -1 & 0 & 1 & 0 & 0 \\ -1 & 2 & -1 & 0 & 1 & 0 \\ 0 & -1 & 2 & 0 & 0 & 1  \end{bmatrix} $$

  * Complete elimination row-by-row

  $$ = \begin{bmatrix} 2 & -1 & 0 & 1 & 0 & 0 \\ 0 & \frac{3}{2} & -1 & \frac{1}{2} & 1 & 0 \\ 0 & -1 & 2 & 0 & 0 & 1  \end{bmatrix} $$

  $$ = \begin{bmatrix} 2 & -1 & 0 & 1 & 0 & 0 \\ 0 & \frac{3}{2} & -1 & \frac{1}{2} & 1 & 0 \\ 0 & 0 & \frac{4}{3} & \frac{1}{3} & \frac{2}{3} & 1  \end{bmatrix} $$

  

* Step 2: continue elimination to the **reduced echelon form**

  * Eliminate value above the third pivot: $\frac{3}{4}$ row 3 + row 2

  $$ = \begin{bmatrix} 2 & -1 & 0 & 1 & 0 & 0 \\ 0 & \frac{3}{2} & 0 & \frac{3}{4} & \frac{3}{2} & \frac{3}{4} \\ 0 & 0 & \frac{4}{3} & \frac{1}{3} & \frac{2}{3} & 1  \end{bmatrix} $$

  * Eliminate value above the second pivot: $\frac{2}{3}$ row 2 + row 1

  $$ = \begin{bmatrix} 2 & 0 & 0 & \frac{3}{2} & 1 & \frac{1}{2} \\ 0 & \frac{3}{2} & 0 & \frac{3}{4} & \frac{3}{2} & \frac{3}{4} \\ 0 & 0 & \frac{4}{3} & \frac{1}{3} & \frac{2}{3} & 1  \end{bmatrix} $$

  * Finally, divide each row by its pivot to get the identity matrix on the left

  $$ = \begin{bmatrix} 2 & 0 & 0 & \frac{3}{2} & 1 & \frac{1}{2} \\ 0 & \frac{3}{2} & 0 & \frac{3}{4} & \frac{3}{2} & \frac{3}{4} \\ 0 & 0 & \frac{4}{3} & \frac{1}{3} & \frac{2}{3} & 1  \end{bmatrix} \begin{matrix} / 2 \\ /\frac{3}{2} \\ /\frac{4}{3} \end{matrix} $$

  $$ = \begin{bmatrix} 1 & 0 & 0 & \frac{3}{4} & \frac{1}{2} & \frac{1}{4} \\ 0 & 1 & 0 & \frac{1}{2} & 1 & \frac{1}{2} \\ 0 & 0 & 1 & \frac{1}{4} & \frac{1}{2} & \frac{3}{4} \end{bmatrix} = \begin{bmatrix} I & x_1 & x_2 & x_3 \end{bmatrix} = \begin{bmatrix} I & K^{-1} \end{bmatrix} $$

* The product of the pivots (in this case $2(\frac{3}{2})(\frac{4}{3}))$ is the determinant of the matrix





