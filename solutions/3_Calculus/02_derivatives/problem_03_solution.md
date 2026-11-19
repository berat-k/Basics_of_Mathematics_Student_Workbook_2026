# Problem 03: The Product Rule — Why Is It Needed?

## 1. The Original Problem

For

$$
f(x)=(x^2+1)e^x
$$

compute the derivative. Then compare the correct result with the incorrect idea

$$
f'(x)\stackrel{?}{=}(2x)e^x
$$

and explain which term is missing.

---

## 2. What Are We Trying to Find?

1. The correct derivative $f'(x)$ of the product $f(x) = (x^2 + 1)e^x$ using the product rule.
2. A clear comparison between the correct derivative and the incorrect candidate $(2x)e^x$.
3. Identification of the exact missing term and an explanation of why the incorrect formula drops it.

---

## 3. Before Calculating: What Idea Do We Need?

- **The product rule:** If $u$ and $v$ are differentiable functions of $x$, then the derivative of their product is **not** $u'v'$. Instead,

$$
(u(x) \cdot v(x))' = u'(x)v(x) + u(x)v'(x).
$$

- **Why two terms appear:** Imagine a rectangle with width $u(x)$ and height $v(x)$, whose area is $A(x) = u(x)v(x)$. When $x$ increases slightly, both the width and the height grow at the same time. The area increases by two strips: one strip of area approximately $\Delta u \cdot v$ from changing the width, and a second strip of area approximately $u \cdot \Delta v$ from changing the height. Dividing by $\Delta x$ and taking the limit gives $u'v + uv'$.
- **Derivative of the natural exponential function:**

$$
\frac{d}{dx}\left(e^x\right) = e^x.
$$

---

## 4. Step-by-Step Solution

### Step 1: Identify the Two Factors and Their Derivatives

Write $f(x) = u(x) \cdot v(x)$ where:

- $u(x) = x^2 + 1$, whose derivative is $u'(x) = 2x$.
- $v(x) = e^x$, whose derivative is $v'(x) = e^x$.

### Step 2: Apply the Product Rule

Substitute $u$, $u'$, $v$, and $v'$ into $f'(x) = u'(x)v(x) + u(x)v'(x)$:

$$
f'(x) = (2x)e^x + (x^2 + 1)e^x.
$$

Factor out the common factor $e^x$ and simplify:

$$
f'(x) = (x^2 + 2x + 1)e^x = (x + 1)^2 e^x.
$$

### Step 3: Compare with the Incorrect Idea and Identify the Missing Term

The incorrect candidate proposes:

$$
g(x) = (2x)e^x.
$$

Compute the difference between the true derivative and the incorrect candidate:

$$
f'(x) - g(x) = \left[(2x)e^x + (x^2 + 1)e^x\right] - (2x)e^x = (x^2 + 1)e^x.
$$

**Which term is missing?** The missing term is precisely

$$
u(x)v'(x) = (x^2 + 1)e^x.
$$

**Why did the incorrect idea fail?**

There are two equivalent ways to see the mistake behind writing $(2x)e^x$:

1. **False product rule $(uv)' \stackrel{?}{=} u'v'$:** The student differentiated each factor separately and multiplied the results: $u'(x) = 2x$ times $v'(x) = e^x$ gives $(2x)e^x$. Unlike sums, derivatives do **not** distribute across products.
2. **Treating $e^x$ as if it were a constant:** If $e^x$ were a constant $c$, then the derivative of $(x^2 + 1)c$ would indeed be $(2x)c$. Because $(e^x)' = e^x$ looks identical to $e^x$, both mistakes produce the exact same incomplete answer $(2x)e^x$, completely ignoring the rate of change contributed by the growing factor $e^x$.

Notice how large the error is: since $x^2 + 1 \ge 1$ and $e^x > 0$ for every real $x$, the missing term $(x^2 + 1)e^x$ is strictly positive everywhere! The incorrect formula underestimates the true slope at every single point on the real line. Even worse, for $x < 0$, the incorrect formula $(2x)e^x$ predicts a negative slope, whereas the true derivative $f'(x) = (x + 1)^2 e^x \ge 0$ is never negative!

---

## 5. Final Answer & Conclusion

- **Correct derivative:**

$$
f'(x) = (2x)e^x + (x^2 + 1)e^x = (x^2 + 2x + 1)e^x = (x + 1)^2 e^x.
$$

- **Comparison and missing term:** The incorrect expression $(2x)e^x$ contains only the $u'(x)v(x)$ piece and is **missing the term $(x^2 + 1)e^x$**, which is the $u(x)v'(x)$ contribution arising from the change in $e^x$.

---

## 6. Quick Verification

1. **Test at $x = 0$ using a difference quotient:**
   - Correct derivative: $f'(0) = (0 + 1)^2 e^0 = 1$.
   - Incorrect formula: $(2 \cdot 0)e^0 = 0$.
   - Direct numerical check with $h = 0.001$: $f(0) = 1 \cdot e^0 = 1$ and $f(0.001) = (1 + 10^{-6})e^{0.001} \approx 1.001001501$, so

$$
\frac{f(0.001) - f(0)}{0.001} \approx 1.001501 \approx 1.
$$

   This immediately refutes the incorrect prediction $0$ and confirms $f'(0) = 1$.

2. **Test at $x = 1$:**
   - Correct derivative: $f'(1) = (1 + 1)^2 e^1 = 4e \approx 10.873127$.
   - Incorrect formula: $2e \approx 5.436564$, which is off by a factor of $2$.
   - Difference quotient with $h = 0.001$: $f(1) = 2e \approx 5.436564$ and $f(1.001) \approx 5.447448$, giving

$$
\frac{f(1.001) - f(1)}{0.001} \approx 10.8840 \approx 4e.
$$

---

## 7. Common Mistakes to Avoid

- **Using the false rule $(u \cdot v)' = u' \cdot v'$:** This fails almost everywhere. Even for the trivial product $x \cdot x = x^2$, the true derivative is $2x$, whereas $1 \cdot 1 = 1$.
- **Forgetting to keep $u(x)$ undifferentiated in the second term:** Writing $u'v + u'v'$ instead of $u'v + uv'$. In each term of the product rule, differentiate **only one** factor and leave the other alone.
- **Skipping simplification:** Leaving the answer as $2xe^x + (x^2 + 1)e^x$ is correct, yet factoring out $e^x$ to obtain $(x + 1)^2 e^x$ immediately reveals that $f'(x) \ge 0$ everywhere and $f'(x) = 0$ only at $x = -1$.
- **Being tricked by $(e^x)' = e^x$:** Because $e^x$ does not change form when differentiated, it is easy to overlook whether you actually differentiated it. Always write out $u'v + uv'$ explicitly.

---

## 8. How I Would Explain This in Class

> "Picture a growing rectangle whose width is $x^2 + 1$ and whose height is $e^x$. If someone tells you the area changes at rate $(2x)e^x$, they are only measuring the strip added by widening the rectangle while pretending the height $e^x$ froze in place! Because $e^x$ is also growing, you get a second strip of width $x^2 + 1$ growing at rate $e^x$. The product rule simply makes sure you count both strips: differentiate the first and keep the second, plus keep the first and differentiate the second."
