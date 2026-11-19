# Problem 10: The Tangent Line as an Application of the Derivative

## 1. The Original Problem

For

$$
f(x) = x^2 - 3x + 1
$$

find the equation of the tangent line at the point with $x = 2$. Give the point of tangency, the value $f'(2)$, the equation of the line, and verify that the point lies on the obtained tangent line.

---

## 2. What Are We Trying to Find?

1. The point of tangency on the graph of $f(x) = x^2 - 3x + 1$ corresponding to $x = 2$, namely the coordinates $(2, f(2))$.
2. The derivative $f'(x)$ and its specific numerical value $f'(2)$, which gives the slope of the tangent line at $x = 2$.
3. The equation of the tangent line to the graph of $f$ at $x = 2$, simplified into slope-intercept form $y = mx + b$.
4. An explicit verification confirming that the point of tangency lies on the obtained tangent line.

---

## 3. Before Calculating: What Idea Do We Need?

- **Point-slope form of a tangent line:** If $f$ is differentiable at $x = a$, then the tangent line to the graph $y = f(x)$ at the point $(a, f(a))$ has slope $m = f'(a)$ and equation

$$
y - f(a) = f'(a)(x - a),
$$

or equivalently

$$
y = f(a) + f'(a)(x - a).
$$

- **Power rule and linearity of differentiation:** For a quadratic polynomial $f(x) = Ax^2 + Bx + C$, the derivative is $f'(x) = 2Ax + B$.
- **Distinction between $f'(x)$ and $f'(a)$:** The expression $f'(x)$ is a function that gives the slope at any $x$. For the tangent line at a fixed point $x = 2$, the slope must be the single constant number $m = f'(2)$, not the variable expression $f'(x)$.
- **Checking membership on a line:** A point $(x_0, y_0)$ lies on the line $y = mx + b$ if and only if substituting $x = x_0$ produces $y = y_0$.

---

## 4. Step-by-Step Solution

### Step 1: Find the Point of Tangency

Evaluate $f(x) = x^2 - 3x + 1$ at $x = 2$:

$$
f(2) = 2^2 - 3(2) + 1 = 4 - 6 + 1 = -1.
$$

Therefore, the point of tangency on the parabola is

$$
P = (2, -1).
$$

### Step 2: Compute $f'(x)$ and Evaluate the Slope $f'(2)$

Differentiate $f(x) = x^2 - 3x + 1$ term by term using the power rule:

$$
f'(x) = \frac{d}{dx}(x^2) - 3\frac{d}{dx}(x) + \frac{d}{dx}(1) = 2x - 3.
$$

Now substitute $x = 2$ to find the slope of the tangent line at $P$:

$$
m = f'(2) = 2(2) - 3 = 4 - 3 = 1.
$$

Geometrically, at $x = 2$ the curve is rising at a $45^\circ$ angle, moving up $1$ unit for every $1$ unit to the right.

### Step 3: Write the Equation of the Tangent Line

Use the point-slope formula with point $(x_0, y_0) = (2, -1)$ and slope $m = 1$:

$$
y - (-1) = 1 \cdot (x - 2).
$$

Simplify to obtain slope-intercept form:

$$
y + 1 = x - 2 \implies y = x - 3.
$$

### Step 4: Verify That the Point of Tangency Lies on the Tangent Line

Substitute $x = 2$ into the tangent line equation $y = x - 3$:

$$
y = 2 - 3 = -1.
$$

Because this matches $f(2) = -1$, the point $(2, -1)$ indeed lies on the line $y = x - 3$.

Below is a qualitative sketch showing the parabola $y = x^2 - 3x + 1$, whose vertex lies at $(1.5, -1.25)$, together with its tangent line $y = x - 3$ touching smoothly at $(2, -1)$:

```text
  y
  ^
  | \                   /  y = x^2 - 3x + 1
  |  \                 /
  |   \               /   /  y = x - 3 (tangent, slope 1)
--+----+-------------+---+---> x
  |     \           * (2, -1)
  |      \___V___/ /
  |            /
  |          /
  |        /  y-intercept (0, -3)
```

---

## 5. Final Answer & Conclusion

- **Point of tangency:** $(2, -1)$.
- **Derivative at $x = 2$:** $f'(2) = 1$.
- **Equation of the tangent line:**

$$
y = x - 3.
$$

- **Verification of the point on the line:** Substituting $x = 2$ into $y = x - 3$ yields $y = 2 - 3 = -1 = f(2)$, confirming that $(2, -1)$ lies on the tangent line.

---

## 6. Quick Verification

1. **Repeated-root algebraic tangency check:** A line is tangent to a parabola if and only if their intersection equation has a double root at the point of tangency. Setting $f(x)$ equal to the line $y = x - 3$:

$$
f(x) - (x - 3) = (x^2 - 3x + 1) - (x - 3) = x^2 - 4x + 4 = (x - 2)^2.
$$

The difference $(x - 2)^2$ equals $0$ uniquely at $x = 2$ with multiplicity $2$, and is strictly positive for all $x \ne 2$. This proves both that $(2, -1)$ is the unique point of contact and that the upward-opening parabola sits cleanly above its tangent line everywhere else.

2. **Local numerical approximation check near $x = 2$:** Compare $f(x)$ with the tangent line $L(x) = x - 3$ at $x = 1.9$ and $x = 2.1$:
  - At $x = 1.9$: $f(1.9) = 3.61 - 5.7 + 1 = -1.09$, while $L(1.9) = 1.9 - 3 = -1.10$, giving a tiny difference of $+0.01 = (1.9 - 2)^2$.
  - At $x = 2.1$: $f(2.1) = 4.41 - 6.3 + 1 = -0.89$, while $L(2.1) = 2.1 - 3 = -0.90$, again giving $+0.01 = (2.1 - 2)^2$.

This confirms that $y = x - 3$ is the best linear approximation to $f(x)$ near $x = 2$.

---

## 7. Common Mistakes to Avoid

- **Using the formula $f'(x)$ instead of the number $f'(2)$ as the slope:** Writing $y - (-1) = (2x - 3)(x - 2)$ produces a quadratic curve, not a straight line! Always plug $x = 2$ into $f'(x)$ first to get the constant slope $m = 1$.
- **Confusing $f(2)$ with $f'(2)$:** The value $f(2) = -1$ is the $y$-coordinate of the point on the graph, whereas $f'(2) = 1$ is the slope of the tangent line. Swapping them yields the wrong line.
- **Sign errors with negative $y$-coordinates:** Because $f(2) = -1$, the left side of the point-slope formula is $y - (-1) = y + 1$, not $y - 1$. Writing $y - 1 = x - 2$ would give $y = x - 1$, which does not even pass through $(2, -1)$.
- **Skipping the check at the end:** Plugging $x = 2$ back into your final equation takes two seconds and immediately catches almost every sign or arithmetic slip.

---

## 8. How I Would Explain This in Class

> "To build any straight line, you need only two ingredients: a point to anchor it and a slope to aim it. The original function $f$ gives you the anchor—plug in $x = 2$ and you land at the point $(2, -1)$. The derivative $f'$ gives you the aim—differentiate to get $2x - 3$, plug in $x = 2$, and you get a constant slope of $1$. Once you have the anchor and the aim, point-slope form hands you the line $y = x - 3$ right away. And for a parabola, there is a wonderful bonus test: subtract the line from the parabola, and if you get a perfect square $(x - 2)^2$, you know with complete algebraic certainty that your line kisses the curve at $x = 2$ and nowhere else."
