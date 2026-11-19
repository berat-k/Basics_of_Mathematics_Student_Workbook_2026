# Problem 03: A Rational Function

## 1. The Original Problem

Analyze the domain, zeros, asymptotes, and monotonicity of

$$
f(x) = \frac{x + 1}{x - 2}.
$$

Finally, sketch a graph consistent with all the information obtained.

---

## 2. What Are We Trying to Find?

1. The domain $D_f$ of the rational function $f(x) = \frac{x + 1}{x - 2}$.
2. All zeros of $f$ and its $y$-intercept for sketching accuracy.
3. All vertical, horizontal, and oblique asymptotes, including the one-sided limits near vertical asymptotes and the side of approach near horizontal asymptotes.
4. The first derivative $f'(x)$, its sign on each interval of the domain, the intervals of monotonicity, and whether any extrema exist.
5. A complete, consistent sketch of the graph showing the asymptotes, intercepts, and monotonicity on both branches.

---

## 3. Before Calculating: What Idea Do We Need?

- **Domain of a rational function:** A fraction $\frac{P(x)}{Q(x)}$ is defined everywhere except where the denominator vanishes, $Q(x) = 0$.
- **Vertical asymptotes:** If $Q(a) = 0$ while $P(a) \ne 0$, then $x = a$ is a vertical asymptote, and one-sided limits determine whether the graph goes to $+\infty$ or $-\infty$ on each side.
- **Horizontal asymptotes:** When $\deg P = \deg Q$, the limits as $x \to \pm\infty$ equal the ratio of the leading coefficients. Because horizontal asymptotes exist at both infinities, there are no oblique asymptotes.
- **Quotient rule and separated intervals:** Even if $f'(x) < 0$ everywhere on $D_f$, monotonicity holds separately on each connected interval of the domain, never across the vertical asymptote.
- **Homographic transformation insight:** Rewriting $\frac{x + 1}{x - 2}$ as $1 + \frac{3}{x - 2}$ reveals that the graph is a shifted and stretched rectangular hyperbola centered at $(2, 1)$.

---

## 4. Step-by-Step Solution

### Step 1: Domain

The denominator vanishes when $x - 2 = 0$, that is, at $x = 2$. Hence the domain consists of two disjoint open intervals:

$$
D_f = \mathbb{R} \setminus \{2\} = (-\infty, 2) \cup (2, \infty).
$$

### Step 2: Zeros and Intercepts

A fraction equals zero if and only if its numerator is zero while its denominator is nonzero:

$$
f(x) = 0 \iff x + 1 = 0 \text{ and } x \ne 2 \iff x = -1.
$$

Thus, $f$ has a unique zero at $x = -1$, giving the $x$-intercept $(-1, 0)$.

For the sketch, we also compute the $y$-intercept at $x = 0 \in D_f$:

$$
f(0) = \frac{0 + 1}{0 - 2} = -\frac{1}{2},
$$

giving the point $\left(0, -\frac{1}{2}\right)$.

### Step 3: Helpful Rewrite and Asymptotes

Performing a quick division gives an especially transparent form of $f$:

$$
f(x) = \frac{(x - 2) + 3}{x - 2} = 1 + \frac{3}{x - 2}.
$$

**Vertical asymptote at $x = 2$:**
As $x \to 2$, the numerator approaches $2 + 1 = 3 > 0$, while the denominator $x - 2$ approaches $0$:

$$
\lim_{x \to 2^-} \frac{x + 1}{x - 2} = -\infty \quad \text{since } x - 2 \to 0^-,
$$

$$
\lim_{x \to 2^+} \frac{x + 1}{x - 2} = +\infty \quad \text{since } x - 2 \to 0^+.
$$

Therefore, the line $x = 2$ is a **vertical asymptote**.

**Horizontal asymptote:**
Dividing numerator and denominator by $x$ for $x \ne 0$, we obtain

$$
\lim_{x \to \pm\infty} \frac{x + 1}{x - 2} = \lim_{x \to \pm\infty} \frac{1 + \frac{1}{x}}{1 - \frac{2}{x}} = \frac{1 + 0}{1 - 0} = 1.
$$

Thus, the line $y = 1$ is a **horizontal asymptote** both as $x \to -\infty$ and as $x \to +\infty$. Using $f(x) - 1 = \frac{3}{x - 2}$, we can also see which side of the asymptote the graph approaches from:

- For $x < 2$, $f(x) - 1 < 0$, so the graph stays strictly below $y = 1$ and approaches $1$ from below as $x \to -\infty$.
- For $x > 2$, $f(x) - 1 > 0$, so the graph stays strictly above $y = 1$ and approaches $1$ from above as $x \to +\infty$.

Because finite horizontal asymptotes exist at both $-\infty$ and $+\infty$, there is **no oblique asymptote**.

### Step 4: Derivative, Monotonicity, and Extrema

Applying the quotient rule to $f(x) = \frac{x + 1}{x - 2}$ for $x \ne 2$ gives

$$
f'(x) = \frac{1 \cdot (x - 2) - (x + 1) \cdot 1}{(x - 2)^2} = \frac{x - 2 - x - 1}{(x - 2)^2} = \frac{-3}{(x - 2)^2}.
$$

Since $(x - 2)^2 > 0$ for all $x \ne 2$, we have

$$
f'(x) < 0 \quad \text{for every } x \in (-\infty, 2) \cup (2, \infty).
$$

| Interval / Point | $(-\infty, 2)$ | $x = 2$ | $(2, \infty)$ |
| :--- | :---: | :---: | :---: |
| Sign of $f'(x)$ | $-$ | Undefined | $-$ |
| Behavior of $f(x)$ | Strictly decreasing | Vertical asymptote | Strictly decreasing |

Therefore:

- $f$ is **strictly decreasing on $(-\infty, 2)$** and **strictly decreasing on $(2, \infty)$**, each considered separately.
- $f$ is **not** decreasing on the entire union $(-\infty, 2) \cup (2, \infty)$, because for example $0 < 3$ yet $f(0) = -\frac{1}{2} < 4 = f(3)$.
- There are **no critical points** in $D_f$ and **no local or global extrema**.

### Step 5: Sample Points and Sketch of the Graph

Computing a few convenient points helps anchor both branches accurately:

- Left branch: $f(-1) = 0$, $f(0) = -\frac{1}{2}$, $f(1) = -2$.
- Right branch: $f(3) = 4$, $f(5) = 2$.

```text
          y
          ^        : x = 2
       4 -|        :  *(3, 4)
          |        : /
       3 -|        :/
          |        :
       2 -|        :       *(5, 2)
          |        :      /
  -----1--+--------+-----*------------  y = 1 (horiz. asymptote)
          |        :
  ---*----+--------+------------------> x
    -1  0 |  1     2    3    4    5
     (-1,0)* (0,-0.5)
          |  \     :
      -2 -|   *(1,-2)
          |    |   :
      -3 -|    |   :
          |    v   :
```

On the sketch:

- The dashed vertical line $x = 2$ separates the two hyperbolic branches.
- The horizontal line $y = 1$ is approached from below as $x \to -\infty$ and from above as $x \to +\infty$.
- Both branches slope downward from left to right everywhere they are defined, passing through $(-1, 0)$, $(0, -\frac{1}{2})$, $(1, -2)$ on the left and $(3, 4)$, $(5, 2)$ on the right.

---

## 5. Final Answer & Conclusion

- **Domain:** $D_f = \mathbb{R} \setminus \{2\} = (-\infty, 2) \cup (2, \infty)$.
- **Zero:** $x = -1$, giving $x$-intercept $(-1, 0)$; $y$-intercept is $\left(0, -\frac{1}{2}\right)$.
- **Asymptotes:**
  - Vertical asymptote: $x = 2$, approaching $-\infty$ from the left and $+\infty$ from the right.
  - Horizontal asymptote: $y = 1$ as $x \to \pm\infty$.
  - No oblique asymptote.
- **Monotonicity:** Strictly decreasing on $(-\infty, 2)$ and strictly decreasing on $(2, \infty)$. No local or global extrema.

---

## 6. Quick Verification

1. **Alternative differentiation check:** Using the rewritten form $f(x) = 1 + 3(x - 2)^{-1}$, the chain rule yields

$$
f'(x) = 0 + 3(-1)(x - 2)^{-2} = -\frac{3}{(x - 2)^2},
$$

which matches the quotient rule calculation identically.
2. **Numerical monotonicity and symmetry check:** Notice that $f(2 + h) + f(2 - h) = \left(1 + \frac{3}{h}\right) + \left(1 - \frac{3}{h}\right) = 2$, confirming point symmetry about the intersection of the asymptotes $(2, 1)$. Indeed, $(1, -2)$ and $(3, 4)$ have midpoint $(2, 1)$, and $(-1, 0)$ and $(5, 2)$ also have midpoint $(2, 1)$.

---

## 7. Common Mistakes to Avoid

- **Claiming $f$ is decreasing on $\mathbb{R} \setminus \{2\}$ as a single set:** A function can decrease on $(-\infty, 2)$ and decrease on $(2, \infty)$ while jumping upward across the vertical asymptote $x = 2$, as seen from $f(1) = -2 < 4 = f(3)$.
- **Sign mistake in the quotient rule:** Reversing the numerator of the quotient rule to $(x + 1)\cdot 1 - 1\cdot(x - 2) = +3$ flips the sign of $f'(x)$ and makes you draw increasing branches instead of decreasing ones.
- **Assuming $y = 1$ means $f(x)$ cannot cross a horizontal asymptote in general:** Here $f(x) = 1 + \frac{3}{x - 2}$ indeed never equals $1$, so it never crosses $y = 1$, but you should always verify this algebraically rather than assuming it blindly for every rational function.
- **Forgetting to check both one-sided limits at $x = 2$:** Knowing $x = 2$ is a vertical asymptote is not enough to sketch the curve; you must determine the signs on the left and right to know which side shoots to $-\infty$ and which shoots to $+\infty$.

---

## 8. How I Would Explain This in Class

> "Before touching the derivative, rewrite $\frac{x + 1}{x - 2}$ as $1 + \frac{3}{x - 2}$. Suddenly the mystery vanishes: this is just the classic hyperbola $\frac{3}{x}$ shifted right by $2$ units and up by $1$ unit. That immediately explains why the crosshairs of asymptotes sit at $x = 2$ and $y = 1$, why both pieces slide downhill from left to right, and why the curve shoots down to $-\infty$ just before $2$ and drops in from $+\infty$ just after $2$."
