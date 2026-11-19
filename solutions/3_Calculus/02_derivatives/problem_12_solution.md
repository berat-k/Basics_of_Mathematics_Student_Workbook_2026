# Problem 12: Several Rules at Once

## 1. The Original Problem

For

$$
f(x) = (x^2 + 1)^3 e^x
$$

compute the derivative. Before calculating, write down a plan: which rule applies to the whole expression and which rule applies to one of its factors. Finally, organize the result by factoring out common factors.

---

## 2. What Are We Trying to Find?

1. An explicit differentiation plan formulated *before* computing: identifying which rule governs the entire expression at the top level, and which rule governs the differentiation of its individual factors.
2. The derivative $f'(x)$ of $f(x) = (x^2 + 1)^3 e^x$, computed step by step according to that plan.
3. A cleanly organized final expression obtained by factoring out all common factors from the resulting sum.

---

## 3. Before Calculating: What Idea Do We Need?

- **Read the structure from the outside in:** To decide which differentiation rule comes first, ask: *if I plug a number $x$ into $f(x)$ and evaluate it step by step, what is the very last operation I perform?* Here the last operation is multiplying $(x^2 + 1)^3$ by $e^x$, so the **product rule** governs the whole expression.
- **Product rule:**

$$
\frac{d}{dx}\bigl[u(x)v(x)\bigr] = u'(x)v(x) + u(x)v'(x).
$$

- **Chain rule for a power of a function:** When differentiating $u(x) = (x^2 + 1)^3$, we have a composition of an outer cube with an inner quadratic, so

$$
\frac{d}{dx}\bigl[(g(x))^n\bigr] = n\bigl(g(x)\bigr)^{n - 1} \cdot g'(x).
$$

- **Exponential rule:** $\frac{d}{dx}(e^x) = e^x$.
- **Factoring common powers:** In expressions of the form $A \cdot B^2 e^x + B^3 e^x$, always factor out the lowest common power of each shared factor—here $B^2 e^x$—to make signs, roots, and further analysis transparent.

---

## 4. Step-by-Step Solution

### Step 1: Differentiation Plan Before Calculating

Before taking any derivative, break $f(x) = (x^2 + 1)^3 e^x$ into its structural hierarchy:

1. **Rule for the whole expression — Product Rule:** At the top level, $f(x)$ is the product of two functions,

$$
u(x) = (x^2 + 1)^3 \qquad \text{and} \qquad v(x) = e^x.
$$

Therefore, we must start with the product rule:

$$
f'(x) = u'(x)v(x) + u(x)v'(x).
$$

2. **Rule for the first factor $u(x) = (x^2 + 1)^3$ — Chain Rule with the Power Rule:** The factor $u(x)$ is a composite function with outer function $w^3$ and inner function $w = x^2 + 1$. Thus we use the chain rule to compute $u'(x)$.
3. **Rule for the second factor $v(x) = e^x$ — Basic Exponential Rule:** The derivative of $e^x$ is $e^x$ itself, with no chain rule needed because the exponent is simply $x$.
4. **Final organization — Factoring:** Both terms produced by the product rule will contain powers of $(x^2 + 1)$ and the factor $e^x$, so we will pull out the greatest common factor $(x^2 + 1)^2 e^x$.

### Step 2: Differentiate Each Factor Separately

Compute $u'(x)$ using the chain rule:

$$
u'(x) = \frac{d}{dx}\bigl[(x^2 + 1)^3\bigr] = 3(x^2 + 1)^2 \cdot \frac{d}{dx}(x^2 + 1) = 3(x^2 + 1)^2 \cdot 2x = 6x(x^2 + 1)^2.
$$

Compute $v'(x)$ using the exponential rule:

$$
v'(x) = \frac{d}{dx}(e^x) = e^x.
$$

### Step 3: Combine Using the Product Rule

Substitute $u(x)$, $u'(x)$, $v(x)$, and $v'(x)$ into $f'(x) = u'(x)v(x) + u(x)v'(x)$:

$$
f'(x) = 6x(x^2 + 1)^2 e^x + (x^2 + 1)^3 e^x.
$$

### Step 4: Organize the Result by Factoring Out Common Factors

Inspect the two terms in the sum:
- First term: $6x \cdot (x^2 + 1)^2 \cdot e^x$.
- Second term: $(x^2 + 1)^3 \cdot e^x = (x^2 + 1) \cdot (x^2 + 1)^2 \cdot e^x$.

Both terms share the common factor $(x^2 + 1)^2 e^x$. Factoring it out gives

$$
f'(x) = (x^2 + 1)^2 e^x \bigl[6x + (x^2 + 1)\bigr] = (x^2 + 1)^2 (x^2 + 6x + 1) e^x.
$$

Notice how clean and informative this factored form is: because $(x^2 + 1)^2 > 0$ and $e^x > 0$ for all $x \in \mathbb{R}$, the sign and zeros of $f'(x)$ depend *exclusively* on the quadratic factor $x^2 + 6x + 1$.

---

## 5. Final Answer & Conclusion

- **Plan:** Apply the **product rule** to the entire product $(x^2 + 1)^3 \cdot e^x$, apply the **chain rule** to differentiate the composite factor $(x^2 + 1)^3$, apply the standard exponential rule to $e^x$, and finally factor out the greatest common factor $(x^2 + 1)^2 e^x$.
- **Factored derivative:**

$$
f'(x) = (x^2 + 1)^2 (x^2 + 6x + 1) e^x.
$$

---

## 6. Quick Verification

1. **Direct expansion check without the chain rule:** Expand $(x^2 + 1)^3 = x^6 + 3x^4 + 3x^2 + 1$, so

$$
f(x) = (x^6 + 3x^4 + 3x^2 + 1)e^x.
$$

Applying only the product rule and power rule gives

$$
f'(x) = \bigl[(6x^5 + 12x^3 + 6x) + (x^6 + 3x^4 + 3x^2 + 1)\bigr]e^x = (x^6 + 6x^5 + 3x^4 + 12x^3 + 3x^2 + 6x + 1)e^x.
$$

Now expand the polynomial part of our factored answer:

$$
(x^2 + 1)^2 (x^2 + 6x + 1) = (x^4 + 2x^2 + 1)(x^2 + 6x + 1) = x^6 + 6x^5 + 3x^4 + 12x^3 + 3x^2 + 6x + 1.
$$

Every single coefficient matches identically.

2. **Logarithmic differentiation check:** Since $f(x) > 0$ for all $x \in \mathbb{R}$, take the natural logarithm of both sides:

$$
\ln f(x) = 3\ln(x^2 + 1) + x.
$$

Differentiating both sides yields

$$
\frac{f'(x)}{f(x)} = \frac{6x}{x^2 + 1} + 1 = \frac{x^2 + 6x + 1}{x^2 + 1}.
$$

Multiplying by $f(x) = (x^2 + 1)^3 e^x$ cancels one factor of $x^2 + 1$ and immediately returns $f'(x) = (x^2 + 1)^2(x^2 + 6x + 1)e^x$.

3. **Point value check at $x = 0$ and $x = 1$:**
  - At $x = 0$: our formula gives $f'(0) = 1^2 \cdot 1 \cdot e^0 = 1$. Near $x = 0$, $f(x) = (1 + 3x^2 + \dots)(1 + x + \dots) = 1 + x + O(x^2)$, whose linear slope is indeed $1$.
  - At $x = 1$: our formula gives $f'(1) = 2^2 \cdot 8 \cdot e = 32e \approx 86.985019$, which agrees with the numerical central difference $\frac{f(1 + 10^{-6}) - f(1 - 10^{-6})}{2 \times 10^{-6}} \approx 86.985019$.

---

## 7. Common Mistakes to Avoid

- **Differentiating each factor and multiplying the results:** Writing $f'(x) = 6x(x^2 + 1)^2 \cdot e^x$ forgets the entire second term $(x^2 + 1)^3 e^x$ of the product rule.
- **Forgetting the inner derivative $2x$ inside the chain rule:** Writing $u'(x) = 3(x^2 + 1)^2$ omits the factor $2x$, leading to the wrong quadratic $x^2 + 4$ instead of $x^2 + 6x + 1$.
- **Expanding everything unnecessarily instead of factoring:** Multiplying out $(x^2 + 1)^3$ before differentiating or multiplying out $6x(x^2 + 1)^2 + (x^2 + 1)^3$ creates long, error-prone degree-$6$ polynomials and hides the structure of the derivative. Factoring out $(x^2 + 1)^2 e^x$ is faster, cleaner, and far more useful.
- **Factoring out $(x^2 + 1)^2$ incorrectly:** When pulling $(x^2 + 1)^2$ out of $(x^2 + 1)^3$, one full power $(x^2 + 1)$ remains inside the brackets—not $1$ and not $x^2$.

---

## 8. How I Would Explain This in Class

> "When a function looks busy, resist the urge to dive straight into differentiating—pause for five seconds and read its architecture from the outside in. Ask yourself: if I plug in $x = 2$, what is the very last button I press on a calculator? First I compute $x^2 + 1$, then I cube it, separately I compute $e^x$, and at the very end I multiply those two results together. Because multiplication is the last operation on the outside, the product rule goes first. Then, when the product rule asks for the derivative of the cubed piece, the chain rule steps in to handle that inner layer. Finally, never leave a messy sum when both terms are wearing the same coat $(x^2 + 1)^2 e^x$—pull that common coat to the front, and the whole derivative snaps into crisp, crystal-clear form."
