# Problem 01: Antiderivative and Verification

## 1. The Original Problem

For

$$
f(x) = 3x^2 - 4x + 5
$$

find one antiderivative $F(x)$. Write the entire family of antiderivatives, verify the result by differentiation, and explain the meaning of the constant $C$.

---

## 2. What Are We Trying to Find?

1. Find one specific antiderivative $F(x)$ of the polynomial $f(x) = 3x^2 - 4x + 5$, meaning a differentiable function whose derivative equals $f(x)$ on $\mathbb{R}$.
2. Write the entire family of antiderivatives of $f(x)$, i.e., the indefinite integral $\int (3x^2 - 4x + 5)\,dx$.
3. Verify the result explicitly by differentiating the general antiderivative and recovering $f(x)$.
4. Explain both the algebraic meaning and the geometric meaning of the arbitrary constant $C$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Definition of an antiderivative:** A function $F$ is an antiderivative of $f$ on an interval $I$ if $F'(x) = f(x)$ for every $x \in I$.
- **Linearity of integration:** For constants $a, b \in \mathbb{R}$ and integrable functions $g, h$,

$$
\int \bigl(a g(x) + b h(x)\bigr)\,dx = a \int g(x)\,dx + b \int h(x)\,dx.
$$

- **Power rule for antiderivatives:** For every real exponent $n \ne -1$,

$$
\int x^n\,dx = \frac{x^{n+1}}{n+1} + C.
$$

- **Constant-difference theorem on an interval:** If $F_1$ and $F_2$ satisfy $F_1'(x) = F_2'(x)$ for all $x$ in a connected interval $I$, then $(F_1 - F_2)'(x) = 0$ on $I$, so $F_1(x) - F_2(x) = C$ for some constant $C \in \mathbb{R}$. Here $f$ is a polynomial defined on the single connected interval $\mathbb{R} = (-\infty, \infty)$.
- **Verification principle:** Because integration reverses differentiation, differentiating a proposed antiderivative is an exact, self-contained correctness test.

---

## 4. Step-by-Step Solution

### Step 1: Identify the Method and Domain

The integrand $f(x) = 3x^2 - 4x + 5$ is a polynomial, so it is continuous and defined on the entire real line $\mathbb{R}$. Because $f(x)$ is a linear combination of basic power functions $x^2$, $x^1$, and $x^0 = 1$, we can integrate it directly term by term using linearity and the power rule.

### Step 2: Integrate Term by Term to Find One Antiderivative

We apply the power rule to each term individually:

1. For the first term $3x^2$, increase the exponent from $2$ to $3$ and divide by $3$:

$$
\int 3x^2\,dx = 3 \cdot \frac{x^3}{3} + C_1 = x^3 + C_1.
$$

2. For the second term $-4x = -4x^1$, increase the exponent from $1$ to $2$ and divide by $2$:

$$
\int (-4x)\,dx = -4 \cdot \frac{x^2}{2} + C_2 = -2x^2 + C_2.
$$

3. For the third term $5 = 5x^0$, increase the exponent from $0$ to $1$ and divide by $1$:

$$
\int 5\,dx = 5x + C_3.
$$

Setting the combined constant to $0$ yields one specific antiderivative:

$$
F(x) = x^3 - 2x^2 + 5x.
$$

Other equally valid specific antiderivatives include $F(x) = x^3 - 2x^2 + 5x + 7$ or $F(x) = x^3 - 2x^2 + 5x - \pi$, corresponding to different choices of the constant term.

### Step 3: Write the Entire Family of Antiderivatives

Combining the three integration constants into a single arbitrary real constant $C = C_1 + C_2 + C_3 \in \mathbb{R}$, we obtain the full family of antiderivatives on $\mathbb{R}$:

$$
\int (3x^2 - 4x + 5)\,dx = x^3 - 2x^2 + 5x + C, \qquad C \in \mathbb{R}.
$$

Because $\mathbb{R}$ is a single connected interval, no function outside this family can have derivative $3x^2 - 4x + 5$ everywhere on $\mathbb{R}$.

### Step 4: Verify the Result by Differentiation

Differentiating the entire family $G(x) = x^3 - 2x^2 + 5x + C$ with respect to $x$ gives:

$$
\begin{aligned}
G'(x) &= \frac{d}{dx}\bigl(x^3 - 2x^2 + 5x + C\bigr) \\
&= \frac{d}{dx}(x^3) - 2\frac{d}{dx}(x^2) + 5\frac{d}{dx}(x) + \frac{d}{dx}(C) \\
&= 3x^2 - 2(2x) + 5(1) + 0 \\
&= 3x^2 - 4x + 5 = f(x).
\end{aligned}
$$

The derivative matches $f(x)$ identically for every $x \in \mathbb{R}$ and every choice of $C \in \mathbb{R}$.

### Step 5: Explain the Meaning of the Constant $C$

The constant $C$ has both an algebraic and a geometric meaning:

- **Algebraic meaning:** Differentiation annihilates constants, since $\frac{d}{dx}(C) = 0$ for every real number $C$. Consequently, differentiating $x^3 - 2x^2 + 5x + C$ erases the value of $C$, so infinitely many functions share the exact same derivative $3x^2 - 4x + 5$. Conversely, by the Mean Value Theorem, if two functions have identical derivatives on the connected interval $\mathbb{R}$, their difference has derivative $0$ everywhere and must therefore be a constant.
- **Geometric meaning:** The graph of $y = x^3 - 2x^2 + 5x + C$ is obtained by shifting the graph of $y = x^3 - 2x^2 + 5x$ vertically by $C$ units. A vertical shift moves every point straight up or down without tilting the curve, so at every horizontal coordinate $x$, all curves in the family have parallel tangent lines with the exact same slope $f(x) = 3x^2 - 4x + 5$.

```text
  y
  ^     /    y = x^3 - 2x^2 + 5x + 2  (shifted up by 2)
  |    /
  |   /    / y = x^3 - 2x^2 + 5x      (C = 0)
  |  /    /
  | /    /    / y = x^3 - 2x^2 + 5x - 2 (shifted down by 2)
--+-----+----+--> x
  |  Same slope f(x) at every x across all vertically shifted curves
```

---

## 5. Final Answer & Conclusion

- **One specific antiderivative:**

$$
F(x) = x^3 - 2x^2 + 5x.
$$

- **Entire family of antiderivatives on $\mathbb{R}$:**

$$
\int (3x^2 - 4x + 5)\,dx = x^3 - 2x^2 + 5x + C, \qquad C \in \mathbb{R}.
$$

- **Verification:** $\frac{d}{dx}(x^3 - 2x^2 + 5x + C) = 3x^2 - 4x + 5 = f(x)$.
- **Meaning of $C$:** Algebraically, $C$ accounts for the fact that constants differentiate to $0$ and any two antiderivatives on $\mathbb{R}$ differ by a constant. Geometrically, varying $C$ produces the family of vertical shifts of $y = x^3 - 2x^2 + 5x$, all sharing the same tangent slope $f(x)$ at every $x$.

---

## 6. Quick Verification

1. **Concrete numerical slope check using the symmetric difference quotient:**
   Let $F(x) = x^3 - 2x^2 + 5x$ and test at $x = 2$, where $f(2) = 3(4) - 4(2) + 5 = 9$.
   With step $h = 0.01$:

$$
F(2.01) = (2.01)^3 - 2(2.01)^2 + 5(2.01) = 8.120601 - 8.0802 + 10.05 = 10.090401,
$$

$$
F(1.99) = (1.99)^3 - 2(1.99)^2 + 5(1.99) = 7.880599 - 7.9202 + 9.95 = 9.910399.
$$

   Then

$$
\frac{F(2.01) - F(1.99)}{0.02} = \frac{0.180002}{0.02} = 9.0001 \approx 9 = f(2).
$$

2. **Pointwise check with a nonzero constant $C$:**
   Choose $C = -10$, so $G(x) = x^3 - 2x^2 + 5x - 10$. Evaluating $G'(x) = 3x^2 - 4x + 5$ at $x = 0$, $x = 1$, and $x = -1$ gives $G'(0) = 5 = f(0)$, $G'(1) = 4 = f(1)$, and $G'(-1) = 12 = f(-1)$, confirming that shifting by $-10$ leaves every derivative value unchanged.

---

## 7. Common Mistakes to Avoid

- **Omitting $+ C$ when writing the family of antiderivatives:** Writing $\int (3x^2 - 4x + 5)\,dx = x^3 - 2x^2 + 5x$ gives only *one* antiderivative, not the entire indefinite integral. Always include $+ C$ for an indefinite integral.
- **Differentiating instead of integrating:** Students sometimes confuse the two rules and write $6x - 4$ instead of $x^3 - 2x^2 + 5x + C$. Differentiating your final answer immediately catches this error.
- **Integrating the constant term $5$ to $0$:** The derivative of $5$ is $0$, not its antiderivative. Because $(5x)' = 5$, the antiderivative of $5$ is $5x + C$.
- **Forgetting to divide by the new exponent:** Writing $\int (-4x)\,dx = -4x^2$ instead of $-2x^2$ forgets the denominator $n + 1 = 2$ in the power rule.

---

## 8. How I Would Explain This in Class

> "When we differentiate a function, we measure its slope at every point and throw away its starting height. Integrating runs that film in reverse: knowing the slope $3x^2 - 4x + 5$ at every $x$ tells you the exact shape of the roller-coaster track $x^3 - 2x^2 + 5x$, but it never tells you how high above sea level the track was built. That missing elevation is the constant $C$. And the best habit in calculus is to take five seconds at the end to differentiate your answer—if you land right back on the original integrand, you know your track has the exact right slope everywhere."
