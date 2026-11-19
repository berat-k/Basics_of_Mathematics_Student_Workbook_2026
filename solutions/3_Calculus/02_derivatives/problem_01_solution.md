# Problem 01: Derivative of a Polynomial and the Slope of a Tangent Line

## 1. The Original Problem

For

$$
f(x)=3x^5-2x^3+7x-4
$$

find $f'(x)$. Then compute $f'(0)$ and $f'(1)$, determine the signs of the obtained values, and explain what they say about the slope of the tangent line to the graph at these two points.

---

## 2. What Are We Trying to Find?

1. The derivative formula $f'(x)$ for the polynomial $f(x) = 3x^5 - 2x^3 + 7x - 4$.
2. The specific numerical values $f'(0)$ and $f'(1)$.
3. The sign of $f'(0)$ and the sign of $f'(1)$, whether each is positive, negative, or zero.
4. A geometric explanation of what these values and signs tell us about the slopes and directions of the tangent lines to the graph of $f$ at $x = 0$ and $x = 1$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Linearity of differentiation, the sum and constant-multiple rules:** The derivative of a sum or difference of differentiable functions is the sum or difference of their derivatives, and constant factors pull outside the derivative:

$$
(a \cdot g(x) + b \cdot h(x))' = a g'(x) + b h'(x).
$$

- **The power rule:** For any real exponent $n$,

$$
\frac{d}{dx}\left(x^n\right) = n x^{n-1}.
$$

- **Derivative of a constant:** A constant function never changes, so for any constant $c \in \mathbb{R}$,

$$
\frac{d}{dx}(c) = 0.
$$

- **Geometric meaning of the derivative:** The value $f'(a)$ equals the slope $m$ of the tangent line to the curve $y = f(x)$ at the point $(a, f(a))$:
  - If $f'(a) > 0$, the tangent line rises from left to right, so the function is locally increasing near $a$.
  - If $f'(a) < 0$, the tangent line falls from left to right, so the function is locally decreasing near $a$.
  - If $f'(a) = 0$, the tangent line is horizontal.
  - A larger positive value of $f'(a)$ means a steeper upward tilt.

---

## 4. Step-by-Step Solution

### Step 1: Differentiate $f(x)$ Term by Term

Because $f(x) = 3x^5 - 2x^3 + 7x - 4$ is a polynomial, it is a linear combination of power functions and a constant. Applying the sum rule and constant-multiple rule gives:

$$
f'(x) = 3 \frac{d}{dx}\left(x^5\right) - 2 \frac{d}{dx}\left(x^3\right) + 7 \frac{d}{dx}\left(x^1\right) - \frac{d}{dx}(4).
$$

Now apply the power rule to each power term and the constant rule to $-4$:

- $\frac{d}{dx}(x^5) = 5x^4$, so $3 \cdot 5x^4 = 15x^4$.
- $\frac{d}{dx}(x^3) = 3x^2$, so $-2 \cdot 3x^2 = -6x^2$.
- $\frac{d}{dx}(x^1) = 1 \cdot x^0 = 1$, so $7 \cdot 1 = 7$.
- $\frac{d}{dx}(4) = 0$.

Combining all four terms yields:

$$
f'(x) = 15x^4 - 6x^2 + 7.
$$

### Step 2: Evaluate $f'(0)$ and $f'(1)$

Substitute $x = 0$ into $f'(x)$:

$$
f'(0) = 15(0)^4 - 6(0)^2 + 7 = 0 - 0 + 7 = 7.
$$

Substitute $x = 1$ into $f'(x)$:

$$
f'(1) = 15(1)^4 - 6(1)^2 + 7 = 15 - 6 + 7 = 16.
$$

We can also note the corresponding points on the graph of $f$ to locate where these tangent lines touch the curve:

$$
f(0) = 3(0)^5 - 2(0)^3 + 7(0) - 4 = -4,
$$

$$
f(1) = 3(1)^5 - 2(1)^3 + 7(1) - 4 = 3 - 2 + 7 - 4 = 4.
$$

Thus the two points of tangency are $(0, -4)$ and $(1, 4)$.

### Step 3: Determine the Signs and Interpret the Tangent Slopes

| Point $a$ | Point on Graph $(a, f(a))$ | Derivative $f'(a)$ | Sign of $f'(a)$ | Geometric Meaning for the Tangent Line |
| :---: | :---: | :---: | :---: | :--- |
| $0$ | $(0, -4)$ | $7$ | Positive, $7 > 0$ | Rises steeply from left to right with slope $7$ |
| $1$ | $(1, 4)$ | $16$ | Positive, $16 > 0$ | Rises even more steeply from left to right with slope $16$ |

- **At $x = 0$:** Since $f'(0) = 7 > 0$, the sign is **positive**. The tangent line to the graph at $(0, -4)$ slopes upward from left to right with slope $7$. Geometrically, moving $1$ unit to the right along this tangent line raises $y$ by $7$ units. Its equation is $y = 7x - 4$.
- **At $x = 1$:** Since $f'(1) = 16 > 0$, the sign is **positive**. The tangent line to the graph at $(1, 4)$ also slopes upward from left to right, with slope $16$. Because $16 > 7$, the graph is more than twice as steep at $x = 1$ as it is at $x = 0$. Its equation is $y = 16(x - 1) + 4 = 16x - 12$.

As a bonus observation, completing the square in $x^2$ reveals something even stronger about this polynomial:

$$
f'(x) = 15\left(x^2 - \frac{1}{5}\right)^2 + 7 - \frac{3}{5} = 15\left(x^2 - \frac{1}{5}\right)^2 + \frac{32}{5} \ge \frac{32}{5} > 0
$$

for every real number $x$. Therefore, the tangent line slopes upward at every single point on the graph, not just at $x = 0$ and $x = 1$.

---

## 5. Final Answer & Conclusion

- **Derivative:**

$$
f'(x) = 15x^4 - 6x^2 + 7.
$$

- **Values and signs:**
  - $f'(0) = 7$, which is **positive**.
  - $f'(1) = 16$, which is **positive**.
- **Geometric interpretation:** At both $(0, -4)$ and $(1, 4)$, the tangent line to the graph of $f$ slopes upward from left to right, meaning the function is increasing at both points. Because $16 > 7$, the tangent line at $x = 1$ is significantly steeper than the tangent line at $x = 0$.

---

## 6. Quick Verification

1. **Numerical difference-quotient check with $h = 0.01$:**
   - Near $x = 0$: $f(0) = -4$ and

$$
f(0.01) = 3(0.01)^5 - 2(0.01)^3 + 7(0.01) - 4 = -3.9300019997.
$$

   The secant slope is

$$
\frac{f(0.01) - f(0)}{0.01} = \frac{0.0699980003}{0.01} = 6.99980003 \approx 7 = f'(0).
$$

   - Near $x = 1$: $f(1) = 4$ and $f(1.01) = 3(1.01)^5 - 2(1.01)^3 + 7(1.01) - 4 \approx 4.16242815$. The secant slope is

$$
\frac{f(1.01) - f(1)}{0.01} \approx \frac{0.16242815}{0.01} = 16.242815 \approx 16 = f'(1).
$$

2. **Degree and antiderivative check:** Differentiating a polynomial of degree $5$ must lower its degree by $1$ to degree $4$, and indeed $\deg(f') = 4$. Reversing the power rule term by term on $15x^4 - 6x^2 + 7$ gives:

$$
\frac{15}{5}x^5 - \frac{6}{3}x^3 + 7x + C = 3x^5 - 2x^3 + 7x + C,
$$

   which matches $f(x)$ with constant $C = -4$.

---

## 7. Common Mistakes to Avoid

- **Keeping the constant term $-4$ in the derivative:** A constant shifts the graph vertically without changing its slope anywhere. Its derivative is $0$, never $-4$.
- **Forgetting to decrease the exponent by $1$:** Writing $\frac{d}{dx}(3x^5) = 15x^5$ instead of $15x^4$ forgets the $-1$ in $nx^{n-1}$.
- **Evaluating first and differentiating second:** Computing $f(1) = 4$ and then taking the derivative of $4$ gives $0$, which is completely wrong. You must find the derivative function $f'(x)$ first and substitute $x = 1$ afterward.
- **Confusing $f(a)$ with $f'(a)$:** At $x = 0$, $f(0) = -4 < 0$ tells us the graph lies below the $x$-axis, whereas $f'(0) = 7 > 0$ tells us the graph is rising steeply as it crosses the $y$-axis. A curve can be below the $x$-axis and still have a positive slope.

---

## 8. How I Would Explain This in Class

> "Think of a polynomial as a sum of simple building blocks, and the power rule is your assembly-line tool: multiply by the exponent, then drop the exponent by one. Constant terms like $-4$ just lift or lower the entire curve like an elevator without tilting it at all, so they vanish when we measure slope. Once you have $f'(x)$, plugging in $0$ and $1$ is like placing a carpenter's level against the curve at those two spots: at $x = 0$ the curve is climbing at a slope of $7$ units up for every $1$ unit right, and by $x = 1$ it has tilted even steeper to a climb of $16$ units up for every $1$ unit right."
