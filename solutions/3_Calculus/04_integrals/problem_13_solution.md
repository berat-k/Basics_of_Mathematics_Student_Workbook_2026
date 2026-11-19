# Problem 13: An Integral Depending on the Upper Limit

## 1. The Original Problem

Let

$$
F(x)=\int_0^x(t^2+1)\,dt.
$$

Determine $F(x)$, compute $F'(x)$, and compare the result with the integrand. Explain in your own words why the height of the function describes the local rate of increase of the accumulated area.

---

## 2. What Are We Trying to Find?

1. An explicit algebraic formula for the accumulation function $F(x) = \int_{0}^{x} (t^2 + 1)\,dt$.
2. The derivative $F'(x)$ computed directly from the explicit formula for $F(x)$.
3. A comparison between $F'(x)$ and the original integrand $f(t) = t^2 + 1$.
4. A clear intuitive and geometric explanation of why the height $f(x)$ of the curve at $x$ measures the instantaneous rate at which accumulated area grows at $x$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Accumulation function:** When the upper limit of a definite integral is a variable $x$, the integral defines a new function $F(x)$ whose output at $x$ is the signed area accumulated under $y = f(t)$ from $t = 0$ to $t = x$.
- **Dummy variable vs. independent variable:** Here $t$ is a **dummy variable of integration** — it runs from $0$ to $x$ and disappears once the limits are substituted. The actual input variable of $F$ is the upper limit $x$.
- **Fundamental Theorem of Calculus, Part 2:** We can evaluate $F(x)$ explicitly by finding an antiderivative of $t^2 + 1$ with respect to $t$ and substituting the limits $t = x$ and $t = 0$.
- **Fundamental Theorem of Calculus, Part 1:** If $f$ is continuous on an interval containing $a$, then the accumulation function $F(x) = \int_{a}^{x} f(t)\,dt$ is differentiable and satisfies

$$
F'(x) = \frac{d}{dx}\int_{a}^{x} f(t)\,dt = f(x).
$$

---

## 4. Step-by-Step Solution

### Step 1: Determine $F(x)$ Explicitly

First find an antiderivative of the integrand $f(t) = t^2 + 1$ with respect to $t$:

$$
G(t) = \frac{t^3}{3} + t.
$$

Now evaluate the definite integral from $t = 0$ to $t = x$:

$$
F(x) = \int_{0}^{x} (t^2 + 1)\,dt = \left[\frac{t^3}{3} + t\right]_{0}^{x} = \left(\frac{x^3}{3} + x\right) - \left(\frac{0^3}{3} + 0\right) = \frac{x^3}{3} + x.
$$

Thus, for every real number $x$,

$$
F(x) = \frac{x^3}{3} + x.
$$

Notice that $F(0) = 0$, $F(x) > 0$ for $x > 0$, and $F(x) < 0$ for $x < 0$ because reversing the integration direction from $0$ to a negative $x$ yields a negative signed integral.

### Step 2: Compute $F'(x)$

Differentiate $F(x) = \frac{x^3}{3} + x$ with respect to $x$ using the power rule:

$$
F'(x) = \frac{d}{dx}\left(\frac{x^3}{3} + x\right) = \frac{3x^2}{3} + 1 = x^2 + 1.
$$

### Step 3: Compare $F'(x)$ with the Integrand

The integrand in $\int_{0}^{x} (t^2 + 1)\,dt$ is $f(t) = t^2 + 1$. Substituting the upper limit $t = x$ into the integrand gives $f(x) = x^2 + 1$, which is **identically equal** to $F'(x)$:

$$
F'(x) = x^2 + 1 = f(x).
$$

In other words, differentiating the accumulation integral undoes the integration and recovers the original integrand evaluated at the upper limit $x$. This is a concrete verification of Part 1 of the Fundamental Theorem of Calculus.

### Step 4: Why Does the Height of the Function Describe the Local Rate of Increase of Accumulated Area?

Suppose $x$ increases by a small positive amount $h > 0$, moving the right boundary of the shaded region from $x$ to $x + h$. Because $f(t) = t^2 + 1 > 0$ everywhere, the change in accumulated area is the area of the thin vertical strip between $t = x$ and $t = x + h$:

$$
\Delta F = F(x + h) - F(x) = \int_{0}^{x+h} f(t)\,dt - \int_{0}^{x} f(t)\,dt = \int_{x}^{x+h} f(t)\,dt.
$$

Look closely at that narrow strip over $[x, x + h]$:

- Its horizontal width is $h$.
- Because $f$ is continuous, when $h$ is very small, the curve's height $f(t)$ across $[x, x + h]$ stays very close to its height $f(x)$ at the left edge.
- Therefore, the strip is nearly a rectangle of width $h$ and height $f(x)$, so its area is approximately

$$
F(x + h) - F(x) \approx f(x) \cdot h.
$$

Divide both sides by the step width $h$ to find the average rate of change of accumulated area per unit increase in $x$:

$$
\frac{F(x + h) - F(x)}{h} \approx f(x).
$$

As $h \to 0$, the tiny triangular or curved discrepancy at the top of the strip shrinks faster than $h$, so the ratio converges to the exact height $f(x)$:

$$
F'(x) = \lim_{h \to 0} \frac{F(x + h) - F(x)}{h} = f(x).
$$

**In plain words:** Whenever you slide the right boundary of the area forward by a tiny horizontal step $h$, the amount of **new area** swept out equals the **height** of the curve at that boundary multiplied by the step width $h$. Dividing new area by step width leaves just the height $f(x)$. Where the curve is tall, even a tiny step forward adds a lot of area, so $F(x)$ increases rapidly; where the curve is short, the same step adds very little area, so $F(x)$ increases slowly.

---

## 5. Final Answer & Conclusion

- Explicit accumulation function:

$$
F(x) = \frac{x^3}{3} + x.
$$

- Derivative:

$$
F'(x) = x^2 + 1.
$$

- **Comparison:** $F'(x)$ matches the integrand $f(t) = t^2 + 1$ evaluated at $t = x$, demonstrating the Fundamental Theorem of Calculus, Part 1: $\frac{d}{dx}\int_{0}^{x} (t^2 + 1)\,dt = x^2 + 1$.
- **Geometric meaning:** Advancing the upper limit from $x$ to $x + h$ adds a thin vertical slice of width $h$ and approximate height $f(x)$, so the added area is $\approx f(x)\cdot h$ and the local rate of area growth per unit change in $x$ is exactly the curve's height $f(x)$.

---

## 6. Quick Verification

1. **Checking concrete values against Problem 10:** At $x = 2$, our formula gives

$$
F(2) = \frac{2^3}{3} + 2 = \frac{8}{3} + 2 = \frac{14}{3},
$$

which agrees with $\int_{0}^{2} (x^2 + 1)\,dx = \frac{14}{3}$ computed in Problem 10. Also $F(0) = \frac{0^3}{3} + 0 = 0$, matching the zero-width integral from $0$ to $0$.
2. **Numerical difference-quotient check at $x = 2$:** Take $h = 0.01$ and compare $\frac{F(2.01) - F(2)}{0.01}$ with the curve height $f(2) = 2^2 + 1 = 5$:
   - $F(2.01) = \frac{(2.01)^3}{3} + 2.01 = \frac{8.120601}{3} + 2.01 = 2.706867 + 2.01 = 4.716867$.
   - $F(2) = \frac{14}{3} \approx 4.666667$.
   - Average rate of area increase:

$$
\frac{F(2.01) - F(2)}{0.01} \approx \frac{4.716867 - 4.666667}{0.01} = \frac{0.050200}{0.01} = 5.02 \approx 5 = f(2).
$$

   Indeed, the thin strip from $t = 2$ to $t = 2.01$ has width $0.01$ and height slightly above $5$, so its area is $\approx 0.0502$ and the rate of accumulation is $\approx 5.02$, converging to $f(2) = 5$ as $h \to 0$.

---

## 7. Common Mistakes to Avoid

- **Leaving the dummy variable $t$ in the final formula for $F(x)$ or $F'(x)$:** Writing $F'(x) = t^2 + 1$ instead of $x^2 + 1$. Once you evaluate the definite integral from $0$ to $x$, the dummy variable $t$ is gone and the result depends solely on $x$.
- **Adding an arbitrary constant $+ C$ to a definite integral:** Writing $F(x) = \frac{x^3}{3} + x + C$. Because the lower limit is fixed at $0$, the constant is already determined by $F(0) = 0$; there is no free constant $C$.
- **Confusing $F(x)$ with $f(x)$:** Forgetting that $F(x)$ represents the **accumulated area** up to $x$, whereas $f(x) = F'(x)$ represents the **height** of the curve at $x$. At $x = 2$, the height is $5$, while the accumulated area is $\frac{14}{3}$.
- **Believing the lower limit changes $F'(x)$:** If the integral were $H(x) = \int_{5}^{x} (t^2 + 1)\,dt$, then $H(x) = \frac{x^3}{3} + x - \frac{140}{3}$, which differs from $F(x)$ only by a constant; its derivative is still $H'(x) = x^2 + 1$!

---

## 8. How I Would Explain This in Class

> "Imagine unrolling a paint roller across the wall from $t = 0$ toward the right, where the ceiling above you follows the curve $y = t^2 + 1$. The function $F(x)$ measures the total square meters you have painted once your roller reaches position $x$. Now ask yourself: right at position $x$, how fast is the painted area growing per centimeter you move right? At that exact spot, your paint roller has to reach all the way up to the ceiling height $f(x)$. Move forward by one millimeter, and you paint a thin vertical strip of area equal to ceiling height times one millimeter. So the instantaneous rate at which painted area grows is literally the height of the ceiling right above you!"
