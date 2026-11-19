# Problem 05: The Same Substitution in a Different Context

## 1. The Original Problem

Compute

$$
\int x e^{x^2}\,dx.
$$

First compare the structure with Problem 4 and explain what is common despite the different appearance of the function.

---

## 2. What Are We Trying to Find?

1. Compare the structure of $\int x e^{x^2}\,dx$ with Problem 4, namely $\int 2x(x^2 + 1)^4\,dx$, and explain what structural feature both integrals share despite involving different types of outer functions.
2. Choose the appropriate substitution $u = g(x)$ and handle the constant factor difference between $x\,dx$ and $du = 2x\,dx$.
3. Compute the indefinite integral $\int x e^{x^2}\,dx$ and express the result in terms of $x$.
4. Verify the final antiderivative explicitly by differentiation.

---

## 3. Before Calculating: What Idea Do We Need?

- **Structure over appearance in substitution:** The substitution method applies whenever an integrand has the form $k \cdot f(g(x))\,g'(x)$ for some nonzero constant $k$. What triggers substitution is the *pairing* of an inner function $g(x)$ with its derivative $g'(x)$ up to a constant multiple—not whether the outer function $f$ is a power, exponential, trigonometric function, or root.
- **Adjusting for a missing constant factor:** Constant factors can be multiplied and divided freely across the integral sign, because $\int c\,h(x)\,dx = c\int h(x)\,dx$. A missing constant factor like $2$ is never an obstacle; a missing *variable* factor like $x$ would be.
- **Basic exponential antiderivative:** $\int e^u\,du = e^u + C$.

---

## 4. Step-by-Step Solution

### Step 1: Compare the Structure with Problem 4

Place Problem 4 and Problem 5 side by side in a structural table:

| Feature | Problem 4: $\int 2x(x^2 + 1)^4\,dx$ | Problem 5: $\int x e^{x^2}\,dx$ |
| :--- | :--- | :--- |
| Outer function $f(u)$ | Power function $u^4$ | Exponential function $e^u$ |
| Inner function $u = g(x)$ | $x^2 + 1$ | $x^2$ |
| Derivative of inner function $g'(x)$ | $2x$ | $2x$ |
| Factor present outside $f(g(x))$ | $2x$, exact match with $g'(x)$ | $x = \frac{1}{2}(2x)$, matches $g'(x)$ up to constant $\frac{1}{2}$ |
| Resulting integral in $u$ | $\int u^4\,du$ | $\frac{1}{2}\int e^u\,du$ |

**What is common despite the different appearance?**
Although Problem 4 is purely algebraic while Problem 5 involves a transcendental exponential function, both integrals share the exact same **chain-rule structure** $\int f(g(x))\,g'(x)\,dx$ up to a constant factor:

1. Each integrand contains a composite function with a quadratic inner expression whose derivative is $2x$.
2. Outside the composite expression sits a linear factor proportional to $x$, which supplies the needed inner derivative $g'(x) = 2x$.
3. The only minor difference is the missing factor of $2$ in front of $x$ in Problem 5, which is immediately resolved by writing $x\,dx = \frac{1}{2}(2x\,dx) = \frac{1}{2}\,du$.

This illustrates a central lesson of integration: **we recognize substitution by the relationship between inner and outer parts, not by the family of functions involved.**

### Step 2: Set Up the Substitution

Choose the exponent as the new variable:

$$
u = x^2.
$$

Differentiating with respect to $x$ gives

$$
\frac{du}{dx} = 2x \implies du = 2x\,dx \implies x\,dx = \frac{1}{2}\,du.
$$

Notice that the variable factor $x$ is completely accounted for by $\frac{1}{2}\,du$.

### Step 3: Evaluate the Integral and Substitute Back

Rewrite the integral completely in terms of $u$:

$$
\int x e^{x^2}\,dx = \int e^{x^2} \cdot x\,dx = \int e^u \cdot \frac{1}{2}\,du = \frac{1}{2}\int e^u\,du.
$$

Using the basic antiderivative $\int e^u\,du = e^u + C$ and substituting $u = x^2$ back yields

$$
\int x e^{x^2}\,dx = \frac{1}{2}e^u + C = \frac{1}{2}e^{x^2} + C, \qquad C \in \mathbb{R}.
$$

This result is valid on the entire real line $\mathbb{R}$.

### Step 4: Verify the Result by Differentiation

Let $F(x) = \frac{1}{2}e^{x^2} + C$. Differentiating with respect to $x$ via the chain rule gives

$$
\begin{aligned}
F'(x) &= \frac{d}{dx}\left(\frac{1}{2}e^{x^2} + C\right) \\
&= \frac{1}{2} e^{x^2} \cdot \frac{d}{dx}(x^2) + 0 \\
&= \frac{1}{2} e^{x^2} \cdot 2x \\
&= x e^{x^2}.
\end{aligned}
$$

The factor of $\frac{1}{2}$ cancels the $2$ produced by the chain rule, recovering $x e^{x^2}$ identically for all $x \in \mathbb{R}$.

---

## 5. Final Answer & Conclusion

- **Structural comparison with Problem 4:** Both $\int 2x(x^2 + 1)^4\,dx$ and $\int x e^{x^2}\,dx$ have the composite-times-inner-derivative form $\int k\,f(g(x))\,g'(x)\,dx$ with quadratic inner function and derivative $g'(x) = 2x$. Only the outer function changes from $u^4$ to $e^u$, and a constant factor $\frac{1}{2}$ adjusts $x$ to $2x$.
- **Indefinite integral on $\mathbb{R}$:**

$$
\int x e^{x^2}\,dx = \frac{1}{2}e^{x^2} + C, \qquad C \in \mathbb{R}.
$$

- **Verification:** Differentiating $\frac{1}{2}e^{x^2} + C$ by the chain rule yields $\frac{1}{2}e^{x^2}\cdot 2x = x e^{x^2}$.

---

## 6. Quick Verification

1. **Symmetry check (odd integrand gives an even antiderivative):**
   The integrand $f(x) = x e^{x^2}$ is an *odd* function because $f(-x) = (-x)e^{(-x)^2} = -x e^{x^2} = -f(x)$. Every antiderivative of an odd function on $\mathbb{R}$ must be an *even* function. Indeed, for $F(x) = \frac{1}{2}e^{x^2} + C$, we have

$$
F(-x) = \frac{1}{2}e^{(-x)^2} + C = \frac{1}{2}e^{x^2} + C = F(x),
$$

   so $F$ is even, consistent with $f$ being odd.

2. **Numerical derivative check at $x = 1$:**
   At $x = 1$, the integrand equals $f(1) = 1 \cdot e^1 = e \approx 2.7182818$.
   Using $F(x) = \frac{1}{2}e^{x^2}$ with $h = 0.001$:
   - $F(1.001) = \frac{1}{2}e^{1.002001} \approx 1.36186328$,
   - $F(0.999) = \frac{1}{2}e^{0.998001} \approx 1.35642671$,
   - Symmetric difference quotient:

$$
\frac{F(1.001) - F(0.999)}{0.002} \approx \frac{0.00543657}{0.002} \approx 2.718286 \approx e = f(1).
$$

---

## 7. Common Mistakes to Avoid

- **Forgetting the factor $\frac{1}{2}$:** Writing $\int x e^{x^2}\,dx = e^{x^2} + C$ overlooks that $(e^{x^2})' = 2x e^{x^2}$, which is twice too large. Always check the constant factor by differentiating.
- **Confusing $\int x e^{x^2}\,dx$ with $\int e^{x^2}\,dx$:** The outside factor $x$ is *essential* here—without it, $\int e^{x^2}\,dx$ has no elementary antiderivative at all. You may pull constants like $\frac{1}{2}$ outside an integral, never variables like $\frac{1}{2x}$.
- **Writing $\int x e^{x^2}\,dx = \frac{x^2}{2} e^{x^2} + C$:** Multiplying separate antiderivatives of $x$ and $e^{x^2}$ violates the product rule and gives derivative $x e^{x^2} + x^3 e^{x^2} \ne x e^{x^2}$.
- **Choosing $u = e^{x^2}$ unnecessarily without tracking $du$:** While $w = e^{x^2}$ actually works too because $dw = 2x e^{x^2}\,dx$ and gives $\frac{1}{2}\int dw = \frac{1}{2}w + C$, students who set $u = e^{x^2}$ often forget the chain rule in $du$ and get stuck. Setting $u = x^2$ keeps the inner-outer structure completely transparent.

---

## 8. How I Would Explain This in Class

> "If you look only at surface costumes, Problem 4 is a polynomial power and Problem 5 is an exponential, so they look like strangers. Strip away the outer costume and look at the skeleton: both have an $x^2$ tucked inside and an $x$ standing right outside ready to play the role of its derivative $2x$. Calculus does not care whether $x^2$ is wrapped inside a fourth power or inside an exponential—the exact same substitution $u = x^2$ unlocks both. The only tiny adjustment is paying for the missing factor of $2$ with a $\frac{1}{2}$ out front."
