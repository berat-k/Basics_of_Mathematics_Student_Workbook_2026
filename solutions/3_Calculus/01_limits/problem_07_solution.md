# Problem 07: Limit at a Point and Canceling a Factor

## 1. The Original Problem

Compute

$$
\lim_{x\to3}\frac{x^2-4x+3}{x-3}.
$$

Explain why the value of the function at $x=3$ is not needed to compute the limit.

---

## 2. What Are We Trying to Find?

We need to:
1. Evaluate the limit of the rational function $f(x) = \frac{x^2 - 4x + 3}{x - 3}$ as $x$ approaches the finite point $x_0 = 3$.
2. Recognize that direct substitution of $x = 3$ yields the indeterminate form $\left[\frac{0}{0}\right]$ and undefined division by zero.
3. Factor the quadratic numerator $x^2 - 4x + 3$ into linear factors, revealing the common factor $(x - 3)$.
4. Cancel the common factor for all $x \ne 3$ to simplify the expression to a well-behaved linear function.
5. Provide a rigorous conceptual explanation of why the actual value of the function at the target point (i.e., whether $f(3)$ is defined or what it equals) is completely irrelevant to the existence and value of the limit.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Indeterminate Form $\left[\frac{0}{0}\right]$ at a Finite Point:**
  When evaluating $\lim_{x \to c} \frac{P(x)}{Q(x)}$, if substituting $x = c$ produces $P(c) = 0$ and $Q(c) = 0$, the Factor Theorem states that $(x - c)$ is an algebraic factor of both polynomials.
- **The Definition of a Limit at a Point where $x \to c$:**
  By the formal $(\varepsilon, \delta)$-definition, $\lim_{x \to c} f(x) = L$ means: $\forall \varepsilon > 0, \ \exists \delta > 0 \ \text{such that} \ 0 < |x - c| < \delta \implies |f(x) - L| < \varepsilon$.
  The condition $0 < |x - c|$ explicitly means $x \ne c$.
  The limit describes what the function approaches as $x$ gets arbitrarily close to $c$, **never** what happens when $x$ actually lands on $c$.
- **Canceling Non-Zero Quantities:**
  Because the limit definition guarantees $x \ne 3$, the factor $(x - 3)$ is strictly non-zero. Dividing a non-zero quantity by itself is identically $1$: $\frac{x - 3}{x - 3} = 1$ for all $x \ne 3$.
  This allows us to replace $f(x)$ by the simpler function $g(x) = x - 1$ everywhere inside the punctured neighborhood.

---

## 4. Step-by-Step Solution

### Step 1: Attempt Direct Substitution and Identify the Indeterminate Form

Consider the function:

$$
f(x) = \frac{x^2 - 4x + 3}{x - 3}
$$

Substitute $x = 3$ into the numerator and denominator:
- Numerator: $3^2 - 4(3) + 3 = 9 - 12 + 3 = 0$
- Denominator: $3 - 3 = 0$

This yields the indeterminate form:

$$
\left[\frac{0}{0}\right]
$$

Division by zero is undefined in arithmetic. The function $f(x)$ is **not defined** at $x = 3$; its natural domain is:

$$
\text{Dom}(f) = \mathbb{R} \setminus \{3\} = (-\infty, 3) \cup (3, \infty).
$$

---

### Step 2: Factor the Numerator

We find the roots of the quadratic numerator $x^2 - 4x + 3 = 0$:
Using the quadratic formula or factoring by inspection:
- Sum of roots: $r_1 + r_2 = 4$
- Product of roots: $r_1 r_2 = 3$

The roots are $r_1 = 3$ and $r_2 = 1$. Therefore:

$$
x^2 - 4x + 3 = (x - 3)(x - 1)
$$

Rewrite the function:

$$
f(x) = \frac{(x - 3)(x - 1)}{x - 3}
$$

---

### Step 3: Cancel the Common Factor for $x \ne 3$

Because the limit as $x \to 3$ considers points $x$ in a punctured neighborhood $0 < |x - 3| < \delta$, we are guaranteed that $x \ne 3$.
When $x \ne 3$, the term $x - 3 \ne 0$. Therefore, we can divide out $(x - 3)$:

$$
\frac{(x - 3)(x - 1)}{x - 3} = x - 1 \quad \text{for all } x \ne 3
$$

Thus, for all $x \ne 3$, the function $f(x)$ is algebraically identical to the linear function:

$$
g(x) = x - 1
$$

---

### Step 4: Evaluate the Limit

Because $f(x) = g(x)$ for all $x \ne 3$, their limits as $x \to 3$ must be identical:

$$
\lim_{x\to3}\frac{x^2-4x+3}{x-3} = \lim_{x\to3}(x - 1)
$$

The function $g(x) = x - 1$ is a polynomial, and polynomials are continuous everywhere. Therefore, we can evaluate its limit by direct substitution:

$$
\lim_{x\to3}(x - 1) = 3 - 1 = 2
$$

---

### Step 5: Why the Value $f(3)$ is Not Needed

Why does computing $\lim_{x \to 3} f(x)$ not require, or even care about, the value $f(3)$?

1. **The Punctured Neighborhood Condition, with $x \ne c$:**
   The definition of a limit strictly inspects the behavior of $f(x)$ for $x$ close to $c$, but explicitly excludes $x = c$ via the inequality $0 < |x - c|$. What happens at the single isolated point $x = c$ has zero mathematical effect on the limit.
2. **$f(3)$ Does Not Even Exist:**
   In our original function $f(x) = \frac{x^2-4x+3}{x-3}$, $f(3)$ is undefined because the denominator is zero. If the limit required $f(3)$ to exist, no limit could ever be computed for any rational function at a hole or vertical asymptote!
3. **Geometric Picture — The Removable Singularity (Hole in the Graph):**
   - The graph of $g(x) = x - 1$ is a solid straight line passing through $(3, 2)$.
   - The graph of $f(x) = \frac{x^2-4x+3}{x-3}$ is that exact same straight line, but with a single microscopic point removed: a **hole** (removable discontinuity) at $(3, 2)$.
   - If an ant walks along the curve from the left, where $x \to 3^-$, or from the right, where $x \to 3^+$, its elevation steadily approaches height $y = 2$. Even if there is a hole in the floor at $x = 3$, both paths aim toward the exact same coordinates $(3, 2)$. That target coordinate is the limit!
4. **Altering the Point Value Does Not Change the Limit:**
   If we defined an artificial function $h(x) = \frac{x^2-4x+3}{x-3}$ for $x \ne 3$ and $h(3) = 999$, the value at $x = 3$ is now $h(3) = 999$. Yet the limit $\lim_{x \to 3} h(x)$ is **still $2$**, because the limit only asks what $h(x)$ approaches as $x \to 3$, completely ignoring the isolated spike at $x = 3$.

---

## 5. Final Answer & Conclusion

The limit is:

$$
\lim_{x\to3}\frac{x^2-4x+3}{x-3} = 2
$$

### Summary of Key Principles:
- Substituting $x = 3$ gave the indeterminate form $\left[\frac{0}{0}\right]$.
- Factoring revealed $x^2 - 4x + 3 = (x - 3)(x - 1)$.
- Because $x \ne 3$ in the definition of a limit, canceling $(x - 3)$ is completely valid.
- The limit of the reduced expression $x - 1$ as $x \to 3$ is $3 - 1 = 2$.
- The value $f(3)$ is not needed because a limit is a local property of the surrounding neighborhood, completely independent of the value (or existence) of the function at the target point itself.

---

## 6. Quick Verification

1. **Numerical Table Approaching $x = 3$ from Both Sides:**
   - From the left, with $x < 3$:
     - $x = 2.9 \implies f(2.9) = \frac{(2.9)^2 - 4(2.9) + 3}{2.9 - 3} = \frac{8.41 - 11.6 + 3}{-0.1} = \frac{-0.19}{-0.1} = 1.9$
     - $x = 2.99 \implies f(2.99) = \frac{-0.0199}{-0.01} = 1.99$
     - $x = 2.999 \implies f(2.999) = 1.999$
   - From the right, with $x > 3$:
     - $x = 3.1 \implies f(3.1) = \frac{(3.1)^2 - 4(3.1) + 3}{3.1 - 3} = \frac{9.61 - 12.4 + 3}{0.1} = \frac{0.21}{0.1} = 2.1$
     - $x = 3.01 \implies f(3.01) = \frac{0.0201}{0.01} = 2.01$
     - $x = 3.001 \implies f(3.001) = 2.001$
   Both sides converge symmetrically and directly to $2.000$.

2. **L'Hôpital's Rule Verification (for reference):**
   Since the limit is in $\left[\frac{0}{0}\right]$ form and both numerator and denominator are differentiable:
   $\lim_{x \to 3} \frac{\frac{d}{dx}(x^2 - 4x + 3)}{\frac{d}{dx}(x - 3)} = \lim_{x \to 3} \frac{2x - 4}{1} = 2(3) - 4 = 2$.
   Matches our algebraic factoring result perfectly.

---

## 7. Common Mistakes to Avoid

1. **Concluding the Limit Does Not Exist Because $f(3)$ is Undefined:**
   Confusing the value of a function at a point with its limit at that point. A function does not need to be defined at $x = c$ for its limit to exist.
2. **Canceling $(x - 3)$ Without Stating $x \ne 3$:**
   In algebra, canceling a variable factor requires ensuring that the factor is not zero. In calculus, this is justified by the definition of the limit, which explicitly stipulates $x \ne 3$.
3. **Stopping at $0/0$:**
   Treating $0/0$ as a final answer. $0/0$ is not a number; it is an algebraic signal that a common factor $(x - c)$ is waiting to be uncovered and canceled.

---

## 8. How I Would Explain This in Class

> "Imagine two roads on opposite sides of a canyon leading toward a bridge. As you drive from the left, you are aiming right at height 2. As you drive from the right, you are aiming right at height 2.
> But right in the middle of the bridge, at coordinate $x = 3$, there is a tiny pothole—a single missing plank of wood!
> Does the pothole change where the two roads were heading? Not at all! The roads clearly meet at height 2. That shared destination is what we call the **limit**.
> A limit doesn't care whether the bridge plank is missing, or painted gold, or replaced with a giant boulder: it only cares where the road was taking you as you approached it!"

