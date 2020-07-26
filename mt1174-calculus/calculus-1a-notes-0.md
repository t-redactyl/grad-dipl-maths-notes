

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

* 

