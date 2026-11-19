# Problem 15: The Difference Quotient as a Check of the Derivative

## 1. The Original Problem

Choose one function from the problem set and a point $x_0$ at which the derivative exists. Compute $f'(x_0)$ exactly, and then calculate

$$
\frac{f(x_0 + h) - f(x_0)}{h}
$$

for $h = 1$, $0.1$, and $0.01$. Compare the values with $f'(x_0)$ and explain why the difference quotient approaching a single number is consistent with the definition of the derivative, while a few computations do not replace a limit argument.

---

## 2. What Are We Trying to Find?

1. A concrete function $f(x)$ chosen from the problem set and a specific point $x_0$ where $f$ is differentiable.
2. The exact derivative $f'(x_0)$ obtained analytically using differentiation rules.
3. The exact and numerical values of the difference quotient $\frac{f(x_0 + h) - f(x_0)}{h}$ for $h = 1$, $h = 0.1$, and $h = 0.01$.
4. A quantitative comparison between those three difference quotients and the exact value $f'(x_0)$.
5. A rigorous explanation of both sides of the conceptual question:
   - why seeing the difference quotient approach $f'(x_0)$ is consistent with the limit definition of the derivative, and
   - why checking finitely many values of $h$ can never substitute for a true limit proof.

---

## 3. Before Calculating: What Idea Do We Need?

- **Limit definition of the derivative:** The derivative of $f$ at $x_0$ is defined as the two-sided limit

$$
f'(x_0) = \lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h}.
$$

- **Geometric interpretation of the difference quotient:** For any fixed $h \ne 0$, the ratio $\frac{f(x_0 + h) - f(x_0)}{h}$ is the slope of the secant line connecting $(x_0, f(x_0))$ and $(x_0 + h, f(x_0 + h))$. As $h \to 0$, these secant lines pivot toward the tangent line of slope $f'(x_0)$.
- **Logarithm identity for simplifying differences:** Using $\ln A - \ln B = \ln\left(\frac{A}{B}\right)$ simplifies difference quotients of logarithmic functions cleanly and avoids subtractive cancellation.
- **Observation vs. proof:** A limit statement $\lim_{h \to 0} Q(h) = L$ makes a claim about *every* sufficiently small nonzero $h$, both positive and negative. Evaluating $Q(h)$ at three specific positive numbers $h = 1, 0.1, 0.01$ tests only three points and leaves infinitely many smaller and negative values untested.

---

## 4. Step-by-Step Solution

### Step 1: Choose a Function from the Problem Set and a Point $x_0$

Choose the logarithmic function from Problem 9:

$$
f(x) = \ln(x^2 + 1),
$$

at the point $x_0 = 1$.

Because $x^2 + 1 \ge 1 > 0$ for all real $x$, the function $f$ is smooth and differentiable everywhere on $\mathbb{R}$, so $f'(1)$ certainly exists.

### Step 2: Compute $f'(1)$ Exactly

Using the chain rule as in Problem 9:

$$
f'(x) = \frac{1}{x^2 + 1} \cdot \frac{d}{dx}(x^2 + 1) = \frac{2x}{x^2 + 1}.
$$

Substituting $x_0 = 1$ gives the exact derivative:

$$
f'(1) = \frac{2(1)}{1^2 + 1} = \frac{2}{2} = 1.
$$

Also record the function value at $x_0 = 1$:

$$
f(1) = \ln(1^2 + 1) = \ln 2 \approx 0.69314718.
$$

### Step 3: Calculate the Difference Quotient for $h = 1$, $0.1$, and $0.01$

For any $h \ne 0$, let $Q(h)$ denote the difference quotient at $x_0 = 1$:

$$
Q(h) = \frac{f(1 + h) - f(1)}{h} = \frac{\ln\bigl((1 + h)^2 + 1\bigr) - \ln 2}{h} = \frac{1}{h} \ln\left(\frac{(1 + h)^2 + 1}{2}\right).
$$

Now compute $Q(h)$ for each required value of $h$:

1. **For $h = 1$:** Here $1 + h = 2$, and $2^2 + 1 = 5$, so $f(2) = \ln 5 \approx 1.60943791$. Therefore:

$$
Q(1) = \frac{\ln 5 - \ln 2}{1} = \ln(2.5) \approx 0.91629073.
$$

2. **For $h = 0.1$:** Here $1 + h = 1.1$, and $(1.1)^2 + 1 = 1.21 + 1 = 2.21$, so $f(1.1) = \ln(2.21) \approx 0.79299252$. Therefore:

$$
Q(0.1) = \frac{\ln(2.21) - \ln 2}{0.1} = 10\ln(1.105) \approx 0.99845335.
$$

3. **For $h = 0.01$:** Here $1 + h = 1.01$, and $(1.01)^2 + 1 = 1.0201 + 1 = 2.0201$, so $f(1.01) = \ln(2.0201) \approx 0.70314702$. Therefore:

$$
Q(0.01) = \frac{\ln(2.0201) - \ln 2}{0.01} = 100\ln(1.01005) \approx 0.99998346.
$$

### Step 4: Compare the Values with $f'(1) = 1$

Organize all three computations alongside the exact derivative $f'(1) = 1$:

| $h$ | $1 + h$ | Exact expression for $Q(h)$ | Decimal value of $Q(h)$ | Error $Q(h) - f'(1)$ |
| :---: | :---: | :---: | :---: | :---: |
| $1$ | $2$ | $\ln(2.5)$ | $0.91629073$ | $-0.08370927$ |
| $0.1$ | $1.1$ | $10\ln(1.105)$ | $0.99845335$ | $-0.00154665$ |
| $0.01$ | $1.01$ | $100\ln(1.01005)$ | $0.99998346$ | $-0.00001654$ |
| Limit $h \to 0$ | $1$ | $f'(1)$ | $1.00000000$ | $0$ |

Observe how rapidly the error shrinks as $h$ decreases by factors of $10$:
- At $h = 1$, $Q(1)$ is off from $1$ by about $8.4 \times 10^{-2}$.
- At $h = 0.1$, $Q(0.1)$ is off from $1$ by about $1.5 \times 10^{-3}$.
- At $h = 0.01$, $Q(0.01)$ is off from $1$ by only about $1.7 \times 10^{-5}$, agreeing with $f'(1) = 1$ to four decimal places.

### Step 5: Explain Why This Is Consistent with the Definition, Yet Cannot Replace a Limit Proof

**Why the numerical convergence is consistent with the definition of the derivative:**

By definition, $f'(1) = 1$ means that for every tolerance $\varepsilon > 0$, we can force $|Q(h) - 1| < \varepsilon$ simply by taking $|h|$ small enough and nonzero. Therefore, as we pick progressively smaller increments $h = 1, 0.1, 0.01$, the secant slopes $Q(h)$ *must* move closer and closer to the single target value $1$. Seeing $0.91629 \to 0.99845 \to 0.99998$ is strong numerical confirmation that our analytic answer $f'(1) = 1$ has no algebraic or sign errors.

**Why a few computations do not replace a limit argument:**

Testing $h = 1, 0.1, 0.01$ is a valuable sanity check, *never* a proof, for three fundamental reasons:

1. **Only one side was tested, $h > 0$:** The derivative is a *two-sided* limit. For $g(x) = |x|$ at $x_0 = 0$, testing $h = 1, 0.1, 0.01$ yields $Q(h) = 1, 1, 1$, making it look as if $g'(0) = 1$. Yet testing negative $h$ yields $Q(h) = -1$, so $g'(0)$ does not exist at all!
2. **Hidden behavior below the smallest tested $h$:** A finite sample of three points tells us nothing about what happens when $0 < |h| < 0.01$. For a concrete counterexample, consider the smooth function

$$
g(x) = \ln(x^2 + 1) + 0.01\sin(100\pi x)
$$

at $x_0 = 1$. At $x = 1, 2, 1.1$, and $1.01$, the quantity $100\pi x$ is an exact integer multiple of $\pi$, so $\sin(100\pi x) = 0$ at all four points! Consequently, $g$ produces the **exact same three difference quotients** $0.91629073$, $0.99845335$, and $0.99998346$ for $h = 1, 0.1, 0.01$—yet its true derivative at $x_0 = 1$ is

$$
g'(1) = 1 + 0.01 \cdot 100\pi \cos(100\pi) = 1 + \pi \approx 4.14159265 \ne 1.
$$

3. **Distinguishing close values and floating-point limits:** From $0.99998346$ alone, numerical sampling cannot prove whether the true limit is $1.00000000$ or $0.99999999$ or even whether $Q(h)$ diverges for ultra-tiny $h$. Only an analytic limit argument proves that $Q(h) \to 1$ for *all* ways $h$ can approach $0$.

---

## 5. Final Answer & Conclusion

- **Chosen function and point:** $f(x) = \ln(x^2 + 1)$ from Problem 9 at $x_0 = 1$.
- **Exact derivative:**

$$
f'(1) = \left.\frac{2x}{x^2 + 1}\right|_{x = 1} = 1.
$$

- **Difference quotients:**
  - $h = 1$: $\frac{f(2) - f(1)}{1} = \ln(2.5) \approx 0.91629073$,
  - $h = 0.1$: $\frac{f(1.1) - f(1)}{0.1} = 10\ln(1.105) \approx 0.99845335$,
  - $h = 0.01$: $\frac{f(1.01) - f(1)}{0.01} = 100\ln(1.01005) \approx 0.99998346$.
- **Conceptual conclusion:** The sequence $0.91629073 \to 0.99845335 \to 0.99998346$ approaches $f'(1) = 1$, which is completely consistent with the limit definition of the derivative and provides a reliable error check. However, finitely many evaluations check only a few positive values of $h$ and cannot rule out two-sided mismatches or smaller-scale oscillations, so they can never replace a rigorous limit argument.

---

## 6. Quick Verification

1. **Direct analytic limit verification of $Q(h) \to 1$:** Expand the argument of the logarithm in $Q(h)$:

$$
\frac{(1 + h)^2 + 1}{2} = \frac{1 + 2h + h^2 + 1}{2} = 1 + h + \frac{h^2}{2}.
$$

Using the fundamental logarithmic limit $\lim_{t \to 0} \frac{\ln(1 + t)}{t} = 1$ with $t = h + \frac{h^2}{2}$, we obtain

$$
\lim_{h \to 0} Q(h) = \lim_{h \to 0} \frac{\ln\left(1 + h + \frac{h^2}{2}\right)}{h + \frac{h^2}{2}} \cdot \frac{h + \frac{h^2}{2}}{h} = 1 \cdot \lim_{h \to 0} \left(1 + \frac{h}{2}\right) = 1.
$$

This proves $f'(1) = 1$ rigorously from the limit definition itself!

2. **Check from the negative side and for smaller $h$:**
  - For $h = -0.01$: $1 + h = 0.99$, so $(0.99)^2 + 1 = 1.9801$, and

$$
Q(-0.01) = \frac{\ln(1.9801) - \ln 2}{-0.01} = -100\ln(0.99005) \approx 0.99998321,
$$

matching $1$ to four decimal places from the left as well.
  - For $h = 0.001$: $(1.001)^2 + 1 = 2.002001$, and

$$
Q(0.001) = 1000\ln(1.0010005) \approx 0.99999983,
$$

now matching $1$ to six decimal places.

---

## 7. Common Mistakes to Avoid

- **Forgetting to divide by $h$:** Computing only $f(x_0 + h) - f(x_0)$ gives $\approx 0.9163, 0.0998, 0.0100$, which approaches $0$ rather than $f'(1) = 1$. That measures the *change* in $f$, not the *rate of change*.
- **Rounding intermediate values too aggressively:** If you round $\ln(2.0201) \approx 0.70$ and $\ln 2 \approx 0.69$ before dividing by $h = 0.01$, dividing by a small $h$ amplifies the rounding error by a factor of $100$! Always keep plenty of precision (or combine logarithms as $\ln(A/B)$ first) before dividing by small $h$.
- **Concluding that three matching decimals constitute a proof:** Numerical agreement is great for spotting mistakes in your algebra, but as our counterexample $g(x) = \ln(x^2 + 1) + 0.01\sin(100\pi x)$ shows, three sample points can be completely fooled by behavior on a finer scale.
- **Choosing a point $x_0$ where $f$ is not differentiable:** Always confirm beforehand that $x_0$ is in the domain of $f'$ (for example, choosing $x_0 = 0$ for Problem 2 or $x_0 = 1$ for Problem 4 would be invalid).

---

## 8. How I Would Explain This in Class

> "Calculating a few difference quotients is like taking three snapshots of a runner approaching a finish line: at $h = 1$, $h = 0.1$, and $h = 0.01$, our secant slopes read $0.9163$, $0.9985$, and $0.99998$—every snapshot shows the runner heading straight for $1$, which gives us huge confidence that our exact derivative $f'(1) = 1$ is right. But three still photographs are not a continuous video: the runner could suddenly turn around, jump, or wiggle violently between $h = 0.01$ and $h = 0$, or behave completely differently coming from the negative side. Numerical difference quotients are an outstanding lie detector for catching algebra mistakes, while the limit argument is the mathematical proof that guarantees what happens all the way down to zero from both sides."
