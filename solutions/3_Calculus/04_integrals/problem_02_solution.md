# Problem 02: Powers, Roots, and the Domain

## 1. The Original Problem

Compute

$$
\int \left(2\sqrt{x} + \frac{3}{x^2} - x^{1/3}\right)\,dx.
$$

First rewrite the terms as powers, determine the domain of the original expression, and verify the result by differentiation.

---

## 2. What Are We Trying to Find?

1. Rewrite every term of the integrand $f(x) = 2\sqrt{x} + \frac{3}{x^2} - x^{1/3}$ in power form $a x^n$.
2. Determine the exact real domain of the original integrand.
3. Compute the indefinite integral on that domain using linearity and the power rule.
4. Verify the resulting antiderivative explicitly by differentiation.

---

## 3. Before Calculating: What Idea Do We Need?

- **Laws of exponents for roots and reciprocals:**
  - $\sqrt{x} = x^{1/2}$ for $x \ge 0$,
  - $\frac{1}{x^2} = x^{-2}$ for $x \ne 0$,
  - $\sqrt[3]{x} = x^{1/3}$ for all $x \in \mathbb{R}$.
- **Domain of a sum of functions:** The domain of a sum or difference of expressions is the intersection of the individual domains of all terms.
- **Power rule for antiderivatives:** For any real exponent $n \ne -1$,

$$
\int x^n\,dx = \frac{x^{n+1}}{n+1} + C.
$$

- **Connectedness of the domain:** Because the domain here turns out to be the single connected open interval $(0, \infty)$, a single constant $C \in \mathbb{R}$ generates all antiderivatives on that domain.

---

## 4. Step-by-Step Solution

### Step 1: Rewrite Each Term as a Power

Convert the square root and the fraction into exponent notation so the power rule applies directly:

$$
2\sqrt{x} = 2x^{1/2}, \qquad \frac{3}{x^2} = 3x^{-2}, \qquad -x^{1/3} = -x^{1/3}.
$$

Thus the integrand becomes

$$
f(x) = 2x^{1/2} + 3x^{-2} - x^{1/3}.
$$

Notice that none of the exponents $\frac{1}{2}$, $-2$, or $\frac{1}{3}$ equals $-1$, so the power rule applies to all three terms.

### Step 2: Determine the Domain of the Original Expression

Inspect the domain condition for each term separately:

| Term | Domain condition | Individual domain |
| :--- | :--- | :--- |
| $2\sqrt{x}$ | The radicand of a square root must be nonnegative: $x \ge 0$ | $[0, \infty)$ |
| $\frac{3}{x^2}$ | The denominator cannot vanish: $x^2 \ne 0 \iff x \ne 0$ | $(-\infty, 0) \cup (0, \infty)$ |
| $-x^{1/3} = -\sqrt[3]{x}$ | Cube roots are defined for every real number | $(-\infty, \infty)$ |

Taking the intersection of all three domains gives

$$
D_f = [0, \infty) \cap \bigl((-\infty, 0) \cup (0, \infty)\bigr) \cap \mathbb{R} = (0, \infty).
$$

Therefore, the original expression is defined precisely for $x > 0$. Since $(0, \infty)$ is a single connected interval, every antiderivative on $(0, \infty)$ differs from any other by a single constant $C \in \mathbb{R}$.

### Step 3: Integrate Term by Term Using the Power Rule

On $(0, \infty)$, apply linearity and $\int x^n\,dx = \frac{x^{n+1}}{n+1} + C$:

1. First term, with $n = \frac{1}{2}$ so $n + 1 = \frac{3}{2}$:

$$
\int 2x^{1/2}\,dx = 2 \cdot \frac{x^{3/2}}{3/2} + C_1 = 2 \cdot \frac{2}{3}x^{3/2} + C_1 = \frac{4}{3}x^{3/2} + C_1.
$$

2. Second term, with $n = -2$ so $n + 1 = -1$:

$$
\int 3x^{-2}\,dx = 3 \cdot \frac{x^{-1}}{-1} + C_2 = -3x^{-1} + C_2 = -\frac{3}{x} + C_2.
$$

3. Third term, with $n = \frac{1}{3}$ so $n + 1 = \frac{4}{3}$:

$$
\int \bigl(-x^{1/3}\bigr)\,dx = -\frac{x^{4/3}}{4/3} + C_3 = -\frac{3}{4}x^{4/3} + C_3.
$$

Combining the three terms and merging the constants into $C = C_1 + C_2 + C_3 \in \mathbb{R}$ gives

$$
\int \left(2\sqrt{x} + \frac{3}{x^2} - x^{1/3}\right)\,dx = \frac{4}{3}x^{3/2} - \frac{3}{x} - \frac{3}{4}x^{4/3} + C, \qquad x > 0.
$$

Equivalently, written in radical form,

$$
F(x) = \frac{4}{3}x\sqrt{x} - \frac{3}{x} - \frac{3}{4}x\sqrt[3]{x} + C, \qquad x > 0.
$$

Notice that this antiderivative also has natural domain $x > 0$, matching the domain of the integrand.

### Step 4: Verify the Result by Differentiation

Let $F(x) = \frac{4}{3}x^{3/2} - 3x^{-1} - \frac{3}{4}x^{4/3} + C$ for $x > 0$. Differentiating term by term gives

$$
\begin{aligned}
F'(x) &= \frac{4}{3} \cdot \frac{3}{2}x^{(3/2) - 1} - 3(-1)x^{-1 - 1} - \frac{3}{4} \cdot \frac{4}{3}x^{(4/3) - 1} + 0 \\
&= 2x^{1/2} + 3x^{-2} - x^{1/3} \\
&= 2\sqrt{x} + \frac{3}{x^2} - x^{1/3}.
\end{aligned}
$$

The derivative reproduces the original integrand identically for every $x > 0$.

---

## 5. Final Answer & Conclusion

- **Power form of the integrand:** $2x^{1/2} + 3x^{-2} - x^{1/3}$.
- **Domain of the original expression:** $x > 0$, i.e., the interval $(0, \infty)$.
- **Indefinite integral on $(0, \infty)$:**

$$
\int \left(2\sqrt{x} + \frac{3}{x^2} - x^{1/3}\right)\,dx = \frac{4}{3}x^{3/2} - \frac{3}{x} - \frac{3}{4}x^{4/3} + C, \qquad x > 0, \quad C \in \mathbb{R}.
$$

- **Verification:** Differentiating $\frac{4}{3}x^{3/2} - 3x^{-1} - \frac{3}{4}x^{4/3} + C$ returns $2\sqrt{x} + \frac{3}{x^2} - x^{1/3}$ on $(0, \infty)$.

---

## 6. Quick Verification

1. **Exact evaluation of $F'(x)$ at a convenient perfect sixth power $x = 1$:**
   At $x = 1$:
   - Original integrand: $f(1) = 2\sqrt{1} + \frac{3}{1^2} - 1^{1/3} = 2 + 3 - 1 = 4$.
   - Derivative of $F(x)$ at $x = 1$: $F'(1) = 2(1) + 3(1) - 1 = 4$.
   Both agree exactly.

2. **Numerical derivative check at $x = 64$ (where both $\sqrt{x} = 8$ and $\sqrt[3]{x} = 4$ are integers):**
   - Original integrand:

$$
f(64) = 2(8) + \frac{3}{4096} - 4 = 12 + \frac{3}{4096} \approx 12.00073242.
$$

   - Using $F(x) = \frac{4}{3}x^{3/2} - \frac{3}{x} - \frac{3}{4}x^{4/3}$ with $h = 0.01$:

$$
F(64.01) \approx 490.739804, \qquad F(63.99) \approx 490.499790,
$$

$$
\frac{F(64.01) - F(63.99)}{0.02} \approx \frac{0.2400146}{0.02} \approx 12.000732 \approx f(64).
$$

   - Also check the sign of each term's derivative on $(0, \infty)$: $\frac{4}{3}x^{3/2}$ increases so its derivative $2\sqrt{x} > 0$; $-\frac{3}{x}$ increases as $x$ grows so its derivative $+\frac{3}{x^2} > 0$; $-\frac{3}{4}x^{4/3}$ decreases so its derivative $-x^{1/3} < 0$. All three signs match.

---

## 7. Common Mistakes to Avoid

- **Integrating the denominator directly:** Writing $\int \frac{3}{x^2}\,dx = \frac{3}{x^3/3}$ is completely wrong because the power rule does not apply inside a denominator. You must first rewrite $\frac{3}{x^2}$ as $3x^{-2}$, which increases the exponent from $-2$ to $-1$ and produces $-3x^{-1} = -\frac{3}{x}$.
- **Missing the negative sign when dividing by $-1$:** Forgetting the minus sign in $\frac{x^{-1}}{-1} = -\frac{1}{x}$ yields $+\frac{3}{x}$, whose derivative is $-\frac{3}{x^2}$ instead of $+\frac{3}{x^2}$.
- **Misstating the domain as $x \ge 0$:** While $\sqrt{x}$ allows $x = 0$, the term $\frac{3}{x^2}$ blows up at $x = 0$. The intersection of $x \ge 0$ and $x \ne 0$ is strictly $x > 0$.
- **Inverting fractional divisors incorrectly:** Dividing by $\frac{3}{2}$ means multiplying by $\frac{2}{3}$, not $\frac{3}{2}$. Thus $2 \div \frac{3}{2} = \frac{4}{3}$, not $3$.

---

## 8. How I Would Explain This in Class

> "Before you integrate anything with roots or fractions, put every term into the same uniform—exponent notation $a x^n$—and check where the original expression actually makes sense. Here the square root blocks negative numbers and the fraction blocks zero, so we live strictly on $x > 0$. Once every term wears its power-form uniform, the same single rule handles all three pieces: add one to the exponent, divide by the new exponent, and flip any fraction in the denominator. Finally, differentiate right back to make sure every sign and fraction cancels cleanly."
