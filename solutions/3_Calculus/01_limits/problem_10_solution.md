# Problem 10: Continuity of a Piecewise Function

## 1. The Original Problem

Find $a$ so that

$$
f(x)=\begin{cases}ax+1,&x<2,\\x^2-1,&x\ge2\end{cases}
$$

is continuous at $x=2$. Explicitly compare the left-hand limit, right-hand limit, and function value.

---

## 2. What Are We Trying to Find?

We need to:
1. Determine the value of the parameter $a \in \mathbb{R}$ that makes the piecewise function $f(x)$ continuous at the transition point $x = 2$.
2. State the formal three-part definition of continuity at a point.
3. Compute the **left-hand limit** $\lim_{x \to 2^-} f(x)$ using the left branch, with $x < 2$.
4. Compute the **right-hand limit** $\lim_{x \to 2^+} f(x)$ using the right branch, with $x \ge 2$.
5. Evaluate the **function value** $f(2)$ from the defined branch, where $x \ge 2$.
6. Equate all three quantities to set up and solve the resulting algebraic equation for $a$.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Three-Part Definition of Continuity at a Point:**
  A function $f(x)$ is continuous at a point $x = c$ if and only if three conditions are simultaneously satisfied:
  1. $f(c)$ is defined (the point exists in the domain).
  2. The two-sided limit $\lim_{x \to c} f(x)$ exists, which requires:

$$
\lim_{x \to c^-} f(x) = \lim_{x \to c^+} f(x)
$$

  3. The limit equals the function value: $\lim_{x \to c} f(x) = f(c)$.
  Compactly, continuity at $x = 2$ means: $\lim_{x \to 2^-} f(x) = \lim_{x \to 2^+} f(x) = f(2)$.
- **Piecewise Branches:**
  - For $x < 2$, the function is governed by the linear formula $f(x) = ax + 1$.
  - For $x \ge 2$, the function is governed by the quadratic formula $f(x) = x^2 - 1$.
  Because polynomials are continuous everywhere on $\mathbb{R}$, each branch is continuous on its own open interval. The only place where continuity can fail is at the seam (transition point) $x = 2$.
- **Welding the Seam:**
  To prevent a jump discontinuity (a tear in the graph), the two pieces must meet seamlessly at $x = 2$. That requires the value coming from the left line, $2a + 1$, to equal the value of the right parabola, $2^2 - 1 = 3$.

---

## 4. Step-by-Step Solution

### Step 1: Evaluate the Function Value $f(2)$

The piecewise definition specifies:

$$
f(x) = \begin{cases} ax + 1 & \text{for } x < 2 \\\\ x^2 - 1 & \text{for } x \ge 2 \end{cases}
$$

Because $x = 2$ satisfies the condition $x \ge 2$, we evaluate $f(2)$ using the second branch:

$$
f(2) = (2)^2 - 1 = 4 - 1 = 3
$$

Thus, the function is well-defined at $x = 2$, and its value is $3$.

---

### Step 2: Compute the Right-Hand Limit as $x \to 2^+$

For $x > 2$, the function is defined by $f(x) = x^2 - 1$.
Because $x^2 - 1$ is a polynomial, it is continuous, and its limit as $x \to 2^+$ can be evaluated by direct substitution:

$$
\lim_{x \to 2^+} f(x) = \lim_{x \to 2^+} (x^2 - 1) = 2^2 - 1 = 3
$$

Notice that the right-hand limit automatically agrees with the function value:

$$
\lim_{x \to 2^+} f(x) = f(2) = 3
$$

This means $f$ is already right-continuous at $x = 2$ for every choice of $a$.

---

### Step 3: Compute the Left-Hand Limit as $x \to 2^-$

For $x < 2$, the function is defined by $f(x) = ax + 1$.
Because $ax + 1$ is a polynomial (linear function), its limit as $x \to 2^-$ is found by direct substitution:

$$
\lim_{x \to 2^-} f(x) = \lim_{x \to 2^-} (ax + 1) = a(2) + 1 = 2a + 1
$$

The left-hand limit depends directly on the parameter $a$.

---

### Step 4: Enforce the Continuity Condition

For $f(x)$ to be continuous at $x = 2$, the left-hand limit, the right-hand limit, and the function value must all be equal:

$$
\lim_{x \to 2^-} f(x) = \lim_{x \to 2^+} f(x) = f(2)
$$

Substitute the expressions obtained in Steps 1, 2, and 3:

$$
2a + 1 = 3
$$

Solve this linear equation for $a$:

$$
2a = 3 - 1
$$

$$
2a = 2 \implies a = 1
$$

---

### Step 5: Verification of the Resulting Function

When $a = 1$, the function becomes:

$$
f(x) = \begin{cases} x + 1 & \text{for } x < 2 \\\\ x^2 - 1 & \text{for } x \ge 2 \end{cases}
$$

Let us check the three quantities explicitly:
1. **Left-hand limit:** $\lim_{x \to 2^-} f(x) = \lim_{x \to 2^-} (x + 1) = 2 + 1 = 3$
2. **Right-hand limit:** $\lim_{x \to 2^+} f(x) = \lim_{x \to 2^+} (x^2 - 1) = 2^2 - 1 = 3$
3. **Function value:** $f(2) = 2^2 - 1 = 3$

Because:

$$
\lim_{x \to 2^-} f(x) = \lim_{x \to 2^+} f(x) = f(2) = 3
$$

the two branches weld together smoothly at the coordinates $(2, 3)$ with **no jump, hole, or gap**.
The function $f(x)$ is continuous at $x = 2$.

---

## 5. Final Answer & Conclusion

The required value of the parameter is:

$$
a = 1
$$

### Three-Way Comparison at $x = 2$:

| Quantity | Formula Used | Value for General $a$ | Value for $a = 1$ |
| :--- | :--- | :--- | :--- |
| **Left-Hand Limit as $x \to 2^-$** | $a(2) + 1$ | $2a + 1$ | **$3$** |
| **Right-Hand Limit as $x \to 2^+$** | $2^2 - 1$ | $3$ | **$3$** |
| **Function Value $f(2)$** | $2^2 - 1$ | $3$ | **$3$** |

Because all three quantities equal $3$ when $a = 1$, the function is continuous at $x = 2$.

---

## 6. Quick Verification

1. **Check for a Different Value, such as $a = 2$:**
   If $a = 2$:
   - Left-hand limit: $\lim_{x \to 2^-} (2x + 1) = 2(2) + 1 = 5$.
   - Right-hand limit: $3$.
   - Function value: $3$.
   Here the left branch approaches $5$ while the right branch starts at $3$. There is a vertical jump of $\Delta y = |5 - 3| = 2$. The graph has a **jump discontinuity**. Only $a = 1$ closes the jump.

2. **Differentiability Check (Bonus Insight):**
   Even though the function is continuous at $x = 2$ when $a = 1$, is it differentiable?
   - Left derivative: $\frac{d}{dx}(x + 1) = 1$.
   - Right derivative: $\frac{d}{dx}(x^2 - 1) = 2x \implies \text{at } x = 2, 2(2) = 4$.
   Because $1 \ne 4$, the function has a sharp corner (cusp) at $(2, 3)$. It is continuous, but not differentiable. This reinforces that continuity requires only heights to match, not slopes!

---

## 7. Common Mistakes to Avoid

1. **Equating Only Left and Right Limits Without Checking $f(2)$:**
   If the problem had defined $f(2) = 10$ as a third separate condition, equating the left and right limits would give $a = 1$, but the function would still have a removable discontinuity at $x = 2$. Always check all three quantities!
2. **Using the Wrong Branch for $f(2)$:**
   Substituting $x = 2$ into $ax + 1$ to find $f(2)$. The branch $ax + 1$ is strictly for $x < 2$. The value $f(2)$ belongs strictly to the branch with the $\ge$ sign, which is $x^2 - 1$.
3. **Algebraic Slip in Solving $2a + 1 = 3$:**
   Subtracting $1$ gives $2a = 2 \implies a = 1$.

---

## 8. How I Would Explain This in Class

> "Imagine you are building a bridge out of two pieces:
> From the right side, where $x \ge 2$, a concrete curved ramp with equation $y = x^2 - 1$ is already built. When it reaches the joint at $x = 2$, its elevation is $2^2 - 1 = 3$.
> From the left side, where $x < 2$, you are laying down a straight wooden plank with equation $y = ax + 1$. The number $a$ is your control knob: it changes the tilt of the plank.
> When the plank reaches the joint at $x = 2$, its height is $a(2) + 1 = 2a + 1$.
> If you want cars to drive across without crashing into a wall or dropping into an abyss, the two road sections must meet at the exact same elevation: $2a + 1 = 3 \implies 2a = 2 \implies a = 1$.
> By setting your knob to $a = 1$, the plank seamlessly touches the concrete ramp at height 3. That smooth connection is what continuity is all about!"
