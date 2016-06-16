# Gradient Descent

### Objectives
- Understand what Gradient Descent is (walk downhill)
- Use it to optimize the cost function for logistic regression
- Know how stochastic gradient descent works

Recall:
- for linear regression we solve the system of equations (normal equations)
\[B = (X^TX)^{-1}X^T\vec y\]
- it can be very hard to invert this matrix because it can be computationally impossible

### Gradient Descent
- mimimize f
- choose:
  - a starting point $\vec x$
  - learning rate $\alpha$
  - threshold $\epsilon$
- move in direction of $-\nabla f(\vec x)$
  - update (loop) $\vec x = \vec x -\alpha \nabla f(x)$
- if at any point $\frac{|f(\vec x) - f(\vec y)|}{|f(\vec x)|} < \epsilon$, then return $f(\vec x_{prev})$ as the min and $x_{prev}$ as the argmin
  - it has now been optimized

- make sure that the alpha level is the right size, if too small it'll take a long time, if too large it can overshoot the minimum

- **How do you handle local minimums?**
  - convex functions have unique global minima
  - if you don't have a convex function, often you you will just pick random starting points and compare the end results after a certain number of training trials

- when using a gradient descent algorithm, it's very important to normalize your features so it doesn't move in any one direction very quickly

## Stochastic Gradient Descent (SGD)
### This is what everyone uses!!!

- understand and implement
- be able to list features and benefits of SGD vs. regular 'batch' GD
- implement Newton's Method to maximize functions
- with regular GD you have to compute the sum of EVERY feature for every observation, this is memory and CPU constrained (everthing has to be in RAM)
- **SGD** - just use one observation at a time since by using the CLT, the Expected value of a single observation with be, on average, the same as the expected value of the mean sum of all the observations
- this is faster, will have a lot more variation to begin with
    - think of it like walking in a bunch of directions, rather than just one
    - will oscillate around a minima
- there is also the 'mini-batch' method which is taking small batches, rather than all like in regular GD, or 1, like SGD. This will take out a lot of variance
- SGD is will get to a decent solution quicker but it will bounce around a bit

### Newton's method
- designed for finding the root of a polynomial
- it's essentially a smart way to change the $\alpha$ (learning rate)
- the alpha level is set to 1 over the second derivative of f
- in higher dimensions, there is no one single second derivative but a matrix of second partial derivatives, this matrix is called the *Hessian*
