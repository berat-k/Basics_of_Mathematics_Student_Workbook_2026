# Problem 08: Choosing the Factors in Integration by Parts

## 1. The Original Problem

Compute

$$
\int x\cos x\,dx.
$$

Before calculating, justify why it is convenient to differentiate $x$ and integrate $\cos x$, rather than the other way around.

---

## 2. What Are We Trying to Find?

1. Compare both possible assignments of $u$ and $dv$ for $\int x\cos x\,dx$ *before* calculating, and justify clearly why differentiating $x$ and integrating $\cos x$ succeeds while the opposite choice makes the integral harder.
2. Compute $\int x\cos x\,dx$ using integration by parts with the convenient choice.
3. Verify the final antiderivative explicitly by differentiation using the product rule.

---

## 3. Before Calculating: What Idea Do We Need?

- **Integration-by-parts formula:**

$$
\int u\,dv = uv - \int v\,du.
$$

- **The guiding principle for choosing $u$ and $dv$:**
  1. $dv$ must be easy to integrate into $v$.
  2. The resulting integral $\int v\,du$ must be *simpler* than the original integral $\int u\,dv$.
  Therefore, we want a factor $u$ whose derivative $u'$ simplifies the integrand—such as lowering the degree of a polynomial—paired with a factor $dv$ whose antiderivative $v$ stays at the same level of simplicity.
- **Basic trigonometric antiderivatives:** $\int \cos x\,dx = \sin x + C$ and $\int \sin x\,dx = -\cos x + C$.

---

## 4. Step-by-Step Solution

### Step 1: Justify the Choice of Factors Before Calculating

The integrand $x\cos x$ is a product of two factors, $x$ and $\cos x$, so there are two natural ways to assign $u$ and $dv$. Let us test both options side by side to see what the new integral $\int v\,du$ looks like:

| Choice | Differentiated factor $u$ | Integrated factor $dv$ | Resulting pieces $du$ and $v$ | New integral $\int v\,du$ | Assessment |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Choice A (convenient)** | $u = x$ | $dv = \cos x\,dx$ | $du = dx$, $v = \sin x$ | $\int \sin x\,dx$ | **Simpler:** polynomial factor vanishes completely! |
| **Choice B (counterproductive)** | $u = \cos x$ | $dv = x\,dx$ | $du = -\sin x\,dx$, $v = \frac{1}{2}x^2$ | $-\frac{1}{2}\int x^2 \sin x\,dx$ | **Harder:** polynomial degree rises from $1$ to $2$! |

Let us state the reason explicitly:

- **Why Choice A works:** Differentiating $x$ reduces its degree from $1$ to $0$, turning $x$ into the constant $1$ and completely eliminating the algebraic factor from the new integral. Meanwhile, integrating $\cos x$ produces $\sin x$, which has the exact same trigonometric complexity as $\cos x$. The product $x\cos x$ therefore simplifies to a single basic trigonometric function $\sin x$.
- **Why Choice B fails to simplify:** Differentiating $\cos x$ gives $-\sin x$, which does *not* simplify the trigonometric factor—it merely cycles between sine and cosine. Simultaneously, integrating $x$ raises its degree to $\frac{1}{2}x^2$. Thus Choice B turns a degree-$1$ product into a more complicated degree-$2$ product $-\frac{1}{2}\int x^2\sin x\,dx$, moving us *away* from an elementary integral.

### Step 2: Compute $\int x\cos x\,dx$ Using Choice A

Set

$$
u = x \implies du = dx,
$$

$$
dv = \cos x\,dx \implies v = \sin x.
$$

Apply the integration-by-parts formula $\int u\,dv = uv - \int v\,du$:

$$
\begin{aligned}
\int x\cos x\,dx &= x\sin x - \int \sin x\,dx \\
&= x\sin x - (-\cos x) + C \\
&= x\sin x + \cos x + C,
\end{aligned}
$$

where $C \in \mathbb{R}$. Watch the double negative carefully: subtracting $\int \sin x\,dx = -\cos x$ produces $+\cos x$. The antiderivative is valid on the entire real line $\mathbb{R}$.

### Step 3: Verify the Result by Differentiation

Let $F(x) = x\sin x + \cos x + C$. Differentiating with respect to $x$ using the product rule on $x\sin x$ yields

$$
\begin{aligned}
F'(x) &= \frac{d}{dx}\bigl(x\sin x + \cos x + C\bigr) \\
&= \bigl(1 \cdot \sin x + x \cdot \cos x\bigr) + (-\sin x) + 0 \\
&= \sin x + x\cos x - \sin x \\
&= x\cos x.
\end{aligned}
$$

The $+\sin x$ from differentiating $x\sin x$ cancels the $-\sin x$ from differentiating $+\cos x$, leaving $x\cos x$ identically for all $x \in \mathbb{R}$.

---

## 5. Final Answer & Conclusion

- **Justification of factor choice:** Choosing $u = x$ and $dv = \cos x\,dx$ reduces the degree of $x$ to $0$ while keeping the trigonometric complexity unchanged, transforming the problem into the immediate integral $\int \sin x\,dx$. The reverse choice $u = \cos x$, $dv = x\,dx$ increases the polynomial degree to $x^2$ and produces the harder integral $-\frac{1}{2}\int x^2\sin x\,dx$.
- **Indefinite integral on $\mathbb{R}$:**

$$
\int x\cos x\,dx = x\sin x + \cos x + C, \qquad C \in \mathbb{R}.
$$

- **Verification:** Differentiating $x\sin x + \cos x + C$ yields $(\sin x + x\cos x) - \sin x = x\cos x$.

---

## 6. Quick Verification

1. **Parity check (odd integrand gives an even antiderivative):**
   The integrand $f(x) = x\cos x$ is odd because $f(-x) = (-x)\cos(-x) = -x\cos x = -f(x)$.
   Check our antiderivative $F(x) = x\sin x + \cos x + C$:

$$
F(-x) = (-x)\sin(-x) + \cos(-x) + C = (-x)(-\sin x) + \cos x + C = x\sin x + \cos x + C = F(x).
$$

   Indeed, $F$ is an even function on $\mathbb{R}$, matching the oddness of $f$.

2. **Exact value and numerical derivative check at $x = \pi$:**
   At $x = \pi$, the integrand equals $f(\pi) = \pi\cos\pi = -\pi \approx -3.1415927$.
   Using $F(x) = x\sin x + \cos x$ with $h = 0.001$:
   - $F(\pi + 0.001) \approx (\pi + 0.001)(-0.0009999998) + (-0.9999995) \approx -1.00314209$,
   - $F(\pi - 0.001) \approx (\pi - 0.001)(+0.0009999998) + (-0.9999995) \approx -0.99685891$,
   - Symmetric difference quotient:

$$
\frac{F(\pi + 0.001) - F(\pi - 0.001)}{0.002} \approx \frac{-0.00628318}{0.002} \approx -3.14159 \approx -\pi = f(\pi).
$$

   Note that if the sign of $\cos x$ were wrong, i.e., $x\sin x - \cos x$, differentiating would give $x\cos x + 2\sin x$, which fails at $x = \frac{\pi}{2}$ where $2\sin(\frac{\pi}{2}) = 2 \ne 0$.

---

## 7. Common Mistakes to Avoid

- **Sign error on $-\int \sin x\,dx$:** Writing $x\sin x - \cos x + C$ instead of $x\sin x + \cos x + C$ is the most frequent mistake on this problem. Because $\int \sin x\,dx = -\cos x$, subtracting it yields $- (-\cos x) = +\cos x$.
- **Choosing $u = \cos x$ and $dv = x\,dx$ without checking $\int v\,du$:** This is legally valid algebraically, because $x\cos x$ really does satisfy $\int x\cos x\,dx = \frac{1}{2}x^2\cos x + \frac{1}{2}\int x^2\sin x\,dx$, yet it walks uphill instead of downhill. Always preview $\int v\,du$ before committing.
- **Mixing up the signs of $(\cos x)'$ and $\int \cos x\,dx$:** Here $dv = \cos x\,dx$ integrates to $v = +\sin x$, not $-\sin x$. Writing $v = -\sin x$ flips every sign in the answer.
- **Attempting substitution $u = \cos x$:** Setting $u = \cos x$ gives $du = -\sin x\,dx$, which does not appear in $x\cos x\,dx$. Products of unlike functions such as $x\cos x$ call for integration by parts, not substitution.

---

## 8. How I Would Explain This in Class

> "Before you jump into integration by parts, play a two-second chess move and look one step ahead. You have two actors on stage: $x$ and $\cos x$. Cosine never gets simpler when you differentiate or integrate it—it just dances back and forth with sine forever. The polynomial $x$, on the other hand, vanishes down to $1$ the moment you differentiate it, whereas integrating it makes it bulkier into $\frac{1}{2}x^2$. So the strategy writes itself: hand the derivative to $x$ to kill it off, and hand the integral to $\cos x$ because it doesn't mind at all."
