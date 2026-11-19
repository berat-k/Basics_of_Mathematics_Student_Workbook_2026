# Problem 01: A Cubic Polynomial

## 1. The Original Problem

Analyze the monotonicity and extrema of

$$
f(x) = x^3 - 3x^2 + 2.
$$

Sketch the graph based on the results and mark the critical points.

---

## 2. What Are We Trying to Find?

1. The domain of $f$ and its first derivative $f'(x)$.
2. All critical points of $f$, namely all values of $x$ where $f'(x) = 0$ or $f'(x)$ does not exist.
3. The sign of $f'(x)$ on each subinterval determined by the critical points, yielding the exact intervals of monotonicity.
4. All local extrema of $f$ and whether $f$ has global extrema on $\mathbb{R}$.
5. Additional key graph features such as intercepts, end behavior, and symmetry/concavity to support an accurate sketch.
6. A labeled sketch of the graph of $f(x) = x^3 - 3x^2 + 2$ with the critical points clearly marked.

---

## 3. Before Calculating: What Idea Do We Need?

- **Polynomial regularity:** Every polynomial is continuous and differentiable on the entire real line $\mathbb{R}$, so critical points occur exclusively where $f'(x) = 0$.
- **First Derivative Test for Monotonicity:** If $f$ is continuous on an interval $I$ and $f'(x) > 0$ on the interior of $I$, then $f$ is strictly increasing on $I$. If $f'(x) < 0$ on the interior of $I$, then $f$ is strictly decreasing on $I$.
- **First Derivative Test for Local Extrema:** At a critical point $c$, if $f'$ changes sign from positive to negative, then $f(c)$ is a local maximum. If $f'$ changes sign from negative to positive, then $f(c)$ is a local minimum.
- **Global shape of a cubic:** Since the leading term is $x^3$ with positive coefficient $1$, we expect $f(x) \to -\infty$ as $x \to -\infty$ and $f(x) \to +\infty$ as $x \to +\infty$, giving an S-shaped curve with at most one local maximum and one local minimum.

---

## 4. Step-by-Step Solution

### Step 1: Domain and First Derivative

Since $f(x) = x^3 - 3x^2 + 2$ is a polynomial, its domain is

$$
D_f = \mathbb{R}.
$$

Differentiating term by term using the power rule gives

$$
f'(x) = 3x^2 - 6x = 3x(x - 2).
$$

### Step 2: Critical Points

Because $f'(x)$ exists for every $x \in \mathbb{R}$, the critical points are the solutions of $f'(x) = 0$:

$$
3x(x - 2) = 0 \iff x = 0 \quad \text{or} \quad x = 2.
$$

Thus, the critical numbers are $x = 0$ and $x = 2$. Evaluating $f$ at these points gives the critical points on the graph:

$$
f(0) = 0^3 - 3(0)^2 + 2 = 2 \implies (0, 2),
$$

$$
f(2) = 2^3 - 3(2)^2 + 2 = 8 - 12 + 2 = -2 \implies (2, -2).
$$

### Step 3: Sign of the Derivative and Monotonicity

The zeros $x = 0$ and $x = 2$ partition $\mathbb{R}$ into three open intervals: $(-\infty, 0)$, $(0, 2)$, and $(2, \infty)$. Since $f'(x) = 3x(x - 2)$ is an upward-opening parabola with roots $0$ and $2$, it is positive outside the roots and negative between them. We can confirm with simple test points:

- On $(-\infty, 0)$, pick $x = -1$: $f'(-1) = 3(-1)(-3) = 9 > 0$.
- On $(0, 2)$, pick $x = 1$: $f'(1) = 3(1)(-1) = -3 < 0$.
- On $(2, \infty)$, pick $x = 3$: $f'(3) = 3(3)(1) = 9 > 0$.

| Interval / Point | $(-\infty, 0)$ | $x = 0$ | $(0, 2)$ | $x = 2$ | $(2, \infty)$ |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Sign of $f'(x)$ | $+$ | $0$ | $-$ | $0$ | $+$ |
| Behavior of $f(x)$ | Strictly increasing | Local max: $2$ | Strictly decreasing | Local min: $-2$ | Strictly increasing |

Because $f$ is continuous on $\mathbb{R}$, monotonicity extends to the endpoints of each interval:

- $f$ is **strictly increasing** on $(-\infty, 0]$ and on $[2, \infty)$.
- $f$ is **strictly decreasing** on $[0, 2]$.

### Step 4: Classification of Extrema

- At $x = 0$, $f'(x)$ changes sign from $+$ to $-$, so $f$ attains a **local maximum** at $(0, 2)$ with value $f(0) = 2$.
- At $x = 2$, $f'(x)$ changes sign from $-$ to $+$, so $f$ attains a **local minimum** at $(2, -2)$ with value $f(2) = -2$.

To check for global extrema, observe the end behavior:

$$
\lim_{x \to -\infty} (x^3 - 3x^2 + 2) = -\infty, \qquad \lim_{x \to \infty} (x^3 - 3x^2 + 2) = +\infty.
$$

Because $f(x)$ takes arbitrarily large positive and negative values, $f$ has **no global maximum** and **no global minimum** on $\mathbb{R}$.

### Step 5: Supporting Features for an Accurate Sketch

To draw a faithful graph, we also locate the intercepts, inflection point, and a couple of helper points:

- **$y$-intercept:** $f(0) = 2$, giving $(0, 2)$, which coincides with the local maximum.
- **Zeros of $f$:** Notice $f(1) = 1 - 3 + 2 = 0$, so $x - 1$ is a factor:

$$
x^3 - 3x^2 + 2 = (x - 1)(x^2 - 2x - 2) = 0.
$$

Solving $x^2 - 2x - 2 = 0$ by the quadratic formula yields $x = 1 \pm \sqrt{3}$. Hence the three $x$-intercepts are

$$
x_1 = 1 - \sqrt{3} \approx -0.73, \qquad x_2 = 1, \qquad x_3 = 1 + \sqrt{3} \approx 2.73.
$$

- **Inflection point and symmetry:** Computing $f''(x) = 6x - 6 = 6(x - 1)$ shows $f''(x) = 0$ at $x = 1$, where $f(1) = 0$. The graph is concave downward on $(-\infty, 1)$ and concave upward on $(1, \infty)$, with central symmetry about the inflection point $(1, 0)$.
- **Helper points:** $f(-1) = -1 - 3 + 2 = -2$ and $f(3) = 27 - 27 + 2 = 2$.

### Step 6: Sketch of the Graph

```text
          y
          ^
       3 -|                                *
          |                               /
       2 -|       *(0, 2)                * (3, 2)
          |      / \   local max        /
       1 -|     /   \                  /
          |    /     \                /
   -------+---*-------*--------------*-----------> x
         -1  -0.73    1             2.73   3
          |  /         \            /
      -1 -| /           \          /
          |/             \        /
      -2 -* (-1, -2)      \      /
          |                *(2, -2)
      -3 -|                local min
```

Key marked points on the curve:

- Local maximum: $(0, 2)$
- Inflection point and zero: $(1, 0)$
- Local minimum: $(2, -2)$
- Remaining $x$-intercepts: $(1 - \sqrt{3}, 0)$ and $(1 + \sqrt{3}, 0)$

---

## 5. Final Answer & Conclusion

- **Domain:** $\mathbb{R}$.
- **Derivative:** $f'(x) = 3x(x - 2)$.
- **Critical points:** $(0, 2)$ and $(2, -2)$.
- **Monotonicity:**
  - Strictly increasing on $(-\infty, 0]$ and on $[2, \infty)$.
  - Strictly decreasing on $[0, 2]$.
- **Extrema:**
  - Local maximum at $x = 0$ with value $f(0) = 2$.
  - Local minimum at $x = 2$ with value $f(2) = -2$.
  - No global maximum or global minimum on $\mathbb{R}$.

---

## 6. Quick Verification

1. **Second Derivative Test check:** With $f''(x) = 6x - 6$, we find $f''(0) = -6 < 0$, confirming a local maximum at $x = 0$, and $f''(2) = 6 > 0$, confirming a local minimum at $x = 2$.
2. **Central symmetry check:** Substituting $x = 1 + h$ into $f$ gives

$$
f(1 + h) = (1 + h)^3 - 3(1 + h)^2 + 2 = (1 + 3h + 3h^2 + h^3) - (3 + 6h + 3h^2) + 2 = h^3 - 3h.
$$

Because $h^3 - 3h$ is an odd function of $h$, the graph is symmetric around $(1, 0)$. Indeed, the critical points $(1 - 1, 2) = (0, 2)$ and $(1 + 1, -2) = (2, -2)$ are exact reflections of each other across $(1, 0)$.

---

## 7. Common Mistakes to Avoid

- **Writing the increasing region as a union:** Students often write that $f$ is increasing on $(-\infty, 0) \cup (2, \infty)$. That is mathematically false because $0 < 2$ yet $f(0) = 2 > -2 = f(2)$. Always list the two intervals separately using the word "and".
- **Confusing the $x$-coordinate with the extremum value:** The location of the local minimum is $x = 2$, while the local minimum value is $f(2) = -2$, giving the point $(2, -2)$.
- **Forgetting to check whether local extrema are global:** A cubic polynomial with nonzero leading coefficient always goes to $+\infty$ on one side and $-\infty$ on the other, so its local extrema are never global extrema on $\mathbb{R}$.
- **Missing the factor $x = 0$ when solving $3x^2 - 6x = 0$:** Dividing both sides by $x$ loses the critical point $x = 0$. Always factor instead of dividing by a variable.

---

## 8. How I Would Explain This in Class

> "Think of the derivative as the speedometer of a roller coaster moving from left to right. Solving $f'(x) = 0$ finds the exact spots where the track goes momentarily flat, namely at $x = 0$ and $x = 2$. Before $0$ the slope is positive so we climb up to a hilltop at height $2$; between $0$ and $2$ the slope is negative so we drop down into a valley at height $-2$; after $2$ the slope turns positive again and we climb forever. Once you plot the hilltop, the valley, and the midpoint where the curve bends, the whole cubic draws itself."
