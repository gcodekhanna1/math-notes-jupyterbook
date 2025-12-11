---
title: Using u-Substitution to Solve Integrals
author: Gaurav Khanna, Ph.D.
date: 2025-12-08
---

Let's discuss solving calculus integrals using $u$-substitution. It's a process we can readily handle because it boils down to recognizing a pattern in an integral and applying defined rules. Here's the breakdown of our thinking when tackling these problems.

## Identifying the Candidate for $u$

The core idea behind $u$-substitution is to simplify an integral by transforming it into a form we can easily integrate. We look for a function within the integrand and its derivative (or a constant multiple of its derivative).

**Our Process:** We scan the integrand for a composition of functions—something like $f(g(x))$. The "inner" function, $g(x)$, is often a good candidate for $u$. We also look for parts that, when differentiated, will leave a piece of the remaining integral. Common candidates include:

- Expressions under radicals, such as $\sqrt{\phantom{x}}$, $\sqrt[3]{\phantom{x}}$, etc.
- Denominators of fractions
- Exponents
- Arguments of logarithmic or trigonometric functions

## Substitution

- **Define $u$:** Once we identify a candidate for $u$, we formally define it: $u = g(x)$.

- **Calculate $\frac{du}{dx}$:** We then calculate the derivative of $u$ with respect to $x$: $\frac{du}{dx} = g'(x)$.

- **Solve for $dx$:** We rearrange this equation to solve for $dx$ in terms of $du$: $dx = \frac{du}{g'(x)}$.

- **Substitute into the Integral:** This is where we replace parts of the original integral with $u$ and $du$. The goal is to rewrite the entire integral *entirely* in terms of $u$. This often involves simplifying the expression.

## Integration with Respect to $u$

- **Simplify and Integrate:** Now we have a new integral that (hopefully) is much simpler to solve. We apply standard integration rules to integrate with respect to $u$. This might involve using the power rule, trigonometric integrals, logarithmic integrals, etc.

- **Result in terms of $u$:** The result will be an expression involving $u$ (e.g., $\frac{1}{2}u^2 + C$).

## Back-Substitution

**Replace $u$ with $g(x)$:** Finally, we substitute the original expression for $u$ (i.e., $u = g(x)$) back into the result to express the answer in terms of the original variable $x$. This gives us the final antiderivative.

**Example:** Let's evaluate $\displaystyle\int 2x \cos(x^2) \, dx$.

1. **Pattern Recognition:** We see $\cos(x^2)$, which is a composition of functions (cosine and $x$ squared). The inner function $x^2$ is a good candidate for $u$, and conveniently, its derivative $2x$ appears in the integrand.

2. **Substitution:** Let $u = x^2$. Then $\frac{du}{dx} = 2x$, so $du = 2x \, dx$.

3. **Rewrite, Integrate, and Back-Substitute:**

$$
\begin{aligned}
    \int 2x \cos(x^2) \, dx & = \int \cos(u) \, du \\
    & = \sin(u) + C \\
    & = \sin(x^2) + C
\end{aligned}
$$

Therefore, the answer is $\sin(x^2) + C$.

## Limitations

- Choosing $u$ isn't always straightforward. Sometimes it takes trial and error to find a substitution that works. With practice, recognizing good candidates becomes more intuitive.

- More complex integrals may require multiple $u$-substitutions or other techniques (such as integration by parts or partial fractions).

- Not every integral can be solved with $u$-substitution; it works best when the integrand contains a function and its derivative.