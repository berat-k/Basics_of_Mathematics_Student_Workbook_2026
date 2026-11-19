# Problem 02: Powers, Roots, and the Domain

## 1. The Original Problem

For

$$
f(x)=2\sqrt{x}-\frac{3}{x^2}+x^{3/2}
$$

1. rewrite the function using powers,
2. determine the domain,
3. compute the derivative,
4. compare the domain of the function with the domain of its derivative.

---

## 2. What Are We Trying to Find?

1. An equivalent expression for $f(x)$ written purely as a linear combination of powers $c \cdot x^p$.
2. The natural real domain $D_f$ of the original function $f$.
3. The derivative $f'(x)$, obtained via the power rule and optionally written back in radical/fraction notation.
4. The domain of the derivative $f'$ and a clear comparison between the domain of $f$ and the domain of $f'$, explaining why they relate the way they do.

---

## 3. Before Calculating: What Idea Do We Need?

- **Algebraic exponent laws:** Roots and reciprocals can be converted into rational and negative exponents:

$$
\sqrt{x} = x^{1/2}, \qquad \frac{1}{x^n} = x^{-n}, \qquad x^{m/n} = \left(\sqrt[n]{x}\right)^m.
$$

- **The general power rule:** The rule $\frac{d}{dx}(x^p) = p x^{p-1}$ works for every real exponent $p$ — including fractions and negative numbers — wherever the expressions are defined.
- **Domain of a sum of functions:** The domain of a sum or difference is the intersection of the domains of all individual terms. Every term must be simultaneously defined as a real number:
  - Even roots like $\sqrt{x}$ require the radicand to be nonnegative, $x \ge 0$.
  - Fractions with $x$ in the denominator require the denominator to be nonzero, $x \ne 0$.
- **Relationship between the domains of $f$ and $f'$:** A function can only be differentiable at points where it is already defined, so $D_{f'} \subseteq D_f$ always holds. Sometimes the domain of $f'$ is strictly smaller than the domain of $f$, for instance when a root moves into a denominator after differentiation; other times both domains are equal.

---

## 4. Step-by-Step Solution

### Step 1: Rewrite the Function Using Powers

Convert each of the three terms of $f(x) = 2\sqrt{x} - \frac{3}{x^2} + x^{3/2}$ into the form $c x^p$:

- $2\sqrt{x} = 2x^{1/2}$.
- $-\frac{3}{x^2} = -3x^{-2}$.
- $x^{3/2}$ is already in power form.

Combining them gives:

$$
f(x) = 2x^{1/2} - 3x^{-2} + x^{3/2}.
$$

### Step 2: Determine the Domain of $f$

Check the real-number restriction for each term separately:

1. $2\sqrt{x}$ requires $x \ge 0$.
2. $-\frac{3}{x^2}$ requires $x^2 \ne 0$, which means $x \ne 0$.
3. $x^{3/2} = (\sqrt{x})^3$ requires $x \ge 0$.

For $f(x)$ to be defined, all three conditions must hold simultaneously:

$$
(x \ge 0) \text{ and } (x \ne 0) \text{ and } (x \ge 0) \iff x > 0.
$$

Therefore, the domain of $f$ is:

$$
D_f = (0, \infty).
$$

### Step 3: Compute the Derivative $f'(x)$

Apply the sum rule, constant-multiple rule, and general power rule $\frac{d}{dx}(x^p) = p x^{p-1}$ to each term of $f(x) = 2x^{1/2} - 3x^{-2} + x^{3/2}$:

- First term:

$$
\frac{d}{dx}\left(2x^{1/2}\right) = 2 \cdot \frac{1}{2} x^{\frac{1}{2} - 1} = x^{-1/2} = \frac{1}{\sqrt{x}}.
$$

- Second term:

$$
\frac{d}{dx}\left(-3x^{-2}\right) = -3 \cdot (-2) x^{-2 - 1} = 6x^{-3} = \frac{6}{x^3}.
$$

- Third term:

$$
\frac{d}{dx}\left(x^{3/2}\right) = \frac{3}{2} x^{\frac{3}{2} - 1} = \frac{3}{2} x^{1/2} = \frac{3}{2}\sqrt{x}.
$$

Putting the three terms together gives the derivative in both power form and radical/fraction form:

$$
f'(x) = x^{-1/2} + 6x^{-3} + \frac{3}{2} x^{1/2} = \frac{1}{\sqrt{x}} + \frac{6}{x^3} + \frac{3}{2}\sqrt{x}.
$$

### Step 4: Compare the Domain of $f$ with the Domain of $f'$

Find the domain of $f'(x) = \frac{1}{\sqrt{x}} + \frac{6}{x^3} + \frac{3}{2}\sqrt{x}$ by checking each term:

1. $\frac{1}{\sqrt{x}}$ requires $x \ge 0$ for the square root and $\sqrt{x} \ne 0$ for the denominator, so $x > 0$.
2. $\frac{6}{x^3}$ requires $x^3 \ne 0$, so $x \ne 0$.
3. $\frac{3}{2}\sqrt{x}$ requires $x \ge 0$.

The intersection of $x > 0$, $x \ne 0$, and $x \ge 0$ is again $x > 0$. Moreover, every point in $(0, \infty)$ is an interior point where each term is differentiable, so:

$$
D_{f'} = (0, \infty).
$$

**Comparison of the domains of $f$ and $f'$:**

| Function | Formula | Restrictions from Terms | Domain |
| :---: | :---: | :--- | :---: |
| $f(x)$ | $2\sqrt{x} - \frac{3}{x^2} + x^{3/2}$ | $x \ge 0$, $x \ne 0$, $x \ge 0$ | $(0, \infty)$ |
| $f'(x)$ | $\frac{1}{\sqrt{x}} + \frac{6}{x^3} + \frac{3}{2}\sqrt{x}$ | $x > 0$, $x \ne 0$, $x \ge 0$ | $(0, \infty)$ |

The two domains are **identical**: $D_{f'} = D_f = (0, \infty)$.

Why did the domain not shrink here? Differentiating $2\sqrt{x}$ individually does tighten its domain from $[0, \infty)$ to $(0, \infty)$, because $\frac{1}{\sqrt{x}}$ is undefined at $x = 0$. However, in the full function $f(x)$, the point $x = 0$ was **already excluded** by the term $-\frac{3}{x^2}$. Since no new points are lost when differentiating on $(0, \infty)$, the domain remains unchanged.

---

## 5. Final Answer & Conclusion

1. **Power form:** $f(x) = 2x^{1/2} - 3x^{-2} + x^{3/2}$.
2. **Domain of $f$:** $D_f = (0, \infty)$.
3. **Derivative:**

$$
f'(x) = x^{-1/2} + 6x^{-3} + \frac{3}{2} x^{1/2} = \frac{1}{\sqrt{x}} + \frac{6}{x^3} + \frac{3}{2}\sqrt{x}.
$$

4. **Domain comparison:** The domain of the derivative is $D_{f'} = (0, \infty)$, which is **equal** to the domain of the original function, $(0, \infty)$, because $x = 0$ was already excluded from the domain of $f$ by the fraction $-\frac{3}{x^2}$.

---

## 6. Quick Verification

1. **Numerical check at $x = 1$:**
   - Exact derivative:

$$
f'(1) = \frac{1}{\sqrt{1}} + \frac{6}{1^3} + \frac{3}{2}\sqrt{1} = 1 + 6 + 1.5 = 8.5.
$$

   - Difference quotient with $h = 0.001$: $f(1) = 2 - 3 + 1 = 0$ and $f(1.001) \approx 0.008491137$, so

$$
\frac{f(1.001) - f(1)}{0.001} \approx 8.491137 \approx 8.5.
$$

2. **Numerical check at $x = 4$:**
   - Exact derivative:

$$
f'(4) = \frac{1}{2} + \frac{6}{64} + \frac{3}{2}(2) = 0.5 + 0.09375 + 3 = 3.59375.
$$

   - Difference quotient with $h = 0.001$: $f(4) = 4 - \frac{3}{16} + 8 = 11.8125$ and $f(4.001) \approx 11.816093871$, giving

$$
\frac{f(4.001) - f(4)}{0.001} \approx 3.593871 \approx 3.59375.
$$

   Notice also that every term in $f'(x)$ is strictly positive on $(0, \infty)$, which confirms that $f$ is strictly increasing everywhere on its domain.

---

## 7. Common Mistakes to Avoid

- **Subtracting $1$ incorrectly from a negative exponent:** Writing $\frac{d}{dx}(x^{-2}) = -2x^{-1}$ instead of $-2x^{-3}$. Always remember that $-2 - 1 = -3$, moving further left on the number line.
- **Losing the double negative on $-3x^{-2}$:** Differentiating $-3x^{-2}$ multiplies $-3$ by $-2$, producing $+6x^{-3}$, not $-6x^{-3}$.
- **Differentiating a denominator directly without rewriting:** Writing $\frac{d}{dx}\left(-\frac{3}{x^2}\right) = -\frac{3}{2x}$ is completely invalid. Either rewrite as $-3x^{-2}$ and use the power rule, or apply the quotient rule.
- **Including $x = 0$ in the domain of $f$:** Seeing $\sqrt{x}$ and $x^{3/2}$ and writing $D_f = [0, \infty)$ forgets that $-\frac{3}{x^2}$ blows up at $x = 0$.

---

## 8. How I Would Explain This in Class

> "Before touching a single derivative rule, put every term into the same uniform: a number times $x$ to a power. Once $\sqrt{x}$ becomes $x^{1/2}$ and $\frac{1}{x^2}$ becomes $x^{-2}$, the exact same power rule handles all three pieces effortlessly — just watch your signs when subtracting $1$ from $-2$. Finally, always check the domain before and after differentiating: normally $\sqrt{x}$ loses $x = 0$ when you differentiate it, because its tangent becomes vertical there, but here $-\frac{3}{x^2}$ had already kicked $x = 0$ out of the club from the very beginning!"
