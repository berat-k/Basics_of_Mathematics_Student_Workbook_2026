# Problem 06: When Does a Logarithm Appear from an Integral?

## 1. The Original Problem

Compute

$$
\int \frac{2x}{x^2 + 5}\,dx.
$$

Identify the denominator as a candidate for substitution, compare the numerator with its derivative, and explain the source of the logarithm in the result.

---

## 2. What Are We Trying to Find?

1. Identify the denominator $x^2 + 5$ as the candidate substitution $u = g(x)$ and note the domain of the integrand.
2. Compare the numerator $2x$ directly with the derivative $g'(x)$ of the denominator.
3. Compute the indefinite integral $\int \frac{2x}{x^2 + 5}\,dx$ and simplify the absolute value sign using the positivity of $x^2 + 5$.
4. Explain clearly *why* a natural logarithm appears in the antiderivative.
5. Verify the final result explicitly by differentiation.

---

## 3. Before Calculating: What Idea Do We Need?

- **The exceptional case of the power rule:** For $n \ne -1$, $\int u^n\,du = \frac{u^{n+1}}{n+1} + C$. At $n = -1$, this formula breaks down because $n + 1 = 0$ would require dividing by zero.
- **Logarithmic antiderivative:** From differentiation, $\frac{d}{du}(\ln|u|) = \frac{1}{u}$ for every $u \ne 0$. Therefore, the missing $n = -1$ rule is

$$
\int \frac{1}{u}\,du = \ln|u| + C, \qquad u \ne 0.
$$

- **The $\frac{g'(x)}{g(x)}$ recognition pattern:** Combining $\int \frac{1}{u}\,du = \ln|u| + C$ with the substitution $u = g(x)$ gives

$$
\int \frac{g'(x)}{g(x)}\,dx = \ln|g(x)| + C, \qquad g(x) \ne 0.
$$

- **Domain and positivity:** For every $x \in \mathbb{R}$, $x^2 \ge 0$, so $x^2 + 5 \ge 5 > 0$. Thus the denominator never vanishes, the integrand is defined on all of $\mathbb{R}$, and $|x^2 + 5| = x^2 + 5$.

---

## 4. Step-by-Step Solution

### Step 1: Identify the Denominator as $u$ and Compare with the Numerator

Set the denominator as our substitution candidate:

$$
u = g(x) = x^2 + 5.
$$

First check the domain: since $x^2 + 5 \ge 5 > 0$ for all $x \in \mathbb{R}$, the fraction $\frac{2x}{x^2 + 5}$ is continuous on the entire real line $\mathbb{R}$.

Next, differentiate the denominator and compare it with the numerator:

$$
\frac{du}{dx} = \frac{d}{dx}(x^2 + 5) = 2x, \qquad \text{so} \qquad du = 2x\,dx.
$$

Comparing with the numerator of $\frac{2x}{x^2 + 5}$, we see that **the numerator $2x$ is literally the exact derivative of the denominator $x^2 + 5$**. In structural terms, the integrand has the exact form $\frac{g'(x)}{g(x)}$.

### Step 2: Compute the Integral via Substitution

Substitute $u = x^2 + 5$ and $du = 2x\,dx$ into the integral:

$$
\int \frac{2x}{x^2 + 5}\,dx = \int \frac{1}{u}\,du = \ln|u| + C = \ln|x^2 + 5| + C.
$$

Because $x^2 + 5 \ge 5 > 0$ for every real number $x$, the quantity inside the absolute value is strictly positive everywhere, so $|x^2 + 5| = x^2 + 5$. Hence we can write the result cleanly without absolute value bars:

$$
\int \frac{2x}{x^2 + 5}\,dx = \ln(x^2 + 5) + C, \qquad C \in \mathbb{R}.
$$

### Step 3: Explain the Source of the Logarithm in the Result

Why does a rational function $\frac{2x}{x^2 + 5}$—made purely of polynomials—produce a transcendental logarithm $\ln(x^2 + 5)$ when integrated?

1. **The missing exponent $n = -1$:** After substituting $u = x^2 + 5$, the integral becomes $\int u^{-1}\,du$. Every other power $u^n$ with $n \ne -1$ integrates to another power $\frac{u^{n+1}}{n+1}$, because differentiating $u^{n+1}$ returns a nonzero multiple of $u^n$. For $n = -1$, raising the exponent by $1$ gives $u^0 = 1$, whose derivative is $0$ rather than $u^{-1}$. No power function can differentiate to $\frac{1}{u}$.
2. **Reversing the derivative of $\ln|u|$:** The natural logarithm fills this exact gap because $\frac{d}{du}(\ln|u|) = \frac{1}{u}$. By the chain rule, differentiating $\ln|g(x)|$ always produces

$$
\frac{d}{dx}\bigl(\ln|g(x)|\bigr) = \frac{1}{g(x)} \cdot g'(x) = \frac{g'(x)}{g(x)}.
$$

3. **Conclusion:** A logarithm appears from an integral precisely when the integrand reduces to $\int \frac{1}{u}\,du$—equivalently, when the numerator is the derivative of the denominator up to a constant factor.

### Step 4: Verify the Result by Differentiation

Let $F(x) = \ln(x^2 + 5) + C$ on $\mathbb{R}$. Differentiating via the chain rule yields

$$
\begin{aligned}
F'(x) &= \frac{d}{dx}\bigl(\ln(x^2 + 5) + C\bigr) \\
&= \frac{1}{x^2 + 5} \cdot \frac{d}{dx}(x^2 + 5) + 0 \\
&= \frac{1}{x^2 + 5} \cdot 2x \\
&= \frac{2x}{x^2 + 5}.
\end{aligned}
$$

The derivative matches the original integrand identically for all $x \in \mathbb{R}$.

---

## 5. Final Answer & Conclusion

- **Substitution and structure:** Setting $u = x^2 + 5$ gives $du = 2x\,dx$, so the numerator equals the derivative of the denominator exactly, yielding the form $\int \frac{g'(x)}{g(x)}\,dx = \int \frac{1}{u}\,du$.
- **Source of the logarithm:** Because $\int u^{-1}\,du$ is the unique exception to the power rule and $(\ln|u|)' = \frac{1}{u}$, any integral of the form $\int \frac{g'(x)}{g(x)}\,dx$ produces $\ln|g(x)| + C$.
- **Indefinite integral on $\mathbb{R}$:**

$$
\int \frac{2x}{x^2 + 5}\,dx = \ln(x^2 + 5) + C, \qquad C \in \mathbb{R}.
$$

- **Verification:** Differentiating $\ln(x^2 + 5) + C$ gives $\frac{2x}{x^2 + 5}$ on $\mathbb{R}$.

---

## 6. Quick Verification

1. **Parity and monotonicity check:**
   - The integrand $f(x) = \frac{2x}{x^2 + 5}$ is negative for $x < 0$, zero at $x = 0$, and positive for $x > 0$.
   - The antiderivative $F(x) = \ln(x^2 + 5) + C$ decreases on $(-\infty, 0)$, reaches a global minimum at $x = 0$ where $F(0) = \ln 5 + C$, and increases on $(0, \infty)$. Moreover, $f$ is odd and $F$ is even. Every qualitative feature matches!

2. **Numerical derivative check at $x = 2$:**
   At $x = 2$, the integrand equals $f(2) = \frac{2(2)}{2^2 + 5} = \frac{4}{9} \approx 0.4444444$.
   Using $F(x) = \ln(x^2 + 5)$ with $h = 0.001$:
   - $F(2.001) = \ln(9.004001) \approx 2.19766903$,
   - $F(1.999) = \ln(8.996001) \approx 2.19678015$,
   - Symmetric difference quotient:

$$
\frac{F(2.001) - F(1.999)}{0.002} \approx \frac{0.00088889}{0.002} \approx 0.444444 \approx \frac{4}{9} = f(2).
$$

---

## 7. Common Mistakes to Avoid

- **Applying the power rule to $u^{-1}$:** Trying to write $\int u^{-1}\,du = \frac{u^0}{0}$ immediately fails by division by zero. Always switch to $\ln|u| + C$ when the exponent is $-1$.
- **Assuming every fraction integrates to a logarithm:** Only a fraction whose numerator is the derivative of the denominator (up to a constant factor) integrates directly to $\ln|\text{denominator}|$. For example, $\int \frac{2x}{(x^2 + 5)^2}\,dx = \int u^{-2}\,du = -\frac{1}{x^2 + 5} + C$ does *not* produce a logarithm because the exponent is $-2$, not $-1$.
- **Forgetting absolute value bars in general:** Here dropping the bars to write $\ln(x^2 + 5)$ is valid *only* because $x^2 + 5 > 0$ for every real $x$. If the denominator were $x^2 - 5$, which can be negative, writing $\ln|x^2 - 5| + C$ would be mandatory on intervals where $x^2 - 5 < 0$.
- **Splitting the denominator:** Writing $\frac{2x}{x^2 + 5} = \frac{2x}{x^2} + \frac{2x}{5}$ is an illegal algebraic split; fractions can be split across a sum in the *numerator*, never in the *denominator*.

---

## 8. How I Would Explain This in Class

> "Whenever you see a fraction inside an integral, run a one-second instinct check before doing anything else: differentiate the bottom in your head and glance at the top. Here the bottom is $x^2 + 5$, its derivative is $2x$, and $2x$ is sitting right on top! That is the unmistakable fingerprint of a logarithm, because differentiating $\ln$ of anything puts the thing in the denominator and its derivative in the numerator. And because $x^2 + 5$ is always at least $5$, we don't even have to worry about negative numbers inside the log."
