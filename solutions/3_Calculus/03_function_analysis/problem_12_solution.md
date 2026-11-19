# Problem 12: A Function with an Absolute Value

## 1. The Original Problem

Analyze

$$
f(x) = |x^2 - 4|.
$$

First sketch $x^2 - 4$, then explain the effect of the absolute value. Indicate the points where the derivative does not exist and justify the reason geometrically.

---

## 2. What Are We Trying to Find?

1. The shape and key features of the auxiliary parabola $h(x) = x^2 - 4$, together with its sketch.
2. The piecewise formula for $f(x) = |x^2 - 4|$ and a clear explanation of the geometric effect of applying the absolute value to $h(x)$.
3. Complete analysis of $f$: domain, symmetry, intercepts, limits at infinity, monotonicity, extrema, and concavity on the smooth intervals.
4. The exact points where $f'(x)$ fails to exist, verified via one-sided derivatives and justified geometrically.
5. A sketch of $y = |x^2 - 4|$ marking all key points and corners.

---

## 3. Before Calculating: What Idea Do We Need?

- **Definition of absolute value:** For any expression $u$, $|u| = u$ when $u \ge 0$ and $|u| = -u$ when $u < 0$. Geometrically, taking $|h(x)|$ keeps all parts of the graph on or above the $x$-axis unchanged and reflects all parts strictly below the $x$-axis across the $x$-axis.
- **Differentiability requires equal one-sided derivatives:** A function $f$ is differentiable at a point $c$ if and only if its left-hand and right-hand derivatives both exist as finite numbers and satisfy $f_-'(c) = f_+'(c)$.
- **Geometric meaning of non-differentiability at a corner:** When a smooth curve crosses the $x$-axis with a non-zero slope $m$, reflecting the negative branch across the $x$-axis changes its slope from $m$ to $-m$, creating a sharp corner with two distinct half-tangents.
- **Critical points include non-differentiable points:** Extrema can occur not only where $f'(x) = 0$, but also at points in the domain where $f'(x)$ does not exist.

---

## 4. Step-by-Step Solution

### Step 1: Analyze and Sketch $h(x) = x^2 - 4$

Consider first the quadratic function $h(x) = x^2 - 4$:

- It is an upward-opening parabola with vertex at $(0, -4)$, which is its global minimum.
- Its zeros are found from $x^2 - 4 = (x - 2)(x + 2) = 0$, giving $x = -2$ and $x = 2$.
- Sign of $h(x)$:
  - $h(x) \ge 0$ for $x \in (-\infty, -2] \cup [2, \infty)$,
  - $h(x) < 0$ for $x \in (-2, 2)$.

```text
                y = x^2 - 4
                     y
                     ^
          *          |          *
           *       2 +         *
            *        |        *
      -------*-------+-------*-------> x
            -2 *     0     * 2
                 *   |   *
                  * -4 *  vertex (0, -4)
                    ***
```

### Step 2: Explain the Effect of the Absolute Value and Write the Piecewise Formula

Applying the absolute value to $h(x) = x^2 - 4$ gives the piecewise definition

$$
f(x) = |x^2 - 4| = \begin{cases} x^2 - 4, & \text{if } x \le -2 \text{ or } x \ge 2, \\ 4 - x^2, & \text{if } -2 < x < 2. \end{cases}
$$

Geometrically, the transformation $y = h(x) \mapsto y = |h(x)|$ acts as follows:

- On $(-\infty, -2]$ and $[2, \infty)$, where $x^2 - 4 \ge 0$, the graph is **completely unchanged**.
- On $(-2, 2)$, where $x^2 - 4 < 0$, the entire downward arc lying below the $x$-axis is **reflected across the $x$-axis**. The vertex $(0, -4)$ flips to $(0, 4)$, turning the downward bowl into an upward arch.
- The two $x$-intercepts $(-2, 0)$ and $(2, 0)$ remain fixed because $|0| = 0$.

### Step 3: Basic Properties — Domain, Symmetry, Intercepts, and Limits

- **Domain:** $D = \mathbb{R}$, and $f$ is continuous everywhere because it is the composition of continuous functions.
- **Symmetry:** $f(-x) = |(-x)^2 - 4| = |x^2 - 4| = f(x)$, so $f$ is an **even function**, symmetric about the $y$-axis.
- **Intercepts and range:** The zeros are $x = -2$ and $x = 2$; the $y$-intercept is $(0, 4)$. Because $|x^2 - 4| \ge 0$ and takes value $0$ at $x = \pm 2$ while growing without bound, the range is $[0, \infty)$.
- **Limits at infinity:** As $x \to -\infty$ and as $x \to +\infty$, we have $f(x) \to +\infty$. There are no asymptotes.

### Step 4: Differentiability and Points Where the Derivative Does Not Exist

On the open intervals where $x^2 - 4$ does not vanish, $f$ agrees with a polynomial and is smoothly differentiable:

$$
f'(x) = \begin{cases} 2x, & \text{if } x < -2 \text{ or } x > 2, \\ -2x, & \text{if } -2 < x < 2. \end{cases}
$$

We must check the transition points $x = -2$ and $x = 2$ using the limit definition of one-sided derivatives.

**At $x = 2$:** Since $f(2) = 0$ and $(2 + h)^2 - 4 = 4h + h^2$:

- For small $h < 0$, we have $2 + h \in (-2, 2)$, so $f(2 + h) = 4 - (2 + h)^2 = -4h - h^2$. Thus the left-hand derivative is

$$
f_-'(2) = \lim_{h \to 0^-} \frac{-4h - h^2}{h} = \lim_{h \to 0^-} (-4 - h) = -4.
$$

- For $h > 0$, we have $2 + h > 2$, so $f(2 + h) = (2 + h)^2 - 4 = 4h + h^2$. Thus the right-hand derivative is

$$
f_+'(2) = \lim_{h \to 0^+} \frac{4h + h^2}{h} = \lim_{h \to 0^+} (4 + h) = 4.
$$

Because $f_-'(2) = -4 \ne 4 = f_+'(2)$, **$f'(2)$ does not exist**.

**At $x = -2$:** Since $f(-2) = 0$ and $(-2 + h)^2 - 4 = -4h + h^2$:

- For $h < 0$, we have $-2 + h < -2$, so $f(-2 + h) = -4h + h^2$, giving

$$
f_-'(-2) = \lim_{h \to 0^-} \frac{-4h + h^2}{h} = \lim_{h \to 0^-} (-4 + h) = -4.
$$

- For small $h > 0$, we have $-2 + h \in (-2, 2)$, so $f(-2 + h) = 4h - h^2$, giving

$$
f_+'(-2) = \lim_{h \to 0^+} \frac{4h - h^2}{h} = \lim_{h \to 0^+} (4 - h) = 4.
$$

Because $f_-'(-2) = -4 \ne 4 = f_+'(-2)$, **$f'(-2)$ does not exist**.

**Geometric justification:** The original parabola $h(x) = x^2 - 4$ crosses the $x$-axis transversally with non-zero slopes $h'(-2) = -4$ and $h'(2) = 4$. Reflecting the negative part across the $x$-axis flips the sign of the slope on the interior side of each root while leaving the exterior slope untouched. Consequently, at both $(-2, 0)$ and $(2, 0)$, the graph arrives from the left with slope $-4$ and abruptly departs to the right with slope $+4$. This creates two sharp **corners** (V-shaped kinks) where no single tangent line can exist.

### Step 5: Monotonicity, Extrema, Concavity, and Final Sketch

The critical points of $f$ are all points where $f'(x) = 0$ or $f'(x)$ does not exist:

- $x = 0$, where $f'(0) = 0$,
- $x = -2$ and $x = 2$, where $f'$ does not exist.

On the open smooth intervals, $f''(x) = 2 > 0$ on $(-\infty, -2)$ and $(2, \infty)$ so $f$ is strictly convex there, while $f''(x) = -2 < 0$ on $(-2, 2)$ so $f$ is strictly concave there. Notice that $x = \pm 2$ are corners, not smooth inflection points.

| Interval / Point | $f'(x)$ | $f''(x)$ | Behavior of $f(x)$ |
| :--- | :---: | :---: | :--- |
| $(-\infty, -2)$ | $2x < 0$ | $+2$ | Strictly decreasing, concave up |
| $x = -2$ | Undefined | Undefined | Sharp corner; strict local and global minimum at $(-2, 0)$ |
| $(-2, 0)$ | $-2x > 0$ | $-2$ | Strictly increasing, concave down |
| $x = 0$ | $0$ | $-2$ | Smooth strict local maximum at $(0, 4)$ |
| $(0, 2)$ | $-2x < 0$ | $-2$ | Strictly decreasing, concave down |
| $x = 2$ | Undefined | Undefined | Sharp corner; strict local and global minimum at $(2, 0)$ |
| $(2, \infty)$ | $2x > 0$ | $+2$ | Strictly increasing, concave up |

```text
               y = |x^2 - 4|
                     y
                     ^
         *         4 +***         *    smooth local max (0, 4)
         *         * |   *        *
          *       *  |    *      *
           *     * 2 +     *    *
            *   *    |      *  *
             * *     |       **
      --------*------+-------*--------> x
             -2      0       2
      corner min (-2,0)   corner min (2,0)
```

---

## 5. Final Answer & Conclusion

- **Effect of absolute value:** The branches of $y = x^2 - 4$ on $(-\infty, -2]$ and $[2, \infty)$ stay fixed, while the negative arc on $(-2, 2)$ reflects across the $x$-axis to form an arch peaking at $(0, 4)$.
- **Points of non-differentiability:** $x = -2$ and $x = 2$. At both points, the one-sided derivatives disagree, $f_-'(\pm 2) = -4 \ne 4 = f_+'(\pm 2)$, forming sharp corners with no unique tangent line.
- **Monotonicity:** Strictly decreasing on $(-\infty, -2]$ and on $[0, 2]$; strictly increasing on $[-2, 0]$ and on $[2, \infty)$.
- **Extrema:**
  - Strict local and global minima at $(-2, 0)$ and $(2, 0)$ — located at the non-differentiable corners.
  - Strict local maximum at $(0, 4)$ — a smooth stationary point, not global since $f(x) \to +\infty$ as $|x| \to \infty$.

---

## 6. Quick Verification

1. **Direct non-negativity check for the global minima:** Since $|x^2 - 4| \ge 0$ for all $x \in \mathbb{R}$, and $|x^2 - 4| = 0$ if and only if $x = \pm 2$, the points $(-2, 0)$ and $(2, 0)$ must be the global minima regardless of non-differentiability.

2. **Numerical secant slope check near $x = 2$:**
   - Just to the left, at $x = 1.99$: $f(1.99) = |3.9601 - 4| = 0.0399$, so the average slope on $[1.99, 2]$ is $\frac{0 - 0.0399}{2 - 1.99} = -3.99 \approx -4$.
   - Just to the right, at $x = 2.01$: $f(2.01) = |4.0401 - 4| = 0.0401$, so the average slope on $[2, 2.01]$ is $\frac{0.0401 - 0}{2.01 - 2} = +4.01 \approx +4$.
   - The sharp jump from $-4$ to $+4$ confirms the corner at $x = 2$.

---

## 7. Common Mistakes to Avoid

- **Differentiating blindly inside absolute value bars:** Claiming that $f'(x) = |2x|$ is completely false. On $(-2, 0)$, for instance, $f(x) = 4 - x^2$ has positive slope $-2x$, whereas on $(0, 2)$ it has negative slope $-2x$; absolute value bars must always be removed via a piecewise definition before differentiating.
- **Missing the minima at $x = \pm 2$ because $f'(x) \ne 0$ there:** Solving only $f'(x) = 0$ yields only $x = 0$ and completely misses the two global minima at $x = \pm 2$. Always include points where $f'$ does not exist among critical points.
- **Assuming every zero of an absolute-value function produces a corner:** A corner occurs at a root $c$ when $h(c) = 0$ and $h'(c) \ne 0$. If $h'(c) = 0$ as well — for example, $g(x) = |x^2| = x^2$ at $x = 0$ — both one-sided slopes equal $0$ and the function stays differentiable. Here $h'(\pm 2) = \pm 4 \ne 0$, which is why corners appear.
- **Calling $x = \pm 2$ inflection points:** Even though concavity switches from up to down across $x = -2$ and from down to up across $x = 2$, a point of inflection requires a tangent line at that point; $x = \pm 2$ are sharp corners, not inflection points.

---

## 8. How I Would Explain This in Class

> "Think of the $x$-axis as a solid floor and $y = x^2 - 4$ as the path of a ball. Without absolute value bars, the parabola dives cleanly beneath the floor at $x = -2$ and comes back up at $x = 2$. Putting absolute value bars around it turns the floor into a mirror — or a hard trampoline. Every time the curve tries to dip underground, it bounces straight back upward at the exact opposite angle. At $x = 2$, the graph hits the floor heading down at slope $-4$ and rebounds heading up at slope $+4$. Because your velocity flips instantly at the bounce, there is no smooth tangent line there — just a crisp V-shaped corner, which happens to be the very lowest point the curve can reach."
