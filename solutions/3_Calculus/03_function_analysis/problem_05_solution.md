# Problem 05: An Exponential Function with a Maximum

## 1. The Original Problem

Analyze the monotonicity and extrema of

$$
f(x) = xe^{-x}.
$$

Also examine the behavior as $x \to \infty$ and explain how the limit affects the shape of the graph on the right-hand side.

---

## 2. What Are We Trying to Find?

1. The domain of $f(x) = xe^{-x}$, its sign and intercepts, and its first derivative $f'(x)$.
2. All critical points of $f$, the sign chart of $f'(x)$, and the exact intervals of monotonicity.
3. All local and global extrema of $f$.
4. The right-hand limit as $x \to \infty$, together with the left-hand behavior as $x \to -\infty$ for global completeness.
5. A clear geometric explanation of how $\lim_{x \to \infty} f(x) = 0$ shapes the right-hand side of the graph, illustrated with a qualitative sketch.

---

## 3. Before Calculating: What Idea Do We Need?

- **Strict positivity of the exponential function:** For every real number $x$, we have $e^{-x} > 0$. This means $e^{-x}$ never causes a zero, never changes sign, and can always be factored out when solving $f'(x) = 0$ or testing the sign of $f'(x)$.
- **Product rule and chain rule:** To differentiate $xe^{-x}$, use $(uv)' = u'v + uv'$ with $\frac{d}{dx}(e^{-x}) = -e^{-x}$.
- **Exponential dominance at infinity:** As $x \to \infty$, the exponential $e^x$ grows much faster than any power of $x$, so $\frac{x}{e^x} \to 0$. This can be justified rigorously by L'Hôpital's rule or an elementary inequality.
- **Global maximum from single turning point:** If a continuous function on $\mathbb{R}$ is strictly increasing on $(-\infty, c]$ and strictly decreasing on $[c, \infty)$, then $f(c)$ is automatically the unique global maximum on $\mathbb{R}$.

---

## 4. Step-by-Step Solution

### Step 1: Domain, Sign, and Intercepts

Both $x$ and $e^{-x}$ are defined and smooth on all of $\mathbb{R}$, so

$$
D_f = \mathbb{R}.
$$

Because $e^{-x} > 0$ for all $x \in \mathbb{R}$, the sign of $f(x) = xe^{-x}$ matches the sign of $x$:

- $f(x) < 0$ for $x < 0$.
- $f(0) = 0$, so $(0, 0)$ is both the unique $x$-intercept and the $y$-intercept.
- $f(x) > 0$ for $x > 0$.

### Step 2: First Derivative and Critical Points

Applying the product rule and chain rule gives

$$
f'(x) = 1 \cdot e^{-x} + x \cdot (-e^{-x}) = (1 - x)e^{-x}.
$$

Since $e^{-x} > 0$ for all $x \in \mathbb{R}$, setting $f'(x) = 0$ yields

$$
(1 - x)e^{-x} = 0 \iff 1 - x = 0 \iff x = 1.
$$

Thus, $x = 1$ is the unique critical number, with function value

$$
f(1) = 1 \cdot e^{-1} = \frac{1}{e} \approx 0.3679.
$$

### Step 3: Monotonicity and Extrema

Because $e^{-x} > 0$ everywhere, the sign of $f'(x) = (1 - x)e^{-x}$ is solely determined by $1 - x$:

- On $(-\infty, 1)$: $1 - x > 0 \implies f'(x) > 0$, so $f$ is strictly increasing on $(-\infty, 1]$.
- On $(1, \infty)$: $1 - x < 0 \implies f'(x) < 0$, so $f$ is strictly decreasing on $[1, \infty)$.

| Interval / Point | $(-\infty, 1)$ | $x = 1$ | $(1, \infty)$ |
| :--- | :---: | :---: | :---: |
| Sign of $f'(x)$ | $+$ | $0$ | $-$ |
| Behavior of $f(x)$ | Strictly increasing | Global max: $\frac{1}{e}$ | Strictly decreasing |

Consequently:

- At $x = 1$, $f'$ changes sign from $+$ to $-$, giving a local maximum at $\left(1, \frac{1}{e}\right)$.
- Because $f$ rises monotonically on $(-\infty, 1]$ and falls monotonically on $[1, \infty)$, the value $f(1) = \frac{1}{e}$ is the **unique global maximum** of $f$ on $\mathbb{R}$.
- There is **no local minimum** and **no global minimum**. Indeed, as $x \to -\infty$, we have $x \to -\infty$ and $e^{-x} \to +\infty$, so

$$
\lim_{x \to -\infty} xe^{-x} = -\infty.
$$

### Step 4: Behavior as $x \to \infty$

Rewrite $f(x)$ as a quotient:

$$
\lim_{x \to \infty} xe^{-x} = \lim_{x \to \infty} \frac{x}{e^x}.
$$

This has the indeterminate form $\frac{\infty}{\infty}$. Both numerator and denominator are differentiable on $\mathbb{R}$ with $(e^x)' = e^x \ne 0$, so L'Hôpital's rule applies:

$$
\lim_{x \to \infty} \frac{x}{e^x} = \lim_{x \to \infty} \frac{1}{e^x} = 0.
$$

We can also verify this limit without L'Hôpital's rule: for $x > 0$, the Maclaurin series of $e^x$ has all positive terms, so $e^x > 1 + x + \frac{x^2}{2} > \frac{x^2}{2}$. Hence

$$
0 < \frac{x}{e^x} < \frac{x}{\frac{x^2}{2}} = \frac{2}{x} \to 0 \quad \text{as } x \to \infty,
$$

and the Squeeze Theorem yields $\lim_{x \to \infty} xe^{-x} = 0$.

Therefore, the line $y = 0$ is a **horizontal asymptote** as $x \to +\infty$.

### Step 5: How the Limit Affects the Shape of the Graph on the Right-Hand Side

Combining positivity for $x > 0$, monotonicity on $[1, \infty)$, and $\lim_{x \to \infty} f(x) = 0$ reveals the exact right-hand geometry of the curve:

1. **Asymptotic decay from above:** After reaching its peak at $\left(1, \frac{1}{e}\right)$, the graph decreases smoothly, staying strictly above the $x$-axis because $f(x) = xe^{-x} > 0$ for every $x > 0$. It approaches the horizontal asymptote $y = 0$ arbitrarily closely without ever touching or crossing it again.
2. **Flattening slope:** Notice that $\lim_{x \to \infty} f'(x) = \lim_{x \to \infty} (1 - x)e^{-x} = 0^-$, so the curve becomes nearly horizontal as $x$ grows large.
3. **Forced inflection point on the right:** To bend away from crashing into the $x$-axis and instead level off along $y = 0$, the graph must switch from concave downward near its peak to concave upward further right. Indeed, computing the second derivative confirms

$$
f''(x) = (-1)e^{-x} + (1 - x)(-e^{-x}) = (x - 2)e^{-x},
$$

which changes sign from $-$ to $+$ at the inflection point $\left(2, \frac{2}{e^2}\right) \approx (2, 0.2707)$. Thus the curve is concave downward on $(-\infty, 2)$ and concave upward on $(2, \infty)$, creating the characteristic decaying tail on the right.

### Step 6: Qualitative Sketch

```text
          y
          ^
          |
    1/e  -|        * (1, 1/e) global max
          |       / \
   2/e^2 -|      /   * (2, 2/e^2) inflection point
          |     /     \__
          |    /         \______  -> y = 0 (horiz. asymptote)
   -------+---*------------------*-------------> x
          |  (0,0)  1   2   3   4
          |  /
          | /
          |/
          |
          v  (goes to -infinity as x -> -infinity)
```

---

## 5. Final Answer & Conclusion

- **Domain:** $\mathbb{R}$.
- **Derivative:** $f'(x) = (1 - x)e^{-x}$.
- **Monotonicity:** Strictly increasing on $(-\infty, 1]$ and strictly decreasing on $[1, \infty)$.
- **Extrema:** Global and local maximum at $x = 1$ with value $f(1) = \frac{1}{e}$. No local or global minimum since $\lim_{x \to -\infty} f(x) = -\infty$.
- **Limit as $x \to \infty$:** $\lim_{x \to \infty} xe^{-x} = 0$, giving the horizontal asymptote $y = 0$ on the right.
- **Effect on the right-hand shape:** Because $f(x) > 0$ for $x > 0$ and $f(x) \to 0$ as $x \to \infty$, the graph descends from its peak $\left(1, \frac{1}{e}\right)$, passes through an inflection point at $\left(2, \frac{2}{e^2}\right)$, and flattens out asymptotically above the positive $x$-axis without ever crossing it.

---

## 6. Quick Verification

1. **Second Derivative Test at $x = 1$:** Using $f''(x) = (x - 2)e^{-x}$, we evaluate $f''(1) = -e^{-1} < 0$, confirming a strict local maximum at $x = 1$.
2. **Numerical sample check:** Evaluating $f(x) = \frac{x}{e^x}$ at integer points gives
   - $f(0) = 0$,
   - $f(1) = e^{-1} \approx 0.3679$,
   - $f(2) = 2e^{-2} \approx 0.2707$,
   - $f(5) = 5e^{-5} \approx 0.0337$,
   - $f(10) = 10e^{-10} \approx 0.000454$.
   The values climb from $0$ up to $0.3679$ at $x = 1$ and then decay rapidly toward $0$ while remaining strictly positive.

---

## 7. Common Mistakes to Avoid

- **Forgetting the chain rule minus sign when differentiating $e^{-x}$:** Writing $(e^{-x})' = e^{-x}$ leads to $f'(x) = (1 + x)e^{-x}$, which puts the critical point at $x = -1$ instead of $x = +1$ and reverses the entire graph.
- **Trying to solve $e^{-x} = 0$ for extra critical points:** The exponential function $e^{-x}$ is strictly positive for all real $x$ and has no real zeros.
- **Treating $\lim_{x \to \infty} xe^{-x}$ as $\infty \cdot 0 = 0$ without justification:** The form $\infty \cdot 0$ is indeterminate; you must rewrite it as $\frac{x}{e^x}$ and apply L'Hôpital's rule or an explicit comparison bound.
- **Assuming $y = 0$ is also a horizontal asymptote as $x \to -\infty$:** On the left side, $e^{-x} \to +\infty$ instead of $0$, so $xe^{-x} \to -\infty$ rapidly. Horizontal asymptotes can be one-sided for exponential functions!

---

## 8. How I Would Explain This in Class

> "Picture a tug-of-war between two factors in $f(x) = x \cdot e^{-x}$ for positive $x$. At first, from $x = 0$ to $x = 1$, the linear factor $x$ wins and pulls the graph upward to its peak at height $\frac{1}{e}$. Right at $x = 1$, the two forces balance. Beyond $x = 1$, the exponential decay factor $e^{-x}$ takes over completely and crushes the linear growth, pulling the curve down toward $0$—yet because both factors stay positive, the curve can never cross below the $x$-axis and instead glides smoothly along it like an airplane landing on a runway."
