# Problem 09: A Logarithm and the Chain Rule

## 1. The Original Problem

For

$$
f(x) = \ln(x^2 + 1)
$$

compute the derivative. Then determine the sign of $f'(x)$ for $x < 0$, $x = 0$, and $x > 0$, and describe qualitatively how the function behaves around zero.

---

## 2. What Are We Trying to Find?

1. The domain of $f(x) = \ln(x^2 + 1)$, to ensure the logarithm and its derivative are well-defined everywhere we evaluate them.
2. The first derivative $f'(x)$, obtained by applying the chain rule to the logarithmic composition.
3. The sign of $f'(x)$ in each of the three cases $x < 0$, $x = 0$, and $x > 0$, organized into a clear sign analysis.
4. A qualitative description of the behavior of $f(x)$ around $x = 0$, including monotonicity, tangent slope, symmetry, and the nature of the extremum at $x = 0$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Domain of the natural logarithm:** The expression $\ln(u)$ is defined if and only if $u > 0$. Here $u = x^2 + 1 \ge 1 > 0$ for every real number $x$, so $f$ is defined on the entire real line $\mathbb{R}$.
- **Chain rule for a natural logarithm:** If $u = g(x)$ is differentiable and $g(x) > 0$, then

$$
\frac{d}{dx}\bigl[\ln(g(x))\bigr] = \frac{1}{g(x)} \cdot g'(x) = \frac{g'(x)}{g(x)}.
$$

- **Sign analysis of a fraction:** When a denominator is strictly positive for all real $x$, the sign of the fraction is completely determined by the sign of its numerator.
- **First derivative and local behavior:**
  - Where $f'(x) < 0$ on an interval, $f$ is strictly decreasing.
  - Where $f'(x) > 0$ on an interval, $f$ is strictly increasing.
  - Where $f'(x)$ changes sign from negative to positive at a point $c$ with $f'(c) = 0$, the graph has a horizontal tangent line and attains a local minimum at $x = c$.

---

## 4. Step-by-Step Solution

### Step 1: Check the Domain and Identify the Composite Structure

For every real number $x$, we have $x^2 \ge 0$, which implies

$$
x^2 + 1 \ge 1 > 0.
$$

Because the argument of the natural logarithm is strictly positive everywhere, the domain of $f$ is all real numbers, $D_f = \mathbb{R}$.

Notice that $f(x) = \ln(x^2 + 1)$ is a composition of two functions:
- Outer function: $g(u) = \ln u$, whose derivative is $g'(u) = \frac{1}{u}$.
- Inner function: $u(x) = x^2 + 1$, whose derivative is $u'(x) = 2x$.

### Step 2: Compute the Derivative Using the Chain Rule

Applying the chain rule $f'(x) = g'(u(x)) \cdot u'(x)$, we differentiate the outer logarithm first, evaluate it at the inner expression $x^2 + 1$, and multiply by the derivative of the inner expression:

$$
f'(x) = \frac{1}{x^2 + 1} \cdot \frac{d}{dx}(x^2 + 1) = \frac{1}{x^2 + 1} \cdot 2x = \frac{2x}{x^2 + 1}.
$$

Since $x^2 + 1 \ge 1 > 0$ for every $x \in \mathbb{R}$, the derivative $f'(x)$ is also defined for all $x \in \mathbb{R}$.

### Step 3: Determine the Sign of $f'(x)$ for $x < 0$, $x = 0$, and $x > 0$

Examine the numerator and denominator of

$$
f'(x) = \frac{2x}{x^2 + 1}
$$

separately:
- **Denominator:** For every real $x$, we have $x^2 + 1 \ge 1 > 0$, so the denominator is always strictly positive and never zero.
- **Numerator:** The expression $2x$ is negative when $x < 0$, equal to $0$ when $x = 0$, and positive when $x > 0$.

Dividing by a strictly positive quantity preserves the sign of the numerator. Therefore:
- For $x < 0$: $2x < 0$ and $x^2 + 1 > 0$, so $f'(x) < 0$.
- For $x = 0$: $2(0) = 0$ and $0^2 + 1 = 1$, so $f'(0) = 0$.
- For $x > 0$: $2x > 0$ and $x^2 + 1 > 0$, so $f'(x) > 0$.

We summarize this sign analysis in a table:

| Interval or Point | Sign of $2x$ | Sign of $x^2 + 1$ | Sign of $f'(x)$ | Behavior of $f(x)$ |
| :--- | :---: | :---: | :---: | :--- |
| $x < 0$ | $-$ | $+$ | $-$ | Strictly decreasing |
| $x = 0$ | $0$ | $+$ | $0$ | Horizontal tangent, local and global minimum |
| $x > 0$ | $+$ | $+$ | $+$ | Strictly increasing |

### Step 4: Describe Qualitatively How $f(x)$ Behaves Around Zero

First compute the function value at $x = 0$:

$$
f(0) = \ln(0^2 + 1) = \ln(1) = 0.
$$

Combining the value $f(0) = 0$ with our sign analysis gives a complete qualitative picture near $x = 0$:

1. **Smooth valley at the origin:** As $x$ approaches $0$ from the left, $f'(x) < 0$, so the graph slopes downward toward the point with coordinates $x = 0$ and $y = 0$.
2. **Horizontal tangent at $x = 0$:** Because $f'(0) = 0$, the tangent line at the origin is the horizontal line $y = 0$, meaning the curve levels off smoothly rather than forming a sharp corner.
3. **Rising for positive $x$:** Immediately to the right of $x = 0$, we have $f'(x) > 0$, so the graph turns upward and increases smoothly.
4. **Strict local and global minimum:** Because $f$ is strictly decreasing on $(-\infty, 0]$ and strictly increasing on $[0, \infty)$, the value $f(0) = 0$ is not only a local minimum, it is the unique global minimum of $f$ on $\mathbb{R}$.
5. **Mirror symmetry:** Since $f(-x) = \ln((-x)^2 + 1) = \ln(x^2 + 1) = f(x)$, the function is even, so the valley around $x = 0$ is perfectly symmetric with respect to the $y$-axis.

A qualitative sketch of $y = \ln(x^2 + 1)$ around $x = 0$ looks like a smooth, symmetric bowl touching the $x$-axis at the origin:

```text
  y
  ^
  |  \                   /
  |   \                 /     y = ln(x^2 + 1)
  |    \               /
  |     \             /       f'(x) < 0 for x < 0
  |       \         /         f'(0) = 0 (horizontal tangent)
  |         \_____/           f'(x) > 0 for x > 0
--+------------*------------+--> x
               0
```

---

## 5. Final Answer & Conclusion

- **Derivative:**

$$
f'(x) = \frac{2x}{x^2 + 1}, \qquad x \in \mathbb{R}.
$$

- **Sign of the derivative:**
  - $f'(x) < 0$ for all $x < 0$,
  - $f'(0) = 0$ at $x = 0$,
  - $f'(x) > 0$ for all $x > 0$.
- **Qualitative behavior around $x = 0$:** The function decreases strictly to the left of $0$, levels off smoothly with a horizontal tangent line $y = 0$ at the origin where $f(0) = 0$, and increases strictly to the right of $0$. Hence $f$ has a smooth, symmetric local and global minimum at $x = 0$.

---

## 6. Quick Verification

1. **Direct algebraic check of the minimum:** For any $x \ne 0$, we have $x^2 > 0$, so $x^2 + 1 > 1$. Because $\ln u$ is strictly increasing and $\ln 1 = 0$, it follows directly that

$$
f(x) = \ln(x^2 + 1) > \ln(1) = 0 = f(0) \qquad \text{for all } x \ne 0.
$$

This independently confirms that $x = 0$ is the unique global minimum.

2. **Symmetry check on the derivative:** Since $f$ is an even function, its derivative must be an odd function. Checking our formula:

$$
f'(-x) = \frac{2(-x)}{(-x)^2 + 1} = -\frac{2x}{x^2 + 1} = -f'(x).
$$

This matches the expected symmetry, and forces $f'(0) = -f'(0)$, so $f'(0) = 0$.

3. **Numerical slope check at $x = -1$, $x = 0$, and $x = 1$:** Using the central difference $\frac{f(x + h) - f(x - h)}{2h}$ with $h = 10^{-4}$:
  - At $x = -1$: our formula gives $f'(-1) = \frac{-2}{2} = -1$, and $\frac{\ln(1.99980001) - \ln(2.00020001)}{0.0002} \approx -1.000000$.
  - At $x = 0$: our formula gives $f'(0) = 0$, and $\frac{f(10^{-4}) - f(-10^{-4})}{2 \times 10^{-4}} = 0$ identically by even symmetry.
  - At $x = 1$: our formula gives $f'(1) = \frac{2}{2} = 1$, and $\frac{\ln(2.00020001) - \ln(1.99980001)}{0.0002} \approx 1.000000$.

---

## 7. Common Mistakes to Avoid

- **Forgetting the chain rule factor $2x$:** Writing $f'(x) = \frac{1}{x^2 + 1}$ ignores the derivative of the inner function $x^2 + 1$. Notice that $\frac{1}{x^2 + 1}$ is positive everywhere, which would falsely claim that $f$ is always increasing—contradicting the fact that $f(-1) = \ln 2 > 0 = f(0)$.
- **Splitting the logarithm incorrectly:** Writing $\ln(x^2 + 1) = \ln(x^2) + \ln(1)$ is algebraically invalid. Logarithms turn *products* into sums, never sums into sums.
- **Worrying about the denominator changing sign:** Some students try to solve $x^2 + 1 = 0$ over the real numbers or mistakenly assume the denominator could be negative for $x < 0$. Because $x^2 \ge 0$ for all real $x$, the denominator $x^2 + 1$ is strictly positive everywhere.
- **Confusing $f'(0) = 0$ with an automatic minimum without checking signs:** Having $f'(0) = 0$ only tells us the tangent line is horizontal. We must check that $f'(x)$ changes sign from negative to positive across $x = 0$ to conclude that $x = 0$ is a minimum rather than a maximum or a flat inflection point like $y = x^3$.

---

## 8. How I Would Explain This in Class

> "Whenever you differentiate the natural logarithm of a box, the rule is always the same: put the derivative of the box on top, and the untouched box on the bottom. Here the box is $x^2 + 1$, its derivative is $2x$, so the derivative is immediately $\frac{2x}{x^2 + 1}$. Now look at the denominator $x^2 + 1$: it is always at least $1$, so it is a strictly positive passenger that can never flip the sign. That means the numerator $2x$ drives the entire story—downhill to the left of zero, completely flat right at zero, and uphill to the right of zero, forming a smooth symmetric bowl resting gently on the origin."
