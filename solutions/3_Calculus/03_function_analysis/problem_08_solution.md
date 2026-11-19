# Problem 08: The Second Derivative

## 1. The Original Problem

For

$$
f(x) = x^4 - 4x^2
$$

find the local extrema, intervals of convexity and concavity, and inflection points. Sketch the graph and mark all the identified features on it.

---

## 2. What Are We Trying to Find?

1. The domain, symmetry, zeros, and end behavior of $f(x) = x^4 - 4x^2$ to anchor the graph.
2. The first derivative $f'(x)$, all critical points, the monotonicity intervals, and all local and global extrema.
3. The second derivative $f''(x)$, its zeros, and its sign chart to determine all intervals of convexity (concave upward) and concavity (concave downward).
4. All inflection points $(x, f(x))$ where the curvature changes sign.
5. A clearly labeled sketch of the graph showing the zeros, local extrema, inflection points, and regions of convexity and concavity.

---

## 3. Before Calculating: What Idea Do We Need?

- **Terminology for curvature:** Throughout function analysis, a twice-differentiable function $f$ is called **convex** (also called **concave upward**) on an interval where $f''(x) > 0$, meaning its graph bends upward like a cup and lies above its tangent lines. It is called **concave** (also called **concave downward**) on an interval where $f''(x) < 0$, meaning its graph bends downward like an arch and lies below its tangent lines.
- **Inflection point criterion:** A point $(c, f(c))$ on the graph of a smooth function is an inflection point if and only if $f''(x)$ **changes sign** across $x = c$. Merely having $f''(c) = 0$ is necessary, not sufficient.
- **Second Derivative Test for Extrema:** At a critical point $c$ with $f'(c) = 0$, having $f''(c) > 0$ implies a local minimum and having $f''(c) < 0$ implies a local maximum.
- **Even symmetry:** Since only even powers of $x$ appear in $f(x) = x^4 - 4x^2$, we have $f(-x) = f(x)$, so extrema, zeros, and inflection points must occur in symmetric pairs across the $y$-axis.

---

## 4. Step-by-Step Solution

### Step 1: Domain, Symmetry, Zeros, and End Behavior

Since $f(x) = x^4 - 4x^2$ is a polynomial, $D_f = \mathbb{R}$. Because

$$
f(-x) = (-x)^4 - 4(-x)^2 = x^4 - 4x^2 = f(x),
$$

$f$ is an **even function**, symmetric with respect to the $y$-axis.

Factoring gives the zeros immediately:

$$
f(x) = x^2(x^2 - 4) = x^2(x - 2)(x + 2) = 0 \iff x = -2, \quad x = 0, \quad \text{or} \quad x = 2.
$$

For end behavior, the leading term $x^4$ dominates as $|x| \to \infty$:

$$
\lim_{x \to -\infty} (x^4 - 4x^2) = +\infty, \qquad \lim_{x \to +\infty} (x^4 - 4x^2) = +\infty.
$$

### Step 2: First Derivative, Monotonicity, and Local Extrema

Differentiating $f(x) = x^4 - 4x^2$ gives

$$
f'(x) = 4x^3 - 8x = 4x(x^2 - 2) = 4x(x - \sqrt{2})(x + \sqrt{2}).
$$

Setting $f'(x) = 0$ produces three critical numbers:

$$
x = -\sqrt{2} \approx -1.414, \qquad x = 0, \qquad x = \sqrt{2} \approx 1.414.
$$

Testing the sign of $f'(x) = 4x(x^2 - 2)$ on the four resulting open intervals:

- On $(-\infty, -\sqrt{2})$, test $x = -2$: $f'(-2) = 4(-2)(2) = -16 < 0$.
- On $(-\sqrt{2}, 0)$, test $x = -1$: $f'(-1) = 4(-1)(-1) = 4 > 0$.
- On $(0, \sqrt{2})$, test $x = 1$: $f'(1) = 4(1)(-1) = -4 < 0$.
- On $(\sqrt{2}, \infty)$, test $x = 2$: $f'(2) = 4(2)(2) = 16 > 0$.

| Interval / Point | $(-\infty, -\sqrt{2})$ | $-\sqrt{2}$ | $(-\sqrt{2}, 0)$ | $0$ | $(0, \sqrt{2})$ | $\sqrt{2}$ | $(\sqrt{2}, \infty)$ |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of $f'(x)$ | $-$ | $0$ | $+$ | $0$ | $-$ | $0$ | $+$ |
| Behavior of $f(x)$ | Decreasing | Min: $-4$ | Increasing | Max: $0$ | Decreasing | Min: $-4$ | Increasing |

Evaluating $f$ at each critical point:

$$
f(-\sqrt{2}) = (-\sqrt{2})^4 - 4(-\sqrt{2})^2 = 4 - 8 = -4,
$$

$$
f(0) = 0^4 - 4(0)^2 = 0,
$$

$$
f(\sqrt{2}) = (\sqrt{2})^4 - 4(\sqrt{2})^2 = 4 - 8 = -4.
$$

Therefore:

- **Local (and global) minima:** $(-\sqrt{2}, -4)$ and $(\sqrt{2}, -4)$, with value $-4$.
- **Local maximum:** $(0, 0)$, with value $0$, which is not global since $f(x) \to +\infty$ as $x \to \pm\infty$.

### Step 3: Second Derivative, Convexity, Concavity, and Inflection Points

Differentiating $f'(x) = 4x^3 - 8x$ gives

$$
f''(x) = 12x^2 - 8 = 4(3x^2 - 2).
$$

Setting $f''(x) = 0$ yields the candidate inflection points:

$$
3x^2 - 2 = 0 \iff x^2 = \frac{2}{3} \iff x = \pm\sqrt{\frac{2}{3}} = \pm\frac{\sqrt{6}}{3} \approx \pm 0.8165.
$$

Since $f''(x) = 12x^2 - 8$ is an upward-opening parabola with roots $-\frac{\sqrt{6}}{3}$ and $\frac{\sqrt{6}}{3}$, it is positive outside the roots and negative between them. Checking with test points $x = -1, 0, 1$:

- On $\left(-\infty, -\frac{\sqrt{6}}{3}\right)$: $f''(-1) = 12 - 8 = 4 > 0$.
- On $\left(-\frac{\sqrt{6}}{3}, \frac{\sqrt{6}}{3}\right)$: $f''(0) = -8 < 0$.
- On $\left(\frac{\sqrt{6}}{3}, \infty\right)$: $f''(1) = 12 - 8 = 4 > 0$.

| Interval / Point | $\left(-\infty, -\frac{\sqrt{6}}{3}\right)$ | $-\frac{\sqrt{6}}{3}$ | $\left(-\frac{\sqrt{6}}{3}, \frac{\sqrt{6}}{3}\right)$ | $\frac{\sqrt{6}}{3}$ | $\left(\frac{\sqrt{6}}{3}, \infty\right)$ |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Sign of $f''(x)$ | $+$ | $0$ | $-$ | $0$ | $+$ |
| Curvature of $f$ | Convex (concave up) | Inflection | Concave (concave down) | Inflection | Convex (concave up) |

Because $f''(x)$ changes sign at both $x = -\frac{\sqrt{6}}{3}$ and $x = \frac{\sqrt{6}}{3}$, **both** are genuine inflection points. To find their $y$-coordinate cleanly, substitute $x^2 = \frac{2}{3}$ directly into $f(x) = x^4 - 4x^2 = (x^2)^2 - 4(x^2)$:

$$
f\left(\pm\frac{\sqrt{6}}{3}\right) = \left(\frac{2}{3}\right)^2 - 4\left(\frac{2}{3}\right) = \frac{4}{9} - \frac{8}{3} = \frac{4 - 24}{9} = -\frac{20}{9} \approx -2.222.
$$

Hence:

- **Convex (concave upward) on:** $\left(-\infty, -\frac{\sqrt{6}}{3}\right]$ and $\left[\frac{\sqrt{6}}{3}, \infty\right)$.
- **Concave (concave downward) on:** $\left[-\frac{\sqrt{6}}{3}, \frac{\sqrt{6}}{3}\right]$.
- **Inflection points:** $\left(-\frac{\sqrt{6}}{3}, -\frac{20}{9}\right)$ and $\left(\frac{\sqrt{6}}{3}, -\frac{20}{9}\right)$.

### Step 4: Sketch of the Graph with All Features Marked

The graph has a symmetric W-shape. Notice how the two inflection points sit roughly halfway in height between the two valleys at $y = -4$ and the central hilltop at $y = 0$, marking the exact spots where each U-shaped valley transitions into the central downward-opening arch.

```text
                       y
                       ^
        2 -|   *       |       *
           |   \       |       /
        1 -|    \      |      /
           |     \     |     /
   --------+------*----+----*------+---------> x
          -2.5  (-2,0) |  (2,0)   2.5
           |       \  / \  /     (0, 0) local max
       -1 -|        \/   \/
           |        |     |
   -20/9  -|        I     I      I = (+-sqrt(6)/3, -20/9)
   (-2.22) |        |     |          inflection points
       -3 -|        |     |
           |        \     /
       -4 -|         *   *       (-sqrt(2), -4) & (sqrt(2), -4)
           |        min min      local & global minima

   Curvature:
   |<---- convex (up) ---->|<-- concave (down) -->|<---- convex (up) ---->|
                         -0.82                  +0.82
```

All identified features marked on the graph:

- Zeros: $(-2, 0)$, $(0, 0)$, $(2, 0)$
- Local maximum: $(0, 0)$
- Local and global minima: $(-\sqrt{2}, -4)$ and $(\sqrt{2}, -4)$
- Inflection points: $\left(-\frac{\sqrt{6}}{3}, -\frac{20}{9}\right)$ and $\left(\frac{\sqrt{6}}{3}, -\frac{20}{9}\right)$

---

## 5. Final Answer & Conclusion

- **Local extrema:**
  - Local (and global) minima at $(-\sqrt{2}, -4)$ and $(\sqrt{2}, -4)$.
  - Local maximum at $(0, 0)$.
- **Intervals of convexity (concave upward):** $\left(-\infty, -\frac{\sqrt{6}}{3}\right]$ and $\left[\frac{\sqrt{6}}{3}, \infty\right)$.
- **Interval of concavity (concave downward):** $\left[-\frac{\sqrt{6}}{3}, \frac{\sqrt{6}}{3}\right]$.
- **Inflection points:** $\left(-\frac{\sqrt{6}}{3}, -\frac{20}{9}\right)$ and $\left(\frac{\sqrt{6}}{3}, -\frac{20}{9}\right)$.

---

## 6. Quick Verification

1. **Second Derivative Test on all three critical points:**
   - $f''(-\sqrt{2}) = 12(2) - 8 = 16 > 0 \implies$ local minimum.
   - $f''(0) = 12(0) - 8 = -8 < 0 \implies$ local maximum.
   - $f''(\sqrt{2}) = 12(2) - 8 = 16 > 0 \implies$ local minimum.
   This matches the first-derivative sign chart completely.
2. **Completing the square in $x^2$ to confirm global minima:** Writing

$$
f(x) = x^4 - 4x^2 = (x^2 - 2)^2 - 4 \ge -4
$$

immediately verifies that $f(x) \ge -4$ for every $x \in \mathbb{R}$, with equality if and only if $x^2 = 2$, that is, $x = \pm\sqrt{2}$. Moreover, at the inflection point $x^2 = \frac{2}{3}$, this form gives $\left(\frac{2}{3} - 2\right)^2 - 4 = \left(-\frac{4}{3}\right)^2 - 4 = \frac{16}{9} - \frac{36}{9} = -\frac{20}{9}$, double-checking the $y$-coordinate!

---

## 7. Common Mistakes to Avoid

- **Confusing $f'(x) = 0$ with $f''(x) = 0$:** Zeros of $f'$ locate horizontal tangents (potential extrema), whereas zeros of $f''$ locate candidate inflection points. Notice here that the inflection points occur at $x = \pm\frac{\sqrt{6}}{3} \approx \pm 0.82$, strictly between the minima at $\pm\sqrt{2} \approx \pm 1.41$ and the local maximum at $0$.
- **Forgetting to check whether $f''(x)$ actually changes sign:** Always confirm a sign change across a zero of $f''$ before declaring an inflection point; for instance, $g(x) = x^4$ has $g''(0) = 0$ yet no inflection point at $x = 0$.
- **Computing $f\left(\frac{\sqrt{6}}{3}\right)$ by expanding complicated radicals instead of using $x^2 = \frac{2}{3}$:** Substituting $x^2 = \frac{2}{3}$ directly into $x^4 - 4x^2 = (x^2)^2 - 4x^2$ avoids arithmetic errors and immediately gives $-\frac{20}{9}$.
- **Mixing up convex and concave terminology:** Remembering the geometry—"convex" or "concave upward" means $f'' > 0$ (holds water like a cup), while "concave" or "concave downward" means $f'' < 0$ (spills water like an umbrella)—prevents sign mix-ups.

---

## 8. How I Would Explain This in Class

> "The first derivative gives you the skeleton of the W-shape: two deep valleys at $x = \pm\sqrt{2}$ and a central hilltop at $x = 0$. The second derivative gives you the steering wheel as you drive along the road from left to right. Coming down into the left valley and climbing out of it, you are steering left—the curve bends upward. Right at $x = -\frac{\sqrt{6}}{3}$, you straighten the wheel for an instant and start steering right to round the top of the hill at $(0, 0)$. Then at $x = +\frac{\sqrt{6}}{3}$, you switch back to steering left to curve through the right valley. Those two steering-switch points are your inflection points!"
