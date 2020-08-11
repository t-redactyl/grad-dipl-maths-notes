

# MIT Calculus 1A: Differentiation

## Unit 0: Limits

### Introduction to limits

#### Moving closer and closer

* Functions take inputs $x$ and give outputs $f(x)$
* In calculus we are not interested in one input; rather, we are interested in the behaviour of the function as the inout moves or varies
* E.g., what happens as the input moves closer and closer to some value:
  * Moves towards 1 from the left
  * Notation: $x \rightarrow 1$, indicating that $x$ is moving closer and closer to 1
  * This does not mean that $x$ will ever _equal_ 1, we are more concerned about the values of $x$ that are near 1
* As $x$ moves, $f(x)$ also moves:
  * As $x$ moves closer to 1, does $f(x)$ move closer to some value of its own?
* Take the function:

$$
f(x) = \frac{\sqrt{3 - 5x + x^2 + x^3}}{x - 1}
$$

* We can simply select certain values that are getting closer and closer to 1 from the left:

  * We simply plug these values into $f(x)$ to see if they get closer to something:

  | $x$  |       $f(x)$        |
  | :--: | :-----------------: |
  |  0   | $-\sqrt{3}$ = -1.73 |
  | 0.5  |        -1.87        |
  | 0.9  |        -1.97        |
  | 0.99 |       -1.997        |

  * It looks like the numbers are getting closer to -2: As $x$ approaches 1 from the left, $f(x)$ approaches -2
  * These are just examples, we could have chose any value near 1
  * We will not choose $x = 1$ (and in fact, $f(x)$ has a 0 denominator as this point so is not defined)
  * $f(x)$ might never equal -2, but it will get arbitrarily close

#### One-sided limits

* In the previous example: As $x \rightarrow 1^-, f(x) \rightarrow -2$ (as $x$ approaches 1 from the left, the limit of $f(x)$ is -2)
* When we calculate the same from the right, we get:

| $x$  | $f(x)$ |
| :--: | :----: |
|  2   |  2.24  |
| 1.5  |  2.12  |
| 1.1  |  2.02  |
| 1.01 | 2.002  |

* As $x \rightarrow 1^+, f(x) \rightarrow 2$ (as $x$ approaches 1 from the right, the limit of $f(x)$ is 2)
  * So approaching 1 from opposite sides gives us different limits
* For this function, $x = 1$ is undefined
* The notation to describe a limit is as follows:
  * The limit of $f(x)$ as $x$ approaches 1 (from the right) is equal to 2
  * $\lim\limits_{x \to 1^+} f(x) = 2$ or $\lim\limits_{x \to 1^+} \frac{\sqrt{3 - 5x + x^2 + x^3}}{x - 1} = 2$
  * This is the right-sided or right-hand limit at the point $x = 1$

* Similarly, we have our left-hand limit:
  * The left-hand limit at the point $x = 1$
  * $\lim\limits_{x \to 1^-} f(x) = -2$ or $\lim\limits_{x \to 1^-} \frac{\sqrt{3 - 5x + x^2 + x^3}}{x - 1} = -2$
* Another way of saying this is:
  * $f(x) \to R$ as $x \to a^+$ or $f(x) \to S$ as $x \to a^-$

#### Possible limit behaviours

* As seen in the previous example, the left- and right-sided limits don't have to agree
* However, they can, e.g. $\lim\limits_{x \to 0^-} \frac{x}{\tan(2x)} = 0.5$ and $\lim\limits_{x \to 0^+} \frac{x}{\tan(2x)} = 0.5$
  * In this case, the value of $f(0)$ might equal 0.5, or it might equal something else, or it might not exist at all
  * In this case, both the left- and right-hand limit still exist
* It is also possible that the limits don't exist, e.g., for $h(x) = \frac{|x| + \sin x}{x^2}$, $\lim\limits_{x \to 0^-} h(x) = 0$, however, $h(x) \to +\infty$ as $x \to 0^+$ 
  * As the values get bigger and bigger _without bound_ as we approach 0 from the right, the right hand limit **does not exist**
  * $h(x)$ is not approaching any particular value
* Finally, it's also possible that the limit doesn't exist because $f(x)$ oscillates between different values but never settles on approaching one particular value
  * E.g., for $j(x) = \sin (13 / x)$, as $x \to 0^+$, $j(x)$ approaches neither some finite fixed value, nor $+\infty$, nor $-\infty$
  * In this case, the limit also **does not exist**

#### Limit concepts

* If $\lim\limits_{x \to a^+} f(x)$ exists and equals $R$, it is not necessarily true that $\lim\limits_{x \to a^-} f(x)$ exists
* If $\lim\limits_{x \to a^+} f(x) = R$ and $\lim\limits_{x \to a^-} f(x) = L$, it is not necessarily true that $R = L$
* If $\lim\limits_{x \to a^+} f(x) = R$, it is not necessarily true that $f(a) = R$
* If $f(a) = K$, it is not necessarily true that $\lim\limits_{x \to a^+} f(x) = K$ (the function may equal something completely "off the line" at that value)
* If we know $f(a)$ exists, we do not necessarily know that $\lim\limits_{x \to a} f(x)$ exists

#### The overall limit

* If the left- and right-sided limits both exist, and they both equal the same number $L$, then we can define an overall limit
* This is denoted as either:
  * $\lim\limits_{x \to a} f(x) = L$ or
  * $f(x) \to L$ as $x \to a$
* It does not matter if $f(a) = L$ as well, only that the values around $a$ are approaching $L$
* The overall limit will not exist if: 
  * Either the left- or right-sided limits do not exist
  * If the left- and right-sided limits are not equal

#### The formal definition of the limit

* Formally, the statement $\lim\limits_{x \to a} f(x) = L$ is defined as:

$$
\textrm{For all } \epsilon > 0, \textrm{ there exists some } \delta > 0 \textrm{ such that if } 0 < |x - a| < \delta, \textrm{ then } |f(x) - L| < \epsilon.
$$

* This means that:
  * There exists some arbitrary small distances $\epsilon$ and $\delta$, both of which are greater than 0
  * If we set the distance between our point of interest $a$ and some input value $x$ to be smaller than this small distance $\delta$ (but still greater than 0), then the distance between $f(x)$ and the limit $L$ will be less than this small value $\epsilon$
  * The "for all" and "there exists" clauses have to do with how small these distances need to get
  * Because we want $f(x)$ to get arbitrarily close to $L$, these statements need to be satisfied no matter how small $\epsilon$ gets
  * Given _any_ choice of $\epsilon$, we can satisfy the condition $|f(x) - L| < \epsilon$ as long as $x$ gets close enough to $a$, where the proximity required is measured by $\delta$

#### Limit laws

* **The limit law for addition**: The limit of the sum of two functions is the sum of the limits of those two functions, as long as they are approaching the same value $a$:
  * $\lim\limits_{x \to a} f(x) = L_1$
  * $\lim\limits_{x \to a} g(x) = L_2$ 
  * $\lim\limits_{x \to a} [f(x) + g(x)] = L_1 + L_2$
  * This will work with one-sided limits as well, as long as both functions and their sum are coming from the _same_ side
* **The limit law for subtraction**: The limit of the difference of two functions is the difference of their two limits:
  * $\lim\limits_{x \to a} [f(x) - g(x)] = L_1 - L_2$
* **The limit law for multiplication**: The limit of the product of two function is the product of their two limits:
  * $\lim\limits_{x \to a} [f(x) \cdotp g(x)] = L_1 \cdotp L_2$
* **The limit law for division**: The limit of the quotient of two functions is the quotient of their two limits, but only if the bottom limit does not equal zero:
  * $\lim\limits_{x \to a} [\frac{f(x)}{g(x)}] = \frac{L_1}{L_2}$ if $L_2 \neq 0$

### Continuity

#### Continuity at a point

* Even if the limit of a function $f(x)$ at point $a$ is $L$, $f(a)$ doesn't necessarily equal $L$
* However, when it does, $f(x)$ is called **continuous** at $a$
  * $f$ is continuous at $x = a$ if $\lim\limits_{x \to a} f(x) = f(a)$
* If we know that $f$ is continuous at $x = a$, it simplifies the calculation of the limit:
  * We can calculate $f(a)$ to get the limit
* For $f$ to be continuous at $x = a$, then:
  * $\lim\limits_{x \to a} f(x)$ (the overall limit) must exist (be defined)
  * $f(a)$ must also exist (be defined)
  * The overall limit must equal $f(a)$: $\lim\limits_{x \to a} f(x) = f(a)$
* We can also have left- and right-continuity for $f$ at $x = a$:
  * Left continuity:
    * $\lim\limits_{x \to a^-} f(x)$ (the left-sided limit) must exist (be defined)
    * $f(a)$ must also exist (be defined)
    * The left-sided limit must equal $f(a)$: $\lim\limits_{x \to a^-} f(x) = f(a)$
  * Right continuity:
    * $\lim\limits_{x \to a^+} f(x)$ (the left-sided limit) must exist (be defined)
    * $f(a)$ must also exist (be defined)
    * The left-sided limit must equal $f(a)$: $\lim\limits_{x \to a^+} f(x) = f(a)$

* **Jump discontinuity**: If the left-hand limit $\lim\limits_{x \to a^-} f(x)$ and the right-hand limit $\lim\limits_{x \to a^+} f(x)$ both exist at point $x = a$, but they are not equal
* **Removable discontinuity**: If the overall limit $\lim\limits_{x \to a} f(x)$ exists (i.e., the left- and right-handed limits are the same), but the overall limit is not equal to $f(a)$ at $x = a$

#### Overall continuity

* If a function is continuous not just at _one_ point, but continuous at _every_ point, then the function is **continuous on the real line**, or **continuous everywhere**
  * There are no discontinuities anywhere (we can draw the whole line without having to lift our pens from the paper)
* The limit of a continuous function will always equal the value of the function at that point, for any $x \in A$ (if $A$ is the function domain)
* A few basic types of continuous functions
  * Constant functions: e.g., $f(x) = 3$
  * $f(x) = x$
  * Absolute value function: $f(x) = |x|$
  * $f(x) = \sin x$ and $f(x) = \cos x$ (however, $f(x) = \tan x$ is _not_ continuous everywhere)

#### Limit laws and continuity

* If we have two functions that are both continuous at $x = a$, $f(g)$ and $f(h)$, then:
  * If we multiply these two functions to get a new function, $h(x) = f(x) \cdotp g(x)$, then the limit of this new function is the product of its composite functions' limits (by the limit law for multiplication)
  * If the limit of $f(x) = f(a)$, and the limit of $g(x) = g(a)$, then the limit of $g(x) = f(a) \cdotp g(a) = h(a)$
  * Therefore, if functions $f$ and $g$ are both continuous at some point, then their product will be continuous at that point
  * By extension, if $f$ and $g$ are continuous everywhere, then their product will be continuous everywhere
* This applies to both sums and differences of functions
* We can then start inferring that quite complex functions are continuous, as they are components of the basic continuous function types we covered above:
  * Polynomials/linear functions: e.g., $5x^2 + 2x - 4$:
    * $5x^2$ = product of constant and $x$ and $x$ $\to$ continuous
    * $2x$ = product of constant and $x$ $\to$ continuous
    * $4$ = constant $\to$ continuous
    * Entire function is sum and difference of continuous functions $\to$ continuous
* Quotients of continuous functions will be continuous at all points where _the denominator is not 0_
  * E.g., $\tan x = \frac{\sin x}{\cos x}$ is the quotient of two continuous functions
    * It will be continuous at all points that $\cos x$ is not 0 (e.g., $-\frac{\pi}{2}, -\frac{\pi}{2}$)
  * E.g., $\frac{1}{x^2 + 1}$ : $x^2 + 1$ will never be 0, therefore this function is continuous everywhere
* Composition of two continuous functions:
  * If $f(x)$ and $g(x)$ are continuous everywhere, then their composition (regardless of the order) will be continuous everywhere:
    * $h(x) = f \circ g(x) = f(g(x))$
    * $x \to a$, $g(x) \to g(a)$
    * $f(g(x)) \to f(g(a))$
    * Therefore, $h(x) \to h(a)$

#### Basic continuous functions

* The following functions are continuous at all _real numbers_
  * all polynomials
  * $\sqrt[3]{x}$
  * $|x|$
  * $\cos x$ and $\sin x$
  * exponential functions $a^x$ with base $a > 0$

#### Intermediate value theorem (IVT)

* Say that we have two points, one below a horizontal line ($A$) and one above it ($B$)
* As our function travels between these lines, it _must intersection this line if the function is continuous_
  * It must have at least one point of intersection, but it could be more than 1
* The intermediate value theorem states that if we have $(a, f(a))$ and $(b, f(b))$ and some point on the y-axis $M$ between them, then there must be some point $(c, f(c))$ between them such that $f(c) = M$, if:
  * $M$ must be between $f(a)$ and $f(b)$ 
  * $f$ must be continuous on $(a, b)$, right continous at $a$ and left continuous at $b$
  * This only works for real numbers, as only real numbers have true continuity (there exists a representation of $c$ and $f(c) = M$)

#### Using the intermediate value theorem

* Say we have a function that allows for negative values of $f(x)$
  * If we have a value of $f(x) < 0$, and a value of $f(x) > 0$, then we know we must have some value of $f(x)$ that intersects the $x$-axis
  * In other words, we have at least one solution to $f(x) = 0$, which means we have at least one root
* E.g., $f(x) = x^4 - x - 1$
  * $f(1) = -1$
  * $f(2) = 13$
  * Therefore, we know that the root of $f(x)$ is between $x = 1$ and $f(2)$
* There are faster techniques to find the exact root using this method (such as Newton's method)
* However, we can use the IVT to deduce that there _is at least one root_ for a given $f(x)$, assuming that $f(x)$ is continuous

### Limits of quotients

* In cases where both $f$ and $g$ of a quotient function $\frac{f}{g}$ tend to zero, then we have an interesting result:
  * This represents the _rise_ and the _run_ of the slope of the tangent line at point $A$ on our curve
  * The slope is the limit of the quotient of the rise and the run of the line though the two points as $B$ approaches $A$
  * This ratio is meaningful and has an honest limit

#### Limits and division

* If the limit of the denominator is not zero, then the limit is simply the limit of the numerator function over the limit of the denominator function
* If the limit of the denominator _is_ zero, then:
  * If the limit of the numerator is not zero, then:
    * If the limit of the numerator is not small, and the limit of the demoninator is zero, then as we approach the limit, the numerator will be divided by a smaller and smaller number
    * Therefore the limit will become huge without bound, either in a positive or negative direction 
    * The quotient will not be approaching any fixed number (instead $+ \infty$ or $- \infty$)
    * Therefore the limit does not exist (DNE)
  * If the limit of the numerator is zero:
    * The limit is not necessary undefined ($\frac{0}{0}$)
    * We can simplify the quotient to get a quotient that does not have a zero denominator, e.g., $\frac{2x}{x} = 2$
    * This limit is 2 almost everywhere (except for $x = 0$), meaning that we have a valid limit of 2

#### Limit law for division, part 3

* When $x$ is near $a$ (when $x \to a$), the numerator and denominator are _approaching_ 0, but that does not mean that they equal 0
* The quotient will be some small number over some small number when $x$ is near to $a$
* What we need to find out is how small the numerator and denominator are _relative to each other_
* The quotient essentially then represents a ratio
  * E.g., $\frac{2x}{x}$ has a ratio of 2

#### Using the division limit law

* E.g., 

$\lim\limits_{x \to 1} \frac{x^2 + 2x - 3}{x^2 - 3x + 2}$ have both numerator and denominator going to 0

*  We need to do extra work to simplify this equation and work out the ratio of the num to the denom
* In the case of polynomials, this work is factorisation:

$$
\begin{aligned}
\lim\limits_{x \to 1} \frac{x^2 + 2x - 3}{x^2 - 3x + 2} &= \lim\limits_{x \to 1} \frac{(x - 1)(x + 3)}{(x - 1)(x - 2)} \\
&= \lim\limits_{x \to 1} \frac{x + 3}{x - 2} \\
&= \frac{4}{-1} \\
&= -4
\end{aligned}
$$

* The simplified function is defined when $x = 1$
  * The limits of both functions is the same, as it doesn't matter whether the function is defined when $x = 1$

#### Infinite limits

* Say we have the function $\lim\limits_{x \to 0} \frac{1}{x}$
  * As we approach 0 from the right, this function will tend towards $+ \infty$, because we have 1 divided by a very small positive number:  $\lim\limits_{x \to 0^+} \frac{1}{x} = + \infty$
  * Similarly, if we approach 0 from the left, this function will tend towards $- \infty$ because we have 1 divided by a very small negative number: $\lim\limits_{x \to 0^-} \frac{1}{x} = - \infty$
* With infinite limits, it is generally easiest to deal with the left- and right-hand sides separately
  * The trick is working out whether the denominator stays positive or negative as it approaches our value of $x$

 

