# MIT Calculus 1A: Differentiation

## Unit 2: Differentiation

### Linear approximation

* When we have a function, $f(x)$ and an input $x$, we can estimate:

  * The value $f(x)$ for any $x$
  * The first derivative of the function
  * With the input and the first derivative, calculate the slope $m = f^{\prime}(x)$ of the tangent line

* Once we have the slope $m$ and the point $(x_1, f(x_1))$, we can use the point-slope formula to work out the tangent line

  * $f(x) - f(x_1) = f^{\prime}(x)(x - x_1) \to f(x) = f^{\prime}(x)(x - x_1) + f(x_1)$

* The formula for the derivative is $f^{\prime}(x) = \lim\limits_{\Delta x \to 0} \frac{\Delta f(x)}{\Delta x}$

  * We can of course think of:
    * $\Delta f(x) = f(x) - f(x_1)$
    * $\Delta x = x - x_1$

* Therefore, rearranging the derivative formula we get:

  * $$
    \begin{aligned}
    f^{\prime}(x) &= \frac{f(x) - f(x_1)}{x - x_1} \\
    f^{\prime}(x) \cdotp (x - x_1) &= f(x) - f(x_1)
    \end{aligned}
    $$

  * Which is the tangent line formula, assuming that the distance between $x$ and $x_1$ is really small

  * The implication is that the tangent line is a good approximation for the function for values close to the point of estimation, but becomes less reliable the further away we move from $x_1$

#### Concavity and linear approximation

* When we are using linear approximation with a straight line, there is no error in our estimates (as the tangent line will equal the curve)
* However, when we have a curved line, there will be some degree of error
  * This error will increase with the "curviness" of the line
  * The second derivative tells us how large this curviness/error is
* When the second derivative is negative, the graph is concave down
  * This means that the graph curves away from the tangent line _below_ the line, meaning that the linear estimation is an _overestimation_ of the actual value
  * In other words, it will be slightly higher than the actual value
* When the second derivative is positive, the graph is concave up
  * This means the graph curves away from the tangent line _above_ the line, meaning that the linear estimate is an _underestimation_ of the actual value

### The product rule

