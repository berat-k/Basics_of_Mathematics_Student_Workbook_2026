# Problem 11: Choose the Method First

## 1. The Original Problem

For each integral, first write which method you choose and how you recognize it, and then compute:

1. $\int\sin(3x)\,dx$,
2. $\int x\ln x\,dx$,
3. $\int\frac{x}{\sqrt{x^2+1}}\,dx$.

---

## 2. What Are We Trying to Find?

For each of the three indefinite integrals:

1. Identify the most appropriate integration method before starting any computation.
2. Explain the structural clues in the integrand that reveal why that method works.
3. Compute the complete family of antiderivatives, including the constant of integration $C$ and noting any domain restrictions.
4. Verify each result by differentiation.

---

## 3. Before Calculating: What Idea Do We Need?

Choosing an integration technique depends on **recognizing algebraic structure**, not guessing at random:

- **Linear $u$-substitution, reversing the chain rule for $f(ax + b)$:** When a basic function is evaluated at a linear expression $ax + b$, setting $u = ax + b$ produces $du = a\,dx$, which simply scales the antiderivative by $\frac{1}{a}$.
- **General $u$-substitution, reversing the chain rule:** Look for a composite function $f(g(x))$ multiplied by $g'(x)$ up to a constant factor. Setting $u = g(x)$ turns $g'(x)\,dx$ into $du$ and collapses the integral to $\int f(u)\,du$.
- **Integration by parts, reversing the product rule:** Look for a product of two unrelated types of functions — such as a polynomial times a logarithm, exponential, or trigonometric function — where substitution fails because neither factor is the derivative of an inner expression in the other. The formula is

$$
\int u\,dv = uv - \int v\,du.
$$

We choose $u$ to be the factor that becomes simpler when differentiated, and $dv$ to be the factor that is easy to integrate.

---

## 4. Step-by-Step Solution

### Step 1: Integral 1 — $\int \sin(3x)\,dx$

**Method choice:** Simple linear $u$-substitution.

**How to recognize it:** The integrand is a composite function $\sin(3x)$ whose outer function $\sin(\cdot)$ has a known elementary antiderivative and whose inner function $3x$ is linear, so its derivative is just the constant $3$.

**Computation:**

Let

$$
u = 3x \implies du = 3\,dx \implies dx = \frac{1}{3}\,du.
$$

Substitute into the integral:

$$
\int \sin(3x)\,dx = \int \sin u \cdot \frac{1}{3}\,du = \frac{1}{3} \int \sin u\,du = -\frac{1}{3}\cos u + C.
$$

Substitute back $u = 3x$:

$$
\int \sin(3x)\,dx = -\frac{1}{3}\cos(3x) + C.
$$

This holds for all $x \in \mathbb{R}$.

### Step 2: Integral 2 — $\int x\ln x\,dx$

**Domain note:** Because $\ln x$ is defined only for positive real numbers, this integral is considered on the domain $x > 0$.

**Method choice:** Integration by parts.

**How to recognize it:** The integrand is a product of an algebraic power $x$ and a logarithmic function $\ln x$. Standard $u$-substitution does not work cleanly here: setting $u = \ln x$ gives $du = \frac{1}{x}\,dx$, whereas we have $x\,dx$ rather than $\frac{1}{x}\,dx$. On the other hand, differentiating $\ln x$ removes the logarithm completely and produces $\frac{1}{x}$, while integrating $x$ gives $\frac{1}{2}x^2$. Their product $\frac{1}{2}x^2 \cdot \frac{1}{x} = \frac{1}{2}x$ is a trivial polynomial to integrate!

**Computation:**

Choose

$$
u = \ln x, \qquad dv = x\,dx.
$$

Then

$$
du = \frac{1}{x}\,dx, \qquad v = \frac{1}{2}x^2.
$$

Apply $\int u\,dv = uv - \int v\,du$:

$$
\begin{aligned}
\int x\ln x\,dx &= (\ln x)\left(\frac{1}{2}x^2\right) - \int \frac{1}{2}x^2 \cdot \frac{1}{x}\,dx \\
&= \frac{1}{2}x^2\ln x - \frac{1}{2}\int x\,dx \\
&= \frac{1}{2}x^2\ln x - \frac{1}{2}\left(\frac{1}{2}x^2\right) + C \\
&= \frac{1}{2}x^2\ln x - \frac{1}{4}x^2 + C.
\end{aligned}
$$

Equivalently, we can factor this as $\frac{x^2}{4}(2\ln x - 1) + C$ for $x > 0$.

### Step 3: Integral 3 — $\int \frac{x}{\sqrt{x^2+1}}\,dx$

**Domain note:** Since $x^2 + 1 \ge 1 > 0$ for every real number $x$, the integrand is defined and continuous for all $x \in \mathbb{R}$.

**Method choice:** $u$-substitution.

**How to recognize it:** Inside the square root sits the quadratic expression $x^2 + 1$. Its derivative is $2x$, and the numerator contains $x$, which matches $2x$ up to the constant factor $\frac{1}{2}$. That is the unmistakable signature of the chain rule in reverse.

**Computation:**

Let

$$
u = x^2 + 1 \implies du = 2x\,dx \implies x\,dx = \frac{1}{2}\,du.
$$

Rewrite $\frac{1}{\sqrt{u}}$ as $u^{-1/2}$ and substitute into the integral:

$$
\begin{aligned}
\int \frac{x}{\sqrt{x^2+1}}\,dx &= \int \frac{1}{\sqrt{u}} \cdot \frac{1}{2}\,du \\
&= \frac{1}{2} \int u^{-1/2}\,du \\
&= \frac{1}{2} \cdot \frac{u^{1/2}}{1/2} + C \\
&= u^{1/2} + C.
\end{aligned}
$$

Substitute back $u = x^2 + 1$:

$$
\int \frac{x}{\sqrt{x^2+1}}\,dx = \sqrt{x^2+1} + C.
$$

### Step 4: Summary Table of Method Recognition

| Integral | Chosen Method | Structural Cue | Final Antiderivative |
| --- | --- | --- | --- |
| $\int \sin(3x)\,dx$ | Linear $u$-substitution | Basic function of linear input $3x$ | $-\frac{1}{3}\cos(3x) + C$ |
| $\int x\ln x\,dx$ | Integration by parts | Product of polynomial and logarithm; no inner derivative match | $\frac{1}{2}x^2\ln x - \frac{1}{4}x^2 + C$ for $x > 0$ |
| $\int \frac{x}{\sqrt{x^2+1}}\,dx$ | $u$-substitution | Inner function $x^2 + 1$ with derivative $2x$ matching numerator $x$ | $\sqrt{x^2+1} + C$ |

---

## 5. Final Answer & Conclusion

1. **Linear $u$-substitution** with $u = 3x$:

$$
\int \sin(3x)\,dx = -\frac{1}{3}\cos(3x) + C.
$$

2. **Integration by parts** with $u = \ln x$ and $dv = x\,dx$, valid for $x > 0$:

$$
\int x\ln x\,dx = \frac{1}{2}x^2\ln x - \frac{1}{4}x^2 + C.
$$

3. **$u$-substitution** with $u = x^2 + 1$:

$$
\int \frac{x}{\sqrt{x^2+1}}\,dx = \sqrt{x^2+1} + C.
$$

---

## 6. Quick Verification

Differentiate each answer to confirm it reproduces the original integrand:

1. **Check for Integral 1:**

$$
\frac{d}{dx}\left(-\frac{1}{3}\cos(3x) + C\right) = -\frac{1}{3}\Big(-\sin(3x)\Big)\cdot 3 = \sin(3x).
$$

2. **Check for Integral 2, using the product rule:**

$$
\frac{d}{dx}\left(\frac{1}{2}x^2\ln x - \frac{1}{4}x^2 + C\right) = x\ln x + \frac{1}{2}x^2\cdot\frac{1}{x} - \frac{1}{2}x = x\ln x + \frac{1}{2}x - \frac{1}{2}x = x\ln x.
$$

3. **Check for Integral 3, using the chain rule:**

$$
\frac{d}{dx}\left(\sqrt{x^2+1} + C\right) = \frac{1}{2}(x^2 + 1)^{-1/2} \cdot 2x = \frac{x}{\sqrt{x^2+1}}.
$$

All three derivatives match their original integrands identically.

---

## 7. Common Mistakes to Avoid

- **Multiplying instead of dividing by $3$ in Integral 1:** Writing $-3\cos(3x) + C$ instead of $-\frac{1}{3}\cos(3x) + C$. Differentiating quickly exposes the extra factor of $9$.
- **Forgetting the minus sign in $\int \sin u\,du$:** Confusing the derivative of $\sin u$ with its antiderivative and writing $+\frac{1}{3}\cos(3x) + C$.
- **Choosing $u = x$ and $dv = \ln x\,dx$ in Integral 2:** While technically possible if you already memorized $\int \ln x\,dx = x\ln x - x$, it makes the problem needlessly harder. Choosing $u = \ln x$ eliminates the logarithm immediately in one step.
- **Misapplying the power rule to $u^{-1/2}$ in Integral 3:** Writing $\frac{1}{2}\int u^{-1/2}\,du = \frac{1}{2}\cdot\frac{1}{2}u^{1/2}$ instead of dividing by $\frac{1}{2}$, which multiplies by $2$ and cancels the $\frac{1}{2}$ in front. Also, do not confuse $\int \frac{x}{\sqrt{x^2+1}}\,dx$ with $\ln\sqrt{x^2+1}$ — logarithms only arise from $u^{-1}$, never from $u^{-1/2}$.

---

## 8. How I Would Explain This in Class

> "Before touching your pencil, pause for five seconds and scan the integrand like a mechanic listening to an engine. In the first integral, I hear a linear stretch inside sine, so I divide by $3$ and reverse the chain rule. In the third integral, I see $x^2 + 1$ trapped inside a square root and its derivative $x$ waiting right outside the door — that screams substitution! In the second integral, $x$ and $\ln x$ have nothing to do with each other's derivatives, so substitution stalls, and integration by parts takes over by differentiating the stubborn $\ln x$ into the friendly $\frac{1}{x}$. Once you pick the right tool, the algebra practically does itself."
