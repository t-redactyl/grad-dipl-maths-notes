# MT2116: Exam notes

## Part 2: Chapters 8-11 (rational and real numbers and limits)

## Chapter 8: rational, real and complex numbers

**Construction of rational numbers using equivalence relations:** Let $X = \mathbb{Z} \times (\mathbb{Z} \backslash [0])$ be all pairs ($m,n$) where $m,n \in \mathbb{Z}$ and $n \neq 0$, and define a relation $R$ on $X$ where: 
$$
(m,n)R(m', n') \iff mn' = m'n
$$
(This is another way of saying that $\frac{m}{n} = \frac{m'}{n'}$, without yet getting into fractions.) This relation is an equivalence class because:

* Reflexive: $mn = nm$

* Symmetric: $(m,n)R(p,q) \Rightarrow mq = np \Rightarrow pn = qm \Rightarrow (p,q)R(m,n)$

* Transitive: If we have $(m,n)R(p,q)$ and $(p,q)R(s,t)$, then $mq = np$ and $pt = qs$. So, $(mq)(pt) = (np)(qs)$ (by multiplying the results together) $= mpqt = npqs = mt = ns$. Therefore $mt = ns \Rightarrow (m,n)R(s,t)$. 

The equivalence class $[(m,n)] = \frac{m}{n}$. We can work out whether rational numbers belong to the same equivalence class if $\frac{m}{n} = \frac{m'}{n'} \textrm{ or } mn' = m'n$. For example, we can work out what is the equivalence class $[(1,2)]$ by working out what conforms to the relation $(m,n)R(1,2)$, or $m \times 2 = n \times 1$, or $n = 2m$. So $[(1,2)] = \{(1,2), (-1,-2), (2,4), (-2,-4), \ldots\}$. In other words, $\frac{1}{2} = \{\frac{1}{2}, \frac{-1}{-2}, \frac{2}{4}, \frac{-2}{-4}, \ldots\}$. Integers are a special case of the rational numbers, where an integer $n$ can be represented with the rational number $\frac{n}{1}$. So $\mathbb{Z} \subseteq \mathbb{Q}$. 

**Arithmetic with rational equivalence classes:** Addition and multiplication can be defined on the set of rational numbers as follows:
$$
\frac{a}{b} \oplus \frac{c}{d} = \frac{ad + bc}{bd}, \frac{a}{b} \otimes \frac{c}{d} = \frac{ac}{bd}
$$
This is exactly the same as addition and multiplication in the "regular" sense using fractions, but we need to establish whether these definition depend on the choice of representatives from each equivalence class. (See course guide pp. 111-112 for details.)

**Infinitely repeating decimal expansions and rationality:** Real numbers encapsulate the set of numbers which are both able to be represented by ratios (or fractions), that is, $\mathbb{Q}$ or the rational numbers, and those that cannot, that is, irrational numbers. Together, rational and irrational number make up the real numbers $\mathbb{R}$. Every irrational number can be represented as a set of infinitely repeating decimals. However, only rational numbers will be represented using either terminating decimals or (infinitely) repeating patterns, which can then be converted into a rational number.

**Finding decimal expansions of rational numbers:** If a number is rational, it will have a repeating pattern (which might be 0). We can find the decimal expansion of a rational number using long division, for example, for $\frac{4}{7}$, where we get $0.\overline{571428}$. Note that during the long division calculation, we will eventually get back to a repeating pattern if our decimal expansion is rational.

We can also work out how to represent infinitely repeating patterns in decimal expansions as rational numbers. For example, if we have the number $a = 0.18\overline{3}$, then:

* Let $x = 0.00\overline{3}$, which is the infinitely expanding portion of the decimal. Then $10x = 0.0\overline{3}$.

* We can now get rid of the infinitely expanding portion by taking $10x - x = 0.0\overline{3} - 0.00\overline{3}$, so we now have $9x = 0.03$, and $x = \frac{\frac{3}{100}}{9} = \frac{1}{300}$.  

* We can now add this to the rest of the decimal as a rational representation:  

$$
0.18\overline{3} = 0.18 + 0.00\overline{3} + \frac{18}{100} + \frac{1}{300} = \frac{55}{300} = \frac{11}{60}
$$

**Prove that numbers are rational or irrational:** In order to prove that a number is not rational, you need to demonstrate that is cannot be represented in the form $\frac{m}{n}$, where $m,n \in \mathbb{Z}$. For example, prove that the real number $\sqrt{2}$ is irrational; that is, there are no positive integers $m,n$ with $(\frac{m}{n})^2 = 2$.

* We demonstrate this by contradiction. Suppose that there were such $m,n$, and suppose there is some $d > 1$ that divides both $m \textrm{ and } n$. So we can divide both $m$ and $n$ to get $m', n'$, where $\frac{m}{n} = \frac{m'}{n'}$. If this is the case, then this means that the $gcd(m,n) = 1$. **(We assume this because we assume that $\frac{m}{n}$ is the simplest form of the fraction, therefore they cannot have any greater common divisor than 1.)**.
* We can rewrite the equation $(\frac{m}{n})^2 = 2$ as $m^2 = 2n^2$. This means that $m^2$ is even, and therefore $m$ is even, so there is some $m_1$ such that $m = 2m_1$. Therefore we can rewrite $m^2 = 2n^2$ as $4m_1^2 = 2n^2$, and $n^2 = 2m_1^2$. This means that $n^2$ and hence $n$ is also even.
* However, we have assumed that $gcd(m,n) = 1$. If $m$ and $n$ are even, then they also have 2 as a common divisor, which contradicts this assumption. This contradicts the assumption that $(\frac{m}{n})^2 = 2$ and hence no integers $m,n$ exist.    

**Rational numbers arbitrarily close to any real number:** There both infinitely many rational numbers, but there are also no gaps in the rational numbers. With the idea that irrational numbers are infinite decimal expansions, we can get quite a good approximation to any real number by terminating the decimal expansion after a large number of digits.

Between any two rational numbers, no matter how close they are together, there is always another rational number. Suppose $q, q' \in \mathbb{Q}$ with $q < q'$. Then there is $r \in \mathbb{Q}$ with $q < r < q'$. For example, $r = (1/2)(q + q')$.

**Countability of sets:** A set is defined as countable if there is a bijection between it and $\mathbb{N}$. In other words, if a set is countable, it can be listed, i.e., $s_1, s_2, s_3, \ldots,$ . Both $\mathbb{Z}$ and $\mathbb{Q}$ are countable, so informally speaking they are the same "size" (although as infinite sets, this is not strictly true). However, $\mathbb{R}$ is not countable. The proof is by contradiction.

Suppose that $f: \mathbb{N} \rightarrow \mathbb{R}$ and that:
$$
f(n) = x_{n0}.x_{n1}x_{n2}x_{n3}\ldots
$$
This produces a set of real numbers:
$$
f(1) = 0.x_{11}x_{12}x_{13}x_{14}\ldots\\
f(2) = 0.x_{21}x_{22}x_{23}x_{24}\ldots\\
f(3) = 0.x_{31}x_{32}x_{33}x_{34}\ldots\\
f(4) = 0.x_{41}x_{42}x_{43}x_{44}\ldots\\
$$
If $\mathbb{R}$ is a bijection with $\mathbb{N}$, then this would be the complete list of real numbers. However, it is simple to imagine a real number $y = 0.y_1y_2y_3y_4\ldots$ which is different from every number in the list: that is, $y_1$ is any digit other than $x_{11}$, $y_2$ is any digit other than $x_{12}$, etc. As real numbers are infinitely expanding, it is possible to find a unique number that differ from every image under $f$. As $y$ is not included in the set produced by $f: \mathbb{N} \rightarrow \mathbb{R}$, then $\mathbb{R}$ is not countable. 

**Complex numbers:** There are a subset of quadratic equations which do not intersect the $x$-axis, and for which there is no solution in the real numbers. This means you cannot factorise them. They are known as _irreducible_ polynomials. We require complex numbers to solve such a polynomial.

In order to start defining the complex numbers, we first take the imaginary number $i$, which has the property that $i^2 = -1$. A complex number is a number of the form $z = a + ib$, where $a$ and $b$ are real numbers, and $i^2 = -1$.  The set of all such numbers is $\mathbb{C} = \{a + ib : a,b \in  \mathbb{R}\}$. Complex numbers $z$ have 2 components: the real number $a$ is the real part of $z$ ($\operatorname{Re}(z)$) and the real number $b$ is the imaginary part of $z$ ($\operatorname{Im}(z)$). If $b = 0$, then $z$ is an real number, meaning that $\mathbb{R}  \subseteq \mathbb{C}$. If $a = 0$, then $z$ is said to be purely imaginary. 

**Complex conjugate:** If $z = a + ib$, then the complex conjugate of $z$ is the complex number $\overline{z}$, $z = a - ib$. For example, if we have the irreducible polynomial $q(z) = x^2 + x + 1$, we can solve using the quadratic formula as so:
$$
\begin{align}
x &= \frac{-1 \pm \sqrt{1^2 - 4\times1\times1}}{2\times1}\\
&= \frac{-1 \pm \sqrt{-3}}{2}
\end{align}
$$
This gives us two solutions, the complex number $\frac{-1}{2}+\frac{\sqrt{-3}}{2}$ and its complex conjugate $\frac{-1}{2}-\frac{\sqrt{-3}}{2}$. 

The complex conjugate has a number of properties:

* $z + \overline{z} = 2 \operatorname{Re}(z)$ 
* $z - \overline{z} = 2i \operatorname{Im}(z)$
* $\overline{\overline{z}} = z$
* $\overline{z + w} = \overline{z} + \overline{w}$
* $\overline{zw} = \overline{z}\overline{w}$
* $\overline{\frac{z}{w}} = \frac{\overline{z}}{\overline{w}}$

**Arithmetic of complex numbers:** We can do addition and multiplication of complex numbers, keeping in mind always that $i^2 = -1$:

Addition example: If $z = (1 + i)$ and $w = (4 - 2i)$, then:
$$
z + w = (1 + i) + (4 - 2i) = 1 + 4 + i - 2i = 5 - i(1-2) = 5 - i
$$
Multiplication example: If $z = (1 + i)$ and $w = (4 - 2i)$, then:
$$
zw = (1 + i)(4 - 2i) = 4 + 4i - 2i - 2i^2 = 4 - (-2) + 2i = 6 + 2i
$$
Division example: Division is defined by $\frac{z}{w} = \frac{z\overline{w}}{w\overline{w}}$ (since $w\overline{w}$ is a real number). For example:
$$
\frac{1 + i}{4 - 2i} = \frac{(1 + i)(4 + 2i)}{(4 - 2i)(4 + 2i)} = \frac{2 + 6i}{16 + 4} = \frac{1}{10} + \frac{3}{10}i
$$
**Fundamental theorem of algebra:** Complex roots of polynomials with real coefficients appear in conjugate pairs. 

## Chapter 9: supremum and infimum

**Triangle inequality:** For any two real numbers, $x,y$, we have:
$$
|x + y| \leq |x| + |y|
$$
This is because $|x + y|$ can equal $|x-y|$, but $|x| + |y|$ must always be $x + y$. From this, we can say:
$$
|x-y| \leq |x - z| + |y-z|
$$
(because $|x-y| = |(x-z) + (z-y)|$). 

In addition, for any two real numbers $x,y$:

$|x-y| \geq ||x| - |y||$

**Bounding of sets of real numbers:** There are different kinds of intervals for real numbers:

* Square bracket $[$: This indicates that the interval is bounded by and includes this number (e.g., $[a,b]=\{x\in\mathbb{R}\mid a\leq x\leq b\}$) 
* Curved bracket $($: This indicates that the interval is bounded by this number but does not include it (e.g., $(a,b)=\{x\in\mathbb{R}\mid a < x < b\}$)
* Infinity as a bound ($\infty \textrm{ or } -\infty$): Indicates that the interval does not have a bound where this is used and includes all numbers above or below the other boundary (e.g., $[a,\infty)=\{x\in\mathbb{R}\mid x \geq a \}$)

The formal definitions of boundedness are:

* $S \subseteq \mathbb{R}$ is **bounded above** if and only if there is $M \in \mathbb{R}$ such that for all $x \in S, x \leq M$. $M$ is then an upper bound on $S$
* $S \subseteq \mathbb{R}$ is **bounded below** if and only if there is $M \in \mathbb{R}$ such that for all $x \in S, x \geq M$. $M$ is then an lower bound on $S$
* A set is **bounded** if it is bounded above and bounded below. 

**Supremum and infimum:** An element $x \in S$ in the **maximum** of $S$ if it is an upper bound of $S$. We can similarly define the **minimum**. However, a set that is bounded above need not have a maximum; a set has a maximum if and only if the upper bound belongs to the set. Similarly for the minimum.

The **continuum property** states that every non-empty set of real numbers that is bounded above has a least upper bound, and every non-empty set of real numbers that is bounded below has a greatest upper bound.

The least upper bound of a set $S$ of real numbers is called the **supremum** of $S$, denoted by sup $S$. Similarly, the greatest upper bound of $S$ is called the **infimum** of $S$, and is denoted by inf $S$.

Alternatively, the supremum can be defined as: $\sigma$ = sup $S$ if and only if $\sigma$ is an upper bound for $S$ and if for any $\sigma' < \sigma$, there is some $x \in S$ with $x > \sigma'$. In other words, for some random value $\epsilon$ in $S$:
$$
\forall\epsilon > 0, \exists x \in S \textrm{ with } x > \sigma - \epsilon
$$
The infimum can be defined similarly: $\tau$ = inf $S$ if and only if $\tau$ is a lower bound for $S$ and if for any $\tau' < \tau$, there is some $y \in S$ with $y < \tau'$. In other words, for some random value $\epsilon$ in $S$:
$$
\forall \epsilon > 0, \exists y \in S \textrm{ with } y < \tau + \epsilon 
$$
You can see that for both the supremum and infimum in intervals of real numbers, that there will always be some value closer to the upper or lower bound (because of the density or real numbers).

## Chapter 10: sequences and limits

**Definition of a sequence:**

**Sequences defined with formulas:**

**Sequences defined recursively:**

**Sequences converging to plus or minus infinity:**

**Formal definition of a limit:**

**Bounding of sequences:**

**Links between boundedness and convergence:**

**Convergence of monotonic sequences:**

**Algebra of limits:**

**Sandwich Theorem:**

**Subsequences of sequences:**

**Convergent subsequences of bounded sequences:**

## Chapter 11: limits of functions and continuity

**Limit of a functions:** Let $f: \mathbb{R} \rightarrow \mathbb{R}$ be a function. We say that $L$ is the limit of $f(x)$ as $x$ approaches $a$, denoted by $\lim_{x \to a} f(x) = L$ (or in other words, $f(x) \rightarrow L \textrm{ as } x \rightarrow a$), if for each $\epsilon > 0$, there exists some $\delta > 0$ such that:
$$
0 < |x - a| < \delta \Rightarrow |f(x) - L| < \epsilon
$$
Or demonstrated graphically:

![Types of functions](/Users/jodieburchell/Documents/grad-dipl-maths-notes/mt2116-abstract-mathematics/limit_function.png)

What this and the above definition are saying is that if someone gives us some arbitrarily small real number $\epsilon$, then there is some neighbourhood of $a$, $(a-\delta, a+\delta)$, such that any $x$ in this neighbourhood - other than $a$ itself - will have $f(x)$ in the $\epsilon$-neighbourhood ($L - \epsilon, L + \epsilon$) of $L$.

We can slso define limits in a different way: Let $f: \mathbb{R} \Rightarrow \mathbb{R}$ be a function. We say that $L$ is the limit of $f(x)$ as $x$ approaches $\infty$, denoted by $lim_{x \to \infty} f(x) = L$, if for each $\epsilon > 0$, there exists $M > 0$ such that:
$$
x \geq M \Rightarrow |f(x) - L| < \epsilon
$$
In other words, $x$ will always be bigger than or equal to some arbitrary $M$ (as it moves to infinity), and the distance between $f(x)$ and $L$ will always be smaller than some arbitrary number $\epsilon$.

**Algebra of limits:** We can derive new functions by applying an algebra on the set of functions. We apply these point wise, so that (for example) a new function $(f + g)$ is obtained for each value of $x$, $(f+g)(x) = f(x) + g(x)$. This also carries through to the limits, as can be seen in the folloing definitions.

Let $f,g: \mathbb{R} \rightarrow \mathbb{R}$ be two functions and $c$ be any real number. Suppose that $\lim_{x \to a} f(x) = L$ and $\lim_{x \to a} g(x) = M$. Then:

* $\lim_{x \to a} (cf)(x) = cL$
* $\lim_{x \to a} (|f|)(x) = |L|$
* $\lim_{x \to a} (f + g)(x) = L + M$ 
* $\lim_{x \to a} (f - g)(x) = L - M$ 
* $\lim_{x \to a} f(x)g(x) = LM$ 
* $\lim_{x \to a} (f / g)(x) = L/M$ provided that $g(x) \neq 0$ for each $x$ in some neighbourhood of $a$.

**Function continuity:** Some functions may have limits that are different depending on whether you approach from the left or the right. Let $f: \mathbb{R} \rightarrow \mathbb{R}$ be a function, and we say that $L$ is the limit of $f(x)$ as $x$ approaches $a$ from the left (or below), or $lim_{x \to a-} f(x) = L$ if for each $\epsilon > 0$ there exists $\delta > 0$ such that $a - \delta < x < a \Rightarrow |f(x) - L| < \epsilon$. A similar definition can be made for $x$ approaching $a$ from the right (or above), or $lim_{x \to a+} f(x) = L$.

These limits are needed to define limits in functions that are not continuous. To define continuity of a function:

* A function is continuous at point $a$ if $f(a)$ is defined and and is equal to $lim_{x \to a} f(x)$. (This simply means that the limit is defined).

* A function is continuous if it is continuous at each point $a$.

* A function is continuous on the interval $[a,b]$ if it is continuous at each point in $(a,b)$ and (i) $f(a) = lim_{x \to a+} f(x)$ and (ii) $f(b) = lim_{x \to a-} f(x)$ (the limit is the same when $x$ is approaching $a$ from the left and right)  

**Continuity and algebra of limits:** Let $f,g: \mathbb{R} \rightarrow \mathbb{R}$ be functions which are continuous at $a \in \mathbb{R}$ and $c$ be any real number. Then $|f|, (cf), (f-g), (f+g), (f(x)g(x))$ are all continuous at $a$, and $(f/g)$ is continuous provided that $g(x) \neq 0$ for any $x$ in the neighbourhood of $a$. In addition, if $g$ is a function that is continuous at $a$, and $f$ is a function that is continuous at $g(a)$, then $(f \circ g)$ is continuous at $a$.

**Continuous functions and convergent sequences:** A function 

**Maximum and minimum value of closed bounded sequence:**

**Intermediate Value Theorem:**

