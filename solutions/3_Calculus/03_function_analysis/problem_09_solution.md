# Problem 09: An Oblique Asymptote

## 1. The Original Problem

Analyze the asymptotes of

$$
f(x) = \frac{x^2 + 1}{x - 1}.
$$

Perform polynomial division and explain why the remainder term vanishes for large $|x|$.

---

## 2. What Are We Trying to Find?

1. The domain of $f(x) = \frac{x^2 + 1}{x - 1}$.
2. All vertical asymptotes of $f$, verified using one-sided limits.
3. The polynomial division of $x^2 + 1$ by $x - 1$, rewriting $f(x)$ as a linear part plus a proper rational remainder.
4. A clear explanation of why the remainder term vanishes as $|x| \to \infty$ and why this yields an oblique asymptote.
5. Confirmation of the oblique asymptote via the standard limit formulas for $m$ and $b$, as well as checking whether any horizontal asymptotes exist.
6. The position of the graph relative to the oblique asymptote for $x < 1$ and $x > 1$, illustrated with a qualitative sketch.

---

## 3. Before Calculating: What Idea Do We Need?

- **Domain of a rational function:** A fraction $\frac{P(x)}{Q(x)}$ is defined wherever $Q(x) \ne 0$. Points where $Q(x) = 0$ and $P(x) \ne 0$ are candidates for vertical asymptotes.
- **Vertical asymptote:** The line $x = c$ is a vertical asymptote if at least one of the one-sided limits from the left or right of $c$ diverges to $+\infty$ or $-\infty$:

$$
\lim_{x \to c^-} f(x) = \pm\infty \qquad \text{or} \qquad \lim_{x \to c^+} f(x) = \pm\infty.
$$

- **Degree rule for rational functions:** When $\deg(P) = \deg(Q) + 1$, polynomial long division writes

$$
\frac{P(x)}{Q(x)} = mx + b + \frac{R(x)}{Q(x)},
$$

where $\deg(R) < \deg(Q)$. Because the denominator outgrows the numerator as $|x| \to \infty$, the remainder fraction $\frac{R(x)}{Q(x)}$ tends to $0$, leaving the line $y = mx + b$ as an oblique (slant) asymptote.
- **Limit definition of an oblique asymptote:** A line $y = mx + b$ is an asymptote as $x \to +\infty$ or as $x \to -\infty$ if and only if

$$
\lim_{x \to \pm\infty} \bigl(f(x) - (mx + b)\bigr) = 0,
$$

which is equivalent to finding the slope and intercept via

$$
m = \lim_{x \to \pm\infty} \frac{f(x)}{x}, \qquad b = \lim_{x \to \pm\infty} \bigl(f(x) - mx\bigr).
$$

---

## 4. Step-by-Step Solution

### Step 1: Determine the Domain

The denominator vanishes when $x - 1 = 0$, that is, when $x = 1$. Therefore, the domain of $f$ is

$$
D = \mathbb{R} \setminus \{1\} = (-\infty, 1) \cup (1, \infty).
$$

### Step 2: Find the Vertical Asymptote

At the excluded point $x = 1$, the numerator approaches $1^2 + 1 = 2 > 0$, while the denominator $x - 1$ approaches $0$. Checking the sign from each side gives

$$
\lim_{x \to 1^-} \frac{x^2 + 1}{x - 1} = -\infty,
$$

because $x - 1 < 0$ for $x < 1$, and

$$
\lim_{x \to 1^+} \frac{x^2 + 1}{x - 1} = +\infty,
$$

because $x - 1 > 0$ for $x > 1$.

Hence, the line $x = 1$ is a two-sided vertical asymptote of $f$. Since $f$ is continuous at every point of $D$, there are no other vertical asymptotes.

### Step 3: Perform Polynomial Division

We divide $x^2 + 1$ by $x - 1$. Using polynomial long division (or adding and subtracting $1$ in the numerator):

- Divide the leading terms: $\frac{x^2}{x} = x$. Multiply $x(x - 1) = x^2 - x$ and subtract from $x^2 + 1$ to get $x + 1$.
- Divide the new leading term: $\frac{x}{x} = 1$. Multiply $1 \cdot (x - 1) = x - 1$ and subtract from $x + 1$ to get the remainder $2$.

Equivalently, using the difference of squares directly:

$$
x^2 + 1 = (x^2 - 1) + 2 = (x - 1)(x + 1) + 2.
$$

Dividing both sides by $x - 1$, for all $x \ne 1$, yields

$$
f(x) = \frac{x^2 + 1}{x - 1} = x + 1 + \frac{2}{x - 1}.
$$

Here, the quotient is the linear function $q(x) = x + 1$, and the remainder term is $r(x) = \frac{2}{x - 1}$.

### Step 4: Explain Why the Remainder Term Vanishes for Large $|x|$

Consider the remainder term $\frac{2}{x - 1}$ when $|x|$ is large:

- The numerator $2$ is a fixed constant.
- The denominator $x - 1$ grows without bound in magnitude as $|x| \to \infty$; specifically, for $|x| > 1$, the reverse triangle inequality gives $|x - 1| \ge |x| - 1 \to \infty$.

Dividing a fixed constant by a quantity whose absolute value becomes arbitrarily large forces the fraction to become arbitrarily close to $0$:

$$
\lim_{x \to +\infty} \frac{2}{x - 1} = 0, \qquad \lim_{x \to -\infty} \frac{2}{x - 1} = 0.
$$

Geometrically, the vertical gap between the graph $y = f(x)$ and the straight line $y = x + 1$ is

$$
f(x) - (x + 1) = \frac{2}{x - 1}.
$$

Because this vertical discrepancy shrinks to $0$ both as $x \to +\infty$ and as $x \to -\infty$, the curve hugs the line $y = x + 1$ arbitrarily closely in both directions. Thus,

$$
y = x + 1
$$

is a two-sided oblique asymptote.

### Step 5: Confirm via Standard Limit Formulas and Check Horizontal Asymptotes

Using the general asymptote formulas as $x \to \pm\infty$:

$$
m = \lim_{x \to \pm\infty} \frac{f(x)}{x} = \lim_{x \to \pm\infty} \frac{x^2 + 1}{x^2 - x} = \lim_{x \to \pm\infty} \frac{1 + \frac{1}{x^2}}{1 - \frac{1}{x}} = 1,
$$

and

$$
b = \lim_{x \to \pm\infty} \bigl(f(x) - 1 \cdot x\bigr) = \lim_{x \to \pm\infty} \frac{x^2 + 1 - x(x - 1)}{x - 1} = \lim_{x \to \pm\infty} \frac{x + 1}{x - 1} = \lim_{x \to \pm\infty} \frac{1 + \frac{1}{x}}{1 - \frac{1}{x}} = 1.
$$

This independently confirms the oblique asymptote $y = x + 1$ on both sides.

For horizontal asymptotes, note that

$$
\lim_{x \to +\infty} f(x) = +\infty, \qquad \lim_{x \to -\infty} f(x) = -\infty.
$$

Because neither limit at infinity is finite, $f$ has **no horizontal asymptotes**.

### Step 6: Position Relative to the Oblique Asymptote and Qualitative Sketch

The sign of the remainder term $f(x) - (x + 1) = \frac{2}{x - 1}$ tells us which side of the asymptote the graph lies on:

| Interval | Sign of $\frac{2}{x - 1}$ | Position of $y = f(x)$ relative to $y = x + 1$ |
| :--- | :---: | :--- |
| $(-\infty, 1)$ | $-$ | Strictly below $y = x + 1$ |
| $(1, \infty)$ | $+$ | Strictly above $y = x + 1$ |

Notice also that the curve never crosses its oblique asymptote $y = x + 1$, because $\frac{2}{x - 1} \ne 0$ for all $x \ne 1$.

```text
          y
          ^      |  :         / y = x + 1
          |      |  :  *     /
          |      |  :  *    /
        5 +      |  :   *  *     (local min at x = 1 + sqrt(2))
          |      |  :    **  *
          |      |  :        /  *
        1 + - - -+ -:- - - / - - -
          |      |  :    /
   -------+------+--:---/-----------------> x
         -2      0  1  /      4
          |     /   :
          |   */    :
       -1 +  *  *   :  (local max at x = 1 - sqrt(2))
          | /    *  :
          |/     *  :  x = 1 (vertical asymptote)
```

---

## 5. Final Answer & Conclusion

- **Domain:** $D = \mathbb{R} \setminus \{1\}$.
- **Polynomial division:**

$$
f(x) = x + 1 + \frac{2}{x - 1}.
$$

- **Vertical asymptote:** $x = 1$, where the left-hand limit is $-\infty$ and the right-hand limit is $+\infty$.
- **Oblique asymptote:** $y = x + 1$ as $x \to -\infty$ and as $x \to +\infty$.
- **Horizontal asymptotes:** None.
- **Why the remainder vanishes:** In $\frac{2}{x - 1}$, the numerator stays constant while $|x - 1|$ grows without bound as $|x| \to \infty$, so $\frac{2}{x - 1} \to 0$. Therefore, $f(x)$ differs from $x + 1$ by an amount that disappears at large $|x|$, approaching the line from below on $(-\infty, 1)$ and from above on $(1, \infty)$.

---

## 6. Quick Verification

1. **Algebraic recombination check:** Recombine the decomposed form over the common denominator $x - 1$:

$$
x + 1 + \frac{2}{x - 1} = \frac{(x + 1)(x - 1) + 2}{x - 1} = \frac{(x^2 - 1) + 2}{x - 1} = \frac{x^2 + 1}{x - 1}.
$$

This matches the original function identically for all $x \ne 1$.

2. **Numerical convergence check at large $|x|$:**
   - At $x = 101$: $f(101) = \frac{10202}{100} = 102.02$, while the asymptote gives $101 + 1 = 102$. The difference is $+0.02 = \frac{2}{100}$, positive and very small.
   - At $x = -99$: $f(-99) = \frac{9802}{-100} = -98.02$, while the asymptote gives $-99 + 1 = -98$. The difference is $-0.02 = \frac{2}{-100}$, negative and very small.
   - Near the vertical asymptote: $f(1.01) = \frac{2.0201}{0.01} = 202.01 \to +\infty$, and $f(0.99) = \frac{1.9801}{-0.01} = -198.01 \to -\infty$.

---

## 7. Common Mistakes to Avoid

- **Misidentifying the linear term without completing the division:** Seeing $\frac{x^2}{x} = x$, some students mistakenly conclude that the oblique asymptote is $y = x$, forgetting the constant term $+1$ produced by the $-1$ in the denominator. Always complete the polynomial division or compute $b = \lim_{x \to \pm\infty} (f(x) - mx)$.
- **Claiming an oblique asymptote exists alongside a horizontal asymptote:** For a single direction such as $x \to +\infty$, a function cannot approach both a horizontal line $y = c$ and a slanted line $y = mx + b$ with $m \ne 0$. Here, because $m = 1 \ne 0$, there is no horizontal asymptote.
- **Confusing the remainder value $2$ with the $y$-intercept of the asymptote:** In $f(x) = x + 1 + \frac{2}{x - 1}$, the asymptote is $y = x + 1$, not $y = x + 2$. The number $2$ belongs to the decaying fraction $\frac{2}{x - 1}$, not to the asymptote itself.
- **Forgetting to check both sides of the vertical asymptote:** Stating only that $x = 1$ is a vertical asymptote without evaluating the one-sided limits as $x \to 1^-$ and as $x \to 1^+$ leaves out whether the curve shoots to $+\infty$ or $-\infty$ on each side, and in other rational functions could even miss a removable discontinuity where the numerator also vanishes.

---

## 8. How I Would Explain This in Class

> "Think of polynomial division as zooming out with a camera. Up close near $x = 1$, the fraction $\frac{2}{x - 1}$ is huge and dominates the picture, throwing the graph vertically to $-\infty$ on the left and $+\infty$ on the right. Now zoom far out to $x = 1000$ or $x = -1000$. At that distance, $\frac{2}{x - 1}$ is roughly two thousandths — almost invisible — so $f(x) = x + 1 + \frac{2}{x - 1}$ looks practically indistinguishable from the straight line $y = x + 1$. The division separates the function into two clear roles: the line $x + 1$ tells you the long-range highway the graph follows at infinity, while the remainder $\frac{2}{x - 1}$ tells you both the vertical wall at $x = 1$ and which side of the highway the curve rides on."
