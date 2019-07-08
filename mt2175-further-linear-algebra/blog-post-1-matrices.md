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

We can see this is a spreadsheet with 3 rows and 2 columns, or a $2 \times 3$ spreadsheet. If we were to represent these numbers in a matrix, we'd end up with:
$$
\begin{bmatrix}1 & 2\\3 & 4\\5 & 6\end{bmatrix}
$$
a matrix with 3 rows and 2 columns, or a $2 \times 3$ matrix. 

## Referring to matrix elements

Let's go back to the Excel spreadsheet above. You're probably used to the Excel notation of referring to elements (or cells) of the spreadsheet, where to reference the element $1$ in the spreadsheet above, you'd point to cell $A1$. Similarly, say our matrix above was called $A$:
$$
A = \begin{bmatrix}a_{11} & a_{12}\\a_{21} & a_{22}\\a_{31} & a_{32}\end{bmatrix} = \begin{bmatrix}1 & 2\\3 & 4\\5 & 6\end{bmatrix}
$$
In this case we'd reference the element $1$ by $ a_{11}$. Unlike our Excel spreadsheet, however, we reference the row first and then the column.

## Matrix operations

There are a number of mathematical operations we can do with matrices. We'll explore some of the most important ones below.

### Matrix addition

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

So we've seen that matrices can be multiplied by scalars. Can we also multiply a matrix by another matrix? The answer is … sometimes. 

### Matrix inversion

jkhkj

### Powers of a matrix

fhksj

### Matrix transposition and symmetrical matrices



 





