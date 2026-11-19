# Problem 13: A Logarithm and an Asymptote

## 1. The Original Problem

Perform a complete analysis of

$$
f(x) = \frac{\ln x}{x}, \qquad x > 0.
$$

Find the maximum and the behavior at the ends of the domain. Explain which information is necessary for a correct sketch.

---

## 2. What Are We Trying to Find?

1. The domain, continuity, zeros, and sign of $f(x) = \frac{\ln x}{x}$.
2. The limiting behavior at both ends of the domain, namely as $x \to 0^+$ and as $x \to +\infty$, together with all asymptotes.
3. The first derivative $f'(x)$, intervals of monotonicity, and the exact location and value of the maximum.
4. The second derivative $f''(x)$, intervals of concavity and convexity, and the inflection point.
5. A complete summary table and a sketch of the graph.
6. A clear explanation of which pieces of analytical information are strictly necessary to produce an accurate sketch.

---

## 3. Before Calculating: What Idea Do We Need?

- **Natural logarithm domain and sign:** $\ln x$ is defined only for $x > 0$, vanishes at $x = 1$, is negative on $(0, 1)$, and is positive on $(1, \infty)$.
- **Boundary limits on an open domain:** For a function defined on $(0, \infty)$, the two ends of the domain are $x \to 0^+$ and $x \to +\infty$. Always check whether each limit is determinate or an indeterminate form before applying L'Hôpital's rule.
- **Growth hierarchy:** For large $x$, $\ln x$ grows strictly slower than any positive power $x^p$, so $\lim_{x \to \infty} \frac{\ln x}{x} = 0$.
- **Role of curvature in sketching:** Knowing the peak and horizontal asymptote alone tells us the curve must descend toward $y = 0$, while $f''(x)$ reveals the exact inflection point where the curve switches from arching downward over the peak to flattening smoothly along the $x$-axis.

---

## 4. Step-by-Step Solution

### Step 1: Domain, Zeros, and Sign

The natural logarithm requires $x > 0$, which automatically ensures the denominator $x$ is nonzero. Thus the domain is

$$
D = (0, \infty).
$$

Since $D$ is not symmetric about $0$, $f$ is neither even nor odd. On $(0, \infty)$, $f$ is infinitely differentiable.

To find the zeros, solve

$$
\frac{\ln x}{x} = 0 \iff \ln x = 0 \iff x = 1.
$$

Thus $(1, 0)$ is the unique $x$-intercept. There is no $y$-intercept because $0 \notin D$. Since $x > 0$ on the entire domain, the sign of $f(x)$ matches the sign of $\ln x$:

- $f(x) < 0$ for $x \in (0, 1)$,
- $f(x) > 0$ for $x \in (1, \infty)$.

### Step 2: Behavior at the Ends of the Domain and Asymptotes

**Left end, as $x \to 0^+$:**
As $x \to 0^+$, we have $\ln x \to -\infty$ and $\frac{1}{x} \to +\infty$. This is **not** an indeterminate form; the product of a negatively diverging factor and a positively diverging factor diverges to $-\infty$:

$$
\lim_{x \to 0^+} \frac{\ln x}{x} = \lim_{x \to 0^+} \left(\ln x \cdot \frac{1}{x}\right) = -\infty.
$$

Therefore, the line $x = 0$ is a **right-hand vertical asymptote**, and the graph plunges steeply downward along the negative $y$-axis.

**Right end, as $x \to +\infty$:**
As $x \to +\infty$, both $\ln x \to +\infty$ and $x \to +\infty$, giving the indeterminate form $\frac{\infty}{\infty}$. Applying L'Hôpital's rule yields

$$
\lim_{x \to \infty} \frac{\ln x}{x} = \lim_{x \to \infty} \frac{\frac{1}{x}}{1} = \lim_{x \to \infty} \frac{1}{x} = 0.
$$

Because $f(x) > 0$ for all $x > 1$, the graph approaches $y = 0$ strictly from above as $x \to +\infty$. Hence the $x$-axis $y = 0$ is a **horizontal asymptote** on the right, and there is no oblique asymptote.

### Step 3: First Derivative, Monotonicity, and Maximum

Differentiate $f(x) = \frac{\ln x}{x}$ using the quotient rule:

$$
f'(x) = \frac{\frac{1}{x} \cdot x - (\ln x) \cdot 1}{x^2} = \frac{1 - \ln x}{x^2}.
$$

Since $x^2 > 0$ for all $x > 0$, the sign of $f'(x)$ is determined solely by $1 - \ln x$. Setting $f'(x) = 0$ gives

$$
1 - \ln x = 0 \iff \ln x = 1 \iff x = e \approx 2.718.
$$

Examining the sign of $1 - \ln x$ on either side of $x = e$:

- On $(0, e)$: $\ln x < 1 \implies f'(x) > 0$, so $f$ is strictly increasing.
- On $(e, \infty)$: $\ln x > 1 \implies f'(x) < 0$, so $f$ is strictly decreasing.

By continuity, $f$ is strictly increasing on $(0, e]$ and strictly decreasing on $[e, \infty)$. Therefore, at $x = e$, $f$ attains its **unique local maximum**, which is also its **global maximum** on $(0, \infty)$:

$$
f(e) = \frac{\ln e}{e} = \frac{1}{e} \approx 0.368.
$$

There is no local or global minimum because $f(x) \to -\infty$ as $x \to 0^+$. The range of $f$ is $\left(-\infty, \frac{1}{e}\right]$. Note also that at the zero $x = 1$, the slope is $f'(1) = \frac{1 - 0}{1} = 1$, so the curve crosses the $x$-axis at a $45^\circ$ angle.

### Step 4: Second Derivative, Convexity, and Inflection Point

Differentiate $f'(x) = \frac{1 - \ln x}{x^2}$ using the quotient rule:

$$
f''(x) = \frac{\left(-\frac{1}{x}\right) x^2 - (1 - \ln x)(2x)}{x^4} = \frac{-x - 2x + 2x\ln x}{x^4} = \frac{2\ln x - 3}{x^3}.
$$

Since $x^3 > 0$ for all $x > 0$, the sign of $f''(x)$ matches the sign of $2\ln x - 3$. Setting $f''(x) = 0$ gives

$$
2\ln x - 3 = 0 \iff \ln x = \frac{3}{2} \iff x = e^{3/2} = e\sqrt{e} \approx 4.482.
$$

Checking the sign on each side of $x = e^{3/2}$:

- On $(0, e^{3/2})$: $2\ln x < 3 \implies f''(x) < 0$, so $f$ is strictly concave (concave down).
- On $(e^{3/2}, \infty)$: $2\ln x > 3 \implies f''(x) > 0$, so $f$ is strictly convex (concave up).

Because $f''(x)$ changes sign at $x = e^{3/2}$, there is a unique **inflection point** at

$$
\left(e^{3/2}, \frac{\ln(e^{3/2})}{e^{3/2}}\right) = \left(e^{3/2}, \frac{3}{2e^{3/2}}\right) \approx (4.482, 0.335).
$$

### Step 5: Summary Table and Sketch

| Interval / Point | $f'(x)$ | $f''(x)$ | Behavior of $f(x)$ |
| :--- | :---: | :---: | :--- |
| $x \to 0^+$ | $+\infty$ | $-\infty$ | Vertical asymptote $x = 0$; $f(x) \to -\infty$ |
| $(0, 1)$ | $+$ | $-$ | Negative, strictly increasing, concave down |
| $x = 1$ | $+1$ | $-3$ | Unique zero at $(1, 0)$ with slope $1$ |
| $(1, e)$ | $+$ | $-$ | Positive, strictly increasing, concave down |
| $x = e$ | $0$ | $-e^{-3}$ | Local and global maximum at $\left(e, \frac{1}{e}\right)$ |
| $(e, e^{3/2})$ | $-$ | $-$ | Positive, strictly decreasing, concave down |
| $x = e^{3/2}$ | $-\frac{1}{2e^3}$ | $0$ | Inflection point at $\left(e^{3/2}, \frac{3}{2e^{3/2}}\right)$ |
| $(e^{3/2}, \infty)$ | $-$ | $+$ | Positive, strictly decreasing, concave up; $f(x) \to 0^+$ |

```text
          y
          ^
          |           M (e, 1/e) ~ (2.72, 0.37)
    0.4 + |           * * *
          |        *        * I (e^(3/2), 3/(2e^(3/2))) ~ (4.48, 0.33)
    0.2 + |      *            * *
          |     *                 * * * *  ---> y = 0+
    ------+----*------------------------------------------> x
          0   1        e        4.48          8
          |   *
          |  *
   -1.0 + |  *
          | *
          | *   x = 0 (vertical asymptote, y -> -infinity)
```

### Step 6: Which Information Is Necessary for a Correct Sketch?

Each ingredient in the analysis removes a specific geometric ambiguity and is genuinely needed for an accurate sketch:

1. **Domain $(0, \infty)$:** Restricts the entire graph to the right half-plane; without it, one might falsely draw a branch for $x < 0$.
2. **Boundary limits as $x \to 0^+$ and $x \to +\infty$:** Establish both asymptotes — showing that the curve dives to $-\infty$ along $x = 0$ on the left and decays asymptotically to $y = 0^+$ on the right rather than crossing below the $x$-axis or diverging.
3. **Unique zero $(1, 0)$:** Anchors the exact point where the graph crosses from negative to positive values.
4. **Monotonicity and global maximum $\left(e, \frac{1}{e}\right)$:** Fixes the exact peak height and confirms there is only one turning point — rising on $(0, e)$ and falling on $(e, \infty)$.
5. **Concavity and inflection point at $x = e^{3/2}$:** Determines the bending of the tail. Over the peak $x = e$, the curve is concave down; yet a decreasing positive curve that never hits the $x$-axis cannot remain concave down forever. The inflection point at $x = e^{3/2}$ pinpoints where the arch flips to concave up so that the curve can glide smoothly along $y = 0$.

---

## 5. Final Answer & Conclusion

- **Domain:** $D = (0, \infty)$.
- **Zero:** Unique zero at $(1, 0)$; $f(x) < 0$ on $(0, 1)$ and $f(x) > 0$ on $(1, \infty)$.
- **End behavior and asymptotes:** As $x \to 0^+$, $f(x) \to -\infty$, giving a vertical asymptote $x = 0$; as $x \to +\infty$, $f(x) \to 0^+$, giving a horizontal asymptote $y = 0$.
- **Monotonicity and maximum:** Strictly increasing on $(0, e]$, strictly decreasing on $[e, \infty)$, with a unique local and global maximum at $\left(e, \frac{1}{e}\right) \approx (2.718, 0.368)$ and no minimum.
- **Convexity and inflection point:** Strictly concave on $(0, e^{3/2})$, strictly convex on $(e^{3/2}, \infty)$, with a unique inflection point at $\left(e^{3/2}, \frac{3}{2e^{3/2}}\right) \approx (4.482, 0.335)$.
- **Essential sketching information:** Domain, both boundary limits (asymptotes), the zero $(1, 0)$, the unique maximum $(e, 1/e)$ with monotonicity intervals, and the inflection point at $x = e^{3/2}$ explaining the transition to the horizontal asymptote.

---

## 6. Quick Verification

1. **Famous inequality check, $e^\pi > \pi^e$:** Since $f(x) = \frac{\ln x}{x}$ is strictly decreasing on $[e, \infty)$ and $e < \pi$, we immediately obtain

$$
\frac{\ln e}{e} > \frac{\ln \pi}{\pi} \iff \pi \ln e > e \ln \pi \iff e^\pi > \pi^e.
$$

Numerically, $e^\pi \approx 23.141 > 22.459 \approx \pi^e$, confirming that $x = e$ indeed maximizes $\frac{\ln x}{x}$ and that $f$ decreases past $e$.

2. **Direct numerical spot checks:**
   - At $x = \frac{1}{e} \approx 0.368$: $f(e^{-1}) = \frac{-1}{e^{-1}} = -e \approx -2.718$, confirming rapid descent toward $-\infty$ near $0^+$.
   - At $x = 2$: $f(2) = \frac{\ln 2}{2} \approx 0.3466 < 0.3679 = f(e)$.
   - At $x = 4$: $f(4) = \frac{\ln 4}{4} = \frac{2\ln 2}{4} = \frac{\ln 2}{2} = f(2) \approx 0.3466$. Notice that $f(2) = f(4)$ nicely brackets the peak at $x = e \approx 2.718$ between $2$ and $4$!
   - At $x = e^2 \approx 7.389$: $f(e^2) = \frac{2}{e^2} \approx 0.2707$, decreasing toward $0^+$.

---

## 7. Common Mistakes to Avoid

- **Applying L'Hôpital's rule as $x \to 0^+$:** When $x \to 0^+$, the numerator $\ln x \to -\infty$ and the denominator $x \to 0^+$. This is **not** $\frac{0}{0}$ or $\frac{\infty}{\infty}$, so L'Hôpital's rule does not apply — misapplying it yields the limit of $\frac{1/x}{1}$, which diverges to $+\infty$ with the completely wrong sign!
- **Forgetting that $\ln x$ is undefined for $x \le 0$:** Sketching values on the left side of the $y$-axis ignores the domain restriction $x > 0$.
- **Thinking the function crosses the $x$-axis again for large $x$:** Because $\ln x > 0$ and $x > 0$ for all $x > 1$, the fraction $\frac{\ln x}{x}$ stays strictly positive forever and approaches $y = 0$ from above without ever touching it again.
- **Skipping the second derivative:** Without $f''(x) = \frac{2\ln x - 3}{x^3}$, it is easy to miss the inflection point at $x = e^{3/2}$ and draw the right tail with the wrong curvature.

---

## 8. How I Would Explain This in Class

> "The function $\frac{\ln x}{x}$ is a race between a slow runner, $\ln x$, and a fast runner, $x$. Near $x = 0^+$, $\ln x$ is deeply negative while dividing by a tiny positive $x$ magnifies that negativity into a vertical plunge down to $-\infty$. At $x = 1$, $\ln x$ catches its breath and crosses $0$. For a short stretch between $1$ and $e$, $\ln x$ rises quickly enough to push the ratio up to its highest point, $\frac{1}{e}$. After $x = e$, the linear denominator $x$ decisively outruns the sluggish logarithm, pulling the fraction slowly back toward $0$ from above — and to make that gentle landing onto the $x$-axis, the graph shifts from arching downward to cupping upward at $x = e^{3/2}$."
