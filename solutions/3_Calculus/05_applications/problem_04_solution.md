# Problem 04: Area Between Curves

## 1. The Original Problem

Find the area of the region bounded by the graphs

$$
y = x
$$

and

$$
y = x^2.
$$

First find the intersection points and justify which function is greater on the relevant interval.

---

## 2. What Are We Trying to Find?

1. All points of intersection of the line $y = x$ and the parabola $y = x^2$, which determine the integration limits.
2. A mathematical proof of which function lies above the other on the interval between those intersection points.
3. The exact area of the enclosed region, computed via a definite integral.

---

## 3. Before Calculating: What Idea Do We Need?

- **Intersection points set the boundaries:** Two curves $y = f(x)$ and $y = g(x)$ enclose a region between consecutive solutions of $f(x) = g(x)$.
- **Upper minus lower:** If $f(x) \ge g(x)$ for all $x \in [a, b]$, then the area of the region bounded by their graphs on $[a, b]$ is

$$
A = \int_a^b \left(f(x) - g(x)\right)\,dx.
$$

- **Why order matters:** Area is always non-negative. Integrating $\text{lower} - \text{upper}$ produces the negative of the true area, and if the curves cross inside the interval, integrating without checking the sign causes positive and negative signed areas to cancel out.
- **Factored difference for sign proof:** Writing $f(x) - g(x)$ in factored form proves rigorously which curve is higher across the entire open interval, rather than relying only on a sketch.

---

## 4. Step-by-Step Solution

### Step 1: Find the intersection points

Set the two equations equal to each other:

$$
x = x^2.
$$

Bring all terms to one side and factor:

$$
x^2 - x = 0 \implies x(x - 1) = 0.
$$

Hence the solutions are:

$$
x = 0 \qquad \text{and} \qquad x = 1.
$$

Substituting these $x$-values into $y = x$ gives the corresponding $y$-coordinates:
- for $x = 0$: $y = 0$, giving the intersection point $(0, 0)$;
- for $x = 1$: $y = 1$, giving the intersection point $(1, 1)$.

Thus, the bounded region lies over the interval $[0, 1]$.

### Step 2: Justify which function is greater on $[0, 1]$

Consider the difference between the linear function and the quadratic function:

$$
d(x) = x - x^2 = x(1 - x).
$$

For every $x$ in the open interval $(0, 1)$:
- the first factor satisfies $x > 0$,
- the second factor satisfies $1 - x > 0$.

Since the product of two positive numbers is positive, we have:

$$
x - x^2 = x(1 - x) > 0 \implies x > x^2 \qquad \text{for all } x \in (0, 1).
$$

At the endpoints $x = 0$ and $x = 1$, the two functions are equal, with $x = x^2$. Therefore, throughout the closed interval $[0, 1]$:

$$
x \ge x^2.
$$

That is, the line $y = x$ is the **upper boundary** and the parabola $y = x^2$ is the **lower boundary** of the region.

For intuition, squaring a number strictly between $0$ and $1$ makes it smaller, for example at $x = \frac{1}{2}$ we have $x = \frac{1}{2} = 0.5$ whereas $x^2 = \frac{1}{4} = 0.25$.

A sketch of the enclosed region confirms this geometry:

```text
y
1.0 +                   * (1, 1)
    |                *  *
    |             *    *
0.5 +          *  /// *    <-- upper curve: y = x
    |       *  ///// *
    |    *  ////// *       <-- lower curve: y = x^2
0.0 +---*--------+------> x
       0        1
```

### Step 3: Set up and evaluate the area integral

Using $\text{upper} - \text{lower} = x - x^2$ on $[0, 1]$, the area $A$ is:

$$
A = \int_0^1 \left(x - x^2\right)\,dx.
$$

Find an antiderivative using the power rule:

$$
F(x) = \frac{x^2}{2} - \frac{x^3}{3}.
$$

Apply the Fundamental Theorem of Calculus:

$$
\begin{aligned}
A &= \left[\frac{x^2}{2} - \frac{x^3}{3}\right]_0^1 \\
  &= \left(\frac{1^2}{2} - \frac{1^3}{3}\right) - \left(\frac{0^2}{2} - \frac{0^3}{3}\right) \\
  &= \frac{1}{2} - \frac{1}{3} \\
  &= \frac{3 - 2}{6} = \frac{1}{6}.
\end{aligned}
$$

---

## 5. Final Answer & Conclusion

- **Intersection points:** $(0, 0)$ and $(1, 1)$, so the region lies over $[0, 1]$.
- **Ordering on $[0, 1]$:** $x \ge x^2$, because $x - x^2 = x(1 - x) \ge 0$ for all $x \in [0, 1]$, with strict inequality on $(0, 1)$.
- **Area of the bounded region:**

$$
A = \frac{1}{6}.
$$

---

## 6. Quick Verification

1. **Differentiation check on the antiderivative:**
   For $F(x) = \frac{x^2}{2} - \frac{x^3}{3}$, we differentiate:

$$
F'(x) = \frac{2x}{2} - \frac{3x^2}{3} = x - x^2,
$$

   which matches the integrand exactly.

2. **Geometric subtraction check:**
   The area under the line $y = x$ on $[0, 1]$ is a right triangle with base $1$ and height $1$, so its area is $\frac{1}{2} \cdot 1 \cdot 1 = \frac{1}{2}$. The area under the parabola $y = x^2$ on $[0, 1]$ is $\int_0^1 x^2\,dx = \frac{1}{3}$. Subtracting the smaller area from the larger gives $\frac{1}{2} - \frac{1}{3} = \frac{1}{6}$.

3. **Geometric bounding and Archimedes' check:**
   The vertical thickness $d(x) = x - x^2 = \frac{1}{4} - \left(x - \frac{1}{2}\right)^2$ reaches its maximum of $\frac{1}{4}$ at $x = \frac{1}{2}$. Thus:
   - the region has area strictly less than $1 \times \frac{1}{4} = \frac{1}{4} = 0.25$;
   - the triangle inscribed inside the region with vertices $(0, 0)$, $(1, 1)$, and $\left(\frac{1}{2}, \frac{1}{4}\right)$ has area $\frac{1}{2}\left|1 \cdot \frac{1}{4} - 1 \cdot \frac{1}{2}\right| = \frac{1}{8} = 0.125$.
   Indeed $\frac{1}{8} < \frac{1}{6} < \frac{1}{4}$. Even better, by Archimedes' quadrature of the parabola, the parabolic segment has area $\frac{4}{3}$ times that inscribed triangle: $\frac{4}{3} \cdot \frac{1}{8} = \frac{1}{6}$.

---

## 7. Common Mistakes to Avoid

- **Assuming $x^2 > x$ everywhere:** For $x > 1$, squaring makes numbers larger, so $x^2 > x$. Many students carry that habit into $(0, 1)$ by mistake, write $\int_0^1 (x^2 - x)\,dx$, and end up with a negative area $-\frac{1}{6}$.
- **Dividing $x = x^2$ by $x$ and losing the root $x = 0$:** Canceling $x$ from both sides of $x = x^2$ leaves only $x = 1$ and hides the intersection at $x = 0$. Always move all terms to one side and factor instead.
- **Integrating without finding the intersection points first:** Guessing limits like $[0, 2]$ integrates beyond $(1, 1)$, where the curves have already crossed and are no longer enclosing the intended finite region.
- **Substituting a single test point without stating continuity or absence of other roots:** Checking $x = \frac{1}{2}$ works *only* because we already proved $x = 0$ and $x = 1$ are the *only* intersection points, so the continuous function $x - x^2$ cannot change sign inside $(0, 1)$.

---

## 8. How I Would Explain This in Class

> "Students are often surprised that the straight line $y = x$ sits above the parabola $y = x^2$ between $0$ and $1$, because we are so used to squares growing faster than linear terms. Just remember what happens when you square half a dollar or half a pie: one half times one half is only one quarter! So between $0$ and $1$, the line forms the roof and the parabola forms the floor. Once you know the two intersection corners $(0, 0)$ and $(1, 1)$ and verify that roof minus floor is $x - x^2$, the definite integral slices the crescent into vertical strips and adds them up cleanly to $\frac{1}{6}$."
