# Problem 06: A Logarithmic Function

## 1. The Original Problem

Analyze the domain, zero, and monotonicity of

$$
f(x) = \ln x - x + 1.
$$

Explain why the analysis must begin with the domain.

---

## 2. What Are We Trying to Find?

1. The domain $D_f$ of $f(x) = \ln x - x + 1$.
2. A clear explanation of why determining the domain must be the very first step of the analysis.
3. The derivative $f'(x)$, its critical points inside $D_f$, the intervals of monotonicity, and the global maximum of $f$.
4. All zeros of $f(x)$—not only finding $x = 1$, but also proving rigorously why no other zero exists.
5. Boundary limits as $x \to 0^+$ and $x \to \infty$ to complete the global picture of the function.

---

## 3. Before Calculating: What Idea Do We Need?

- **Domain of the natural logarithm:** The real-valued function $\ln x$ is defined if and only if its argument is strictly positive, $x > 0$.
- **Derivative domain can be larger than function domain:** The algebraic formula $f'(x) = \frac{1}{x} - 1$ makes formal sense for $x < 0$, even though the original function $f(x) = \ln x - x + 1$ does not exist there. Keeping the domain fixed prevents nonsensical conclusions on $(-\infty, 0]$.
- **Using monotonicity to prove uniqueness of a zero:** Because $\ln x - x + 1 = 0$ is a transcendental equation that cannot be solved by elementary algebra alone, monotonicity is the key tool: if $f(1) = 0$ is the strict global maximum, then $f(x) < 0$ everywhere else in $(0, \infty)$, proving $x = 1$ is the unique zero.

---

## 4. Step-by-Step Solution

### Step 1: Domain

The linear part $-x + 1$ is defined for all $x \in \mathbb{R}$, while $\ln x$ requires $x > 0$. Therefore, the domain of $f$ is

$$
D_f = (0, \infty).
$$

### Step 2: Why the Analysis Must Begin with the Domain

Starting with the domain is not a formality; it governs every subsequent step of the analysis:

1. **Preventing invalid calculations on non-existent inputs:** For $x \le 0$, $\ln x$ is undefined in $\mathbb{R}$, so $f(x)$ has no value, no sign, no zero, and no graph on $(-\infty, 0]$.
2. **Avoiding the derivative trap:** The derivative formula is $f'(x) = \frac{1}{x} - 1 = \frac{1 - x}{x}$. Looked at purely as a rational expression, $\frac{1 - x}{x}$ is defined and negative for $x < 0$. If someone forgot the domain $D_f = (0, \infty)$, they would erroneously place $(-\infty, 0)$ in their sign chart and conclude that $f$ is decreasing on $(-\infty, 0)$—a completely false statement about a region where $f$ does not exist!
3. **Simplifying sign analysis correctly:** Knowing from the outset that $x > 0$ tells us the denominator $x$ in $f'(x) = \frac{1 - x}{x}$ is always strictly positive, so the sign of $f'(x)$ depends only on $1 - x$.
4. **Identifying the true boundary points:** Knowing $D_f = (0, \infty)$ tells us that the left boundary of the graph is the one-sided limit $x \to 0^+$ rather than $x \to -\infty$.

### Step 3: Derivative, Monotonicity, and Maximum

Differentiating $f(x) = \ln x - x + 1$ on $D_f = (0, \infty)$ gives

$$
f'(x) = \frac{1}{x} - 1 = \frac{1 - x}{x}, \qquad x > 0.
$$

Finding the critical points in $(0, \infty)$:

$$
f'(x) = 0 \iff \frac{1 - x}{x} = 0 \iff 1 - x = 0 \iff x = 1.
$$

Since $x > 0$ throughout the domain, the sign of $f'(x)$ is determined entirely by the numerator $1 - x$:

- On $(0, 1)$: $1 - x > 0 \implies f'(x) > 0$, so $f$ is **strictly increasing** on $(0, 1]$.
- On $(1, \infty)$: $1 - x < 0 \implies f'(x) < 0$, so $f$ is **strictly decreasing** on $[1, \infty)$.

| Interval / Point | $(0, 1)$ | $x = 1$ | $(1, \infty)$ |
| :--- | :---: | :---: | :---: |
| Sign of $f'(x)$ | $+$ | $0$ | $-$ |
| Behavior of $f(x)$ | Strictly increasing | Global max: $0$ | Strictly decreasing |

At $x = 1$, $f'$ changes sign from $+$ to $-$, and the function value is

$$
f(1) = \ln 1 - 1 + 1 = 0 - 1 + 1 = 0.
$$

Because $f$ strictly increases on $(0, 1]$ up to $0$ and strictly decreases on $[1, \infty)$ down from $0$, the point $(1, 0)$ is the **unique global maximum** of $f$ on $(0, \infty)$.

### Step 4: Finding and Proving Uniqueness of the Zero

We already noticed that $f(1) = 0$, so $x = 1$ is a zero of $f$. Could there be any other zero in $(0, \infty)$?

- For every $x \in (0, 1)$, strict increase on $(0, 1]$ implies $f(x) < f(1) = 0$.
- For every $x \in (1, \infty)$, strict decrease on $[1, \infty)$ implies $f(x) < f(1) = 0$.

Therefore,

$$
f(x) \le 0 \quad \text{for all } x > 0,
$$

with equality if and only if $x = 1$. Thus $x = 1$ is the **unique zero** of $f$ on its entire domain!

As a bonus consequence, rearranging $\ln x - x + 1 \le 0$ proves the classical fundamental inequality

$$
\ln x \le x - 1 \quad \text{for all } x > 0,
$$

with equality only at $x = 1$.

### Step 5: Boundary Behavior for Completeness

Checking the two ends of $D_f = (0, \infty)$ completes the global description:

- As $x \to 0^+$: $\ln x \to -\infty$ and $-x + 1 \to 1$, so

$$
\lim_{x \to 0^+} (\ln x - x + 1) = -\infty,
$$

giving a right-sided vertical asymptote at $x = 0$.

- As $x \to \infty$: factoring out $x$ gives

$$
\lim_{x \to \infty} (\ln x - x + 1) = \lim_{x \to \infty} x\left(\frac{\ln x}{x} - 1 + \frac{1}{x}\right) = -\infty,
$$

because $\lim_{x \to \infty} \frac{\ln x}{x} = 0$ and $\frac{1}{x} \to 0$, so the quantity inside the parentheses approaches $-1 < 0$ while $x \to +\infty$.

Hence the range of $f$ is $(-\infty, 0]$, and $f$ has no minimum.

---

## 5. Final Answer & Conclusion

- **Domain:** $D_f = (0, \infty)$.
- **Why begin with the domain:** Because $\ln x$ is undefined for $x \le 0$, whereas the algebraic expression for $f'(x) = \frac{1 - x}{x}$ appears to make sense for $x < 0$; establishing $D_f = (0, \infty)$ first prevents invalid analysis on $(-\infty, 0]$, simplifies sign testing since $x > 0$, and identifies the true left boundary $x \to 0^+$.
- **Monotonicity:** Strictly increasing on $(0, 1]$ and strictly decreasing on $[1, \infty)$, with a unique global maximum at $(1, 0)$.
- **Zero:** $x = 1$ is the **unique** zero of $f(x)$ on $(0, \infty)$, and $f(x) < 0$ for all $x \in (0, 1) \cup (1, \infty)$.

---

## 6. Quick Verification

1. **Concavity check via second derivative:** Differentiating $f'(x) = \frac{1}{x} - 1$ gives

$$
f''(x) = -\frac{1}{x^2} < 0 \quad \text{for all } x > 0.
$$

Thus $f$ is strictly concave downward on all of $(0, \infty)$. A strictly concave function lies strictly below its horizontal tangent line $y = 0$ at $(1, 0)$ everywhere except at the point of tangency $x = 1$, independently confirming both the global maximum and the uniqueness of the zero.
2. **Numerical values on both sides of $x = 1$:**
   - At $x = \frac{1}{e} \approx 0.3679$: $f\left(\frac{1}{e}\right) = -1 - \frac{1}{e} + 1 = -\frac{1}{e} \approx -0.3679 < 0$.
   - At $x = 1$: $f(1) = 0$.
   - At $x = e \approx 2.7183$: $f(e) = 1 - e + 1 = 2 - e \approx -0.7183 < 0$.
   Both test values lie strictly below $0$, matching the sign and monotonicity table.

---

## 7. Common Mistakes to Avoid

- **Analyzing $f'(x) = \frac{1 - x}{x}$ on $(-\infty, 0)$:** Students who jump straight to differentiating often include $x < 0$ in the sign chart and write that $f$ decreases on $(-\infty, 0)$, forgetting that $\ln x$ is not even defined there.
- **Finding $x = 1$ by guessing without proving it is the only zero:** Checking $f(1) = 0$ shows existence of a zero, not uniqueness. Monotonicity on $(0, 1]$ and $[1, \infty)$ is what proves no other zero can occur.
- **Assuming $f(x)$ must cross the $x$-axis at a zero:** Here the graph touches the $x$-axis tangentially at $(1, 0)$ and turns back downward without ever taking positive values.
- **Forgetting that $\ln 1 = 0$:** Mistaking $\ln 1$ for $1$ gives the wrong value $f(1) = 1$ and hides the zero at $x = 1$.

---

## 8. How I Would Explain This in Class

> "This problem is a great lesson in why you always check the domain before touching the derivative. If you blindly differentiate $\ln x - x + 1$, you get $\frac{1 - x}{x}$, which looks totally happy accepting negative numbers like $x = -5$—even though the original function dies at $x = 0$! Once you lock yourself inside $(0, \infty)$, everything snaps into focus: the graph climbs up from $-\infty$, kisses the $x$-axis gently at $x = 1$, and then falls back down forever. That single kiss at $(1, 0)$ simultaneously tells us the maximum, the only zero, and the famous inequality $\ln x \le x - 1$."
