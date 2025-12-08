---
title: Fourier's Proof - e is Irrational
author: Gaurav Khanna, Ph.D.
date: 2025-12-06
---

```{figure} j_fourier_1.jpg
:name: fig-joseph-fourier-portrait
:width: 50%
:align: center

A portrait of Jean-Baptiste Joseph Fourier (1768-1830) who did this clever proof.
```

# Setting up the proof

We will show that $e$ is an irrational number using proof by contradiction. That is, we will assume that it is a rational number and show that this assumption creates a consequence that is contradictory to our assumption.

We first start with the definitions of $e^x$ and $e$:

$$
e^x = \sum_{k = 0}^{\infty} \frac{x^k}{k!}
$$

If $x = 1$, then:

$$
\begin{split}
e = \sum_{k = 0}^{\infty} \frac{1}{k!} & = 1 + \frac{1}{1!} + \frac{1}{2!} + \frac{1}{3!} + \ldots + \frac{1}{n!} \\
& \quad + \frac{1}{(n+1)!} + \frac{1}{(n+2)!} + \ldots
\end{split}
$$

Recall that for proof by contradiction, we first assume a condition and then show that it leads to a problem (i.e., the contradiction).  We now assume that $e$ is a rational number. By the definition of rational numbers, we can express $e$ as the ratio of two integers $p, q > 0$ and $q \neq 0$. Note that we can make the assumption that $p,q$ are positive without loss of generality since $e>0$. So expressing $e$ in this manner, we get:

$$
\begin{aligned}
e & = \frac{p}{q} \\
& = 1 + \frac{1}{1!} + \frac{1}{2!} + \frac{1}{3!} + \ldots + \frac{1}{n!} + \frac{1}{(n+1)!} + \frac{1}{(n+2)!} + \ldots
\end{aligned}
$$ (eq:proof_e_irrational_1)

Since $q$ is an integer, we will reach a point in the sum where $n = q$. Let's demarcate this point and simply re-write the above expression as two different partial sums:

$$
\frac{p}{q} = \underbrace{ 1 + \frac{1}{1!} + \frac{1}{2!} + \frac{1}{3!} + \ldots + \frac{1}{q!}}_{q^{th}\ \text{partial sum}} \hspace{1em} +\hspace{1em} \underbrace{ \frac{1}{(q+1)!} + \frac{1}{(q+2)!} + \ldots }_{\Delta}
$$ (eq:proof_e_irrational_2)

Writing the expression in this manner will help us as we go along in the proof as we shall see shortly.

To complete this proof, we will show that the difference between $\displaystyle \frac{p}{q}$ and the $q^{th}$ partial sum forces a situation that is contradictory. We proceed by looking at this difference:

$$
\begin{aligned}
e - q^{th}\ \text{partial sum} & = \Delta \\
\frac{p}{q} - \sum_{k = 0}^{q} \frac{1}{k!}  & = \sum_{k = q + 1}^{\infty} \frac{1}{k!}
\end{aligned}
$$ (eq:proof_e_irrational_3)

We first note that the term on the left-hand side is greater than zero. Why? Because each successive term in Equation {eq}`eq:proof_e_irrational_1` is positive and decreasing in magnitude. The more partial sums we have, the closer we get to the limiting value of $e$ from below. If we take any partial sum — i.e., the $q^{th}$ partial sum — we know that it will only approximate $e$ but will be smaller than $e$. Therefore:

$$
\Delta = \frac{p}{q} - \sum_{k = 0}^{q} \frac{1}{k!} > 0
$$ (eq:proof_e_irrational_4)

We now multiply both sides of Equation {eq}`eq:proof_e_irrational_2` by $q!$ to get:

$$
\begin{aligned}
q! \left( \frac{p}{q} - \sum_{k = 0}^{q} \frac{1}{k!} \right) & = q! (\Delta) \\
\left[ (q - 1)!\ p \right] - q! \left( 1 + \frac{1}{1!} + \frac{1}{2!} + \frac{1}{3!} + \ldots + \frac{1}{q!} \right) & = q! (\Delta)
\end{aligned}
$$ (eq:proof_e_irrational_5)

Note that both the expressions on the left-hand side are integers. Let's look at them one at a time. Since $p, q$ are integers, then $(q-1)! p \in \mathbb{Z}$. The second term on the left-hand side when expanded looks like:

$$
q! + \frac{q!}{1!} + \frac{q!}{2!} + \frac{q!}{3!} + \ldots + \frac{q!}{q!}
$$ (eq:proof_e_irrational_6)

This expression contains the sum of ratios of factorials where the numerator was greater than the denominator until the last term (when the numerator and denominator were equal). Therefore $q!$ is divisible by all factorials up to and including $q!$, so each ratio is an integer. For example, for some arbitrary value of $q$ we may have a term in Equation {eq}`eq:proof_e_irrational_6` that looks as follows:

$$
\begin{aligned}
\frac{q!}{3!} & = \frac{q (q-1)(q-2) \ldots (q - (q-4))(3)(2)(1)}{3!} \\
& = q (q-1)(q-2) \ldots (q - (q-4)) \\
& = q (q-1)(q-2) \ldots (4)
\end{aligned}
$$

Every term in the above multiplication is an integer, and so is the result. Since every ratio in Equation {eq}`eq:proof_e_irrational_6` is an integer, the sum of the terms in Equation {eq}`eq:proof_e_irrational_6` is also an integer.

Given that both terms on the left-hand side of Equation {eq}`eq:proof_e_irrational_5` are integers, their difference is also an integer. Therefore $q! (\Delta) \in \mathbb{Z}$ has to also be an integer.

The last step in the proof is to evaluate $q! (\Delta)$ and verify that it indeed is an integer. Using $\Delta$ from Equation {eq}`eq:proof_e_irrational_2`, we express $q! (\Delta)$ as:

$$
\begin{aligned}
q! (\Delta) & = q!\ \sum_{k = q + 1}^{\infty} \frac{1}{k!} \\
& = q! \left( \frac{1}{(q+1)!} + \frac{1}{(q+2)!} + \frac{1}{(q+3)!} + \ldots \right) \\
& = \frac{q!}{(q+1)!} + \frac{q!}{(q+2)!} + \frac{q!}{(q+3)!} + \ldots \\
& = \frac{1}{(q+1)} + \frac{1}{(q+2)(q+1)} + \frac{1}{(q+3)(q+2)(q+1)} + \ldots
\end{aligned}
$$ (eq:proof_e_irrational_7)

This is not an easy sum to calculate. However, we can make life easier by noting that the right-hand side can be expressed as an inequality:

$$
\begin{split}
\frac{1}{(q+1)} + \frac{1}{(q+2)(q+1)} + \frac{1}{(q+3)(q+2)(q+1)} + \ldots \\
< \frac{1}{(q+1)} + \frac{1}{(q+1)^2} + \frac{1}{(q+1)^3} + \ldots
\end{split}
$$ (eq:proof_e_irrational_8)

The right-hand side of the above equation is an infinite geometric series. Since the ratio of successive terms is $\displaystyle r = \frac{1}{q+1}$ and $|r| < 1$, we know that this sum converges. Therefore, we can use the geometric series formula:

$$
\sum_{k = 1}^{\infty} ar^k  =  \frac{a r}{1 - r}
$$

with $a = 1$, $\displaystyle r = \frac{1}{q+1}$ to get:

$$
\begin{aligned}
\frac{1}{(q+1)} + \frac{1}{(q+1)^2} + \frac{1}{(q+1)^3} + \ldots & = \sum_{k = 1}^{\infty}  \left( \frac{1}{q+1} \right)^k \\
& = \frac{ \frac{1}{q+1} } {1 - \frac{1}{q+1}  }  \\
& = \frac{1}{ (q+1) -1 } \\
& = \frac{1}{q}
\end{aligned}
$$

Up to this point, the only assumption we have made about $q$ is that $q \neq 0$ as required by the definition of rational numbers. However, we also know that $q \neq 1$; if that were so, then we would have the trivial case of $e = \frac{p}{q} = p$ which we know to be false since $e$ is not an integer! So $q > 1$ which means $\displaystyle \frac{1}{q} < 1$. Therefore:

$$
q! (\Delta) = \frac{1}{(q+1)} + \frac{1}{(q+2)(q+1)} + \ldots < \frac{1}{q} < 1
$$

And now we get to the contradiction: our assumption about $e$ being a rational number has led to $0 < q! (\Delta) < 1$. But $q! (\Delta)$ is required to be an integer in order to satisfy Equation {eq}`eq:proof_e_irrational_5`. It cannot be the case that $q! (\Delta)$ is an integer but fall somewhere between zero and one. So our assumption that $e$ is rational cannot be valid.

**Therefore, $e$ is an irrational number.**

---

## Alternative Approach

There is another way to examine the last part of the proof, i.e., the evaluation of $q! (\Delta)$. We can make some determination of what integers $q$ *can not* be. As mentioned above, we know that $q \neq 1$ since that would mean $\displaystyle e = \frac{p}{q} = p$ which is an integer... and $e$ is certainly not an integer! We also know that $q \neq 2$, since $\displaystyle e = \frac{p}{q} = \frac{p}{2}$ and any integer divided by two leaves a decimal value of exactly 0 or 0.5. Again, this does not characterize $e$.

Therefore $q > 2$, which means that the first term in $q! (\Delta)$ is less than $\displaystyle \frac{1}{3}$, the second term is less than $\displaystyle \frac{1}{3} \cdot \frac{1}{3}$, etc. Looking at $q! (\Delta)$ in more detail:

$$
q! (\Delta) = \underbrace{ \frac{1}{(q+1)}}_{< \frac{1}{3}} + \underbrace{ \frac{1}{(q+1)(q+2)} }_{< \frac{1}{3} \cdot \frac{1}{3}} + \underbrace{ \frac{1}{(q+1)(q+2)(q+3)}}_{< \frac{1}{3} \cdot \frac{1}{3} \cdot \frac{1}{3}} + \ldots
$$

This implies that $q! (\Delta)$ is less than the geometric series where the ratio between terms is $\displaystyle \frac{1}{3}$; that is:

$$
q! (\Delta) < \frac{1}{3} + \frac{1}{3} \cdot \frac{1}{3} + \frac{1}{3} \cdot \frac{1}{3} \cdot \frac{1}{3} + \ldots
$$

We know the geometric series on the right-hand side very well. As we did in the first version of this proof, we calculate the right-hand side using the geometric series formula with $a = 1$, $\displaystyle r = \frac{1}{3}$. This yields:

$$
\dfrac{ \frac{1}{3} }{1 - \frac{1}{3}} = \frac{1}{2}
$$

Therefore:
$$
q! (\Delta) < \frac{1}{2}
$$

If $\displaystyle 0 < q! (\Delta) < \frac{1}{2}$, then it is not possible for $q! (\Delta) \in \mathbb{Z}$ as required. This is a contradiction and our original assumption of $e$ being a rational number is incorrect. **Therefore, $e$ is an irrational number.**

---

## Intuitive Examination

In Equation {eq}`eq:proof_e_irrational_7`, we avoided having to calculate the value of $q! (\Delta)$ explicitly by reconfiguring the series into an inequality relative to a series we knew how to calculate. That is, the general expression for the remaining partial sum is:

$$
q!\ \sum_{k = q+1}^{\infty} \frac{1}{k!}
$$

is not an easy one to calculate by hand. Although I have not derived this rigorously, using *Mathematica*, we derive the general expression for this sum is:

$$
q!\ \sum_{k = q+1}^{\infty} \frac{1}{k!} = q! \left(e-\frac{e\ \Gamma (q+1,1)}{\Gamma (q+1)}\right)
$$ (eq:proof_e_irrational_9)

where $\Gamma(a,z)$ is the incomplete Gamma function. Evaluating this function for any value of $q \geq 3$ gives a value that is positive but less than 1.

Since this is such an important (and famous) discovery, it's worth an intuitive examination of why this proof works. During the proof, when we got to Equation {eq}`eq:proof_e_irrational_5`, we were dealing with any arbitrary value of $q!$. Let's do a concrete example by picking a value of $q$ to see how this proof works. Starting with the Taylor series expansion for $e$ and assuming $e$ is rational, we have:

$$
e = \frac{p}{q} = 1 + \frac{1}{1!} + \frac{1}{2!} + \frac{1}{3!} + \frac{1}{4!} + \frac{1}{5!} + \frac{1}{6!} + \frac{1}{7!} + \ldots
$$

Let's pick $q = 5$ and multiply both sides of the above expression by $5!$ to get:

$$
5!\ \frac{p}{5} = 5! \left( 1 + \frac{1}{1!} + \frac{1}{2!} + \frac{1}{3!} + \frac{1}{4!} + \frac{1}{5!} \right) + 5! \left(\frac{1}{6!} + \frac{1}{7!} + \ldots \right)
$$

which is just:

$$
4! (p) = 5! + \frac{5!}{1!} + \frac{5!}{2!} + \frac{5!}{3!} + \frac{5!}{4!} + \frac{5!}{5!} + 5! \left(\frac{1}{6!} + \frac{1}{7!} + \ldots \right)
$$ (eq:proof_e_irrational_10)

We have written things deliberately this way so that when we take the difference between the left-hand side and the partial sum up to $\displaystyle \frac{5!}{5!}$, we get:

$$
\begin{aligned}
4! (p) - \left(5! + \frac{5!}{1!} + \frac{5!}{2!} + \frac{5!}{3!} + \frac{5!}{4!} +  \frac{5!}{5!} \right) & = 5! \left(\frac{1}{6!} + \frac{1}{7!} + \ldots \right) \\
24 (p) - \left(120 + 120 + 60 + 20 + 5 + 1 \right) & = 5! \left(\frac{1}{6!} + \frac{1}{7!} + \ldots \right) \\
24 (p) - 326 & = 5! \left(\frac{1}{6!} + \frac{1}{7!} + \ldots \right) \\
24 (p) - 326 & \approx 0.193
\end{aligned}
$$

Although we don't know what $p$ is, we know $p \in \mathbb{Z}$ because $p$ was the numerator of a rational number and, by definition, it has to be an integer. Therefore $24 (p)$ is also an integer and so is 326 (obviously!).

Note that the partial sums remaining on the right-hand side sum to 0.193, which is not an integer. In fact, the larger the value of $q!$ we pick to be the multiplier in Equation {eq}`eq:proof_e_irrational_10`, the smaller the partial sum on the right-hand side will be (and will always be $< 1$). So it is easy to see the contradiction here — you cannot have one side of an equation be an integer and the other be a non-integer.

As we saw in Equation {eq}`eq:proof_e_irrational_9`, any $q \geq 3$ will give a positive value that is less than 1.
