# Problem 11: A Parameter and the Number of Extrema

## 1. The Original Problem

For

$$
f_a(x) = x^3 - 3ax
$$

depending on $a$, determine the number of critical points and their character. Separate the parameter cases and justify why the structure of the graph changes.

---

## 2. What Are We Trying to Find?

1. The first derivative $f_a'(x)$ and the equation determining all critical points in terms of the real parameter $a$.
2. A complete case-by-case separation for $a < 0$, $a = 0$, and $a > 0$, stating for each case:
   - the exact number and locations of critical points,
   - the sign of $f_a'(x)$ and intervals of monotonicity,
   - the character of every critical point (local maximum, local minimum, or stationary inflection point) and the corresponding function values.
3. A clear analytical and geometric justification of why the qualitative shape of the graph changes as $a$ crosses $0$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Critical points of a polynomial:** Because the polynomial $f_a$ is differentiable everywhere on $\mathbb{R}$, its critical points are precisely the real roots of its first derivative.
- **Parameter case splitting:** When solving $x^2 = a$ over $\mathbb{R}$, the number of real roots depends strictly on the sign of $a$: zero roots if $a < 0$, one double root if $a = 0$, and two distinct roots if $a > 0$.
- **First and second derivative tests:** A critical point is a local extremum if and only if the first derivative changes sign across it. If $f_a'(x_0) = 0$ without a sign change, the point is a stationary inflection point rather than an extremum.
- **Geometric role of the parameter:** Writing $f_a'(x) = 3x^2 - 3a$ shows that varying $a$ vertically shifts the derivative parabola, controlling whether it stays above the $x$-axis, touches it tangentially, or dips below it.

---

## 4. Step-by-Step Solution

### Step 1: Compute the Derivatives and Set Up the Critical Point Equation

For every $a \in \mathbb{R}$, the function $f_a(x) = x^3 - 3ax$ is a polynomial defined on $\mathbb{R}$. Replacing $x$ with $-x$ negates the output, so every member of this family is an odd function whose graph passes through $(0, 0)$ and satisfies

$$
\lim_{x \to -\infty} f_a(x) = -\infty, \qquad \lim_{x \to +\infty} f_a(x) = +\infty.
$$

Differentiating with respect to $x$, while treating $a$ as a constant, yields

$$
f_a'(x) = 3x^2 - 3a = 3(x^2 - a),
$$

and

$$
f_a''(x) = 6x.
$$

Note that for every value of $a$, the second derivative $f_a''(x) = 6x$ changes sign from $-$ to $+$ at $x = 0$, so $(0, 0)$ is always an inflection point of the graph.

To find the critical points, we solve

$$
f_a'(x) = 0 \iff 3(x^2 - a) = 0 \iff x^2 = a.
$$

The number and behavior of the real solutions depend directly on whether $a < 0$, $a = 0$, or $a > 0$.

### Step 2: Case 1 — $a < 0$

When $a < 0$, we have $-a > 0$, so for all $x \in \mathbb{R}$,

$$
f_a'(x) = 3(x^2 - a) \ge -3a > 0.
$$

- **Number of critical points:** $0$, because $x^2 = a < 0$ has no real solutions.
- **Monotonicity:** Since $f_a'(x) > 0$ for all $x \in \mathbb{R}$, the function is strictly increasing on all of $\mathbb{R}$.
- **Character of extrema:** None. The slope reaches its positive minimum value $-3a > 0$ at the inflection point $(0, 0)$, so the tangent line is never horizontal.

### Step 3: Case 2 — $a = 0$

When $a = 0$, the function simplifies to $f_0(x) = x^3$, with derivative

$$
f_0'(x) = 3x^2.
$$

- **Number of critical points:** $1$, located at $x = 0$.
- **Monotonicity:** We have $f_0'(x) = 3x^2 > 0$ for all $x \ne 0$, and the derivative equals $0$ only at $x = 0$. Because the slope is positive on $(-\infty, 0)$ and positive on $(0, \infty)$, the function is still strictly increasing on all of $\mathbb{R}$.
- **Character of the critical point:** Since the first derivative does not change sign at $x = 0$, the point $(0, 0)$ is **not a local extremum**. Instead, because $f_0''(x) = 6x$ changes sign at $x = 0$, the point $(0, 0)$ is a **stationary inflection point** — a horizontal inflection point where the curve momentarily flattens before continuing upward.

### Step 4: Case 3 — $a > 0$

When $a > 0$, the equation $x^2 = a$ has **two distinct real solutions**:

$$
x = -\sqrt{a} \qquad \text{and} \qquad x = \sqrt{a}.
$$

Factoring the derivative gives

$$
f_a'(x) = 3(x + \sqrt{a})(x - \sqrt{a}).
$$

The sign chart of $f_a'(x)$ is:

| Interval / Point | $f_a'(x)$ | Monotonicity / Character |
| :--- | :---: | :--- |
| $(-\infty, -\sqrt{a})$ | $+$ | Strictly increasing |
| $x = -\sqrt{a}$ | $0$ | Strict local maximum |
| $(-\sqrt{a}, \sqrt{a})$ | $-$ | Strictly decreasing |
| $x = \sqrt{a}$ | $0$ | Strict local minimum |
| $(\sqrt{a}, \infty)$ | $+$ | Strictly increasing |

Let us evaluate the function and second derivative at both critical points:

- At $x = -\sqrt{a}$: the first derivative changes from $+$ to $-$, and $f_a''(-\sqrt{a}) = -6\sqrt{a} < 0$. Hence $x = -\sqrt{a}$ is a **strict local maximum**, with value

$$
f_a(-\sqrt{a}) = (-\sqrt{a})^3 - 3a(-\sqrt{a}) = -a\sqrt{a} + 3a\sqrt{a} = 2a\sqrt{a}.
$$

- At $x = \sqrt{a}$: the first derivative changes from $-$ to $+$, and $f_a''(\sqrt{a}) = 6\sqrt{a} > 0$. Hence $x = \sqrt{a}$ is a **strict local minimum**, with value

$$
f_a(\sqrt{a}) = (\sqrt{a})^3 - 3a\sqrt{a} = a\sqrt{a} - 3a\sqrt{a} = -2a\sqrt{a}.
$$

Neither extremum is global, because the cubic diverges to $-\infty$ on the left and to $+\infty$ on the right:

$$
\lim_{x \to -\infty} f_a(x) = -\infty, \qquad \lim_{x \to +\infty} f_a(x) = +\infty.
$$

### Step 5: Justify Why the Structure of the Graph Changes

We can see the structural change from two complementary perspectives:

1. **Slope-parabola perspective:** The derivative $f_a'(x) = 3x^2 - 3a$ is an upward-opening parabola with vertex at $(0, -3a)$. Increasing $a$ shifts this parabola downward without changing its shape:
   - For $a < 0$, the vertex sits strictly above the $x$-axis, so $f_a'(x)$ stays strictly positive everywhere; the curve climbs monotonically without pausing.
   - At the threshold $a = 0$, the vertex kisses the $x$-axis at $(0, 0)$; the slope touches $0$ at a single point without becoming negative, creating a horizontal inflection point.
   - For $a > 0$, the vertex drops below the $x$-axis, so the parabola pierces the $x$-axis at $-\sqrt{a}$ and $\sqrt{a}$, creating a central interval $(-\sqrt{a}, \sqrt{a})$ of negative slope bounded by a local maximum on the left and a local minimum on the right.

2. **Competition between the cubic and linear terms:** Rewrite $f_a(x) = x^3 + (-3a)x$. Near $x = 0$, the term $x^3$ is very small compared with the linear term $-3ax$, so the behavior near the origin is controlled by the slope $-3a$:
   - If $a < 0$, then $-3a > 0$, so both the linear term near $0$ and the cubic term for large $|x|$ push the graph upward.
   - If $a > 0$, then $-3a < 0$, so the linear term tilts the curve downward across the origin. Far from the origin, however, $x^3$ inevitably overpowers $-3ax$ and forces the curve back upward. Reversing direction twice creates the local maximum at $-\sqrt{a}$ and the local minimum at $\sqrt{a}$.

```text
    Case 1: a < 0            Case 2: a = 0            Case 3: a > 0
      (0 crit. pts)            (1 crit. pt)             (2 crit. pts)

          y   *                    y   *                    y      *
          |  *                     |   *                    |     *
          | *                      |  *                 max |    *
      ----+-----> x            ---***---> x             * * +---*--> x
         *|                       *|  (0,0)            *   *|  *
        * |                      * |                  *     |* min
       *  |                      * |                 *      |
```

---

## 5. Final Answer & Conclusion

| Parameter Case | Critical Points | Character | Monotonicity |
| :--- | :---: | :--- | :--- |
| $a < 0$ | None, $0$ points | No extrema | Strictly increasing on $\mathbb{R}$ |
| $a = 0$ | $x = 0$, $1$ point | Stationary inflection point at $(0, 0)$; no extrema | Strictly increasing on $\mathbb{R}$ |
| $a > 0$ | $x = -\sqrt{a}$ and $x = \sqrt{a}$, $2$ points | Strict local max at $(-\sqrt{a}, 2a\sqrt{a})$; strict local min at $(\sqrt{a}, -2a\sqrt{a})$ | Increasing on $(-\infty, -\sqrt{a}]$, decreasing on $[-\sqrt{a}, \sqrt{a}]$, increasing on $[\sqrt{a}, \infty)$ |

The graph changes structure at the critical threshold $a = 0$ because the slope at the origin, $f_a'(0) = -3a$, changes sign from positive to negative, causing the derivative parabola $3x^2 - 3a$ to cross the $x$-axis and giving birth to a pair of local extrema when $a > 0$.

---

## 6. Quick Verification

1. **Concrete numerical test in each regime:**
   - Choose $a = -1$: $f_{-1}(x) = x^3 + 3x$ has derivative $3x^2 + 3 \ge 3 > 0$, confirming no critical points and strict increase everywhere.
   - Choose $a = 0$: the cubic $x^3$ satisfies $(-1)^3 = -1 < 0^3 = 0 < 1^3 = 1$, confirming $(0, 0)$ is not an extremum even though $f_0'(0) = 0$.
   - Choose $a = 1$: the cubic $f_1(x) = x^3 - 3x$ has critical points $x = \pm 1$, local maximum value $2 = 2(1)\sqrt{1}$ at $x = -1$, and local minimum value $-2 = -2(1)\sqrt{1}$ at $x = 1$.

2. **Continuity of the bifurcation as $a \to 0^+$:** As $a \to 0^+$, the two critical points $-\sqrt{a}$ and $\sqrt{a}$ both converge to $0$, and their extrema heights $\pm 2a\sqrt{a}$ both shrink to $0$. Thus the max-min pair merges smoothly into the single stationary inflection point $(0, 0)$ at $a = 0$ and then disappears for $a < 0$.

---

## 7. Common Mistakes to Avoid

- **Taking $\sqrt{a}$ without restricting $a \ge 0$:** Claiming that $x = \pm\sqrt{a}$ are always the critical points without splitting into cases fails when $a < 0$ because $\sqrt{a}$ is not a real number.
- **Calling $x = 0$ an extremum when $a = 0$:** Finding $f_0'(0) = 0$ does not automatically produce a maximum or minimum. Because $3x^2 \ge 0$ never changes sign, $x = 0$ is a horizontal inflection point, not an extremum.
- **Treating $a$ as a variable when differentiating:** The function is differentiated with respect to $x$, not $a$; the derivative of $-3ax$ is $-3a$, not $-3a - 3x$.
- **Assuming the local extrema for $a > 0$ are global extrema:** Every cubic polynomial with non-zero leading coefficient has range $(-\infty, \infty)$, so its extrema are strictly local.

---

## 8. How I Would Explain This in Class

> "Picture $f_a(x) = x^3 - 3ax$ as a tug-of-war between two shapes: the steep cubic $x^3$ that always wants to climb from bottom-left to top-right, and the straight line $-3ax$ that tilts the middle of the graph. When $a$ is negative, the tilt is upward, so both pieces pull in the same direction and you get a smooth ramp with no hills or valleys. At $a = 0$, the tilt disappears, leaving the classic curve $y = x^3$ that pauses flat at the origin for a single instant. The moment $a$ becomes positive, the middle tilts downward while the outer ends still shoot upward — and the only way a continuous curve can climb, dip down through the origin, and climb again is to form a hilltop on the left and a valley on the right."
