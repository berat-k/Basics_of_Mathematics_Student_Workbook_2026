# Problem 10: Complete Function Analysis

## 1. The Original Problem

Perform a complete analysis of

$$
f(x) = \frac{x}{x^2 + 1}.
$$

Include the domain, symmetry, zeros, limits, monotonicity, extrema, and convexity. Finally, produce a sketch based only on this information.

---

## 2. What Are We Trying to Find?

1. The domain of $f(x) = \frac{x}{x^2 + 1}$.
2. Parity and symmetry properties of the graph.
3. All zeros, intercepts, and intervals where $f(x)$ is positive or negative.
4. Limits at $\pm\infty$ and all asymptotes.
5. The first derivative $f'(x)$, critical points, intervals of monotonicity, and all local and global extrema.
6. The second derivative $f''(x)$, intervals of convexity and concavity, and all inflection points.
7. A unified summary table and a sketch constructed solely from these analytical results.

---

## 3. Before Calculating: What Idea Do We Need?

- **Complete function analysis workflow:** Organize the investigation in logical order: domain $\to$ symmetry and intercepts $\to$ limits and asymptotes $\to$ first derivative for monotonicity and extrema $\to$ second derivative for convexity and inflection points $\to$ synthesis into a graph.
- **Odd symmetry:** A function with a symmetric domain is odd if $f(-x) = -f(x)$ for all $x$. Its graph is symmetric with respect to the origin $(0, 0)$, which halves the geometric work and provides an immediate consistency check for extrema and inflection points.
- **Quotient rule and factoring:** When differentiating rational functions with a strictly positive denominator such as $(x^2 + 1)^2$ or $(x^2 + 1)^3$, the sign of the derivative depends solely on the numerator.
- **Convexity and concavity terminology:** A twice-differentiable function is strictly convex (concave up) where $f''(x) > 0$, strictly concave (concave down) where $f''(x) < 0$, and has an inflection point wherever $f''(x)$ changes sign.

---

## 4. Step-by-Step Solution

### Step 1: Domain

Since $x^2 \ge 0$ for every real number $x$, the denominator satisfies $x^2 + 1 \ge 1 > 0$ everywhere. Thus the denominator never vanishes, and the domain is

$$
D = \mathbb{R} = (-\infty, \infty).
$$

As a rational function with a non-vanishing denominator, $f$ is continuous and infinitely differentiable on all of $\mathbb{R}$.

### Step 2: Symmetry

The domain $\mathbb{R}$ is symmetric about $0$. Evaluating $f(-x)$ gives

$$
f(-x) = \frac{-x}{(-x)^2 + 1} = -\frac{x}{x^2 + 1} = -f(x).
$$

Therefore, $f$ is an **odd function**, and its graph is symmetric with respect to the origin $(0, 0)$.

### Step 3: Zeros, Intercepts, and Sign

Setting $f(x) = 0$ gives

$$
\frac{x}{x^2 + 1} = 0 \iff x = 0.
$$

Hence the unique zero and $y$-intercept coincide at the origin $(0, 0)$. Because $x^2 + 1 > 0$ for all $x$:

- $f(x) < 0$ for $x \in (-\infty, 0)$,
- $f(x) > 0$ for $x \in (0, \infty)$.

### Step 4: Limits and Asymptotes

Because $f$ is continuous on all of $\mathbb{R}$, it has **no vertical asymptotes**.

For the behavior as $x \to \pm\infty$, divide numerator and denominator by $x^2$:

$$
\lim_{x \to \pm\infty} \frac{x}{x^2 + 1} = \lim_{x \to \pm\infty} \frac{\frac{1}{x}}{1 + \frac{1}{x^2}} = \frac{0}{1 + 0} = 0.
$$

Therefore, the $x$-axis $y = 0$ is a **two-sided horizontal asymptote**. Combining this with the sign analysis from Step 3:

- As $x \to -\infty$, $f(x) \to 0^-$; the graph approaches $y = 0$ from below.
- As $x \to +\infty$, $f(x) \to 0^+$; the graph approaches $y = 0$ from above.

Because a finite horizontal asymptote exists in both directions, there are **no oblique asymptotes**.

### Step 5: First Derivative, Monotonicity, and Extrema

Apply the quotient rule to $f(x) = \frac{x}{x^2 + 1}$:

$$
f'(x) = \frac{1 \cdot (x^2 + 1) - x \cdot (2x)}{(x^2 + 1)^2} = \frac{1 - x^2}{(x^2 + 1)^2} = \frac{(1 - x)(1 + x)}{(x^2 + 1)^2}.
$$

Since $(x^2 + 1)^2 > 0$ for all $x \in \mathbb{R}$, the sign of $f'(x)$ matches the sign of $1 - x^2$. Solving $f'(x) = 0$ gives the critical points

$$
x = -1 \qquad \text{and} \qquad x = 1.
$$

Checking the sign of $1 - x^2$ on the three intervals:

- On $(-\infty, -1)$: $x^2 > 1 \implies f'(x) < 0$, so $f$ is strictly decreasing.
- On $(-1, 1)$: $x^2 < 1 \implies f'(x) > 0$, so $f$ is strictly increasing.
- On $(1, \infty)$: $x^2 > 1 \implies f'(x) < 0$, so $f$ is strictly decreasing.

By continuity, $f$ is strictly decreasing on $(-\infty, -1]$, strictly increasing on $[-1, 1]$, and strictly decreasing on $[1, \infty)$. Note also that the slope at the origin is $f'(0) = 1$, so the graph crosses the origin at a $45^\circ$ angle.

Evaluating $f$ at the critical points:

- At $x = -1$, $f'$ changes sign from $-$ to $+$, giving a **strict local minimum** with value $f(-1) = \frac{-1}{1 + 1} = -\frac{1}{2}$.
- At $x = 1$, $f'$ changes sign from $+$ to $-$, giving a **strict local maximum** with value $f(1) = \frac{1}{1 + 1} = \frac{1}{2}$.

Moreover, these are **global extrema**: on $(-\infty, -1]$, $f$ decreases from $0$ down to $-\frac{1}{2}$; on $[-1, 1]$, $f$ rises from $-\frac{1}{2}$ to $\frac{1}{2}$; and on $[1, \infty)$, $f$ falls from $\frac{1}{2}$ down toward $0$. Thus the range of $f$ is $\left[-\frac{1}{2}, \frac{1}{2}\right]$.

### Step 6: Second Derivative, Convexity, and Inflection Points

Differentiate $f'(x) = \frac{1 - x^2}{(x^2 + 1)^2}$ using the quotient rule and chain rule:

$$
\begin{aligned}
f''(x) &= \frac{(-2x)(x^2 + 1)^2 - (1 - x^2) \cdot 2(x^2 + 1)(2x)}{(x^2 + 1)^4} \\
&= \frac{2x(x^2 + 1)\bigl[-(x^2 + 1) - 2(1 - x^2)\bigr]}{(x^2 + 1)^4} \\
&= \frac{2x(x^2 - 3)}{(x^2 + 1)^3} = \frac{2x(x - \sqrt{3})(x + \sqrt{3})}{(x^2 + 1)^3}.
\end{aligned}
$$

Because $(x^2 + 1)^3 > 0$ for all $x$, the sign of $f''(x)$ matches the sign of $2x(x - \sqrt{3})(x + \sqrt{3})$. Solving $f''(x) = 0$ yields three candidate inflection points:

$$
x = -\sqrt{3}, \qquad x = 0, \qquad x = \sqrt{3}.
$$

Analyzing the sign of $f''(x)$ across the four resulting intervals:

- On $(-\infty, -\sqrt{3})$: $f''(x) < 0$, so $f$ is strictly concave (concave down).
- On $(-\sqrt{3}, 0)$: $f''(x) > 0$, so $f$ is strictly convex (concave up).
- On $(0, \sqrt{3})$: $f''(x) < 0$, so $f$ is strictly concave (concave down).
- On $(\sqrt{3}, \infty)$: $f''(x) > 0$, so $f$ is strictly convex (concave up).

Since $f''(x)$ changes sign at all three zeros, all three give **inflection points**:

$$
\left(-\sqrt{3}, -\frac{\sqrt{3}}{4}\right), \qquad (0, 0), \qquad \left(\sqrt{3}, \frac{\sqrt{3}}{4}\right).
$$

Numerically, $\sqrt{3} \approx 1.732$ and $\frac{\sqrt{3}}{4} \approx 0.433$. Notice how the outer inflection points $\pm\sqrt{3}$ occur just beyond the extrema $\pm 1$, allowing the curve to flatten out smoothly toward the horizontal asymptote $y = 0$.

### Step 7: Combined Analysis Table and Sketch

| Interval / Point | $f'(x)$ | $f''(x)$ | Behavior of $f(x)$ |
| :--- | :---: | :---: | :--- |
| $(-\infty, -\sqrt{3})$ | $-$ | $-$ | Decreasing, concave down; approaches $0^-$ as $x \to -\infty$ |
| $x = -\sqrt{3}$ | $-\frac{1}{8}$ | $0$ | Inflection point at $\left(-\sqrt{3}, -\frac{\sqrt{3}}{4}\right)$ |
| $(-\sqrt{3}, -1)$ | $-$ | $+$ | Decreasing, concave up |
| $x = -1$ | $0$ | $+\frac{1}{2}$ | Local and global minimum at $\left(-1, -\frac{1}{2}\right)$ |
| $(-1, 0)$ | $+$ | $+$ | Increasing, concave up |
| $x = 0$ | $+1$ | $0$ | Zero and inflection point at $(0, 0)$ |
| $(0, 1)$ | $+$ | $-$ | Increasing, concave down |
| $x = 1$ | $0$ | $-\frac{1}{2}$ | Local and global maximum at $\left(1, \frac{1}{2}\right)$ |
| $(1, \sqrt{3})$ | $-$ | $-$ | Decreasing, concave down |
| $x = \sqrt{3}$ | $-\frac{1}{8}$ | $0$ | Inflection point at $\left(\sqrt{3}, \frac{\sqrt{3}}{4}\right)$ |
| $(\sqrt{3}, \infty)$ | $-$ | $+$ | Decreasing, concave up; approaches $0^+$ as $x \to +\infty$ |

```text
                       y
                       ^
                       |        M (1, 1/2)
                 0.5 + |        * *
                       |      *     * I3 (sqrt(3), sqrt(3)/4)
                       |    *         * *
                       |  *               * * * *  ---> y = 0+
    -------------------+--+-----------------------------> x
    * * * *            | -1   0   1  1.73    3
            * *        |
  I1 (-sqrt(3),   *    | *
     -sqrt(3)/4)    *  |*
               -0.5 + * *
                    m (-1, -1/2)
```

---

## 5. Final Answer & Conclusion

- **Domain:** $D = \mathbb{R}$.
- **Symmetry:** Odd function, symmetric about the origin $(0, 0)$.
- **Zero / intercepts:** Unique zero and $y$-intercept at $(0, 0)$.
- **Asymptotes:** Horizontal asymptote $y = 0$ as $x \to \pm\infty$; no vertical or oblique asymptotes.
- **Monotonicity:** Strictly decreasing on $(-\infty, -1]$ and on $[1, \infty)$; strictly increasing on $[-1, 1]$.
- **Extrema:** Local and global minimum at $\left(-1, -\frac{1}{2}\right)$; local and global maximum at $\left(1, \frac{1}{2}\right)$.
- **Convexity:** Strictly concave (concave down) on $(-\infty, -\sqrt{3})$ and on $(0, \sqrt{3})$; strictly convex (concave up) on $(-\sqrt{3}, 0)$ and on $(\sqrt{3}, \infty)$.
- **Inflection points:** $\left(-\sqrt{3}, -\frac{\sqrt{3}}{4}\right)$, $(0, 0)$, and $\left(\sqrt{3}, \frac{\sqrt{3}}{4}\right)$.

---

## 6. Quick Verification

1. **Algebraic bound check via AM-GM / perfect square:** For every $x \in \mathbb{R}$, we have $(|x| - 1)^2 \ge 0$, which expands to $x^2 - 2|x| + 1 \ge 0$, or $2|x| \le x^2 + 1$. Dividing by $2(x^2 + 1) > 0$ yields

$$
|f(x)| = \frac{|x|}{x^2 + 1} \le \frac{1}{2},
$$

with equality if and only if $|x| = 1$. This independently confirms without calculus that $f(1) = \frac{1}{2}$ is the global maximum and $f(-1) = -\frac{1}{2}$ is the global minimum.

2. **Second-derivative test and symmetry check:**
   - $f''(1) = \frac{2(1)(1 - 3)}{(1 + 1)^3} = -\frac{4}{8} = -\frac{1}{2} < 0$, confirming a local maximum at $x = 1$.
   - $f''(-1) = \frac{2(-1)(1 - 3)}{(1 + 1)^3} = \frac{4}{8} = \frac{1}{2} > 0$, confirming a local minimum at $x = -1$.
   - Parity check: since $f$ is odd, $f'$ must be even and $f''$ must be odd. Indeed, $f'(-x) = f'(x)$ and $f''(-x) = -f''(x)$, and the extrema and inflection points occur in symmetric pairs about $(0, 0)$.

---

## 7. Common Mistakes to Avoid

- **Miscomputing $f''(x)$ by forgetting the chain rule factor $2x$:** When differentiating $(x^2 + 1)^2$, its derivative is $2(x^2 + 1) \cdot 2x = 4x(x^2 + 1)$, not $2(x^2 + 1)$. Dropping the $2x$ produces the wrong inflection points.
- **Missing the outer inflection points $\pm\sqrt{3}$:** Students often notice only the obvious inflection point at $(0, 0)$ by symmetry and draw the curve curving straight into the $x$-axis without switching concavity. In fact, a smooth curve approaching a horizontal asymptote from above after a peak must bend upward again, which forces the inflection point at $x = \sqrt{3}$.
- **Writing that $f$ is decreasing on $(-\infty, -1) \cup (1, \infty)$ as a single decreasing set:** Although $f'(x) < 0$ on both intervals, $f$ is not decreasing across their union; for example, $-2 < 2$ yet $f(-2) = -\frac{2}{5} < \frac{2}{5} = f(2)$. Always state separate intervals of monotonicity.
- **Searching for vertical asymptotes by setting $x^2 + 1 = 0$ over $\mathbb{R}$:** The equation $x^2 + 1 = 0$ has no real solutions, so there are no vertical asymptotes in the real plane.

---

## 8. How I Would Explain This in Class

> "This curve is one of the cleanest portraits in all of calculus because every single feature has a visible job. Odd symmetry tells you to understand the right half first and mirror it through the origin. Starting from $(0, 0)$ at a $45^\circ$ slope, the numerator $x$ initially pulls the curve upward until $x = 1$, where the curve reaches its peak height of one half. Past $x = 1$, the quadratic denominator $x^2 + 1$ takes over and drags the curve back toward the $x$-axis. And notice why calculus gives us that extra gift at $x = \sqrt{3}$: to glide softly down onto the horizontal asymptote $y = 0$ without crashing through it, the curve has to stop arching downward and start cupping upward — that exact landing transition is the inflection point."
