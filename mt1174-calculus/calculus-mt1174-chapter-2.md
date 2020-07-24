# Calculus MT1174

## Chapter 2: Functions

#### Domain and codomain

* Taking 2 sets $A$ and $B$, a function $f$ from $A$ to $B$ is a rule which takes each element of $A$ and produces exactly one element of $B$
  * $f$ cannot give us more than one element of $B$ for any given element of $A$
  * $f : A \rightarrow B$ 
* In the setting of this function, $A$ is called the _domain_ and $B$ is called the _codomain_ (or _range_)
* A function is like a "black box" that takes in any $x \in A$ in the domain and applies the rule given by $f$ to it, to output the unique output $f(x) \in B$

$$ x \in A \rightarrow \boxed{f} \rightarrow f(x) \in B $$

* The $x \in A$ is called the _independent variable_, while the $f(x) \in B$ is the _dependent variable_, or $y = f(x)$
* The set of the domain and codomain might be $\mathbb{R}$, or some subsets called intervals. The finite intervals can have the following forms:
  * $(a, b) = \{x \in \mathbb{R} \mid  a < x < b \}$: open interval
  * $[a, b] = \{ x \in \mathbb{R} \mid a \leq x \leq b \}$: closed interval
  * $(a, b] = \{ x \in \mathbb{R} \mid a < x \leq b \}$ and $[a, b) = \{ x \in \mathbb{R} \mid a \leq x < b \}$: half-open intervals
* There are also infinite intervals which have one finite endpoint:
  * $(- \infty, a] = \{ x \in \mathbb{R} \mid x \leq a \}$ and $[a, \infty) = \{ x \in \mathbb{R} \mid a \leq x \}$
  * $(- \infty, a) = \{ x \in \mathbb{R} \mid x < a \}$ and $(a, \infty) = \{ x \in \mathbb{R} \mid a < x \}$
* Infinity is never included in the interval as it is symbolic, therefore is not a real number that can be included

#### Graphs

* We can represent all mappings between the domain and codomain produced by $f : A \rightarrow B$ as a set of ordered pairs $(x, y)$ in $\mathbb{R}^2$
  * In this case, $(x, y)$ is equivalent to $(x, f(x))$
* These ordered pairs can be represented as a graph
* When thought of this way, it becomes obvious that every $x \in A$ _must_ produce one unique output $y \in B$

#### Power functions

* Power functions are those of the form $f : \mathbb{R} \rightarrow \mathbb{R}$, where $f(x) = x^n$
* Depending on whether $n$ is odd or even, $f(x) = y = x^n$ will behave the same as $x$ approaches $\infty$ but differently as $x$ approaches $-\infty$:
  * As $x$ approaches $\infty$, $f(x)$ approaches $\infty$, regardless of whether $n$ is odd or even
  * As $x$ approaches $-\infty$, $f(x)$ approaches $-\infty$ if $n$ is odd, and $\infty$ if $n$ is even

#### Exponential functions

* Exponential functions with a base $a$ take the form $f : \mathbb{R} \rightarrow (0, \infty)$ where $f(x) = a^x$ and $a$ is any positive real number that is not 1
* Exponential functions have the following behaviours:
  * If $0 < a < 1$ (i.e., if the base $a$ is positive but less than 1) then:
    * $f(x) = a^x \rightarrow 0$ as $x \rightarrow \infty$ 
      * As the base is raised to the power of larger positive numbers, then $f(x)$ gets closer and closer to 0
      * E.g., $0.5^2 = 0.25$ while $0.5^3 = 0.125$
    * $f(x) = a^x \rightarrow \infty$ as $x \rightarrow -\infty$ 
      * As the base is raised to the power of smaller negative numbers, then $f(x)$ gets larger and larger
      * E.g., $0.5^{-2} = \frac{1}{0.5^2} = 4$ while $0.5^{-3} = \frac{1}{0.5^3} = 8$
  * If a > 1, then:
    * $f(x) = a^x \rightarrow \infty$ as $x \rightarrow \infty$
      * As the base is raised to the power of larger positive numbers, then $f(x)$ gets larger and larger
      * E.g., $2^2 = 4$ while $2^3 = 8$
    * $f(x) = a^x \rightarrow 0$ as $x \rightarrow -\infty$
      * As the base is raised to the power of smaller negative numbers, then $f(x)$ gets closer to 0
      * E.g., $2^{-2} = \frac{1}{2^2} = 0.25$ while $2^{-3} = \frac{1}{2^3} = 0.125$
  * When $x = 0$, $a^0 = 1$, meaning that exponential graphs always go through the point $(0, 1)$ regardless of the base

#### Trigonometric functions

* The conversion between radians and degrees is: $\textrm{angle in radians} = \frac{2 \pi}{360} \times \textrm{angle in degrees}$
  * 360° is $2\pi$ radians
  * 180° is $\pi$ radians
  * 90° is $\frac{\pi}{2}$ radians
* Measuring $\theta$ in radians means the sine and cosine functions will give a solution where $0 \leq \theta \leq \pi / 2$
* These functions are defined as the following for a right-angled triangle:
  * $\sin \theta = \frac{\textrm{opposite}}{\textrm{hypotenuse}}$
  * $\cos \theta = \frac{\textrm{adjacent}}{\textrm{hypotenuse}}$
* We have some special triangles: one where both non-right angles are equal (both $\theta = \pi / 4$) and one where one of the non-right angles is double the size of the other ($\theta_1 = \pi / 6, \theta_2 = \pi / 3$)
* The unit circle allows us to extend the definition of the sine and cosine to $0 \leq \theta \leq 2\pi$
  * We take a triangle with a hypotenuse of 1, and plot the hypotenuse as a vector coming from the origin, like below:

![](/Users/burchj01/Desktop/unit-circle.png "Unit circle")

* We can see that for every triangle within this unit circle with an angle $0 \leq \theta \leq \pi / 2$, $\cos \theta = x$ and $\sin \theta = y$
  * Because the hypotenuse is 1 for all triangles in the unit circle, $\cos \theta = \textrm{adjacent}$ and $\sin \theta = \textrm{opposite}$
  * These represent the distance along the $x$ and $y$ axes of the underlying Cartesian plane respectively
  * Therefore, the lengths of the adjacent and opposite sides of the triangle represent $(x, y)$ directly when $0 \leq \theta \leq \pi / 2$
* In order to work out the $x, y$ coordinates for $\pi /2 \leq \theta \leq 2\pi$, we need to work out what quadrant they are in:
  * For example, if $\theta = 5\pi / 4$, then this angle is in the third quadrant, and $\pi$ radians away from the first quadrant
  * We can work out what the angle of this triangle would be if it were in the first quadrant by subtracting this distance from the angle: $\theta = 5\pi / 4 - \pi = \pi / 4$
  * Knowing the angle is $\pi / 4$, we know that both sides of the triangle in the unit circle are $1 / \sqrt{2}$, meaning that $(x, y) = (1 / \sqrt{2}, 1 / \sqrt{2})$ if the triangle were in the first quadrant
  * However, because this triangle would be in the third quadrant (where both $x$ and $y$ are negative), the actual coordinates are $(x, y) = (-1 / \sqrt{2}, -1 / \sqrt{2})$
* The unit circle also demonstrates that the functions $\sin \theta$ and $\cos \theta$ are periodic over a period of $2\pi$
* The graph of the cosine function is what we get if we shift the sine function to the left by $\pi / 2$, i.e., $\cos \theta = \sin(\theta + \frac{\pi}{2})$

#### Combinations of functions

* **Linear combinations**:
  * If we have two functions with the same domain and codomain, we can define a new function that is a linear combination of the two:
    * $f : A \rightarrow B$, $g : A \rightarrow B$
    * If $k$ and $l$ are constants, then we could create the new function $kf + lg: A \rightarrow B$, defined by $(kf + lg)(x) = kf(x) + lg(x)$ for all $x \in A$
  * Polynomials (or linear equations) take this form, where:
    * $p_n(x) = a_nx^n + a_{n - 1}x^{n - 1} + \ldots + a_1x + a_0$, when $a_i$ represents some real constant
* **Products and quotients**:
  * If we have two functions with the same domain, but possibly different codomains, we can define a new function which is the product of these two functions:
    * $(f \cdotp g)(x) = f(x)g(x)$
  * The quotient of two functions can also be defined, with the additional caveat that it is only defined for $x \in A$ where $g(x) \neq 0$:
    * $(f / g)(x) = \frac{f(x)}{g(x)}$
    * This function is defined as $f / g : A^\prime \rightarrow B$, where $A^\prime$ is a new domain given by $A^\prime = \{x \in A \mid g(x) \neq 0 \}$
  * $\tan \theta$ is an example of a trigonometric quotient where:
    * $\tan \theta = \frac{\sin \theta}{\cos \theta}$
    * This function will be defined as long as $\cos \theta \neq 0$, that is, as long as $\theta \neq (2n + 1)\frac{\pi}{2}$ for $n \in \mathbb{Z}$
  * The reciprocals of the three trigonometric functions are also quotients:
    * Secant: $\sec \theta = \frac{1}{\cos \theta}$, defined when $\theta \neq (2n + 1)\frac{\pi}{2}$
    * Cosecant: $\sec \theta = \frac{1}{\sin \theta}$, defined when $\theta \neq n\pi$
    * Cotangent: $\cot \theta = \frac{1}{\tan \theta}$, defined when $\theta \neq n\pi$

#### Composition of functions

* Composition of functions involves applying functions to the same $x \in A$ in a sequence:
  * $(g \circ f)(x) = g(f(x))$ indicates that we are applying "g after f"
* This can be represented as:

$$ x \in A \rightarrow \boxed{f}\rightarrow f(x) \in B \rightarrow \boxed{g}\rightarrow g(f(x)) \in C$$

#### Inverse functions

* If we have the sets $A$ and $B$ and the function $f : A \rightarrow B$, we know that for every $x \in A$ there is a unique $y \in B$ such that $y = f(x)$
* We _might_ also be able to define another function $g : B \rightarrow A$, so that for every $y \in B$ there is a unique $x \in A$ such that $y = f(x)$ if and only if $x = g(y)$
* $g$ in this case is the invese of $f$, $f^{-1}$
* Looking at this "black box" perspective, we have the following diagram for $f$

$x \in A \rightarrow \boxed{f} \rightarrow f(x) \in B$

* Now $f^{-1}$, if it exists, will work like this:

$y \in B \rightarrow \boxed{f^{-1}} \rightarrow f^{-1}(y) \in A = x \in A$

* The composition of $f^{-1}$ after $f$ gives us:

$x \in A \rightarrow \boxed{f} \rightarrow f(x) \in B \rightarrow \boxed{f^{-1}} \rightarrow x \in A$ or $(f^{-1} \circ f)(x) = f^{-1}(f(x)) = x$

* It also works the other way around, with the composition of $f$ after $f^{-1}$:

$ y \in B \rightarrow \boxed{f^{-1}} \rightarrow f^{-1}(y) \in A \rightarrow \boxed{f} \rightarrow y \in B$, or $(f \circ f^{-1})(y) = f(f^{-1}(y )) = y$

* Functions will only have an inverse we can take $y = f(x)$ and solve it to obtain a unique solution, $x$, in terms of $y$ for every $y \in B$: that is 
  * No $x \in A$ will map to the same $y \in B$ as any other $x \in A$
  * Every $y \in B$ represents some $f(x)$ 
* For example:
  * $f : \mathbb{R} \rightarrow \mathbb{R}$ given by $f(x) = x + 2$ has an inverse, as every $y \in \mathbb{R}$ is represented by an $f(x)$ for an $x \in A$, and no $x \in A$ maps to the same $f(x)$
  * The inverse of this function is $f^{-1}(y) = y - 2$, which is the reflection of $f(x) = x + 2$ around the line y = x
* Another example:
  * $f : \mathbb{R} \rightarrow \mathbb{R}$ given by $f(x) = x^2$ does not have an inverse as:
    * If $y < 0$, we get no solution, meaning that all values in $\mathbb{R}$ are not an $f(x)$ for $x \in A$
    * If $y > 0$, we get two solutions because $x = \pm \sqrt{y} \in \mathbb{R}$

#### Power functions: root functions

* A power function is defined as $f(x) = x^n$ where $x \in \mathbb{N}$ and $f : [0, \infty) \rightarrow [0, \infty)$ 
* The inverse is the root function: $x = f^{-1}(y) = y^{1/n}$
  * $x = y^{1/n}$ if and only if $y = x^n$, provided that $x, y \geq 0$
* E.g., for $n = 2$, we get the square function and its inverse, the square root function
* Additionally, if $n$ is odd, the root function is the inverse of the power function for $f : \mathbb{R} \rightarrow \mathbb{R}$

#### Exponential functions: logarithmic functions

* An exponential function is defined as $f(x) = a^x$ where $f: \mathbb{R} \rightarrow (0, \infty)$ and $a \neq 1$ is a positive real number
* Its inverse is the the logarithm to base $a$: $x = f^{-1}(y) = \log_a y$
  * $x = log_a y$ if and only if $y = a^x$ provided that $y > 0$

#### Trigonometric functions: inverse trigonometric functions

* As sine and cosine oscillate, we need to restrict the domain to an interval of values of $\theta$ called the principal range
* **Sine function**: the principal range of the domain is $[-\frac{\pi}{2}, \frac{\pi}{2}]$, meaning that $f(\theta) = y = \sin \theta$ given $f : [-\frac{\pi}{2}, \frac{\pi}{2}] \rightarrow [-1, 1]$ 
  * The inverse is the **arcsin** function $\sin^{-1}$, where $\sin^{-1} : [-1, 1] \rightarrow [-\frac{\pi}{2}, \frac{\pi}{2}]$ 
* **Cosine function**: the principal range is the interval $[0, \pi]$, meaning that $f(\theta) = y = \cos \theta$ given $f : [0, \pi] \rightarrow [-1, 1]$ 
  * The inverse is the **arccos** function $\cos^{-1}$, where $\cos^{-1} : [-1, 1] \rightarrow [0, \pi]$
* **Tangent function**: For the inverse of the tangent function, we need to take into account both the oscillations and the asymptotes that occur when the function is undefined
  * The principal range is the interval $(-\frac{\pi}{2}, \frac{\pi}{2})$, meaning that $f(\theta) = y = \tan \theta$ given that $f :  (-\frac{\pi}{2}, \frac{\pi}{2}) \rightarrow \mathbb{R}$
  * The inverse is the **arctan** function $\tan^{-1}$, where $\tan^{-1} : \mathbb{R} \rightarrow (-\frac{\pi}{2}, \frac{\pi}{2})$ 
* Note the difference between the **inverses** of the trigonometric functions (arcsin, arccos and arctan) and the **reciprocals** (cosec, sec and cot)

#### Identities 

* Identities are expressions that are true for all $x$, e.g., $(x + 1)^2 = x^2 + 2x + 1$
* The power laws are identities that work for any values of $a$, $n$ and $m$ for which both sides of the expression are defined:
  * $a^ma^n = a^{m + n}$
  * $\frac{a^m}{a^n} = a^{m - n}$
  * $(a^m)^n = a^{mn}$

#### The laws of logarithms

* As long as all terms are defined, the laws of logarithms state that:
  * $\log_ax + \log_ay = \log_a(xy)$
  * $\log_ax - \log_ay = \log_a (\frac{x}{y})$
  * $y\log_ax = \log_a(x^y)$
* These laws are derived from the power laws, and the fact that $a^{log_ax} = x$
* If $a, b \neq 1$ are positive real numbers, then we have a change of base formula such that: $\log_ax = \frac{\log_bx}{\log_ba}$

#### Trigonometric identities

* Pythagorian identities:

  * For acute angles, $\sin^2 \theta + cos^2 \theta = 1$:
    * From Pythagora's theorem: 

  $$
  \begin{aligned}
  \sin^2 \theta + \cos^2 \theta &= (\frac{\textrm{opposite}}{\textrm{hypotenuse}})^2 +  (\frac{\textrm{adjacent}}{\textrm{hypotenuse}})^2 \\
  &= \frac{\textrm{opposite}^2 + \textrm{adjacent}^2}{\textrm{hypotenuse}^2} \\
  &= \frac{\textrm{hypotenuse}^2}{\textrm{hypotenuse}^2} \\
  &= 1
  \end{aligned}
  $$

  * If we divide both sides of this equation by $\sin^2 \theta$, we get:
    * $1 + \cot^2 \theta = \csc^2 \theta$
    * This holds true when $\theta \neq n\pi$ for $n \in \mathbb{Z}$ 
  * If we divide both sides of this equation by $\cos^2 \theta$, we get:
    * $\tan^2 \theta + 1 = \sec^2 \theta$
    * This holds true when $\theta \neq (2n + 1)\frac{\pi}{2}$ for $n \in \mathbb{Z}$

* Compound-angle formulae:

  * When we have two angles, $\theta$ and $\phi$:
    * $\sin(\theta + \phi) = \sin \theta \cos \phi + \cos \theta \sin \phi$
    * $\cos(\theta + \phi) = \cos \theta \cos \phi - \sin \theta \sin \phi$
    * $\sin(\theta - \phi) = \sin \theta \cos \phi - \cos \theta \sin \phi$
    * $\cos(\theta - \phi) = \cos \theta \cos \phi + \sin \theta \sin \phi$
  * These work for all $\theta, \phi \in \mathbb{R}$
  * These equations are summarised as:
    * $\sin(\theta \pm \phi) = \sin \theta \cos \phi \pm \cos \theta \sin \phi$
    * $\cos(\theta \pm \phi) = \cos \theta \cos \phi \mp \sin \theta \sin \phi$
  * If $\theta = \phi$, then we have the double-angle formulae:
    * $\sin(2\theta) = 2 \sin \theta \cos \theta$
    * $\cos(2\theta) = \cos^2 \theta - \sin^2 \theta$
  * These work for all $\theta \in \mathbb{R}$

#### Conic sections

#### Parabolae

* A parabola is a curve of the form: $y = ax^2 + bx + c$, where $a$, $b$ and $c$ are constants and $a \neq 0$
* If we complete the square, the equation is then of the form: $y = a(x - p)^2 + q$
* This means we can infer the following:
  * The $y$-intercept of the curve, found by setting $x$ to 0
  * The $x$-intercepts of the curve, if they exist, found by setting $y$ to 0
  * The turning point with coordinates $(p, q)$: this will be a minimum if $a > 0$ and a maximum if $a < 0$

#### Circles

* A circle of radius $r$, centred on point $(a, b)$ has the equation: $(x - a)^2 + (y - b)^2 = r^2$
* The $x$- and $y$-intercepts can be found by finding where $y = 0$ and $x = 0$ respectively
  * This is done by completing the square for an equation of the form $ax^2 + bx + cy^2 + dy = 0$ and then solving when $x = 0$ or $y = 0$

#### Ellipses

* An ellipse has the equation: $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$
* This is essentially a circle centred on the origin that has been "squashed"
* We can as always find the $x$- and $y$-intercepts by solving for when $y = 0$ and $x = 0$
  * In the case of quotients, any term with a 0 numerator is 0, therefore $x$ and $y$ disappear from the equation when we solve for when they are 0

#### Hyperbolae

* A hyperbola with no $y$-intercepts has the equation: $\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$

  * These hyperbola never cross the $y$-axis, therefore they have no $y$-intercept
  * They do have $x$ intercepts that can be found by setting $y$ to 0
  * They also have slant or oblique asymptotes that can be found by rewriting the equation as:

  $$
  \begin{aligned}
  \frac{y^2}{x^2} = b^2(\frac{1}{a^2} - \frac{1}{x^2})
  \end{aligned}
  $$

  

  * When rewritten in this form, as $x \rightarrow \infty$, we have $1 / x^2 \rightarrow 0$, which leaves us with $\frac{y^2}{x^2} = \frac{b^2}{a^2}$ and then $y = \pm \frac{b}{a}x$
  * Rewriting the above equation:

$$
\begin{aligned}
\frac{x^2}{a^2} - \frac{y^2}{b^2} &= 1 \\
\frac{x^2b^2 - y^2a^2}{a^2b^2} &= 1 \\
x^2b^2 - y^2a^2 &= a^2b^2 \\
\frac{x^2b^2}{a^2} - y^2 &= b^2 \\
x^2b^2(\frac{1}{a^2}) - b^2 &= y^2 \\
b^2(\frac{1}{a^2}) - b^2(\frac{1}{x^2}) &= \frac{y^2}{x^2} \\
b^2(\frac{1}{a^2} - \frac{1}{x^2}) &= \frac{y^2}{x^2}
\end{aligned}
$$

* A hyperbola with no $x$-intercepts has the equation: $\frac{y^2}{b^2} - \frac{x^2}{a^2} = 1$
* Finally, we have rectangular hyperbolae, which have equations of the form: $(x - a)(y - b) = c$
  * These occur when the asymptotes are the horizontal line $y = b$ and the vertical line $x = a$