# Problem 07: Integration by Parts as Reversing the Product Rule

## 1. The Original Problem

Compute

$$
\int x e^x\,dx.
$$

First write the product differentiation rule and, on that basis, explain the meaning of the integration-by-parts formula. Verify the result by differentiation.

---

## 2. What Are We Trying to Find?

1. State the product rule for differentiating a product $u(x)v(x)$.
2. Derive the integration-by-parts formula from the product rule and explain its conceptual meaning and strategic purpose.
3. Apply integration by parts to compute $\int x e^x\,dx$.
4. Verify the final antiderivative explicitly by differentiation using the product rule.

---

## 3. Before Calculating: What Idea Do We Need?

- **Why substitution does not work here:** Unlike Problem 5, namely $\int x e^{x^2}\,dx$, the exponent of $e^x$ is simply $x$, whose derivative is $1$ rather than $x$. The integrand $x e^x$ is a *product* of two unrelated function types—a polynomial $x$ and an exponential $e^x$—so we need a technique that reverses the product rule rather than the chain rule.
- **Product rule of differentiation:** For differentiable functions $u(x)$ and $v(x)$,

$$
\bigl(u(x)v(x)\bigr)' = u'(x)v(x) + u(x)v'(x).
$$

- **Integration by parts:** Integrating and rearranging the product rule trades one integral for another, shifting the derivative from $v$ onto $u$.
- **Basic exponential antiderivative:** $\int e^x\,dx = e^x + C$.

---

## 4. Step-by-Step Solution

### Step 1: Write the Product Rule and Derive Integration by Parts

Suppose $u(x)$ and $v(x)$ are continuously differentiable functions on an interval. The **product rule** states:

$$
\frac{d}{dx}\bigl(u(x)v(x)\bigr) = u'(x)v(x) + u(x)v'(x).
$$

Integrate both sides with respect to $x$:

$$
u(x)v(x) = \int u'(x)v(x)\,dx + \int u(x)v'(x)\,dx.
$$

Subtract $\int u'(x)v(x)\,dx$ from both sides to isolate $\int u(x)v'(x)\,dx$:

$$
\int u(x)v'(x)\,dx = u(x)v(x) - \int u'(x)v(x)\,dx.
$$

In compact differential notation, setting $du = u'(x)\,dx$ and $dv = v'(x)\,dx$, this reads

$$
\int u\,dv = uv - \int v\,du.
$$

**Meaning of the integration-by-parts formula:**
Integration by parts does *not* evaluate an integral directly in a single leap; instead, it is a **derivative-transfer tool**. In the original integral $\int u(x)v'(x)\,dx$, the derivative sits on $v$. The formula expresses this integral as the boundary product $u(x)v(x)$ minus a new integral $\int u'(x)v(x)\,dx$ in which the derivative has moved onto $u$. The trade is productive whenever differentiating $u$ simplifies it and integrating $v'$ does not complicate $v$, making the new integral $\int u'(x)v(x)\,dx$ much easier to evaluate than the original.

### Step 2: Choose the Factors for $\int x e^x\,dx$

We view $x e^x$ as $u(x) \cdot v'(x)$ by choosing:

$$
u(x) = x \implies u'(x) = 1 \qquad (\text{so } du = dx),
$$

$$
v'(x) = e^x \implies v(x) = e^x \qquad (\text{so } dv = e^x\,dx).
$$

Notice why this choice works immediately: differentiating $u(x) = x$ drops the polynomial degree from $1$ to $0$, turning $x$ into $1$, while integrating $v'(x) = e^x$ leaves $e^x$ completely unchanged. Note also that we choose the simplest antiderivative $v(x) = e^x$ with constant $0$—any other constant in $v$ cancels out in the formula.

### Step 3: Apply the Formula and Finish the Calculation

Substitute $u = x$, $du = dx$, $v = e^x$, and $dv = e^x\,dx$ into $\int u\,dv = uv - \int v\,du$:

$$
\begin{aligned}
\int x e^x\,dx &= x e^x - \int e^x \cdot 1\,dx \\
&= x e^x - \int e^x\,dx \\
&= x e^x - e^x + C \\
&= (x - 1)e^x + C,
\end{aligned}
$$

where $C \in \mathbb{R}$. The result holds for all $x \in \mathbb{R}$.

### Step 4: Verify the Result by Differentiation

Let $F(x) = (x - 1)e^x + C$. Differentiating with the product rule gives

$$
\begin{aligned}
F'(x) &= \frac{d}{dx}\bigl((x - 1)e^x + C\bigr) \\
&= \frac{d}{dx}(x - 1) \cdot e^x + (x - 1)\frac{d}{dx}(e^x) + 0 \\
&= 1 \cdot e^x + (x - 1)e^x \\
&= e^x + x e^x - e^x \\
&= x e^x.
\end{aligned}
$$

Notice how the $+e^x$ and $-e^x$ terms cancel cleanly, leaving $x e^x$ identically on $\mathbb{R}$.

---

## 5. Final Answer & Conclusion

- **Product rule and integration-by-parts formula:** From $(uv)' = u'v + uv'$, integrating and rearranging yields

$$
\int u(x)v'(x)\,dx = u(x)v(x) - \int u'(x)v(x)\,dx,
$$

  which transfers differentiation from one factor of a product to the other in order to produce a simpler integral.
- **Indefinite integral on $\mathbb{R}$:**

$$
\int x e^x\,dx = x e^x - e^x + C = (x - 1)e^x + C, \qquad C \in \mathbb{R}.
$$

- **Verification:** Differentiating $(x - 1)e^x + C$ by the product rule yields $e^x + (x - 1)e^x = x e^x$.

---

## 6. Quick Verification

1. **Check that adding an arbitrary constant $k$ to $v(x) = e^x + k$ does not change the result:**
   With $u = x$ and $v = e^x + k$:

$$
u v - \int v\,du = x(e^x + k) - \int (e^x + k)\,dx = x e^x + kx - (e^x + kx) + C = (x - 1)e^x + C.
$$

   The extra $kx$ terms cancel identically, confirming why picking the simplest antiderivative $v = e^x$ is always valid.

2. **Numerical derivative check at $x = 2$:**
   At $x = 2$, the integrand equals $f(2) = 2e^2 \approx 14.7781122$.
   Using $F(x) = (x - 1)e^x$ with $h = 0.001$:
   - $F(2.001) = 1.001\,e^{2.001} \approx 7.4038453$,
   - $F(1.999) = 0.999\,e^{1.999} \approx 7.3742891$,
   - Symmetric difference quotient:

$$
\frac{F(2.001) - F(1.999)}{0.002} \approx \frac{0.0295562}{0.002} \approx 14.77812 \approx 2e^2 = f(2).
$$

---

## 7. Common Mistakes to Avoid

- **Integrating each factor separately:** Writing $\int x e^x\,dx = \frac{1}{2}x^2 e^x + C$ is false because integration does not distribute across products. Differentiating $\frac{1}{2}x^2 e^x$ gives $x e^x + \frac{1}{2}x^2 e^x$, which contains an unwanted $\frac{1}{2}x^2 e^x$ term.
- **Using a plus sign instead of a minus sign in the formula:** Writing $uv + \int v\,du$ yields $x e^x + e^x + C$, whose derivative is $(x + 2)e^x \ne x e^x$. Remember that the minus sign comes from subtracting $\int u'v\,dx$ across the equals sign in the product rule.
- **Forgetting to integrate the remaining term $\int v\,du$:** Stopping at $x e^x - e^x$ is right *only* here by coincidence because $\int e^x\,dx = e^x$. In general you must actually integrate $v\,du$, not just copy $v$.
- **Choosing $u = e^x$ and $dv = x\,dx$:** That reverses the simplification and produces $\frac{1}{2}x^2 e^x - \frac{1}{2}\int x^2 e^x\,dx$, which increases the power of $x$ from $1$ to $2$ instead of eliminating it.

---

## 8. How I Would Explain This in Class

> "Substitution is the reverse gear of the chain rule; integration by parts is the reverse gear of the product rule. When you differentiate $x e^x$, the product rule gives you $x e^x$ plus an extra leftover $e^x$. Integration by parts simply says: keep $x e^x$ as your first guess, and then subtract the integral of that leftover piece $e^x$ to clean up the overshoot. That is why the answer $(x - 1)e^x$ is just $x e^x$ minus the correction $e^x$—and when you differentiate it, the correction kills the leftover on the spot."
