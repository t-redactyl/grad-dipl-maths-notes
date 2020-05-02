---
title: What is a matrix?  
date: 2019-07-15   
comments: false  
tags: Maths, Linear algebra  
keywords:   
---

Hello! I'm alive! After writing my last blog post not long after I touched down in Germany, I've had (unsurprisingly) an extremely busy 18 months which has (also unsurprisingly) allowed exactly zero time for blogging. In addition to all of the tasks associated with moving to a new job and country, I have been devoting a lot of time to try and learn German (which is an impossible language, don't even get me started). On top of all of that I had the opportunity to enrol in a mathematics diploma by distance learning late last year, and I decided to use this to fill in some of the gaps in maths knowledge that I have coming from a behavioural sciences background. If you're also interested in getting a solid background in formal mathematics I can highly recommend my programme so far (you can find out more information about it [here](https://london.ac.uk/courses/mathematics)).

As I work my way through my latest unit, linear algebra, I'll be posting about things that I am learning. In addition to helping me fully understand the material, hopefully it will be a gentle introduction to these topics for those of you who also don't have a formal maths background. I'll also be including very accessible links throughout the posts when I use terms or refer to things that you might not be familiar with, in order to help you build up your knowledge bit-by-bit.

First up, we'll cover one of the basic units of analysis in linear algebra, the matrix. It turns out that understanding what the matrix is is not just useful for 90's hackers (forgive my lame Matrix joke!), as we will see in the following blog post.

![What is the matrix?](/Users/jodieburchell/Documents/t-redactyl.io/content/figure/linear-algebra-1.jpg)

## What is a matrix?

A matrix is simply an arrangement of symbols in a rectangle. The symbols can be anything, but going forward we'll be talking about matrices that contain numbers. You can think about a matrix like a table in Excel, where you have $m$ rows and $n$ columns, like so:

![A matrix is like a table](/Users/jodieburchell/Documents/t-redactyl.io/content/figure/linear-algebra-2.png)

We can see this is an Excel spreadsheet with 3 rows and 2 columns, or a $3 \times 2$ spreadsheet. If we were to represent these numbers in a matrix, we'd end up with:
$$
\begin{bmatrix}1 & 2\\3 & 4\\5 & 6\end{bmatrix}
$$
a matrix with 3 rows and 2 columns, or a $3 \times 2$ matrix. 

## Referring to matrix elements

Let's go back to the Excel spreadsheet above. You're probably used to the Excel notation of referring to elements in the spreadsheet using their column name and row number. For example, to get the element $2$ in the spreadsheet above, you'd point to cell $B1$. Similarly, say our matrix above was called $A$:
$$
A = \begin{bmatrix}a_{11} & a_{12}\\a_{21} & a_{22}\\a_{31} & a_{32}\end{bmatrix} = \begin{bmatrix}1 & 2\\3 & 4\\5 & 6\end{bmatrix}
$$
In this case we'd reference the element $2$ using $ a_{12}$. Unlike our Excel spreadsheet, however, we reference the row first and then the column.

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
This operation can also be extended to allow us to subtract a matrix from another matrix, where instead of adding each number in the two matrices, we would subtract one from the other.

### Multiplying a matrix by a scalar

We can also create a new matrix by multiplying a matrix by a [real number](https://www.mathsisfun.com/numbers/real-numbers.html) (called a scalar in this context). Taking our original matrix $A$ and a scalar (let's say $2$), we can create a new matrix $D$ by multiplying every element of $A$ by $2$, like so:
$$
D = 2A = \begin{bmatrix}(2 \times 1) & (2 \times 2)\\(2 \times 3) & (2 \times 4)\\(2 \times 5) & (2 \times 6)\end{bmatrix} = \begin{bmatrix}2 & 4\\6 & 8\\10 & 12\end{bmatrix}
$$

### Matrix multiplication

So we've seen that matrices can be multiplied by scalars. Can we also multiply a matrix by another matrix? Just like with matrix addition and subtraction, this depends on the size of the two matrices. However, unlike addition and subtraction, the matrices don't have to be the same size. Instead the number of _columns_ in the first matrix must be the same as the number of _rows_ in the second matrix. We'll see why by doing an example.

Let's say that we have a $2 \times 4$ matrix, $D$, and we want to multiply $A$ by this matrix:
$$
D = \begin{bmatrix}10 & 11 & 12 & 13\\14 & 15 & 16 & 17\end{bmatrix}
$$
To get the first element of our new matrix $AD$ (which we'll call $E$ to make it a bit neater), we use the following formula:
$$
\begin{align}
e_{11} &= a_{11}d_{11} + a_{12}d_{21}\\
&= (1 \times 10) + (2 \times 14)\\
&= 10 + 28\\
&= 38
\end{align}
$$
In other words, in order to get the first element of our new matrix $E$, we multiply the first and second elements of the first row in $A$ by the first and second elements of the first column in $D$ respectively and then add them. You can now see that this way of pairing of elements is why the number of columns in the first matrix must be the same as the number of rows in the second matrix. 

Where do we go next? In order to get the next element $e_{12}$ (that is, the second element of the first row), we take the elements of the first row of the first matrix and those of the _second_ column of the second matrix and multiply them together like so:
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
And there we have it! We have ended up with a new $3 \times 4$ matrix: that is, a matrix with the same number of rows as the first matrix and the same number of columns as the second matrix.

### Matrix inversion

So far we've seen matrix addition, subtraction and multiplication, but what about matrix division? Well, technically there is no such thing! The closest thing we have is multiplying a matrix by its inverse. Before we get into what an inverse is, we need to pause to describe a special matrix called the _identity matrix_. 

The identity matrix is simply a square matrix which has $0$ everywhere except along the diagonal, where it instead contains $1$'s. The identity matrix can be thought of as the equivalent of $1$ for matrices. For example, a $2 \times 2$ identity matrix would be:
$$
I = \begin{bmatrix}1 & 0\\0 & 1\end{bmatrix}
$$
The inverse of a matrix is another matrix by which you multiply that matrix to get the identity matrix. This is comparable to the inverse with numbers, [where the inverse of a number is what you multiply that number by to get 1](https://www.mathsisfun.com/numbers/inverse.html). You may have noticed that I referred to _the_ inverse of a matrix. This is because every matrix that can be inverted has only one unique inverse. The inverse of the matrix is indicated by writing the name of the original matrix with a little $-1$ superscript ([which is exactly the same as for the multiplicative inverse for numbers](https://www.mathsisfun.com/numbers/inverse.html)). For example, the matrix $Z$ would have the inverse $Z^{-1}$.

How do we find the inverse of a matrix? For $2 \times 2$ matrices it is straightforward. In order to do so, we transform our original matrix in the following way:
$$
M^{-1} = \frac{1}{m_{11}m_{22} - m_{12}m_{21}} \begin{bmatrix}m_{22} & -m_{12}\\-m_{21} & m_{11}\end{bmatrix}
$$
This looks a little complicated, but let's break it down. Have a look at the matrix component of this equation. You can see that we have swapped the positions of the first and last elements in the matrix, so that the element that was in $m_{11}$ is now in $m_{22}$, and vice versa. $m_{12}$ and $m_{21}$ stay in their original spots, but we multiply them by $-1$. We then calculate something called the _determinant_, which is basically a number we divide this reorganised matrix by to get the inverse. This is calculated by the formula $m_{11}m_{22} - m_{12}m_{21}$, and if we multiply our reorganised matrix by $1$ divided by this number, we get the inverse.

Let's try this with a concrete example, a new square matrix $F$:
$$
F = \begin{bmatrix}4 & 3\\6 & 5\end{bmatrix}
$$
In order to get the inverse of $F$, or $F^{-1}$, we do the following:
$$
F^{-1} = \frac{1}{4 \times 5 - 3 \times 6} \begin{bmatrix}5 & -3\\-6 & 4\end{bmatrix}
= \frac{1}{2} \begin{bmatrix}5 & -3\\-6 & 4\end{bmatrix}
= \begin{bmatrix}(\frac{1}{2} \times 5) & (\frac{1}{2} \times -3)\\(\frac{1}{2} \times -6) & (\frac{1}{2} \times 4)\end{bmatrix}
= \begin{bmatrix}\frac{5}{2} & -\frac{3}{2}\\-3 & 2\end{bmatrix}
$$
And voilà, we have our matrix inversion! Let's just double check it worked by multiplying $F$ by it:
$$
FF^{-1} = \begin{bmatrix}(4 \times \frac{5}{2} + 3 \times -3) & (4\times-\frac{3}{2} + 3\times2)\\(6\times\frac{5}{2} + -3 \times 5) & (6\times-\frac{3}{2} + 5\times2)\end{bmatrix}
= \begin{bmatrix}(10-9) & (-6 + 6)\\(15-15) & (-9 + 10)\end{bmatrix} 
= \begin{bmatrix}1 & 0\\0 & 1\end{bmatrix}
$$
And we can see that this has worked perfectly, indicating that we did indeed have the correct inverse of $F$.

You might have also noticed that the order of the multiplication was $F \times F^{-1}$. Multiplying in this order will give us the identity matrix, but multiplying in the opposite order may not. This is true with all matrix multiplications where it is possible to multiply in both directions - you may not get the same result if you flip the order of the multiplication.

Unfortunately, finding the inverse of matrices that are bigger than $2 \times 2$ is less straightforward. There are a few methods to do it, but they are beyond the scope of this blog post. A couple of nice (and gentle) introductions to these can be found [here](https://www.mathsisfun.com/algebra/matrix-inverse-row-operations-gauss-jordan.html) and [here](https://www.mathsisfun.com/algebra/matrix-inverse-minors-cofactors-adjugate.html). 

You've probably guessed from what I said earlier that not all matrices are invertible. Firstly, only square matrices are invertible. In addition, if one row is a multiple of the other, then you cannot invert the matrix. Let's see why this is the case. Let's say we have a matrix $G$, where the second row is a multiple of the first row:
$$
G = \begin{bmatrix}1 & 2\\3 & 6\end{bmatrix}
$$
Let's now try to calculate the inverse, $G^{-1}$:
$$
G^{-1} = \frac{1}{(1 \times 6) - (2 \times 3)}\begin{bmatrix}6 & -2\\-3 & 1\end{bmatrix} = \frac{1}{6 - 6}\begin{bmatrix}6 & -2\\-3 & 1\end{bmatrix} = \frac{1}{0}\begin{bmatrix}6 & -2\\-3 & 1\end{bmatrix}
$$
But wait! Our determinant is $\frac{1}{0}$, which is undefined. This means we can't go any further in solving this equation, making our matrix uninvertable.

### Powers of a matrix

Say we have a number $a$, and we're asked to solve $a^2$. Well, this is easy: we just multiply $a$ by itself to get $a \times a$. [Powers](https://www.mathsisfun.com/exponent.html) of matrices work in exactly the same way. If we take our matrix $F$ again, we can get $F^2$ by multiplying $F$ by itself:
$$
F^2 = FF = \begin{bmatrix}4 & 3\\6 & 5\end{bmatrix}\begin{bmatrix}4 & 3\\6 & 5\end{bmatrix} = \begin{bmatrix}34 & 27\\54 & 43\end{bmatrix}
$$
You can probably guess that, because of the way that matrix multiplication works, we can only raise square matrices to a power. We can raise square matrices to any (positive) power in the same way: if we want to get the cube of $G$, or $G^3$, we multiply the matrix by itself $3$ times, if we want $G^4$, we multiply it by itself $4$ times, and so on.

Powers of matrices follow the [same rules as do powers of a number](https://www.mathplanet.com/education/algebra-1/exponents-and-exponential-functions/properties-of-exponents). Let's have a look at a couple of examples of these. Say we have two [integers](https://www.mathsisfun.com/definitions/integer.html), $m$ and $n$. If we have two matrices, $G^m$ and $G^n$ and we multiply them, we get $G^mG^n = G^{m+n}$. Similarly, if we have the matrix $G^m$ and we raise it to $n$, then we get $(G^m)^n = G^{mn}$.

We can also raise matrices to negative powers. We've already seen an example of this with the inverse of a matrix, which is written as $G^{-1}$. In order to raise a matrix to the power of $-2$, we simply need to multiply the inverse by itself. This logic can then be extended in the same way as we did for raising the matrix to a positive power.

### Matrix transposition and symmetrical matrices

The final thing we will cover is matrix transposition. This is simply what happens if you flip the rows and columns of a matrix. Let's go back to our original matrix, $A$:
$$
A = \begin{bmatrix}1 & 2\\3 & 4\\5 & 6\end{bmatrix}
$$
What would the transpose of $A$ (denoted by $A^T$) look like? Well, it is simple as taking the rows of $A$ and turning them into the columns of $A^T$ (or vice versa):
$$
A^T = \begin{bmatrix}1 & 3 & 5\\2 & 4 & 6\end{bmatrix}
$$
And what would the transpose of $A^T$ look like (in other words, what is $(A^T)^T$)? Well, if we flip the rows and columns again, we just end up back at our original matrix! In other words, $(A^T)^T = A$.

As usual, square matrices behave a little differently to non-square matrices, in that the diagonal values of the matrix don't move when you take the transpose of the matrix. If we go back to our square matrix $F$, and take the transpose, we end up with:
$$
F^T = \begin{bmatrix}4 & 6\\3 & 5\end{bmatrix}
$$
You can see that the values in $f_{12}$ and $f_{21}$ have moved, but the values on the diagonals ($f_{11}$ and $f_{22}$) haven't. This means that if values that are diagonally opposite to each other in a square matrix are equal (say, if $f_{12} = f_{21}$ in the example above), then the transpose of the matrix would be identical to the matrix. Such matrices are called _symmetrical matrices_. Let's have a look at an example. Let's say we have a $3 \times 3$ matrix, $H$, which is symmetrical. Because of this:
$$
H = H^T = \begin{bmatrix}1 & 4 & 5\\4 & 2 & 6\\5 & 6 & 3\end{bmatrix}
$$
This matrix might not look symmetrical at a first glance. However, one way to see that it is really symmetrical is to compare the first row and the first column (and the second row and second column, and the third row and third column). You can see that they are identical, which means that it doesn't matter whether these elements function as a row or a column: the result will be the same. Another way to see this a bit more explicitly is to compare those elements are diagonal to each other in the matrix, as we spoke about above. We can see that $h_{12} = h_{21} = 4$, $h_{13} = h_{31} = 5$ and $h_{23} = h_{32} = 6$.

And that is it for the basics of matrices! In the next post I'll be looking at a special case of matrices called vectors, and some of their useful mathematical properties.