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
  * As such, $\ell_{32} = \frac{1}{1} = 1
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

* This essential says:
  * The first and third components of $Ea_{12}$ remain the same as in A
  * The second component is made up of $-2$ components of the first component as well as the second component. These add to give a final value of 0.
* 







