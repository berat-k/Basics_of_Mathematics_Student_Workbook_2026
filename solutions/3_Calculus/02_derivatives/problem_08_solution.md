# Problem 08: Two Exponential Functions

## 1. The Original Problem

For

$$
f(x)=e^{2x-3}+5^x
$$

compute the derivative. Explain why the factor $2$ appears in the first term and why $\ln5$ appears in the second.

---

## 2. What Are We Trying to Find?

1. The derivative $f'(x)$ of $f(x) = e^{2x - 3} + 5^x$.
2. A clear explanation of the mathematical mechanism that produces the factor $2$ in the derivative of $e^{2x - 3}$.
3. A clear explanation of the mathematical mechanism that produces the factor $\ln 5$ in the derivative of $5^x$, contrasting the two mechanisms and showing how they connect.

---

## 3. Before Calculating: What Idea Do We Need?

- **Sum rule:** Differentiate $e^{2x - 3}$ and $5^x$ separately, then add.
- **Natural exponential derivative:** Base $e$ is the unique positive base whose exponential function equals its own derivative with proportionality constant $1$:

$$
\frac{d}{du}\left(e^u\right) = e^u.
$$

- **Chain rule for composite exponentials:** If $u = g(x)$ is differentiable, then

$$
\frac{d}{dx}\left(e^{g(x)}\right) = e^{g(x)} \cdot g'(x).
$$

- **Change-of-base identity for general exponentials:** Any positive base $a > 0$ can be written as $a = e^{\ln a}$, so

$$
a^x = \left(e^{\ln a}\right)^x = e^{(\ln a) x}.
$$

  Applying the chain rule to $e^{(\ln a)x}$ yields the general exponential rule:

$$
\frac{d}{dx}\left(a^x\right) = a^x \ln a.
$$

---

## 4. Step-by-Step Solution

### Step 1: Differentiate the First Term $e^{2x - 3}$

Recognize $e^{2x - 3}$ as a composition with outer function $h(u) = e^u$ and inner function $g(x) = 2x - 3$.

- Outer derivative: $h'(u) = e^u$, so $h'(g(x)) = e^{2x - 3}$.
- Inner derivative: $g'(x) = \frac{d}{dx}(2x - 3) = 2$.

By the chain rule:

$$
\frac{d}{dx}\left(e^{2x - 3}\right) = e^{2x - 3} \cdot 2 = 2e^{2x - 3}.
$$

### Step 2: Differentiate the Second Term $5^x$

Rewrite $5^x$ using the natural base $e$ via $5 = e^{\ln 5}$:

$$
5^x = \left(e^{\ln 5}\right)^x = e^{(\ln 5) x}.
$$

Now apply the chain rule with outer function $e^u$ and inner function $u(x) = (\ln 5) x$, whose derivative is the constant $\ln 5$:

$$
\frac{d}{dx}\left(5^x\right) = \frac{d}{dx}\left(e^{(\ln 5) x}\right) = e^{(\ln 5) x} \cdot \ln 5 = 5^x \ln 5.
$$

### Step 3: Combine Both Terms

By the sum rule, the derivative of $f(x) = e^{2x - 3} + 5^x$ is:

$$
f'(x) = 2e^{2x - 3} + 5^x \ln 5.
$$

### Step 4: Explain Why $2$ Appears in the First Term and $\ln 5$ Appears in the Second

Although both terms gain a multiplicative constant upon differentiation, the two factors arise from **two different structural features**:

| Term | Base | Exponent | Rule / Mechanism | Extra Factor |
| :---: | :---: | :---: | :--- | :---: |
| $e^{2x - 3}$ | Natural base $e$ | Linear composition $2x - 3$ | Chain rule on the inner exponent $g(x) = 2x - 3$ | $g'(x) = 2$ |
| $5^x$ | Non-natural base $5$ | Simple variable $x$ | Change of base to $e$, $5^x = e^{(\ln 5)x}$ | $\ln 5$ |

1. **Why the factor $2$ appears in $2e^{2x - 3}$:**
   The base is already the natural base $e$, which carries no base-conversion factor because $\ln e = 1$. However, the exponent is $2x - 3$ rather than plain $x$. When $x$ increases by $1$, the exponent $2x - 3$ increases by $2$ — twice as fast. By the chain rule, this inner rate of change $g'(x) = 2$ multiplies the outer derivative $e^{2x - 3}$. Meanwhile, the constant $-3$ only shifts the graph horizontally and has derivative $0$, so it stays in the exponent without producing an extra factor.

2. **Why the factor $\ln 5$ appears in $5^x \ln 5$:**
   Here the exponent is just $x$, with no stretching inside the exponent, but the base is $5 \ne e$. From the limit definition of the derivative:

$$
\frac{d}{dx}\left(5^x\right) = \lim_{h \to 0} \frac{5^{x+h} - 5^x}{h} = 5^x \lim_{h \to 0} \frac{5^h - 1}{h}.
$$

   Only for base $e$ does $\lim_{h \to 0} \frac{e^h - 1}{h}$ equal $1$. For base $5$, rewriting $5^h = e^{h \ln 5}$ shows that this limit equals $\ln 5 \approx 1.6094$, which is the slope of $y = 5^x$ at $x = 0$. Equivalently, writing $5^x = e^{(\ln 5) x}$ reveals that changing the base from $e$ to $5$ is mathematically identical to scaling the exponent of $e$ by $\ln 5$.

**The unifying insight:** Once both terms are written with the natural base $e$,

$$
f(x) = e^{2x - 3} + e^{(\ln 5) x},
$$

we see why $2$ and $\ln 5$ play parallel roles in $f'(x) = 2e^{2x - 3} + (\ln 5)e^{(\ln 5)x}$: both are the rates at which the natural-base exponent grows with $x$, even though one came from a composite exponent and the other came from a non-$e$ base.

---

## 5. Final Answer & Conclusion

- **Derivative:**

$$
f'(x) = 2e^{2x - 3} + 5^x \ln 5.
$$

- **Origin of the two factors:**
  - The factor **$2$** in $2e^{2x - 3}$ comes from the **chain rule** applied to the inner linear exponent $2x - 3$, since $\frac{d}{dx}(2x - 3) = 2$.
  - The factor **$\ln 5$** in $5^x \ln 5$ comes from the **base being $5$ rather than $e$**: converting to natural base gives $5^x = e^{(\ln 5)x}$, which introduces the base-conversion factor $\ln 5 = \lim_{h \to 0} \frac{5^h - 1}{h}$.

---

## 6. Quick Verification

1. **Numerical difference-quotient check at $x = 0$:**
   - Formula value:

$$
f'(0) = 2e^{-3} + 5^0 \ln 5 = 2e^{-3} + \ln 5 \approx 2(0.049787) + 1.609438 = 1.709012.
$$

   - Difference quotient with $h = 0.001$: $f(0) = e^{-3} + 1 \approx 1.049787$ and $f(0.001) = e^{-2.998} + 5^{0.001} \approx 1.051497$, giving

$$
\frac{f(0.001) - f(0)}{0.001} \approx 1.7104 \approx 1.7090.
$$

2. **Numerical difference-quotient check at $x = 1.5$:**
   - Formula value: at $x = 1.5$, $2x - 3 = 0$, so $e^{2x - 3} = e^0 = 1$ and $5^{1.5} = 5\sqrt{5} \approx 11.180340$:

$$
f'(1.5) = 2(1) + 5\sqrt{5}\ln 5 \approx 2 + 17.994063 = 19.994063.
$$

   - Difference quotient with $h = 0.001$: $f(1.5) = 1 + 5\sqrt{5} \approx 12.180340$ and $f(1.501) = e^{0.002} + 5^{1.501} \approx 12.200350$, giving

$$
\frac{f(1.501) - f(1.5)}{0.001} \approx 20.0106 \approx 19.9941.
$$

3. **Special-case consistency check:** If we apply the general formula $\frac{d}{dx}(a^{g(x)}) = a^{g(x)} \cdot (\ln a) \cdot g'(x)$ to both terms:
   - First term, $a = e$, $g(x) = 2x - 3$: $e^{2x - 3} \cdot (\ln e) \cdot 2 = 2e^{2x - 3}$ because $\ln e = 1$.
   - Second term, $a = 5$, $g(x) = x$: $5^x \cdot (\ln 5) \cdot 1 = 5^x \ln 5$.

   Both terms follow the exact same unified law!

---

## 7. Common Mistakes to Avoid

- **Applying the power rule to $5^x$:** Writing $\frac{d}{dx}(5^x) = x \cdot 5^{x-1}$ treats an exponential function as if it were a power function $x^5$. Remember the crucial difference: in $x^5$ the variable is in the **base**, whereas in $5^x$ the variable is in the **exponent**.
- **Forgetting $\ln 5$ and writing $\frac{d}{dx}(5^x) = 5^x$:** Only base $e$ satisfies $(e^x)' = e^x$ with coefficient $1$. Every other base $a > 0$ multiplies by $\ln a$.
- **Forgetting the chain-rule factor $2$ on $e^{2x - 3}$:** Writing $\frac{d}{dx}(e^{2x - 3}) = e^{2x - 3}$ ignores the inner function $2x - 3$.
- **Putting $2x - 3$ in front instead of its derivative $2$:** Writing $(2x - 3)e^{2x - 3}$ multiplies by $g(x)$ instead of $g'(x)$.

---

## 8. How I Would Explain This in Class

> "Students often wonder why extra numbers pop out in front of exponentials when you differentiate them. In this problem, you get to see both causes standing side by side! In $e^{2x - 3}$, you are already using calculus's home currency — base $e$ — so there is no exchange fee, and the factor $2$ comes purely from the chain rule because the exponent $2x - 3$ is running at double speed. In $5^x$, the exponent $x$ is running at normal speed, so the chain rule gives $1$, and the factor $\ln 5$ is the currency-exchange fee for translating base $5$ into base $e$ via $5^x = e^{(\ln 5)x}$."
