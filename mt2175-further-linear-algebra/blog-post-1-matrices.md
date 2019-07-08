---
title: What is a matrix, and what can you do with it?  
date: 2019-07-07   
comments: false  
tags: Maths, Linear algebra  
keywords:   
---

## What is a matrix?

A matrix is simply an arrangement of symbols in a rectangle. The symbols can be anything, but going forward we'll be talking about matrices that contain numbers. You can think about a matrix like a table in Excel, where you have $m$ rows and $y$ columns, like so:

![A matrix is like a table](/Users/jodieburchell/Documents/t-redactyl.io/content/figure/linear-algebra-1.png)

We can see this is a spreadsheet with 3 rows and 2 columns, or a $3 \times 2$ spreadsheet. If we were to represent these numbers in a matrix, we'd end up with:
$$
\begin{bmatrix}1 & 2\\3 & 4\\5 & 6\end{bmatrix}
$$
a matrix with 3 rows and 2 columns, or a $3 \times 2$ matrix. 

## Referring to matrix elements

Let's go back to the Excel spreadsheet above. You're probably used to the Excel notation of referring to elements (or cells) of the spreadsheet, where to reference the element $1$ in the spreadsheet above, you'd point to cell $A1$. Similarly, say our matrix above was called $A$:
$$
A = \begin{bmatrix}a_{11} & a_{12}\\a_{21} & a_{22}\\a_{31} & a_{32}\end{bmatrix} = \begin{bmatrix}1 & 2\\3 & 4\\5 & 6\end{bmatrix}
$$
In this case we'd reference the element $1$ by $ a_{11}$. Unlike our Excel spreadsheet, however, we reference the row first and then the column.

## Matrix operations

There are a number of mathematical operations we can do with matrices. We'll explore some of the most important ones below.

### Matrix addition and subtraction

Say was have two matrices, $A$ and $B$. If these matrices are the same size (that is, they both have $m$ rows and $n$ columns), we can add them together. We do this by adding each element in $A$ with the equivalent element in $B$ to get matrix $C$, so that $c_{11} = a_{11} + b_{11}$, $c_{12} = a_{12} + b_{12}$, up to $c_{mn} = a_{mn} + b_{mn}$.

Let's say that in addition to our matrix $A$ above, we have a matrix $B$ like so:
$$
B = \begin{bmatrix}7 & 8\\9 & 10\\11 & 12\end{bmatrix}
$$
Then our new matrix $C = A + B$ is then:
$$
C = (A + B) = \begin{bmatrix}(1 + 7) & (2 + 8)\\(3 + 9) & (4 + 10)\\(5 + 11) & (6 + 12)\end{bmatrix} = \begin{bmatrix}8 & 10\\12 & 14\\16 & 18\end{bmatrix}
$$
This operation can also be extended to allow us to subtract a matrix from another matrix, where instead of adding each number in each matrix, we would subtract one from the other.

### Multiplying a matrix by a scalar

We can also create a new matrix by multiplying a matrix by a real number (called a scalar in this context). Taking our original matrix $A$ and a scalar (let's say $2$), we can create a new matrix $D$ by multiplying every element of $A$ by $2$, like so:
$$
D = 2A = \begin{bmatrix}(2 \times 1) & (2 \times 2)\\(2 \times 3) & (2 \times 4)\\(2 \times 5) & (2 \times 6)\end{bmatrix} = \begin{bmatrix}2 & 4\\6 & 8\\10 & 12\end{bmatrix}
$$

### Matrix multiplication

So we've seen that matrices can be multiplied by scalars. Can we also multiply a matrix by another matrix? Just like with matrix addition and subtraction, this depends on the size of the two matrices. However, unlike addition and subtraction, the matrices don't have to be the same size. Instead the number of _columns_ in the first matrix must be the same as the number of _rows_ in the second column. We'll see why next, when we multiply our matrix $A$ by another matrix. 

Let's say that we have a $2 \times 4$ matrix, $D$:
$$
D = \begin{bmatrix}10 & 11 & 12 & 13\\14 & 15 & 16 & 17\end{bmatrix}
$$
To get the first element of our new matrix $E$ (or $AD$), we use the following formula:
$$
\begin{align}
e_{11} &= a_{11}d_{11} + a_{12}d_{21}\\
&= (1 \times 10) + (2 \times 14)\\
&= 10 + 28\\
&= 38
\end{align}
$$
In other words, in order to get the first element of our new matrix $E$, we multiply the first and second elements of the first row in $A$ by the first and second elements of the first column in $D$ respectively and then add them. You can now see that this way of pairing of elements is why the number of columns in the first matrix must be the same as the number of rows in the second matrix. 

Where do we go next? In order to get the next element $e_{12}$ (that is, the second element of the first row), we take the elements of the first row of the first matrix and those of the _second_ row of the second matrix and multiply them together like so:
$$
\begin{align}
e_{12} &= a_{11}d_{21} + a_{12}d_{22}\\
&= (1 \times 11) + (2 \times 15)\\
&= 11 + 30\\
&= 41
\end{align}
$$
Continuing this across all of the elements, we end up with:
$$
E = AD = \begin{bmatrix}38 & 41 & 44 & 47\\86 & 93 & 100 & 107\\134 & 145 & 156 & 167\end{bmatrix}
$$
And there we have it! We have ended up with a new $3 \times 4$ matrix: that is, a matrix with the number of rows as the first matrix and the number of columns as the second matrix.

### Matrix inversion

So far we've seen matrix addition, subtraction and multiplication, but what about matrix division? Well, technically there is no such thing. The closest thing we have is multiplying a matrix by it's inverse. Before we get into what an inverse is, we need to pause to describe a special matrix called the _identity matrix_. 

The identity matrix is simply a square matrix which has $0$ everywhere except along the diagnonal, where it instead contains $1$'s. For example, a $2 \times 2$ identity matrix would be:
$$
I = \begin{bmatrix}1 0\\0 1\end{bmatrix}
$$
The inverse of a matrix is simple another matrix by which you multiply that matrix to get the identity matrix. You may have noticed that I referred to _the_ inverse of a matrix. This is because every matrix that can be inverted has only one unique inverse.

How do we find the inverse of a matrix? For $2 \times 2$ matrices it is straightforward.

blah blah blah

Are all matrices invertible? Actually, no! Firstly, only square matrices are invertible. In addition, [read up on matrix inversion].

### Powers of a matrix

fhksj

### Matrix transposition and symmetrical matrices



 





