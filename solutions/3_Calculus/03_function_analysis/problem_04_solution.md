# Problem 04: A Function with Two Vertical Asymptotes

## 1. The Original Problem

Analyze

$$
f(x) = \frac{1}{x^2 - 1}.
$$

Determine the domain, asymptotes, sign, and monotonicity on the intervals of the domain. Explain why each interval must be analyzed separately.

---

## 2. What Are We Trying to Find?

1. The domain $D_f$ of $f(x) = \frac{1}{x^2 - 1}$, decomposed into its maximal open intervals.
2. All vertical and horizontal asymptotes, including all four one-sided limits at the vertical asymptotes and both limits at $\pm\infty$.
3. The sign of $f(x)$ on each interval of the domain, along with any intercepts and symmetry.
4. The first derivative $f'(x)$, its critical points, its sign on each subinterval, the exact intervals of monotonicity, and any local extrema.
5. A clear mathematical and concrete explanation of why each connected interval of the domain must be analyzed separately.

---

## 3. Before Calculating: What Idea Do We Need?

- **Factoring the denominator:** Writing $x^2 - 1 = (x - 1)(x + 1)$ immediately reveals both excluded points, the sign changes of $f(x)$, and the signs of the one-sided limits near $x = -1$ and $x = 1$.
- **Even symmetry:** Checking $f(-x) = f(x)$ cuts the conceptual work in half and provides a built-in consistency check on every limit, sign, and monotonicity interval.
- **Role of connectedness in the Mean Value Theorem:** The theorem that $f' > 0$ implies $f$ is increasing applies only on an *interval* where $f$ is continuous and differentiable. Across a missing point such as a vertical asymptote, values can jump discontinuously, breaking monotonicity across the gap.

---

## 4. Step-by-Step Solution

### Step 1: Domain and Symmetry

The denominator $x^2 - 1 = (x - 1)(x + 1)$ vanishes at $x = -1$ and $x = 1$. Removing these two points splits the real line into three disjoint open intervals:

$$
D_f = \mathbb{R} \setminus \{-1, 1\} = (-\infty, -1) \cup (-1, 1) \cup (1, \infty).
$$

Notice also that $D_f$ is symmetric about $0$ and

$$
f(-x) = \frac{1}{(-x)^2 - 1} = \frac{1}{x^2 - 1} = f(x).
$$

Hence $f$ is an **even function**, so its graph is symmetric with respect to the $y$-axis.

### Step 2: Sign of $f(x)$ and Intercepts

Because the numerator is the constant $1 > 0$, the sign of $f(x)$ is identical to the sign of the denominator $x^2 - 1 = (x - 1)(x + 1)$, and $f(x)$ is never zero:

- On $(-\infty, -1)$: both $x - 1 < 0$ and $x + 1 < 0$, so $x^2 - 1 > 0$ and $f(x) > 0$.
- On $(-1, 1)$: $x - 1 < 0$ and $x + 1 > 0$, so $x^2 - 1 < 0$ and $f(x) < 0$.
- On $(1, \infty)$: both $x - 1 > 0$ and $x + 1 > 0$, so $x^2 - 1 > 0$ and $f(x) > 0$.

Therefore:

- **$x$-intercepts:** None, since $\frac{1}{x^2 - 1} \ne 0$ for all $x \in D_f$.
- **$y$-intercept:** $f(0) = \frac{1}{0 - 1} = -1$, giving the point $(0, -1)$.

### Step 3: Asymptotes

**Vertical asymptote at $x = -1$:**
As $x \to -1$, the numerator is $1 > 0$ and the denominator $x^2 - 1 \to 0$:

$$
\lim_{x \to -1^-} \frac{1}{x^2 - 1} = +\infty \quad \text{since } x^2 - 1 \to 0^+,
$$

$$
\lim_{x \to -1^+} \frac{1}{x^2 - 1} = -\infty \quad \text{since } x^2 - 1 \to 0^-.
$$

Thus $x = -1$ is a **vertical asymptote**.

**Vertical asymptote at $x = 1$:**
Similarly,

$$
\lim_{x \to 1^-} \frac{1}{x^2 - 1} = -\infty \quad \text{since } x^2 - 1 \to 0^-,
$$

$$
\lim_{x \to 1^+} \frac{1}{x^2 - 1} = +\infty \quad \text{since } x^2 - 1 \to 0^+.
$$

Thus $x = 1$ is a **vertical asymptote**.

**Horizontal asymptote:**
As $|x| \to \infty$, $x^2 - 1 \to +\infty$, so

$$
\lim_{x \to -\infty} \frac{1}{x^2 - 1} = 0, \qquad \lim_{x \to +\infty} \frac{1}{x^2 - 1} = 0.
$$

Therefore, $y = 0$ is a **horizontal asymptote** on both sides, and since $f(x) > 0$ for $|x| > 1$, the graph approaches the $x$-axis from above as $x \to \pm\infty$. There are no oblique asymptotes.

### Step 4: Derivative, Monotonicity, and Local Extremum

Writing $f(x) = (x^2 - 1)^{-1}$ and applying the chain rule for $x \in D_f$ yields

$$
f'(x) = -(x^2 - 1)^{-2} \cdot 2x = \frac{-2x}{(x^2 - 1)^2}.
$$

Since $(x^2 - 1)^2 > 0$ for every $x \in D_f$, the sign of $f'(x)$ is completely determined by the numerator $-2x$:

- $f'(x) = 0 \iff -2x = 0 \iff x = 0$, which lies in the middle interval $(-1, 1)$.
- For $x < 0$ in $D_f$, $-2x > 0$, so $f'(x) > 0$.
- For $x > 0$ in $D_f$, $-2x < 0$, so $f'(x) < 0$.

Combining the domain intervals with the critical point $x = 0$ produces four monotonicity intervals:

| Interval / Point | $(-\infty, -1)$ | $x = -1$ | $(-1, 0)$ | $x = 0$ | $(0, 1)$ | $x = 1$ | $(1, \infty)$ |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of $f(x)$ | $+$ | Undef. | $-$ | $-1$ | $-$ | Undef. | $+$ |
| Sign of $f'(x)$ | $+$ | Undef. | $+$ | $0$ | $-$ | Undef. | $-$ |
| Behavior of $f(x)$ | Increasing | Vert. asy. | Increasing | Local max | Decreasing | Vert. asy. | Decreasing |

Thus:

- $f$ is **strictly increasing** on $(-\infty, -1)$ and **strictly increasing** on $(-1, 0]$.
- $f$ is **strictly decreasing** on $[0, 1)$ and **strictly decreasing** on $(1, \infty)$.
- At $x = 0$, $f'$ changes sign from $+$ to $-$, so $(0, -1)$ is a **local maximum** of $f$. There are no global extrema because $f(x)$ takes arbitrarily large positive and negative values near $x = \pm 1$.

### Step 5: Why Each Interval Must Be Analyzed Separately

Analyzing each connected interval of the domain separately is essential for both theoretical and concrete reasons:

1. **Theoretical reason:** The link between the sign of $f'$ and monotonicity comes from the Mean Value Theorem: for any $a < b$, there exists $c \in (a, b)$ with $f(b) - f(a) = f'(c)(b - a)$ *only when* $f$ is continuous on $[a, b]$ and differentiable on $(a, b)$. If $a$ and $b$ lie on opposite sides of $x = -1$ or $x = 1$, then $f$ is not even defined on all of $[a, b]$, so the Mean Value Theorem does not apply and the sign of $f'$ cannot compare $f(a)$ with $f(b)$.
2. **Concrete counterexample on the left:** Although $f'(x) > 0$ on both $(-\infty, -1)$ and $(-1, 0)$, the function is **not** increasing across $x = -1$. Choose $a = -2 \in (-\infty, -1)$ and $b = -\frac{1}{2} \in (-1, 0)$. Then $a < b$, yet

$$
f(-2) = \frac{1}{4 - 1} = \frac{1}{3} > -\frac{4}{3} = \frac{1}{\frac{1}{4} - 1} = f\left(-\frac{1}{2}\right).
$$

Across the vertical asymptote $x = -1$, the curve climbs to $+\infty$ on the left and restarts from $-\infty$ on the right.
3. **Concrete counterexample on the right:** Similarly, $f'(x) < 0$ on both $(0, 1)$ and $(1, \infty)$, yet for $\frac{1}{2} < 2$ we have $f\left(\frac{1}{2}\right) = -\frac{4}{3} < \frac{1}{3} = f(2)$. Furthermore, the sign of $f(x)$ itself changes across each vertical asymptote, jumping from positive to negative at $x = -1$ and from negative to positive at $x = 1$.

Hence every property—sign, limits, and monotonicity—must be stated and checked independently on $(-\infty, -1)$, $(-1, 1)$, and $(1, \infty)$.

### Step 6: Qualitative Sketch

```text
                y
                ^
           x=-1 :      : x=1
             |  :      :  |
             |  :      :  |
             \  :      :  /
        ______\ :      : /______   y = 0 (horiz. asymptote)
    -----------+--------+-----------> x
              -1   0    1
                :  *   :
                : / \  :   (0, -1) local max
                :/   \ :
                :|   | :
                :v   v :
```

---

## 5. Final Answer & Conclusion

- **Domain:** $D_f = (-\infty, -1) \cup (-1, 1) \cup (1, \infty)$.
- **Asymptotes:**
  - Vertical asymptote at $x = -1$, approaching $+\infty$ from the left and $-\infty$ from the right.
  - Vertical asymptote at $x = 1$, approaching $-\infty$ from the left and $+\infty$ from the right.
  - Horizontal asymptote $y = 0$ as $x \to \pm\infty$.
- **Sign of $f(x)$:** Positive on $(-\infty, -1)$ and $(1, \infty)$; negative on $(-1, 1)$; no zeros.
- **Monotonicity and Extrema:**
  - Strictly increasing on $(-\infty, -1)$ and on $(-1, 0]$.
  - Strictly decreasing on $[0, 1)$ and on $(1, \infty)$.
  - Local maximum at $(0, -1)$; no global extrema.
- **Why intervals are analyzed separately:** Vertical asymptotes break continuity and disconnect the domain, so the Mean Value Theorem does not bridge across $x = \pm 1$; both the sign of $f$ and the ordering of function values reverse across each asymptote.

---

## 6. Quick Verification

1. **Second Derivative Test at $x = 0$:** Differentiating $f'(x) = \frac{-2x}{(x^2 - 1)^2}$ via the quotient rule gives

$$
f''(x) = \frac{-2(x^2 - 1)^2 - (-2x) \cdot 2(x^2 - 1)(2x)}{(x^2 - 1)^4} = \frac{-2(x^2 - 1) + 8x^2}{(x^2 - 1)^3} = \frac{6x^2 + 2}{(x^2 - 1)^3}.
$$

At $x = 0$, $f''(0) = \frac{2}{-1} = -2 < 0$, confirming a local maximum at $(0, -1)$. Moreover, $f''(x) > 0$ for $|x| > 1$ and $f''(x) < 0$ for $|x| < 1$, matching the upward-opening outer wings and downward-opening middle arch in the sketch.
2. **Numerical check on every subinterval:**
   - On $(-\infty, -1)$: $f(-3) = \frac{1}{8} < \frac{1}{3} = f(-2)$ (increasing, positive).
   - On $(-1, 0]$: $f(-0.5) = -\frac{4}{3} < -1 = f(0)$ (increasing, negative).
   - On $[0, 1)$: $f(0) = -1 > -\frac{4}{3} = f(0.5)$ (decreasing, negative).
   - On $(1, \infty)$: $f(2) = \frac{1}{3} > \frac{1}{8} = f(3)$ (decreasing, positive).

---

## 7. Common Mistakes to Avoid

- **Merging intervals across a vertical asymptote:** Writing that $f$ is increasing on $(-\infty, 0) \setminus \{-1\}$ or $(-\infty, -1) \cup (-1, 0)$ is false because $f(-2) = \frac{1}{3} > -\frac{4}{3} = f(-0.5)$.
- **Mistaking $(0, -1)$ for a global maximum:** Even though $x = 0$ is the only critical point and $f'(x)$ changes from $+$ to $-$, the outer branches take arbitrarily large positive values, so $(0, -1)$ is strictly a local maximum.
- **Forgetting that $f(x)$ has negative values on $(-1, 1)$:** Because the numerator is $1$ and $x^2 \ge 0$, some students carelessly assume $f(x) > 0$ everywhere, forgetting that $x^2 < 1$ when $|x| < 1$.
- **Miscomputing the derivative as $\frac{1}{2x}$:** You cannot differentiate the denominator independently; you must apply the chain rule or quotient rule to $(x^2 - 1)^{-1}$.

---

## 8. How I Would Explain This in Class

> "Think of the two vertical asymptotes $x = -1$ and $x = 1$ as two brick walls dividing the real line into three separate rooms. Calculus only lets you track height changes while you walk continuously inside one room at a time. In the left room you climb uphill from floor level $0$ up toward the ceiling $+\infty$; then you teleport through the wall into the middle room, where you emerge from the basement $-\infty$, rise up to a cozy arch peak at $(0, -1)$, and drop back to $-\infty$; finally you cross the second wall into the right room and slide down from $+\infty$ back toward $0$. Never combine two rooms into one monotonicity claim!"
