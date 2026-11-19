# Problem 04: Substitution as Reversing the Chain Rule

## 1. The Original Problem

Compute

$$
\int 2x(x^2 + 1)^4\,dx.
$$

Before calculating, identify a candidate for the new variable $u$ and show that its derivative appears in the integral. Finally, verify the result by differentiation.

---

## 2. What Are We Trying to Find?

1. Recognize the composite structure of the integrand and choose an appropriate substitution variable $u = g(x)$ before computing.
2. Show explicitly that the derivative $g'(x)$ appears as a multiplicative factor in the integral, matching the chain-rule pattern.
3. Compute the indefinite integral $\int 2x(x^2 + 1)^4\,dx$ using the substitution and rewrite the final antiderivative in terms of $x$.
4. Verify the result explicitly by differentiation using the chain rule.

---

## 3. Before Calculating: What Idea Do We Need?

- **The chain rule in reverse (substitution rule):** If $F$ is an antiderivative of $f$ and $u = g(x)$ is differentiable, then by the chain rule,

$$
\frac{d}{dx}\bigl(F(g(x))\bigr) = F'(g(x))\,g'(x) = f(g(x))\,g'(x).
$$

  Integrating both sides gives the substitution formula:

$$
\int f(g(x))\,g'(x)\,dx = \int f(u)\,du = F(u) + C = F(g(x)) + C,
$$

  where $u = g(x)$ and $du = g'(x)\,dx$.
- **How to spot $u$:** Look for an *inner* expression inside a power, root, exponential, or trigonometric function whose derivative also appears outside as a factor, up to a constant multiple.
- **Power rule in the new variable:** Once rewritten in terms of $u$, the integral reduces to $\int u^4\,du = \frac{u^5}{5} + C$.

---

## 4. Step-by-Step Solution

### Step 1: Identify the Candidate for $u$ and Locate Its Derivative

Examine the structure of the integrand $2x(x^2 + 1)^4$:

- It contains a composite power $(x^2 + 1)^4$, with outer function $f(u) = u^4$ and inner function

$$
u = g(x) = x^2 + 1.
$$

- Differentiating this candidate with respect to $x$ gives

$$
\frac{du}{dx} = 2x, \qquad \text{so} \qquad du = 2x\,dx.
$$

- Now compare with the original integral, reordered to highlight the two pieces:

$$
\int \underbrace{(x^2 + 1)^4}_{u^4} \cdot \underbrace{2x\,dx}_{du}.
$$

The derivative $2x$ of the inner function $x^2 + 1$ appears *verbatim* as the remaining factor in the integrand. This exact match confirms that substitution reverses the chain rule cleanly.

### Step 2: Transform and Evaluate the Integral in Terms of $u$

Replacing $x^2 + 1$ by $u$ and $2x\,dx$ by $du$ transforms the integral into a single power-rule integral:

$$
\int 2x(x^2 + 1)^4\,dx = \int u^4\,du = \frac{u^5}{5} + C, \qquad C \in \mathbb{R}.
$$

### Step 3: Substitute Back to the Original Variable $x$

Since the original integral was asked in terms of $x$, replace $u$ with $x^2 + 1$:

$$
\int 2x(x^2 + 1)^4\,dx = \frac{(x^2 + 1)^5}{5} + C, \qquad C \in \mathbb{R}.
$$

This antiderivative is defined and smooth for all $x \in \mathbb{R}$.

### Step 4: Verify the Result by Differentiation

Let $F(x) = \frac{(x^2 + 1)^5}{5} + C$. Differentiating with respect to $x$ via the chain rule yields

$$
\begin{aligned}
F'(x) &= \frac{d}{dx}\left(\frac{(x^2 + 1)^5}{5} + C\right) \\
&= \frac{1}{5} \cdot 5(x^2 + 1)^4 \cdot \frac{d}{dx}(x^2 + 1) + 0 \\
&= (x^2 + 1)^4 \cdot 2x \\
&= 2x(x^2 + 1)^4.
\end{aligned}
$$

The derivative recovers the exact integrand for every $x \in \mathbb{R}$.

---

## 5. Final Answer & Conclusion

- **Chosen substitution:** $u = x^2 + 1$, with $du = 2x\,dx$, which matches the factor $2x\,dx$ already present in the integral.
- **Indefinite integral on $\mathbb{R}$:**

$$
\int 2x(x^2 + 1)^4\,dx = \frac{(x^2 + 1)^5}{5} + C, \qquad C \in \mathbb{R}.
$$

- **Verification:** Differentiating $\frac{(x^2 + 1)^5}{5} + C$ by the chain rule gives $2x(x^2 + 1)^4$.

---

## 6. Quick Verification

1. **Independent check by polynomial expansion:**
   Using the binomial theorem, $(x^2 + 1)^4 = x^8 + 4x^6 + 6x^4 + 4x^2 + 1$, so

$$
2x(x^2 + 1)^4 = 2x^9 + 8x^7 + 12x^5 + 8x^3 + 2x.
$$

   Integrating term by term gives

$$
\frac{1}{5}x^{10} + x^8 + 2x^6 + 2x^4 + x^2 + C_1.
$$

   Meanwhile, expanding our substitution answer gives

$$
\frac{(x^2 + 1)^5}{5} + C = \frac{x^{10} + 5x^8 + 10x^6 + 10x^4 + 5x^2 + 1}{5} + C = \frac{1}{5}x^{10} + x^8 + 2x^6 + 2x^4 + x^2 + \left(\frac{1}{5} + C\right).
$$

   The two families are identical, since $\frac{1}{5} + C$ is just another arbitrary constant $C_1$. Notice how much faster and cleaner substitution is than expanding!

2. **Pointwise value check of the derivative at $x = 1$:**
   At $x = 1$, the integrand is $2(1)(1^2 + 1)^4 = 2 \cdot 16 = 32$.
   For $F(x) = \frac{(x^2 + 1)^5}{5}$, we have $F'(1) = (1^2 + 1)^4 \cdot 2(1) = 16 \cdot 2 = 32$, confirming the result.

---

## 7. Common Mistakes to Avoid

- **Leaving the answer in terms of $u$:** Stopping at $\frac{u^5}{5} + C$ is incomplete because $u$ was an auxiliary variable introduced by the solver. Always substitute $u = x^2 + 1$ back at the end.
- **Integrating $2x$ and $(x^2 + 1)^4$ separately and multiplying:** The integral of a product is *not* the product of the integrals. Writing $x^2 \cdot \frac{(x^2 + 1)^5}{5} + C$ fails differentiation completely.
- **Forgetting that $2x$ is absorbed into $du$:** Because $du = 2x\,dx$, the factor $2x$ disappears into $du$ rather than remaining outside the integral. Keeping an extra $2x$ produces a mixed integral containing both $x$ and $u$, which is invalid.
- **Ignoring the chain-rule factor when differentiating to check:** When checking $\frac{(x^2 + 1)^5}{5}$, you must multiply by the inner derivative $(x^2 + 1)' = 2x$; omitting it would make a correct answer look wrong.

---

## 8. How I Would Explain This in Class

> "Whenever you see a complicated chunk raised to a power, pause before reaching for algebra and ask a detective question: is the derivative of the inside sitting right outside? Here the inside is $x^2 + 1$, and its derivative $2x$ is standing right next to it in plain sight. That $2x$ is the footprint left behind by the chain rule. When we set $u = x^2 + 1$, the whole $2x\,dx$ folds neatly into $du$, leaving just $\int u^4\,du$, which takes one line to finish."
