# MIT Calculus 1A: Differentiation

## Unit 1: The derivative

### What is the derivate?

#### Average velocity

* If we are dealing with an equation for velocity, then $t$ = time, and $f(t)$ = position
* To calculate the average velocity between 8:00 and 10:00, we would calculate:

$$
\begin{aligned}
\textrm{Avg velocity} &= 85\textrm{mph} \\
&= \frac{220 - 50\textrm{mi}}{10 - 8\textrm{hr}} \\
&= \frac{f(10) - f(8)}{10 - 8} \\
&= \frac{\Delta f}{\Delta t}
\end{aligned}
$$

* Numerator is change in position, denominator is change in time
  * This is what the $\Delta$ notations in the numerator and denominator represent
* In order to get a more accurate estimate, we can narrow the time span $\Delta t$ that we're looking at, e.g., between 8:00 and 8:01:

$$
\begin{aligned}
\textrm{Avg velocity} &= 60\textrm{mph} \\
&= \frac{51 - 50\textrm{mi}}{8 \frac{1}{60} - 8\textrm{hr}} \\
&= \frac{f(8 \frac{1}{60}) - f(8)}{8 \frac{1}{60} - 8} \\
&= \frac{\Delta f}{\Delta t}
\end{aligned}
$$

* The relationship between the two variables doesn't need to be velocity (time and distance):
  * E.g., change in pressure with respect to change in temperature
  * Any function $f$ with some input $x$, as $x$ goes from some value $a$ to some value $b$
  * Average rate of change of $f(x)$ with respect to $x$, as $x$ goes from $x = a$ to $x = b$: $\frac{\Delta f}{\Delta x} = \frac{f(b) - f(a)}{b - a}$

#### The derivate at a point

* What if we want the instantaneous rate of change?
  * The issue is picking some specific point $b$, as anything that is not $a$ will be an average, and $a$ itself will result in $\frac{0}{0}$
* Instead, we take the velocity as $b$ approaches $a$:
  * Instantaneous velocity at 8:00 = $\lim\limits_{b \to 8} \frac{f(b) - f(8)}{b - 8}$
  * This applies to instantaneous rate of change for any function $f$
  * This is the derivate of $f(x)$ at $x = a$ = instantaneous rate of change of $f(x)$ at $x = a$
    * $f^{\prime}(a) = \lim\limits_{b \to a} = \frac{f(b) - f(a)}{b - a}$

#### Tossing a pumpkin

* Imagine we throw a pumpkin off a building, and the height at time $t$ in seconds = $f(t) = 100 + 20t - 5t^2$ meters

* Instantaneous rate of change at $t = 1$:

  * $$
    \begin{aligned}
    f^{\prime}(1) &= \lim\limits_{b \to 1} \frac{f(b) - f(1)}{b - 1} \\\\
    
    \frac{f(b) - f(1)}{b - 1} &= \frac{(100 + 20b - 5b^2) - 115}{b - 1} \\
    &= \frac{-5b^2 + 20b - 15}{b - 1}
    \end{aligned}
    $$

  * We need to simplify this, as our numerator and denominator are both going to 0

  * $$
    \begin{aligned}
    \frac{f(b) - f(1)}{b - 1} &= \frac{-5b^2 + 20b - 15}{b - 1} \\
    &= \frac{-5(b^2 - 4b + 3)}{b - 1} \\
    &= \frac{-5(b - 1)(b - 3)}{b - 1} \\
    &= -5(b - 3)
    \end{aligned}
    $$

  * We then just plug in $b = 1$ (the value that we are approaching), so then we get $f^{\prime}(1) = \lim\limits_{b \to 1} -5(b - 3) = -5(1- 3) = 10$

    * This indicates that the instantaneous rate of change of 10m/s at $t = 1$

#### Negative derivative

* Sign of the derivative indicate the direction in which the function is changing:
  * Positive derivative indicates the function is increasing
  * Negative derivative indicates the function is decreasing
* A zero derivative indicates that the velocity (or rate of change) is not changing

### Geometric interpretation of the derivative

* Starting with some function $f(x)$, what is the tangent line?
  * It is firstly a line, and to understand a line it is enough to know a point on the line and the slope on the line: $y − y1 = m(x − x1)$
  * In the context of our function, the point is $(a, f(a))$, so the equation becomes: $y - f(a) = m(x - a)$
* The slope $m$ can be found using calculus: $m = f^{\prime}(a)$

#### Intuition for tangent lines

* As we zoom closer and closer to our function, our line will eventually look like a straight line
  * This line _is_ the tangent line
  * The tangent line and the function will have the same slope at this point
  * The tangent line will only be close to the function in a small area

#### Secant line defined

* Taking some function $f(x)$, we can choose two points, $x = a$ and $x = b$
* If we take the corresponding points in the function, $f(a)$ and $f(b)$, and draw a line between them, this is the _secant line_
* To get the slope, we need $\frac{rise}{run}$:
  * The rise is the vertical distance between $f(b)$ and $f(a)$: $\Delta y$
  * The run is the horizontal distance between $a$ and $b$: $\Delta x$

#### Slopes of secant lines

* $\Delta y = \Delta f = f(b) - f(a)$
* $\Delta x = b - a$
* The slope therefore is:

$$ m = \frac{f(b) - f(a)}{b - a}$$

* This is the same as the formula for $f^{\prime}(x)$

#### Limits of secant lines

* As $a$ and $b$ get closer and closer ($\Delta x$ gets smaller and smaller), the secant line becomes the tangent line
* In the limit as $b$ approaches $a$, the secant line approaches the tangent line
  * The slope of the secant line becomes the slope of the tangent line
* We now have 3 interpretations for the same object:

| Interpretation | Two points on the function  | $b \to a$ | One point on the function    |
| -------------- | --------------------------- | --------- | ---------------------------- |
| Geometric      | Slope of the secant line    | $b \to a$ | Slope of the tangent line    |
| Symbolic       | $\frac{f(b) - f(a)}{b - a}$ | $b \to a$ | $f^{\prime}(a)$              |
| Physical       | Average rate of change      | $b \to a$ | Instantaneous rate of change |

* We can estimate the slope of the tangent line often by eyeballing the rise and the run of the line, which then gives us a pretty good estimate of the derivate

#### The existence of tangent lines and derivatives

* If no tangent line exists at a point, then there is no derivative at that point
  * E.g., the absolute value function has a corner at the point $x = 0$, therefore there is no derivate at this point
  * E.g., the Heaviside function has a jump discontinuity at $x = 0$, therefore there is no derivate at this point
* If $f$ is not continuous at $x = a$, then $f$ is not differentiable at $a$
* The absolute value function:
  * If we cover up the left side of this function, we have a sequence of secant lines approaching 0 from the right that are equal to the function line itself
  * As such, $\lim\limits_{x \to 0^+} \frac{f(x) - f(0)}{x - 0}$ exists from the right, and the right sided derivative $f^{\prime}(0^+)$ also exists
    * Its value is the slope of the line, which is 1
  * If we similarly cover the right side of this function, we get $\lim\limits_{x \to 0^-} \frac{f(x) - f(0)}{x - 0}$ exists from the right, and the right sided derivative $f^{\prime}(0^-)$ also exists, which is in this case -1
  * While $f^{\prime}(0+)$ and $f^{\prime}(0-)$ both exist, $f^{\prime}(0+) \neq f^{\prime}(0-) = 1 \neq -1$
  * Therefore, the derivative does not exist at $x = 0$
* For the Heaviside function, when we approach from the left, as the function does not exist at $x = 0$, the tangent will become a vertical line as we approach 0
* If the tangent exists at a point, the derivate almost always exists, except in this case of vertical tangent lines
  * The slope of a vertical line is infinite, therefore we cannot have a derivative
* Tangent lines review:
  * If it is exists, the derivative of a function at a point is a number
  * If $f$ is continuous at $x = a$, it is not necessarily differentiable there (in the case of vertical lines)
  * A tangent can intersect $f$ at multiple points
  * A tangent line to the graph of $f$ at $(a, f(a))$ can cross the graph of $f$ at that point

### The derivative as a function

* Derivatives can be defined by their own functions
* We can learn these functions by plotting the slopes of the tangents to the function at different points
* The graph of $f^{\prime}$ is increasing as $f$ is getting more steep in a positive direction or getting less steep in a negative direction
* The graph of $f^{\prime}$ is increasing as $f$ is getting less steep in a positive direction or getting more steep in a negative direction
* The graph of $f^{\prime}$ is zero when $f$ is not increasing or decreasing (when the slope of the tangent is 0)

#### Graphing the derivative of $f$

* Every point on the graph of $f^{\prime}(x)$ corresponds to a single point $x = a$
* The value of $f^{\prime}(a)$ for any given $x = a$ is the slope of the tangent to $f$ at that point

#### Review points

* If $f$ is differentiable at $x = 3$, then $f^{\prime}(3)$ is a number representing the slope of the tangent line to that point
* If $f^{\prime}$ is a function, then $f^{\prime}$ is also a function

### Calculating derivatives: Finding formulas



