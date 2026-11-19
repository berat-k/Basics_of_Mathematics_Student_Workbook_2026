# Problem 14: Reconstructing Information from the Derivative

## 1. The Original Problem

It is known that

$$
f'(x) = (x - 1)(x + 2).
$$

Determine the monotonicity and the locations of the extrema, and sketch a possible qualitative shape of the function. Then, for

$$
g(x) = \frac{x^3}{3} + \frac{x^2}{2} - 2x
$$

verify that $g'(x) = (x - 1)(x + 2)$, and compare the specific graph with the earlier qualitative sketch.

---

## 2. What Are We Trying to Find?

1. The critical points, sign chart of $f'(x)$, intervals of monotonicity, and locations and types of local extrema of any function $f$ satisfying $f'(x) = (x - 1)(x + 2)$.
2. The concavity and inflection point location obtained from $f''(x)$, and an explanation of what remains undetermined when only $f'(x)$ is known.
3. A qualitative sketch of a possible graph of $y = f(x)$.
4. Verification by differentiation that $g(x) = \frac{x^3}{3} + \frac{x^2}{2} - 2x$ satisfies $g'(x) = (x - 1)(x + 2)$.
5. Exact coordinates of the extrema, inflection point, and intercepts of $g(x)$, together with a sketch of $y = g(x)$ and a direct comparison with the earlier qualitative sketch.

---

## 3. Before Calculating: What Idea Do We Need?

- **Reading monotonicity and extrema directly from $f'(x)$:** Where $f'(x) > 0$, $f$ increases; where $f'(x) < 0$, $f$ decreases. A sign change of $f'$ from $+$ to $-$ signals a local maximum, while a sign change from $-$ to $+$ signals a local minimum.
- **Reading curvature from $f''(x)$:** Differentiating $f'(x)$ once gives $f''(x)$, which tells us the exact $x$-coordinate of any inflection point and the intervals of concavity and convexity — still without ever finding $f(x)$ explicitly.
- **Uniqueness up to an additive constant:** If two functions on $\mathbb{R}$ share the same derivative, i.e., $f'(x) = g'(x)$ for all $x \in \mathbb{R}$, then $f(x) = g(x) + C$ for some constant $C \in \mathbb{R}$. Geometrically, $f'$ completely determines the shape, slopes, and vertical height differences of $f$, leaving only its overall vertical position free.

---

## 4. Step-by-Step Solution

### Step 1: Analyze $f'(x) = (x - 1)(x + 2)$ for Monotonicity and Extrema

Because $f'(x) = (x - 1)(x + 2)$ is a polynomial defined on all of $\mathbb{R}$, any antiderivative $f$ is differentiable and continuous on $\mathbb{R}$.

Finding the critical points:

$$
f'(x) = (x - 1)(x + 2) = 0 \iff x = -2 \quad \text{or} \quad x = 1.
$$

Expanding shows $f'(x) = x^2 + x - 2$, an upward-opening parabola with roots at $-2$ and $1$. Therefore:

| Interval / Point | $x + 2$ | $x - 1$ | $f'(x)$ | Behavior of $f(x)$ |
| :--- | :---: | :---: | :---: | :--- |
| $(-\infty, -2)$ | $-$ | $-$ | $+$ | Strictly increasing |
| $x = -2$ | $0$ | $-$ | $0$ | Strict local maximum |
| $(-2, 1)$ | $+$ | $-$ | $-$ | Strictly decreasing |
| $x = 1$ | $+$ | $0$ | $0$ | Strict local minimum |
| $(1, \infty)$ | $+$ | $+$ | $+$ | Strictly increasing |

Thus, for **every** function $f$ satisfying $f'(x) = (x - 1)(x + 2)$:

- $f$ is strictly increasing on $(-\infty, -2]$ and on $[1, \infty)$.
- $f$ is strictly decreasing on $[-2, 1]$.
- $f$ has a **strict local maximum** at $x = -2$ and a **strict local minimum** at $x = 1$.

### Step 2: Curvature and What Remains Undetermined

Differentiating $f'(x) = x^2 + x - 2$ gives the second derivative:

$$
f''(x) = 2x + 1.
$$

Setting $f''(x) = 0$ yields $x = -\frac{1}{2}$, which is the exact midpoint between $-2$ and $1$:

- On $\left(-\infty, -\frac{1}{2}\right)$: $f''(x) < 0$, so $f$ is strictly concave (concave down).
- On $\left(-\frac{1}{2}, \infty\right)$: $f''(x) > 0$, so $f$ is strictly convex (concave up).
- At $x = -\frac{1}{2}$: $f$ has an **inflection point**, where the downward slope is steepest, $f'\left(-\frac{1}{2}\right) = -\frac{9}{4}$.

Furthermore, the net vertical drop from the local maximum at $x = -2$ to the local minimum at $x = 1$ is completely fixed by $f'$:

$$
f(1) - f(-2) = \int_{-2}^{1} (x^2 + x - 2)\,dx = \left[\frac{x^3}{3} + \frac{x^2}{2} - 2x\right]_{-2}^{1} = -\frac{7}{6} - \frac{10}{3} = -\frac{9}{2} = -4.5.
$$

What we **cannot** determine from $f'(x)$ alone is the exact vertical placement of the graph — that is, the $y$-values $f(-2)$, $f(1)$, the $y$-intercept $f(0)$, and the number or locations of the $x$-intercepts — because adding any constant $C$ shifts the entire graph vertically without altering $f'(x)$.

### Step 3: Qualitative Sketch of a Possible Graph $y = f(x)$

```text
          Qualitative shape of y = f(x)  (vertical height +C is free)

                     y
                     ^
            max      |            *
            * *      |           *
           *   *     |          *
          *     *    |         *
         *      I *  |        *     vertical drop from max to min = 4.5
        *          * |       *
       *            *|      *
      *              * *   *
                     |  * *
                     |  min
    --------+----+---+----+---------> x
           -2  -0.5  0    1
           max  infl     min
```

### Step 4: Verify That $g'(x) = (x - 1)(x + 2)$

We are given

$$
g(x) = \frac{x^3}{3} + \frac{x^2}{2} - 2x.
$$

Differentiate term by term using the power rule:

$$
g'(x) = \frac{3x^2}{3} + \frac{2x}{2} - 2 = x^2 + x - 2.
$$

Now expand $(x - 1)(x + 2)$:

$$
(x - 1)(x + 2) = x^2 + 2x - x - 2 = x^2 + x - 2.
$$

Therefore, $g'(x) = (x - 1)(x + 2)$ for all $x \in \mathbb{R}$, confirming that $g$ is one specific antiderivative of $f'$, corresponding to the choice $C = g(0) = 0$.

### Step 5: Compute Exact Coordinates of $g(x)$ and Sketch Its Graph

Evaluating $g$ at all key points:

- **$y$-intercept:** $g(0) = 0$, so the graph passes through the origin $(0, 0)$.
- **Local maximum at $x = -2$:**

$$
g(-2) = \frac{(-2)^3}{3} + \frac{(-2)^2}{2} - 2(-2) = -\frac{8}{3} + 2 + 4 = 6 - \frac{8}{3} = \frac{10}{3} \approx 3.333.
$$

- **Local minimum at $x = 1$:**

$$
g(1) = \frac{1^3}{3} + \frac{1^2}{2} - 2(1) = \frac{1}{3} + \frac{1}{2} - 2 = \frac{2 + 3 - 12}{6} = -\frac{7}{6} \approx -1.167.
$$

- **Inflection point at $x = -\frac{1}{2}$:**

$$
g\left(-\frac{1}{2}\right) = \frac{-\frac{1}{8}}{3} + \frac{\frac{1}{4}}{2} - 2\left(-\frac{1}{2}\right) = -\frac{1}{24} + \frac{1}{8} + 1 = \frac{-1 + 3 + 24}{24} = \frac{13}{12} \approx 1.083.
$$

- **Zeros of $g(x)$:** Factor out $\frac{x}{6}$:

$$
g(x) = \frac{x}{6}(2x^2 + 3x - 12) = 0 \iff x = 0 \quad \text{or} \quad x = \frac{-3 \pm \sqrt{9 + 96}}{4} = \frac{-3 \pm \sqrt{105}}{4}.
$$

Numerically, the three $x$-intercepts are $x \approx -3.312$, $x = 0$, and $x \approx 1.812$.

```text
          Specific graph of g(x) = x^3/3 + x^2/2 - 2x

                       y
                       ^
            M (-2,10/3)|               *
                * *    |              *
               *   * 3 +             *
              *     *  |            *
             *     I * |           *  (-0.5, 13/12)
            *        *1+          *
           *          *|         *
    ------*------------+--------*----------> x
        -3.31  -2     0*   1  1.81
         *             |*     *
         *          -1 + * * *
                       |  m (1, -7/6)
```

### Step 6: Compare the Specific Graph of $g(x)$ with the Qualitative Sketch

| Feature | Qualitative sketch from $f'(x)$ alone | Specific graph of $g(x)$ |
| :--- | :--- | :--- |
| Monotonicity intervals | Increasing on $(-\infty, -2]$ and $[1, \infty)$; decreasing on $[-2, 1]$ | Identical |
| Local maximum $x$-coordinate | $x = -2$ | $x = -2$, pinned at $\left(-2, \frac{10}{3}\right)$ |
| Local minimum $x$-coordinate | $x = 1$ | $x = 1$, pinned at $\left(1, -\frac{7}{6}\right)$ |
| Inflection point $x$-coordinate | $x = -\frac{1}{2}$ | $x = -\frac{1}{2}$, pinned at $\left(-\frac{1}{2}, \frac{13}{12}\right)$ |
| Vertical drop from max to min | Fixed at $\frac{9}{2} = 4.5$ | $\frac{10}{3} - \left(-\frac{7}{6}\right) = \frac{9}{2} = 4.5$ |
| Vertical position and zeros | Undetermined — free vertical shift $+C$ | Fixed by $g(0) = 0$; three real zeros at $0$ and $\frac{-3 \pm \sqrt{105}}{4}$ |

In short, the specific graph of $g(x)$ has the **exact same shape, slopes, curvature, and turning-point spacing** as the qualitative sketch; specifying $g(x)$ simply locks in the vertical anchor $g(0) = 0$, placing the maximum above the $x$-axis at $\frac{10}{3}$ and the minimum below the $x$-axis at $-\frac{7}{6}$ so that the curve crosses the $x$-axis three times. Every other solution $f$ of $f'(x) = (x - 1)(x + 2)$ is simply a rigid vertical translation $f(x) = g(x) + C$.

---

## 5. Final Answer & Conclusion

- **From $f'(x) = (x - 1)(x + 2)$:**
  - Strictly increasing on $(-\infty, -2]$ and on $[1, \infty)$; strictly decreasing on $[-2, 1]$.
  - Strict local maximum at $x = -2$; strict local minimum at $x = 1$; inflection point at $x = -\frac{1}{2}$.
  - The graph's shape is uniquely determined up to an arbitrary vertical shift $+C$.
- **Verification for $g(x) = \frac{x^3}{3} + \frac{x^2}{2} - 2x$:** $g'(x) = x^2 + x - 2 = (x - 1)(x + 2)$.
- **Comparison:** The graph of $g(x)$ matches the qualitative sketch in all monotonicity, concavity, and critical-point $x$-coordinates, while fixing the vertical position through $(0, 0)$ with local maximum $\left(-2, \frac{10}{3}\right)$, local minimum $\left(1, -\frac{7}{6}\right)$, inflection point $\left(-\frac{1}{2}, \frac{13}{12}\right)$, and zeros at $0$ and $\frac{-3 \pm \sqrt{105}}{4}$.

---

## 6. Quick Verification

1. **Cubic symmetry check about the inflection point:** Every cubic polynomial is centrally symmetric with respect to its inflection point. Let us check whether the midpoint of the local maximum $\left(-2, \frac{10}{3}\right)$ and local minimum $\left(1, -\frac{7}{6}\right)$ equals the inflection point $\left(-\frac{1}{2}, \frac{13}{12}\right)$:

$$
\left(\frac{-2 + 1}{2}, \frac{\frac{10}{3} + \left(-\frac{7}{6}\right)}{2}\right) = \left(-\frac{1}{2}, \frac{\frac{20 - 7}{6}}{2}\right) = \left(-\frac{1}{2}, \frac{13}{12}\right).
$$

Exact match!

2. **Second-derivative test on $g(x)$:**
   - $g''(-2) = 2(-2) + 1 = -3 < 0$, confirming the local maximum at $x = -2$.
   - $g''(1) = 2(1) + 1 = +3 > 0$, confirming the local minimum at $x = 1$.
   - Also $g(-2) - g(1) = \frac{10}{3} + \frac{7}{6} = \frac{27}{6} = \frac{9}{2}$, matching the integral $\int_{-2}^{1} (-f'(x))\,dx = \frac{9}{2}$.

---

## 7. Common Mistakes to Avoid

- **Confusing the graph of $f'(x)$ with the graph of $f(x)$:** Because $f'(x) = (x - 1)(x + 2)$ is a parabola with its vertex at $x = -\frac{1}{2}$, students sometimes draw a parabola for $f(x)$ instead of a cubic wave. Remember that the *zeros* of $f'$ are the *turning points* of $f$, while the *vertex* of $f'$ is the *inflection point* of $f$.
- **Assuming $f$ must pass through the origin or have specific zeros from $f'$ alone:** Knowing $f'(x) = (x - 1)(x + 2)$ never determines the $y$-intercept or the number of $x$-intercepts of $f$. For instance, $g(x) + 5$ has the exact same derivative as $g(x)$ yet has only one real zero instead of three!
- **Reversing the extrema locations:** Because $x = -2$ is the smaller number and $x = 1$ is the larger number, students sometimes guess that $-2$ is the minimum and $1$ is the maximum. Always check the sign change of $f'$: $+$ to $-$ at $-2$ means maximum, and $-$ to $+$ at $1$ means minimum.
- **Forgetting to simplify the fractions when evaluating $g(-2)$ and $g(1)$:** Careless sign handling in $\frac{(-2)^3}{3} = -\frac{8}{3}$ and $-2(-2) = +4$ often leads to the wrong height of the maximum.

---

## 8. How I Would Explain This in Class

> "Imagine hiking along a trail in thick fog where you cannot see your altitude, only a slope meter strapped to your backpack that reads $f'(x) = (x - 1)(x + 2)$. Even without knowing your elevation above sea level, you know everything about the shape of the hike: you climb steadily until mile $-2$, reach a ridge peak there, descend all the way from mile $-2$ to mile $1$ — losing exactly $4.5$ units of elevation — hit a valley floor at mile $1$, and climb again afterward. When someone finally hands you the formula $g(x) = \frac{x^3}{3} + \frac{x^2}{2} - 2x$, all it does is clear the fog and tell you your exact elevation at mile $0$ is sea level, pinning your ridge at $\frac{10}{3}$ and your valley at $-\frac{7}{6}$ without changing a single slope of the trail."
