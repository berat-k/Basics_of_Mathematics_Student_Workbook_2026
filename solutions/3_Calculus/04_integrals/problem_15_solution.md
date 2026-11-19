# Problem 15: Recovering a Function from Its Derivative and a Condition

## 1. The Original Problem

The function $F$ satisfies

$$
F'(x)=2xe^{x^2}
$$

and

$$
F(0)=3.
$$

1. Recognize the method needed to find the function $F$.
2. Determine the entire family of functions with the given derivative.
3. Use the condition $F(0)=3$ to determine the correct constant.
4. Verify the final result by differentiation and substitution of $x=0$.

---

## 2. What Are We Trying to Find?

1. The integration technique needed to recover $F(x)$ from $F'(x) = 2xe^{x^2}$, together with the structural reason for choosing it.
2. The complete family of antiderivatives $F(x)$ whose derivative is $2xe^{x^2}$, containing the arbitrary constant $C$.
3. The unique value of the constant $C$ forced by the initial condition $F(0) = 3$, and thus the unique function $F(x)$.
4. A two-part verification confirming both $F'(x) = 2xe^{x^2}$ and $F(0) = 3$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Antiderivatives and initial-value problems:** Knowing $F'(x)$ determines $F(x)$ only **up to an additive constant $C$**, because any two functions with the same derivative on $\mathbb{R}$ differ by a constant. Graphically, $F(x) + C$ is a family of vertically shifted parallel curves.
- **Role of an initial condition:** A single point condition such as $F(0) = 3$ pins down the vertical shift and selects **one unique curve** from the infinite family.
- **$u$-substitution, reversing the chain rule:** To compute $F(x) = \int 2xe^{x^2}\,dx$, look for a composite function $e^{g(x)}$ multiplied by the derivative $g'(x)$. Here the inner exponent is $g(x) = x^2$, and its exact derivative $g'(x) = 2x$ stands directly in front of the exponential!
- **Key exponential fact:** Never forget that $e^0 = 1$, not $0$.

---

## 4. Step-by-Step Solution

### Step 1: Recognize the Method Needed to Find $F$

Since we know the derivative $F'(x) = 2xe^{x^2}$, finding $F(x)$ means evaluating the indefinite integral

$$
F(x) = \int 2xe^{x^2}\,dx.
$$

Inspect the structure of the integrand:

- We have an exponential function composed with an inner quadratic function: $e^{x^2}$.
- The derivative of the inner function $u = x^2$ is $\frac{du}{dx} = 2x$, which appears **verbatim** as a factor multiplying $e^{x^2}$.

This is the exact pattern of the chain rule in reverse, $\frac{d}{dx}\left(e^{u(x)}\right) = u'(x)e^{u(x)}$. Therefore, the appropriate method is **$u$-substitution** with $u = x^2$.

### Step 2: Determine the Entire Family of Functions with Derivative $2xe^{x^2}$

Set

$$
u = x^2 \implies du = 2x\,dx.
$$

Substitute $u$ and $du$ into the integral:

$$
F(x) = \int 2xe^{x^2}\,dx = \int e^{u}\,du = e^{u} + C.
$$

Replace $u$ with $x^2$:

$$
F(x) = e^{x^2} + C, \qquad C \in \mathbb{R}.
$$

This expression describes the **entire family** of functions on $\mathbb{R}$ whose derivative is $2xe^{x^2}$. Every choice of $C$ shifts the symmetric curve $y = e^{x^2}$ vertically without changing its slope at any $x$.

### Step 3: Use the Condition $F(0) = 3$ to Determine $C$

Substitute $x = 0$ into the general formula $F(x) = e^{x^2} + C$:

$$
F(0) = e^{0^2} + C = e^{0} + C = 1 + C.
$$

Impose the given condition $F(0) = 3$:

$$
1 + C = 3 \implies C = 3 - 1 = 2.
$$

Substituting $C = 2$ back into the general family gives the unique solution:

$$
F(x) = e^{x^2} + 2.
$$

### Step 4: Verify the Final Result

We check both conditions required by the problem statement:

1. **Differentiation check:** Apply the chain rule to $F(x) = e^{x^2} + 2$:

$$
F'(x) = \frac{d}{dx}\left(e^{x^2} + 2\right) = e^{x^2}\cdot\frac{d}{dx}(x^2) + 0 = e^{x^2}\cdot 2x = 2xe^{x^2}.
$$

This matches the given derivative for all $x \in \mathbb{R}$.

2. **Initial-condition check at $x = 0$:** Substitute $x = 0$ into $F(x) = e^{x^2} + 2$:

$$
F(0) = e^{0^2} + 2 = e^{0} + 2 = 1 + 2 = 3.
$$

This matches the given condition $F(0) = 3$ exactly.

---

## 5. Final Answer & Conclusion

1. **Method:** $u$-substitution with $u = x^2$ and $du = 2x\,dx$, recognizing the chain rule in reverse.
2. **Entire family of antiderivatives:**

$$
F(x) = e^{x^2} + C, \qquad C \in \mathbb{R}.
$$

3. **Constant determined by $F(0) = 3$:** Since $e^0 + C = 1 + C = 3$, we obtain $C = 2$, so the unique function is

$$
F(x) = e^{x^2} + 2.
$$

4. **Verification:** Both $F'(x) = 2xe^{x^2}$ and $F(0) = 3$ hold identically.

---

## 6. Quick Verification

1. **Definite-integral formulation check:** By the Fundamental Theorem of Calculus, any function $F$ with $F'(t) = 2te^{t^2}$ and $F(0) = 3$ must satisfy

$$
F(x) = F(0) + \int_{0}^{x} 2te^{t^2}\,dt.
$$

Using $u = t^2$ with limits $u(0) = 0$ and $u(x) = x^2$:

$$
F(x) = 3 + \int_{0}^{x^2} e^{u}\,du = 3 + \Big[e^{u}\Big]_{0}^{x^2} = 3 + (e^{x^2} - 1) = e^{x^2} + 2.
$$

This independently confirms $C = 2$ without even writing an arbitrary constant!
2. **Numerical point-slope check at $x = 1$:**
   - $F(1) = e^{1} + 2 \approx 2.71828 + 2 = 4.71828$.
   - $F'(1) = 2(1)e^{1} = 2e \approx 5.43656$.
   - Compare with the small-step difference quotient at $h = 0.001$: $F(1.001) = e^{1.002001} + 2 \approx 4.723727$, so

$$
\frac{F(1.001) - F(1)}{0.001} \approx \frac{4.723727 - 4.718282}{0.001} \approx 5.445 \approx 5.437 = 2e.
$$

   Both value and slope align tightly.

---

## 7. Common Mistakes to Avoid

- **Assuming $C$ always equals $F(0)$:** Many students automatically write $C = 3$ because $F(0) = 3$, forgetting that $e^{0} = 1$, not $0$. That produces $F(x) = e^{x^2} + 3$, for which $F(0) = 4 \ne 3$! Always substitute $x = 0$ explicitly and solve for $C$.
- **Leaving an extra factor of $2x$ after substituting:** Writing $\int 2xe^{x^2}\,dx = 2xe^{x^2} + C$ or $x^2 e^{x^2} + C$. Remember that $2x\,dx$ is completely absorbed into $du$, leaving only $\int e^u\,du = e^u + C$.
- **Trying integration by parts instead of substitution:** Attempting parts on $2x \cdot e^{x^2}$ fails immediately because $e^{x^2}$ has no elementary antiderivative on its own. Always check for $u$-substitution first!
- **Forgetting to state the general family before plugging in $F(0) = 3$:** The problem explicitly asks for the entire family first, and then the specific constant. Skipping $+ C$ loses the conceptual meaning of the initial condition.

---

## 8. How I Would Explain This in Class

> "Knowing $F'(x)$ is like having a complete map of the steepness of a mountain road at every kilometer, without knowing what altitude you started at. Integrating $2xe^{x^2}$ via $u = x^2$ gives you the exact shape of the road, $y = e^{x^2} + C$, floating at any height you like. Then the clue $F(0) = 3$ drops a pin on the map: at $x = 0$, the road passes through height $3$. Because $e^0$ already puts you at height $1$, you only need to lift the curve by $C = 2$ more units — not $3$ — to hit $3$ right on the nose."
