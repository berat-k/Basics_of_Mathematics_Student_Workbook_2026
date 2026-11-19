# Problem 05: Hyperbola and Asymptotes

## 1. The Original Problem

For

$$
\frac{x^2}{16} - \frac{y^2}{9} = 1,
$$

find the intercepts with the $x$-axis, the asymptotes, and make a sketch. Explain why the asymptotes describe the behavior of the curve far from the center.

---

## 2. What Are We Trying to Find?

We need to:
1. Find the coordinates of the intercepts of the hyperbola with the $x$-axis (the vertices).
2. Derive the linear equations of the two asymptotes.
3. Provide a clear structural sketch layout showing the vertices, branches, and asymptotes.
4. Explain mathematically why the asymptotes accurately describe the shape and trajectory of the curve far from the center ($|x| \to \infty$).

---

## 3. Before Calculating: What Idea Do We Need?

- **Canonical Form of a Horizontal Hyperbola:**

$$
\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1
$$

  where:
  - $a = \sqrt{16} = 4$ is the real (transverse) semiaxis.
  - $b = \sqrt{9} = 3$ is the imaginary (conjugate) semiaxis.
  - The positive sign on $x^2$ indicates that the hyperbola opens horizontally along the $x$-axis.
- **Asymptote Equations:**
  The asymptotes are obtained algebraically by replacing the constant $1$ on the right-hand side with $0$:

$$
\frac{x^2}{a^2} - \frac{y^2}{b^2} = 0 \implies \frac{y^2}{b^2} = \frac{x^2}{a^2} \implies y = \pm \frac{b}{a} x
$$

- **Asymptotic Behavior Far from the Center:**
  Solving for $y$ gives $y = \pm \frac{b}{a} x \sqrt{1 - \frac{a^2}{x^2}}$. As $|x| \to \infty$, the fraction $\frac{a^2}{x^2} \to 0$, which means $\sqrt{1 - \frac{a^2}{x^2}} \to 1$. Thus, the vertical distance between the hyperbola and its asymptotes approaches zero.

---

## 4. Step-by-Step Solution

### Step 1: Find the Intercepts with the $x$-Axis

To find where the curve crosses the $x$-axis, set $y = 0$:

$$
\frac{x^2}{16} - \frac{0^2}{9} = 1 \implies \frac{x^2}{16} = 1 \implies x^2 = 16 \implies x = \pm 4
$$

The intercepts with the $x$-axis (the real vertices of the hyperbola) are:

$$
V_1(-4, 0) \quad \text{and} \quad V_2(4, 0)
$$

*(Note: Setting $x = 0$ yields $-\frac{y^2}{9} = 1 \implies y^2 = -9$, which has no real solutions. The curve never crosses the $y$-axis.)*

---

### Step 2: Derive the Asymptote Equations

Set the right-hand side of $\frac{x^2}{16} - \frac{y^2}{9} = 1$ to $0$:

$$
\frac{x^2}{16} - \frac{y^2}{9} = 0
$$

Add $\frac{y^2}{9}$ to both sides:

$$
\frac{y^2}{9} = \frac{x^2}{16}
$$

Multiply by $9$:

$$
y^2 = \frac{9}{16} x^2
$$

Take the square root of both sides:

$$
y = \pm \sqrt{\frac{9}{16} x^2} = \pm \frac{3}{4} x
$$

The two asymptotes are the straight lines:

$$
y = \frac{3}{4} x \quad \text{and} \quad y = -\frac{3}{4} x
$$

---

### Step 3: Explain Why Asymptotes Describe the Curve Far from the Center

Solve the hyperbola equation explicitly for $y$:

$$
\frac{y^2}{9} = \frac{x^2}{16} - 1 = \frac{x^2}{16} \left( 1 - \frac{16}{x^2} \right)
$$

Take the square root for $|x| \ge 4$:

$$
y_{\text{curve}} = \pm \frac{3}{4} |x| \sqrt{1 - \frac{16}{x^2}} = \pm \frac{3}{4} x \sqrt{1 - \frac{16}{x^2}}
$$

Now examine what happens as we move far from the center ($|x| \to \infty$):
1. **Ratio Behavior:**
   As $|x| \to \infty$, the term $\frac{16}{x^2}$ becomes infinitesimally small:

$$
\lim_{|x| \to \infty} \frac{16}{x^2} = 0 \implies \lim_{|x| \to \infty} \sqrt{1 - \frac{16}{x^2}} = \sqrt{1 - 0} = 1
$$

   Therefore:

$$
\lim_{|x| \to \infty} \frac{y_{\text{curve}}}{y_{\text{asymptote}}} = \lim_{|x| \to \infty} \frac{\pm \frac{3}{4} x \sqrt{1 - \frac{16}{x^2}}}{\pm \frac{3}{4} x} = 1
$$

2. **Absolute Distance Behavior:**
   Using the Taylor/binomial approximation $\sqrt{1 - u} \approx 1 - \frac{1}{2}u$ for small $u = \frac{16}{x^2}$:

$$
y_{\text{curve}} \approx \pm \frac{3}{4} x \left( 1 - \frac{8}{x^2} \right) = \pm \frac{3}{4} x \mp \frac{6}{x}
$$

   The vertical separation between the hyperbola and its asymptote is:

$$
|y_{\text{curve}} - y_{\text{asymptote}}| \approx \frac{6}{|x|}
$$

   As $|x| \to \infty$, $\frac{6}{|x|} \to 0$.
   The distance between the hyperbola and the straight lines shrinks continuously toward zero. Far from the center, the constant $1$ in the equation becomes negligible compared to the massive values of $x^2/16$ and $y^2/9$, so the curve blends almost imperceptibly into its asymptotes.

---

### Step 4: Qualitative Sketch Layout

- Center at the origin $(0, 0)$.
- The central rectangular guide box has width $2a = 8$ (from $x = -4$ to $x = 4$) and height $2b = 6$ (from $y = -3$ to $y = 3$).
- The two asymptotes $y = \pm \frac{3}{4}x$ pass through the origin and the corners of this guide box.
- The **right branch** has vertex at $(4, 0)$ and curves to the right, sandwiched between the asymptotes.
- The **left branch** has vertex at $(-4, 0)$ and curves to the left, sandwiched between the asymptotes.
- The region between $x = -4$ and $x = 4$ is completely empty.

---

## 5. Final Answer & Conclusion

- **Intercepts with the $x$-axis:**

$$
(-4, 0) \quad \text{and} \quad (4, 0)
$$

- **Asymptote Equations:**

$$
y = \frac{3}{4} x \quad \text{and} \quad y = -\frac{3}{4} x \quad \left(y = \pm \frac{3}{4}x\right)
$$

- **Asymptotic Explanation:** Far from the center ($|x| \to \infty$), the constant $1$ is dwarfed by the quadratic terms, so $\frac{x^2}{16} - \frac{y^2}{9} = 1$ behaves indistinguishably from $\frac{x^2}{16} - \frac{y^2}{9} = 0$, meaning the curve gets arbitrarily close to the straight lines $y = \pm \frac{3}{4}x$.

---

## 6. Quick Verification

Calculate a point far out on the hyperbola, say $x = 20$:
- On the hyperbola:

$$
\frac{20^2}{16} - \frac{y^2}{9} = 1 \implies \frac{400}{16} - \frac{y^2}{9} = 1 \implies 25 - \frac{y^2}{9} = 1 \implies \frac{y^2}{9} = 24 \implies y = \sqrt{216} \approx 14.6969
$$

- On the asymptote $y = \frac{3}{4}x$:

$$
y_{\text{asymptote}} = \frac{3}{4}(20) = 15
$$

The vertical difference is only $15 - 14.6969 \approx 0.303$.
Notice that our approximation formula gave $|y - y_{\text{asym}}| \approx \frac{6}{|x|} = \frac{6}{20} = 0.300$, matching the true behavior with outstanding precision.

---

## 7. Common Mistakes to Avoid

1. **Inverting the Slope of the Asymptotes:**
   Writing $y = \pm \frac{4}{3} x$ instead of $\pm \frac{3}{4} x$. Remember that $y^2/9 = x^2/16 \implies y^2 = (9/16)x^2 \implies y = \pm (3/4)x$. The numerator of the slope is always $\sqrt{\text{denominator under } y^2}$.
2. **Claiming the Hyperbola Touches the Asymptotes:**
   Assuming the curve intersects its asymptotes at some finite point. The hyperbola approaches the asymptotes indefinitely, but never touches them at any finite real coordinates because $\frac{16}{x^2} > 0$ for all real $x$.
3. **Looking for $y$-Intercepts:**
   Attempting to solve for $y$-intercepts when the minus sign is in front of $y^2$. A horizontal hyperbola has no real $y$-intercepts.

---

## 8. How I Would Explain This in Class

> "When $x$ is small, the number 1 on the right-hand side matters a lot—it creates the gap between $-4$ and $4$ where the curve cannot go. But when $x$ reaches 1,000, $x^2/16$ is over 60,000, and that tiny number 1 becomes like a single grain of sand on a truckload of gravel. Ignoring that negligible 1 turns the equation into $\frac{x^2}{16} - \frac{y^2}{9} = 0$, which is just the two straight X-shaped lines $y = \pm \frac{3}{4}x$ that guide the curve all the way out to infinity."

