# Introduction to Linear Algebra

## Gilbert Strang

### Chapter 6: Eigenvalues and Eigenvectors

* Almost all vectors change direction when they are multiplied by $A$
* However, all  _square_ matrices have special vectors that return a scalar multiple of themselves when multiplied by $A$
  * $Ax$ is on the same line as $x$
  * $Ax$ is a stretched, shrunk, flipped version of $x$, or in the case of the scalar multiple being $1$, $Ax = x$
* The basic equation is: $Ax = \lambda x$, where $\lambda$ is a scalar called the eigenvalue
* If $\lambda = 0$, then $Ax = 0x$ means that this eigenvector $x$ is in the nullspace
* Square matrices usually have $n$ eigenvalues and $n$ eigenvectors.
  * The eigenvalues and eigenvectors are matched, to solve $Ax = \lambda x$
  * A $2 \times 2$ matrix would have 2 eigenvalues and 2 eigenvectors
* For example, the matrix $\begin{bmatrix} .8 & .3 \\ .2 & .7 \end{bmatrix}$ has the eigenvectors $x_1 = \begin{bmatrix} .6 \\ .4 \end{bmatrix}$ and $x_2 = \begin{bmatrix} 1 \\ -1 \end{bmatrix}$, and the eigenvalues $\lambda_1 = 1$ and $\lambda_2 = \frac{1}{2}$
  * $Ax_1 =  \begin{bmatrix} .8 & .3 \\ .2 & .7 \end{bmatrix}\begin{bmatrix} .6 \\ .4 \end{bmatrix} = \begin{bmatrix} .6 \\ .4 \end{bmatrix} = x_1$
  * $Ax_2 =  \begin{bmatrix} .8 & .3 \\ .2 & .7 \end{bmatrix}\begin{bmatrix} 1 \\ -1 \end{bmatrix} = \begin{bmatrix} .5 \\ -.5 \end{bmatrix} = \frac{1}{2}x_2$
* All other vectors are combinations of the eigenvectors, weighted by some constant:
  * $\begin{bmatrix} .8 \\ .2 \end{bmatrix} = x_1 + (.2)x_2 = \begin{bmatrix} .6 \\ .4 \end{bmatrix} + \begin{bmatrix} .2 \\ -.2 \end{bmatrix}$
* If we multiply this vector by $A$, we multiply each component eigenvector separately, weighted by its eigenvalue:
  * $A \begin{bmatrix} .8 \\ .2 \end{bmatrix} = x_1 + \frac{1}{2}(.2)x_2 = \begin{bmatrix} .6 \\ .4 \end{bmatrix} + \begin{bmatrix} .1 \\ -.1 \end{bmatrix} = \begin{bmatrix} .7 \\ .3 \end{bmatrix}$

#### The equation for the eigenvalues

* Starting with the equation $Ax = \lambda x$, we move $\lambda x$ to the left side:

$$
\begin{aligned}
Ax &= \lambda x \\
Ax - \lambda x &= 0 \\
Ax - \lambda Ix &= 0 \\
(A - \lambda I)x &= 0
\end{aligned}
$$

* We know that for any matrix $A$, if $Ax = 0$ has a non-zero solution, then this matrix $A$ is not invertible/singular

  * Similarly, for the matrix $A - \lambda I$, if $(A - \lambda I)x = 0$ has a non-zero solution, then $A - \lambda I$ is singular

* If $A - \lambda I$ is singular, then $\det (A - \lambda I)$ must be zero:

  *  $\det (A - \lambda I) = 0$

* We have therefore removed $x$ from the equation (the "characteristic polynomial"), meaning we can now solve for $\lambda$

  * For an $n \times n$ matrix $A$, we end up with an equation of degree $n$, meaning that $A$ will have $n$ $\lambda$'s (eigenvalues), which leads to $n$ $x$'s (eigenvectors)

* Once we have the eigenvalues, we can backsubstitute them into $(A - \lambda I)x = 0$ to get the eigenvectors.

* For example, take the matrix $A = \begin{bmatrix} 1 & 2 \\ 2 & 4 \end{bmatrix}$:

  * When $A$ is already singular, as above, $\lambda = 0$ is one of the eigenvalues (as the determinant is equal to the product of the eigenvalues)
  * To solve, we first find $\det (A - \lambda I)$:

  $$
  \begin{aligned}
  A - \lambda I &= \begin{bmatrix} 1 & 2 \\ 2 & 4 \end{bmatrix} - \begin{bmatrix} \lambda & 0 \\ 0 & \lambda \end{bmatrix} \\
  &= \begin{bmatrix} 1 - \lambda & 2 \\ 2 & 4 - \lambda \end{bmatrix} \\ \\
  
  \end{aligned}
  $$

  $$
  \begin{aligned}
  \det(A - \lambda I) &= \begin{vmatrix} 1 - \lambda & 2 \\ 2 & 4 - \lambda \end{vmatrix} \\
  &= (1 - \lambda)(4 - \lambda) - (2)(2) \\
  &= \lambda^2 - 5 \lambda
  \end{aligned}
  $$

  * Set this determinant to zero and solve for the two $\lambda$'s: $\lambda^2 - 5 \lambda = 0$

    * To get the solutions, we factor the equation into: $\lambda (\lambda - 5) = 0$

    $$
    \begin{aligned}
    \lambda^2 - 5 \lambda &= 0 \\
    \lambda (\lambda - 5) &= 0 \\ \\
    
    \end{aligned} \\
    
    \lambda = 0,\quad \lambda - 5 = 0 \\
    \lambda_1 = 0,\quad \lambda_2 = 5
    $$

  * We can now find the eigenvectors by backsubstituting these values into $(A - \lambda I)x = 0$:

  $$
  \begin{aligned}
  (A - 0I)x &= \begin{bmatrix} 1 & 2 \\ 2 & 4 \end{bmatrix}\begin{bmatrix} y \\ z \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix} \\
  &= \begin{bmatrix} 1 & 2 \\ 0 & 0 \end{bmatrix}\begin{bmatrix} y \\ z \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix} (\textrm{through elimination}) \\
  &= \begin{bmatrix} 1 & 2 \\ 0 & 0 \end{bmatrix}\begin{bmatrix} 2 \\ -1 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix} (\textrm{through backsubstition, see below}) \\ \\
  
  x &= \begin{bmatrix} 2 \\ -1 \end{bmatrix} (\textrm{eigenvector 1})
  \end{aligned} \\
  $$

  $$
  \begin{aligned}
  1y + 2z &= 0 \\
  2(1y) -1(2z) &= 0 \\
  2y - 2z &= 0
  \end{aligned}
  $$

  $$
  \begin{aligned}
  (A - 5I)x &= \begin{bmatrix} -4 & 2 \\ 2 & -1 \end{bmatrix}\begin{bmatrix} y \\ z \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix} \\
  &= \begin{bmatrix} -4 & 2 \\ 0 & 0 \end{bmatrix}\begin{bmatrix} y \\ z \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix} (\textrm{through elimination}) \\
  &= \begin{bmatrix} -4 & 2 \\ 0 & 0 \end{bmatrix}\begin{bmatrix} 1 \\ 2 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix} (\textrm{through backsubstition}) \\ \\
  
  x &= \begin{bmatrix} 1 \\ 2 \end{bmatrix} (\textrm{eigenvector 2})
  \end{aligned} \\
  $$

  * The eigenvectors $x_1 = \begin{bmatrix} 2 \\ -1 \end{bmatrix}$ and $x_2 = \begin{bmatrix} 1 \\ 2 \end{bmatrix}$ are in the nullspaces of the matrices $A - 0I$ (or $A$ in this case) and $A - 5I$

* The eigenvectors represent a line of possible vectors, with the two eigenvectors of the matrix $A$ representing the basis for the eigenspace of that matrix

  * Some matrices have repeated eigenvalues, and therefore do not have the full set of $n$ eigenvectors

#### Determinant and trace

* Exchanging rows or adding a row of $A$ to another row (i.e., elimination) usually changes the eigenvalues
  * The pivots of $U$ are **not** the eigenvalues of $A$
* The sum of the eigenvalues is equal to the sum of the values in the diagonals of the matrix:
  * $\lambda_1 + \lambda_2 + \ldots + \lambda_n = a_{11} + a_{22} + \ldots + a_{nn}$
  * This is called the **trace** of the matrix $A$
* The product of the eigenvalues is equal to the determinant of the matrix $A$:
  * $\det A = a_{11}a_{22}\ldots a_{nn}$
* The eigenvalues of a triangular matrix lie along its diagonal

#### Imaginary eigenvalues

* The eigenvalues may not be real numbers, as in the case of a rotation matrix:
  * No real vector $x$ can lie on the same line as itself when it has been rotated 90° in $\mathbb{R}^n$
  * Therefore, it is only possible to find eigenvalues and eigenvectors by using complex numbers

#### Eigenvalues of $AB$ and $A + B$

* If we have matrices $A$ and $B$ with eigenvalues $\lambda$ and $\beta$, you might assume that if you multiply $A$ and $B$, an eigenvalue of $AB = \lambda \beta$:
  * $ABx = A \beta x = \beta Ax = \beta \lambda x$
* However, this assumes that both $A$ and $B$ have the same eigenvector $x$, which is generally not the case
* The same applies with the matrix $A + B$, where an eigenvalue of this matrix will generally **not** $\lambda + \beta$
* Only when all $n$ eigenvectors are shared between the two matrices $A$ and $B$, will $ABx = \lambda \beta x$ and $BAx = \lambda \beta x$

#### $AX = X \Lambda$ 

* We can take each of our eigenvectors $x$ and put them into a matrix $X$:

$$
X = \begin{bmatrix} & &  \\ x_1 & \ldots & x_n \\  & & \end{bmatrix}
$$

* Because each $Ax_j = \lambda x_j$, if we calculate $AX$, then each column of $X$ will transform into $\lambda x$:

$$
AX = A\begin{bmatrix} & & \\ x_1 & \ldots & x_n \\ & & \end{bmatrix} = \begin{bmatrix} & & \\ \lambda_1 x_1 & \ldots & \lambda_n x_n \\ & & \end{bmatrix}
$$

* We can split $AX$ into $X$ and $\Lambda$, where $\Lambda$ is equal to $\lambda_1 \lambda_2 \ldots \lambda_n \begin{bmatrix} 1 & & \\ & \ddots & \\ & & 1 \end{bmatrix}$
  * This is quite similar to how we converted $\lambda$ into $\lambda I$ when calculating $(A - \lambda I)x$

$$
X \Lambda = \begin{bmatrix} & & \\ \lambda_1 x_1 & \ldots & \lambda_n x_n \\ & & \end{bmatrix} = \begin{bmatrix} & & \\ x_1 & \ldots & x_n \\ & & \end{bmatrix}\begin{bmatrix} \lambda_1 & & \\ & \ddots & \\ & & \lambda_n \end{bmatrix}
$$

* When written this way, the eigenvalue $\lambda_1$ multiplies the first column of $X$, the eigenvector $x_1$

* This is called the _diagonalisation_ of $A$

* We can rewrite $AX = X \Lambda$ by taking the inverse of $X^{-1}$ from either side

  * We assume that $A$ has $n$ independent eigenvectors, and therefore $X$ is invertible
  * $AX = X \Lambda$ is $X^{-1}AX = \Lambda$ or $A = X \Lambda X^{-1}$

* When we factorise $A$ into $A = X \Lambda X^{-1}$, then we are able to easily calculate equations involving powers of $A$:

  * When we want to calculate $A^2$, we can now multiply:

  $$
  \begin{aligned}
  A^2 &= (A)(A) \\
  &= (X \Lambda X^{-1})(X \Lambda X^{-1}) \\
  &= X \Lambda (X^{-1}X) \Lambda X^{-1} \\
  &= X \Lambda I \Lambda X^{-1} \\
  &= X (\Lambda)(\Lambda) X^{-1} \\
  &= X \Lambda^2 X^{-1}
  \end{aligned}
  $$

  * This generalises out for any power of $A$: the matrix of $\lambda$'s, $\Lambda$, is squared while $X$ and its inverse remain unchanged.
  * This greatly simplifies the calculation of $A^k$, as we are now only have to square the scalars on the diagonal of $\Lambda$

* A few remarks on eigenvectors:

  * If the eigenvalues $\lambda_1, \ldots, \lambda_n$ are all different, then the eigenvectors $x_1, \ldots, x_n$ are independent. In this case, the eigenvector $X$ will be invertible, therefore any matrix that has no repeated eigenvectors is diagonalisable
  * Eigenvectors can be multiplied by non-zero constants, because they represent a line of values that can be multiplied by $A$ and not change direction. $A(cx) = \lambda (cx)$ is still true.
  * The eigenvectors in $X$ come in the same order as the eigenvalues in $\Lambda$.
  * Some matrices have insufficient eigenvectors (repeated eigenvalues and eigenvectors). These matrices cannot be diagonalised.
    * The invertibility of $A$ has no connection to the diagonalisability of $A$. $A$ is diagonalisable only if there are sufficient eigenvectors.

#### Similar matrices: same eigenvalues

* Suppose we fix the eigenvalue matrix $\Lambda$ to the same values, but change the values in $X$. 
* We end up with a whole family of different matrices $A = X \Lambda X^{-1}$ which have shared eigenvalues in $\Lambda$
  * $\Lambda$ is the same in each matrix, but $A$ and $X$ are different
  * All of these matrices $A$ and $\Lambda$ are called **similar**
* Similarly, say we have a matrix $C$ (which is not necessarily $\Lambda$) which we keep constant:
  * If we have invertible matrices $B$, then we have the family $A = BCB^{-1}$
  * The matrices $A$ and $C$ are also called similar
* The cases of $B$ and $C$ indicate that the invertible matrix $B$ might not be made up of eigenvectors, and $C$ might not be diagonal
  * However, even in this case, the similar matrices $A$ and $C$ have the same eigenvalues

#### Matrix powers $A^k$

* As said earlier, any time we need to do a calculation that involves powers of $A$, this is greatly sped up by using the factorisation $A = X \Lambda X^{-1}$
  * Each time we multiply $A$ by itself in this factorised form, we end up with values of $X^{-1}X$, which cancel out to $I$
* Powers of $A$: $A^ku_0 = (X \Lambda X^{-1}) \ldots (X \Lambda X^{-1})u_0 = X \Lambda^k X^{-1}u_0$
  * Write $u_0$ as a combination of $c_1x_1 + \ldots + c_nx_n$ of the eigenvectors
  * Multiply this by $A$: $c_1 \lambda_1 x_1 + \ldots + c_n \lambda_n x_n$
  * Multiply now by $A^k$: $c_1 \lambda_1^k x_1 + \ldots + c_n \lambda_n^k x_n$
* Rather than having to complete 100 matrix multiplications, we now only have to get the $k$th power of _scalars_ $\lambda_1, \ldots, \lambda_n$



