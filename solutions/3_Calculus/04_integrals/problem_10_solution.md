# Problem 10: Definite Integral and Checking the Result

## 1. The Original Problem

Before carrying out the exact calculation, estimate the possible range of values of the integral

$$
\int_0^2(x^2+1)\,dx,
$$

using

$$
1\le x^2+1\le5
$$

on $[0,2]$. Only then compute the integral exactly, compare the result with the earlier estimate, and explain what type of computational error such a check can detect.

---

## 2. What Are We Trying to Find?

1. A lower bound and an upper bound for $\int_{0}^{2} (x^2 + 1)\,dx$ derived **before** integrating, using the inequality $1 \le x^2 + 1 \le 5$ on $[0, 2]$.
2. The exact value of $\int_{0}^{2} (x^2 + 1)\,dx$ using the Fundamental Theorem of Calculus.
3. A comparison between the exact result and the predicted interval.
4. An explanation of what types of computational errors this bounding check can detect, as well as what limitations it has.

---

## 3. Before Calculating: What Idea Do We Need?

- **Comparison and Bounding Property of Definite Integrals:** If a continuous function $f$ satisfies $m \le f(x) \le M$ for all $x \in [a, b]$ with $a \le b$, then

$$
m(b - a) \le \int_{a}^{b} f(x)\,dx \le M(b - a).
$$

- **Geometric interpretation:** Because $f(x) = x^2 + 1 > 0$ on $[0, 2]$, the integral is the area under the parabola. That area must be at least the area of the inscribed rectangle of height $m$ and width $b - a$, and at most the area of the circumscribed rectangle of height $M$ and width $b - a$.
- **Strict inequality refinement:** If $f$ is continuous and not identically equal to $m$ or $M$ on $[a, b]$ with $a < b$, then the integral actually lies strictly between $m(b - a)$ and $M(b - a)$.
- **Fundamental Theorem of Calculus, Part 2:** To compute the exact integral, find an antiderivative $F$ of $x^2 + 1$ using the power rule and evaluate $F(2) - F(0)$.

---

## 4. Step-by-Step Solution

### Step 1: Verify the Given Bounds and Estimate the Integral

On the interval $[0, 2]$, we have $0 \le x \le 2$. Squaring preserves the inequalities for non-negative numbers, so $0 \le x^2 \le 4$. Adding $1$ throughout confirms the given inequality:

$$
1 \le x^2 + 1 \le 5 \quad \text{for all } x \in [0, 2].
$$

Integrate all three parts of this inequality from $x = 0$ to $x = 2$:

$$
\int_{0}^{2} 1\,dx \le \int_{0}^{2} (x^2 + 1)\,dx \le \int_{0}^{2} 5\,dx.
$$

Each constant integral equals the constant multiplied by the interval length $b - a = 2 - 0 = 2$:

$$
1 \cdot (2 - 0) \le \int_{0}^{2} (x^2 + 1)\,dx \le 5 \cdot (2 - 0).
$$

Therefore, before computing any antiderivative, we know with certainty that

$$
2 \le \int_{0}^{2} (x^2 + 1)\,dx \le 10.
$$

Moreover, because $x^2 + 1$ is strictly greater than $1$ for all $x \in (0, 2]$ and strictly less than $5$ for all $x \in [0, 2)$, the true value must actually satisfy the strict bounds

$$
2 < \int_{0}^{2} (x^2 + 1)\,dx < 10.
$$

### Step 2: Compute the Exact Integral

Using linearity and the power rule, an antiderivative of $f(x) = x^2 + 1$ is

$$
F(x) = \frac{x^3}{3} + x.
$$

Now apply the Fundamental Theorem of Calculus on $[0, 2]$:

$$
\begin{aligned}
\int_{0}^{2} (x^2 + 1)\,dx &= \left[\frac{x^3}{3} + x\right]_{0}^{2} \\
&= \left(\frac{2^3}{3} + 2\right) - \left(\frac{0^3}{3} + 0\right) \\
&= \left(\frac{8}{3} + 2\right) - 0 \\
&= \frac{8}{3} + \frac{6}{3} = \frac{14}{3}.
\end{aligned}
$$

In decimal form, $\frac{14}{3} \approx 4.667$.

### Step 3: Compare the Exact Value with the Estimate

Compare $\frac{14}{3}$ with our predicted range $[2, 10]$:

$$
2 < \frac{14}{3} \approx 4.667 < 10.
$$

The exact answer fits comfortably inside the interval $(2, 10)$. Notice also that the midpoint of $2$ and $10$ is $6$, which would be the area under the straight line connecting $(0, 1)$ to $(2, 5)$. Because $f(x) = x^2 + 1$ is concave up, its graph bends **below** that straight secant line, so the exact area $\frac{14}{3} \approx 4.667$ being smaller than $6$ is geometrically right on target.

### Step 4: What Types of Computational Errors Can This Check Detect?

Comparing an exact integral against a quick bound interval $[m(b-a), M(b-a)]$ acts as a mathematical "smoke detector."

**Errors it DOES catch reliably:**

- **Sign errors and reversed limits:** Computing $F(0) - F(2) = -\frac{14}{3}$ gives a negative number, immediately violating the lower bound $2$.
- **Missing or inverted power-rule coefficients:** Writing $\int x^2\,dx = 3x^3$ instead of $\frac{x^3}{3}$ yields $3(8) + 2 = 26 > 10$. Even forgetting to divide by $3$ altogether gives $x^3 + x \implies 8 + 2 = 10$, which hits the upper bound $10$ and violates the strict inequality $< 10$.
- **Wrong evaluation limits or dropped interval scaling:** Evaluating at $x = 1$ instead of $x = 2$ gives $\frac{1}{3} + 1 = \frac{4}{3} < 2$, which falls below the lower bound.
- **Order-of-magnitude arithmetic slips:** Miscomputing $2^3$ as $2^4 = 16$ or making a fraction-addition mistake that pushes the value outside $[2, 10]$.

**Errors it CANNOT catch on its own:**

- Because $[2, 10]$ is a relatively wide interval, smaller mistakes can still land inside it. For example, forgetting the $+1$ term altogether gives $\int_{0}^{2} x^2\,dx = \frac{8}{3} \approx 2.667$, which is still inside $(2, 10)$. Similarly, mistakenly differentiating $x^2 + 1$ to $2x$ and evaluating $2(2) - 2(0) = 4$ also lands inside $(2, 10)$.
- Therefore, bounding is a **necessary sanity check** that quickly exposes gross errors, but it should be paired with verifying the antiderivative by differentiation.

---

## 5. Final Answer & Conclusion

- Predicted range from $1 \le x^2 + 1 \le 5$ on $[0, 2]$:

$$
2 \le \int_{0}^{2} (x^2 + 1)\,dx \le 10
$$

with strict inequalities $2 < \int_{0}^{2} (x^2 + 1)\,dx < 10$.

- Exact value:

$$
\int_{0}^{2} (x^2 + 1)\,dx = \frac{14}{3} \approx 4.667.
$$

- **Comparison and diagnostic value:** Since $2 < \frac{14}{3} < 10$, the exact answer is fully consistent with the estimate. This check detects sign errors, reversed limits, order-of-magnitude arithmetic errors, and wrong scaling or power-rule factors that push the answer outside the permissible bounds, though fine-grained errors inside $(2, 10)$ require an antiderivative derivative check.

---

## 6. Quick Verification

1. **Derivative check of the antiderivative:**

$$
\frac{d}{dx}\left(\frac{x^3}{3} + x\right) = \frac{3x^2}{3} + 1 = x^2 + 1.
$$

The antiderivative is exact, and evaluating at the endpoints gives $F(2) = \frac{8}{3} + 2 = \frac{14}{3}$ and $F(0) = 0$.
2. **Tighter two-subinterval bounding check:** Split $[0, 2]$ into $[0, 1]$ and $[1, 2]$.
   - On $[0, 1]$, we have $1 \le x^2 + 1 \le 2$, giving area in $[1, 2]$.
   - On $[1, 2]$, we have $2 \le x^2 + 1 \le 5$, giving area in $[2, 5]$.
   - Adding these bounds gives the much tighter range

$$
3 \le \int_{0}^{2} (x^2 + 1)\,dx \le 7.
$$

   - Also, Simpson's Rule with $n = 2$ subintervals is exact for cubics and quadratics:

$$
\frac{2 - 0}{6}\Big(f(0) + 4f(1) + f(2)\Big) = \frac{1}{3}\Big(1 + 4(2) + 5\Big) = \frac{14}{3}.
$$

   Both checks confirm $\frac{14}{3}$ exactly!

---

## 7. Common Mistakes to Avoid

- **Forgetting to multiply the bounds by the interval length $b - a$:** Concluding $1 \le \int_{0}^{2} (x^2 + 1)\,dx \le 5$ instead of multiplying $1$ and $5$ by $2 - 0 = 2$ to obtain $[2, 10]$. Bounds on function **height** must be multiplied by the **width** of the interval to bound the **area**.
- **Forgetting the antiderivative of the constant $1$:** Writing $\int_{0}^{2} (x^2 + 1)\,dx = \left[\frac{x^3}{3} + 1\right]_{0}^{2} = \frac{8}{3}$, forgetting that the antiderivative of $1$ is $x$, not $1$.
- **Assuming an answer inside $[2, 10]$ is guaranteed to be right:** Falling into false confidence when a calculation gives, say, $4$ or $\frac{8}{3}$ — being inside the bounds is necessary for correctness, not sufficient.
- **Skipping the estimate until after computing:** The pedagogical value of estimating first is that it builds an independent expectation before algebraic tunnel vision sets in.

---

## 8. How I Would Explain This in Class

> "Before you trust a calculator or a page of algebra, fence the answer in! Imagine painting a wall whose height starts at $1$ meter and rises smoothly to $5$ meters over a width of $2$ meters. Without doing a single integral, you know you need more than $2$ square meters of paint and less than $10$ square meters. Then you do the exact calculus and get $\frac{14}{3}$, or about $4.67$ square meters — right inside the fence, and a little below the halfway mark of $6$ because the parabola swoops low at first. If your algebra had somehow handed you $-4.67$ or $26$, that fence would have caught the mistake in one second."
