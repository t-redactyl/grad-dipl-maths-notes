# Introduction to Linear Algebra

## Gilbert Strang

### Chapter 1: Introduction to vectors

* Vector addition:
  * Vectors are added component by component, so if we have:

$$ \vec v = \begin{bmatrix} v_1 \\ v_2 \end{bmatrix}, \vec w = \begin{bmatrix} w_1 \\ w_2 \end{bmatrix} $$  then $ \vec v + \vec w = \begin{bmatrix} v_1 + w_1 \\ v_2 + w_2 \end{bmatrix} $$

* Scalar multiplication:
  * Each component of the vector is multiplied by the scalar:

$$  2\vec v = \begin{bmatrix} 2v_1 \\ 2v_2 \end{bmatrix} $$

* These two operations form the basis of linear combinations:
  * Linear combination of any two vectors is of the form:

$$ c\vec v + d\vec w = c\begin{bmatrix} 1 \\ 1 \end{bmatrix} + d\begin{bmatrix} 2 \\ 3 \end{bmatrix} = c\begin{bmatrix} c + 2d \\ c + 3d \end{bmatrix} $$

* Linear combinations represent all vectors that fill a certain part of $\mathbb{R}^n$. Taking $\mathbb{R}^3$ as an example:
  * If we have only linear combinations of the zero vector $c\begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix}$, then the part of $\mathbb{R}^3$ being filled would only be the point $(0, 0, 0)$
  * If we have linear combinations of any other vector in $\mathbb{R}^3$, $c\vec u$, then we have a line running through $(0, 0, 0)$
  * If we have linear combinations of two _independent_ vectors $c\vec u + d\vec v$, we have a plane through $(0, 0, 0)$. Independent means that the vectors are not linear combinations of each other. If they were, they would lie on the same line $c\vec u$.
  * If we have linear combinations of three independent vectors $c\vec u + d\vec v + e\vec w$, we have all vectors in $\mathbb{R}^3$. Again, if any of these vectors are dependent, we will have instead a line or plane in $\mathbb{R}^3$ which runs through the origin.
* The dot product or the inner product of two vectors $\vec v = \begin{bmatrix} v_1 \\ v_2 \end{bmatrix}$ and $\vec w = \begin{bmatrix} w_1 \\ w_2 \end{bmatrix}$ is a **scalar** $v \cdot w$ and is calculated by:
  * $v \cdot w = v_1w_1 + v_2w_2$
  * In addition, $v \cdot w$ equals $w \cdot v$. That is, the inner product of vectors is **commutative** 
* When the dot product of two vectors is $0$, this means that these vectors are perpendicular
* The length of a vector is the square root of its dot product with itself:
  * vector length $= \lVert \vec v \rVert = \sqrt{\vec v \cdot \vec v} = (v_1^2 + v_2^2 \ldots v_2^n)^{1/2} $
  * This is because when we draw the vector from the origin, the components of the vector have their own lengths along the $x, y, \ldots $ axes. This is easiest to imagine in $\mathbb{R}^2$, where component 1 will have a length along the $x$-axis, component 2 will have a length along the $y$-axis, and the vector runs along the diagonal of these two lengths to form a right-angled triangle. Thus, we can use Pythagora's theorem to solve for the length of the vector.
* Unit vectors are a special vector whose length equals 1:  $\vec u \cdot \vec u = 1$
  * The unit vector for any (non-zero) vector is obtained by dividing the vector by its length: $u = \vec v / \lVert \vec v \rVert$

* The dot product of two unit vectors gives the cosine of the angle between them:
  * For two unit vectors $\vec u$ and $\vec U$, $\vec u \cdot \vec U = \cos\theta$ 
  * $\cos\theta$ is always between -1 and 1
  * If we don't have unit vectors, we will need to convert them by dividing them by their length to get the cosine of the angle between them:

$$ \frac{\vec v \cdot \vec w}{\lVert \vec v \rVert \lVert \vec w \rVert} = \cos\theta $$

* **Schwarz inequality**:
  * Because of the dot product of two unit vectors cannot exceed 1, this means that $\vec v \cdot \vec w$ (the numerator of the equation) cannot be bigger than $\lVert \vec v \rVert \lVert \vec w \rVert$.
  * This is summed up in the Schwarz inequality:

$$ |\vec v \cdot \vec w| \leq \lVert \vec v \rVert \lVert \vec w \rVert $$

* **Triangle inequality**:
  * The length of the third side of a triangle must be less than or equal to the sum of the lengths of the other two sides
  * **COME BACK TO THIS**: https://www.khanacademy.org/math/linear-algebra/vectors-and-spaces/dot-cross-products/v/linear-algebra-vector-triangle-inequality

* Matrix inversion:
  * Some matrices are invertible: i.e., it means that for any $Ax = b$, we can recover the values of $x$ given $b$
    * This means there is a unique solution $x$ for every $b$ in $\mathbb{R}^n$
    * The matrix $A^{-1}$ produces $x = A^{-1}b$
  * $A \times A^{-1} = I$, the identity matrix
* When a column vector is dependent on other column vectors in a matrix, it means:
  * It is a linear combination of those vectors
  * It lies on the same line/plane/hyperplane as the other column vectors
  * $Cx = 0$ has man solutions, as combinations other than $0\vec u + 0\vec v + 0\vec w$ give $b = 0$

