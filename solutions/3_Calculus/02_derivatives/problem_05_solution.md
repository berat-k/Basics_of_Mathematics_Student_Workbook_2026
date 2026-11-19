# Problem 05: The Chain Rule as Working Through Layers

## 1. The Original Problem

For

$$
f(x)=(3x^2-2x+1)^5
$$

identify the inner and outer functions, compute their derivatives, and combine the result according to the chain rule. Explain the origin of the additional factor.

---

## 2. What Are We Trying to Find?

1. The explicit **inner function** $g(x)$ and **outer function** $h(u)$ such that $f(x) = h(g(x))$.
2. The derivatives $h'(u)$ and $g'(x)$ of the outer and inner layers.
3. The complete derivative $f'(x)$ combined via the chain rule and written in clean factored form.
4. A clear conceptual and mathematical explanation of why the additional factor $g'(x) = 6x - 2$ must appear.

---

## 3. Before Calculating: What Idea Do We Need?

- **Composition of functions as layers:** To evaluate $f(x) = (3x^2 - 2x + 1)^5$ for a given input $x$, we perform two operations in sequence:

```text
x  --->  u = 3x^2 - 2x + 1  --->  y = u^5
       (inner function g)       (outer function h)
```

- **The chain rule:** If $g$ is differentiable at $x$ and $h$ is differentiable at $u = g(x)$, then the composite function $f(x) = h(g(x))$ is differentiable at $x$ and

$$
f'(x) = h'(g(x)) \cdot g'(x).
$$

- **Leibniz notation for rates of change:** Writing $y = h(u)$ and $u = g(x)$, the chain rule reads

$$
\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dx}.
$$

  This shows that rates of change multiply along a chain of linked variables.

---

## 4. Step-by-Step Solution

### Step 1: Identify the Inner and Outer Functions

Look at the order of operations when computing $(3x^2 - 2x + 1)^5$:

- **Inner function** — applied first to $x$:

$$
u = g(x) = 3x^2 - 2x + 1.
$$

- **Outer function** — applied last to the result $u$:

$$
y = h(u) = u^5.
$$

Indeed, substituting $u = g(x)$ into $h(u)$ recovers $h(g(x)) = (3x^2 - 2x + 1)^5 = f(x)$.

### Step 2: Compute the Derivatives of Each Layer

Differentiate the outer function with respect to $u$, and the inner function with respect to $x$:

- **Derivative of the outer function:**

$$
h'(u) = \frac{d}{du}\left(u^5\right) = 5u^4.
$$

  Evaluated at the inner expression $u = g(x) = 3x^2 - 2x + 1$, this is:

$$
h'(g(x)) = 5(3x^2 - 2x + 1)^4.
$$

- **Derivative of the inner function:**

$$
g'(x) = \frac{d}{dx}\left(3x^2 - 2x + 1\right) = 6x - 2 = 2(3x - 1).
$$

### Step 3: Combine the Results Using the Chain Rule

Multiply the derivative of the outer layer evaluated at the inner function by the derivative of the inner layer:

$$
f'(x) = h'(g(x)) \cdot g'(x) = 5(3x^2 - 2x + 1)^4 \cdot (6x - 2).
$$

Factoring $2$ out of $(6x - 2)$ and multiplying by $5$ gives a neat factored form:

$$
f'(x) = 10(3x - 1)(3x^2 - 2x + 1)^4.
$$

### Step 4: Explain the Origin of the Additional Factor $(6x - 2)$

Why is the derivative **not** simply $5(3x^2 - 2x + 1)^4$?

1. **Sensitivity of the inner layer:** The power rule $5u^4$ measures how fast $y = u^5$ changes **per unit change in $u$**, not per unit change in $x$. When $x$ changes by a small amount $\Delta x$, the inner expression $u = 3x^2 - 2x + 1$ does not simply change by $\Delta x$; instead, it changes by approximately

$$
\Delta u \approx g'(x) \cdot \Delta x = (6x - 2) \Delta x.
$$

2. **Multiplying the two local stretch factors:** Next, the outer function $y = u^5$ magnifies that change $\Delta u$ by a factor of $h'(u) = 5u^4$:

$$
\Delta y \approx h'(u) \cdot \Delta u \approx 5(3x^2 - 2x + 1)^4 \cdot (6x - 2)\Delta x.
$$

   Dividing by $\Delta x$ and letting $\Delta x \to 0$ yields

$$
\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dx} = 5(3x^2 - 2x + 1)^4 \cdot (6x - 2).
$$

3. **Concrete check at a special point:** Look at $x = \frac{1}{3}$, where the inner quadratic $3x^2 - 2x + 1$ reaches its vertex and has horizontal tangent $g'(1/3) = 0$. Near $x = \frac{1}{3}$, nudging $x$ barely changes $u$ at all, so $u^5$ barely changes either, forcing $f'(1/3) = 0$. Without the additional factor $(6x - 2)$, the incomplete expression $5(3x^2 - 2x + 1)^4$ would be strictly positive everywhere and would completely miss this horizontal tangent!

---

## 5. Final Answer & Conclusion

- **Inner function:** $g(x) = 3x^2 - 2x + 1$, with $g'(x) = 6x - 2$.
- **Outer function:** $h(u) = u^5$, with $h'(u) = 5u^4$.
- **Derivative:**

$$
f'(x) = 5(3x^2 - 2x + 1)^4 (6x - 2) = 10(3x - 1)(3x^2 - 2x + 1)^4.
$$

- **Origin of the additional factor:** The factor $(6x - 2) = \frac{du}{dx}$ converts the rate of change with respect to $u$ into the rate of change with respect to $x$, accounting for how rapidly the inner quadratic $3x^2 - 2x + 1$ itself responds to changes in $x$.

---

## 6. Quick Verification

1. **Numerical difference-quotient check at $x = 0$:**
   - Formula value:

$$
f'(0) = 10(3 \cdot 0 - 1)(0 - 0 + 1)^4 = 10(-1)(1) = -10.
$$

   - Notice that without the inner derivative $(6x - 2)$, we would have gotten $+5$ — even the **sign** would be wrong!
   - Difference quotient with $h = 0.001$: $f(0) = 1^5 = 1$ and $f(0.001) = (3 \cdot 10^{-6} - 0.002 + 1)^5 = (0.998003)^5 \approx 0.99005480$, so

$$
\frac{f(0.001) - f(0)}{0.001} \approx -9.9452 \approx -10.
$$

2. **Numerical difference-quotient check at $x = 1$:**
   - Formula value:

$$
f'(1) = 10(3 - 1)(3 - 2 + 1)^4 = 10(2)(2^4) = 20 \cdot 16 = 320.
$$

   - Difference quotient with $h = 0.001$: $f(1) = 2^5 = 32$ and $f(1.001) = (2.004003)^5 \approx 32.321524$, giving

$$
\frac{f(1.001) - f(1)}{0.001} \approx 321.52 \approx 320.
$$

3. **Leading-term polynomial check:** Expanding $(3x^2 - 2x + 1)^5$ produces a polynomial of degree $10$ whose leading term is $(3x^2)^5 = 243x^{10}$. Its derivative must have leading term $2430x^9$. In our answer $10(3x - 1)(3x^2 - 2x + 1)^4$, the leading term is $10(3x)(3x^2)^4 = 30x \cdot 81x^8 = 2430x^9$, matching perfectly!

---

## 7. Common Mistakes to Avoid

- **Forgetting the inner derivative completely:** Writing $f'(x) = 5(3x^2 - 2x + 1)^4$ treats $3x^2 - 2x + 1$ as if its derivative were $1$.
- **Putting $g'(x)$ inside the outer derivative instead of multiplying outside:** Writing $5(6x - 2)^4$ is a classic and severe error. You must keep the **original** inner function $g(x)$ inside $h'$, and multiply by $g'(x)$ **outside**: $h'(g(x)) \cdot g'(x)$, never $h'(g'(x))$.
- **Omitting parentheses around $6x - 2$:** Writing $5(3x^2 - 2x + 1)^4 \cdot 6x - 2$ disconnects the $-2$ from the product and gives the wrong expression.
- **Trying to expand the fifth power first:** Expanding $(3x^2 - 2x + 1)^5$ generates $11$ terms and invites arithmetic mistakes, whereas the chain rule produces the factored derivative in two lines.

---

## 8. How I Would Explain This in Class

> "Imagine two gears connected together. Turning the input shaft $x$ spins the middle gear $u = 3x^2 - 2x + 1$ at speed $6x - 2$, and that middle gear spins the output wheel $y = u^5$ at $5u^4$ times the speed of the middle gear. How fast does the output wheel spin compared to $x$? You multiply the gear ratios! The outer derivative $5(3x^2 - 2x + 1)^4$ is the second gear ratio — keeping the middle gear untouched inside — and the extra factor $(6x - 2)$ is the first gear ratio telling you how fast the middle gear was turning in the first place."
