# Problem 04: A Quotient and Domain Control

## 1. The Original Problem

For

$$
f(x)=\frac{x^2+1}{x-1}
$$

determine the domain, compute the derivative, simplify the result, and explain why the restriction $x\neq1$ remains important.

---

## 2. What Are We Trying to Find?

1. The domain $D_f$ of the rational function $f(x) = \frac{x^2 + 1}{x - 1}$.
2. The derivative $f'(x)$ using the quotient rule.
3. The fully simplified form of $f'(x)$, checking whether any common factors cancel.
4. A clear mathematical explanation of why the domain restriction $x \ne 1$ remains essential for $f'(x)$ and for analyzing $f$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Domain of a rational function:** A quotient $\frac{u(x)}{v(x)}$ of polynomials is defined for all real $x$ such that the denominator is nonzero, $v(x) \ne 0$.
- **The quotient rule:** If $u$ and $v$ are differentiable and $v(x) \ne 0$, then

$$
\left(\frac{u(x)}{v(x)}\right)' = \frac{u'(x)v(x) - u(x)v'(x)}{(v(x))^2}.
$$

- **Order in the numerator matters:** Because of the minus sign, $u'v - uv'$ cannot be reversed without flipping the sign of the entire derivative.
- **Differentiability requires being in the domain:** A function cannot have a derivative at a point where the function itself is undefined. Thus $D_{f'} \subseteq D_f$ always holds, and points excluded from the domain of $f$ also split the real line into separate intervals when studying monotonicity.

---

## 4. Step-by-Step Solution

### Step 1: Determine the Domain of $f$

The numerator $x^2 + 1$ and denominator $x - 1$ are polynomials, so the only restriction is that the denominator cannot equal zero:

$$
x - 1 \ne 0 \iff x \ne 1.
$$

Therefore, the domain of $f$ is:

$$
D_f = \mathbb{R} \setminus \{1\} = (-\infty, 1) \cup (1, \infty).
$$

### Step 2: Apply the Quotient Rule

Set $u(x) = x^2 + 1$ and $v(x) = x - 1$. Their derivatives are:

$$
u'(x) = 2x, \qquad v'(x) = 1.
$$

For all $x \ne 1$, apply the quotient rule:

$$
f'(x) = \frac{u'(x)v(x) - u(x)v'(x)}{(v(x))^2} = \frac{(2x)(x - 1) - (x^2 + 1)(1)}{(x - 1)^2}.
$$

### Step 3: Simplify the Numerator

Expand the numerator carefully, paying close attention to the minus sign in front of $(x^2 + 1)$:

$$
(2x)(x - 1) - (x^2 + 1) = 2x^2 - 2x - x^2 - 1 = x^2 - 2x - 1.
$$

Thus,

$$
f'(x) = \frac{x^2 - 2x - 1}{(x - 1)^2}, \qquad x \ne 1.
$$

Let us check whether the numerator shares a factor of $(x - 1)$ with the denominator. Evaluating the numerator at $x = 1$ gives:

$$
1^2 - 2(1) - 1 = -2 \ne 0.
$$

By the Remainder Theorem, $(x - 1)$ is not a factor of $x^2 - 2x - 1$, so the fraction is already in lowest terms. Note that we leave the denominator factored as $(x - 1)^2$ because it makes both the domain restriction $x \ne 1$ and the sign $(x - 1)^2 > 0$ immediately visible.

### Step 4: Explain Why the Restriction $x \ne 1$ Remains Important

The condition $x \ne 1$ remains essential for three distinct reasons:

1. **The derivative formula itself is undefined at $x = 1$:** Substituting $x = 1$ into $f'(x) = \frac{x^2 - 2x - 1}{(x - 1)^2}$ yields $\frac{-2}{0}$, which is division by zero. As $x \to 1$, $f'(x) \to -\infty$.
2. **Differentiability requires $f$ to be defined and continuous at the point:** Since $f(x) = \frac{x^2 + 1}{x - 1}$ has a vertical asymptote at $x = 1$ with

$$
\lim_{x \to 1^-} f(x) = -\infty \qquad \text{and} \qquad \lim_{x \to 1^+} f(x) = +\infty,
$$

  there is no point on the graph at $x = 1$ and therefore no tangent line there. Even in problems where an algebraic cancellation removes a denominator factor, the domain of $f'$ can never exceed the domain of $f$.
3. **Domain breaks matter for monotonicity and sign analysis:** Because $(x - 1)^2 > 0$ for all $x \ne 1$, the sign of $f'(x)$ is determined by $x^2 - 2x - 1$, whose roots are $x = 1 - \sqrt{2} \approx -0.414$ and $x = 1 + \sqrt{2} \approx 2.414$. Between these two roots, $f'(x) < 0$. However, we **cannot** say that $f$ is decreasing on the whole interval $(1 - \sqrt{2}, 1 + \sqrt{2})$! Because of the asymptote at $x = 1$, $f$ decreases on $(1 - \sqrt{2}, 1)$ and separately decreases on $(1, 1 + \sqrt{2})$, while jumping upward from $-\infty$ to $+\infty$ across $x = 1$ — for instance, $f(0) = -1 < 5 = f(2)$ even though $f'(x) < 0$ on both sides of $1$.

---

## 5. Final Answer & Conclusion

- **Domain:** $D_f = \mathbb{R} \setminus \{1\} = (-\infty, 1) \cup (1, \infty)$.
- **Simplified derivative:**

$$
f'(x) = \frac{x^2 - 2x - 1}{(x - 1)^2}, \qquad x \ne 1.
$$

- **Why $x \ne 1$ remains important:** Both $f(x)$ and $f'(x)$ are undefined at $x = 1$ because the denominator vanishes there and $f$ has a vertical asymptote at $x = 1$. Keeping track of $x \ne 1$ ensures we never evaluate $f'(1)$ and never draw false conclusions about monotonicity across the discontinuity at $x = 1$.

---

## 6. Quick Verification

1. **Independent method via polynomial division:**
   Divide $x^2 + 1$ by $x - 1$:

$$
x^2 + 1 = (x - 1)(x + 1) + 2 \implies f(x) = x + 1 + \frac{2}{x - 1} = x + 1 + 2(x - 1)^{-1}.
$$

   Differentiating this rewritten form using the power and chain rules gives:

$$
f'(x) = 1 - 2(x - 1)^{-2} = 1 - \frac{2}{(x - 1)^2} = \frac{(x - 1)^2 - 2}{(x - 1)^2} = \frac{x^2 - 2x - 1}{(x - 1)^2}.
$$

   Both methods produce the exact same formula!

2. **Numerical difference-quotient check at $x = 0$ and $x = 3$:**
   - At $x = 0$: $f'(0) = \frac{-1}{(-1)^2} = -1$. With $h = 0.001$, $f(0) = -1$ and $f(0.001) = \frac{1.000001}{-0.999} \approx -1.001002$, so

$$
\frac{f(0.001) - f(0)}{0.001} \approx -1.0020 \approx -1.
$$

   - At $x = 3$: $f'(3) = \frac{9 - 6 - 1}{2^2} = \frac{2}{4} = 0.5$. With $h = 0.001$, $f(3) = 5$ and $f(3.001) \approx 5.00050025$, so

$$
\frac{f(3.001) - f(3)}{0.001} \approx 0.50025 \approx 0.5.
$$

---

## 7. Common Mistakes to Avoid

- **Using the false quotient rule $\left(\frac{u}{v}\right)' = \frac{u'}{v'}$:** That would yield $\frac{2x}{1} = 2x$, which completely ignores the quotient structure and does not even vanish or blow up at the right places.
- **Dropping parentheses around $u(x) = x^2 + 1$ after the minus sign:** Writing $2x(x - 1) - x^2 + 1$ instead of $2x(x - 1) - (x^2 + 1)$ gives $x^2 - 2x + 1 = (x - 1)^2$ in the numerator, which would falsely simplify to $f'(x) = 1$! That single sign error destroys the whole problem.
- **Reversing the numerator to $uv' - u'v$:** Swapping the subtraction flips the sign of $f'(x)$ everywhere.
- **Expanding $(x - 1)^2$ unnecessarily or forgetting $x \ne 1$:** Leaving $(x - 1)^2$ factored keeps the excluded point $x = 1$ and the positivity of the denominator completely transparent.

---

## 8. How I Would Explain This in Class

> "The quotient rule has one famous trap: the minus sign in the numerator. Always put parentheses around the second product, because turning $-(x^2 + 1)$ into $-x^2 + 1$ magically tricks the numerator into becoming $(x - 1)^2$ and gives the completely bogus derivative $1$! Also, think of $x = 1$ as a deep canyon splitting the graph into two separate worlds. Neither the function nor its derivative can stand inside the canyon, and you can never claim the function is smoothly decreasing across a canyon where it teleports from $-\infty$ up to $+\infty$."
