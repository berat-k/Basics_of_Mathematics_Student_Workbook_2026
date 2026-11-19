# Problem 06: Shifted Ellipse

## 1. The Original Problem

Reduce

$$
4x^2 + 9y^2 - 16x + 18y - 11 = 0
$$

to canonical form. Give the center and semiaxis lengths. Check that substituting the coordinates of the center into the left-hand side gives a value consistent with the form you obtained.

---

## 2. What Are We Trying to Find?

We need to:
1. Complete the square for both the $x$ and $y$ variables in the general quadratic equation.
2. Reduce the equation to canonical form: $\frac{(x - x_0)^2}{a^2} + \frac{(y - y_0)^2}{b^2} = 1$.
3. Identify the coordinates of the center $S(x_0, y_0)$ and the semiaxis lengths $a$ and $b$.
4. Substitute the center coordinates into the original left-hand side expression and explain why the resulting numerical value is completely consistent with the canonical equation.

---

## 3. Before Calculating: What Idea Do We Need?

- **Factoring Out Leading Coefficients:**
  Before completing the square, the leading coefficient of the squared term must be factored out from both the quadratic and linear terms of that variable:
  - $4x^2 - 16x = 4(x^2 - 4x) = 4[(x - 2)^2 - 4] = 4(x - 2)^2 - 16$.
  - $9y^2 + 18y = 9(y^2 + 2y) = 9[(y + 1)^2 - 1] = 9(y + 1)^2 - 9$.
- **Canonical Form of a Translated Ellipse:**

$$
\frac{(x - x_0)^2}{a^2} + \frac{(y - y_0)^2}{b^2} = 1
$$

  where $(x_0, y_0)$ is the center, $a$ is the horizontal semiaxis, and $b$ is the vertical semiaxis.
- **Consistency Check at the Center:**
  If the canonical form is $4(x - x_0)^2 + 9(y - y_0)^2 = C$, substituting the center $(x_0, y_0)$ into the squared brackets makes them both vanish to $0$:

$$
4(0)^2 + 9(0)^2 - C = -C
$$

  Therefore, evaluating the left-hand side of the original equation at the center must yield exactly the negative of the constant $C$ produced during completion of the square.

---

## 4. Step-by-Step Solution

### Step 1: Group and Factor Variables

Group the $x$-terms and $y$-terms and move the constant $-11$ to the right-hand side:

$$
(4x^2 - 16x) + (9y^2 + 18y) = 11
$$

Factor out the leading coefficient from each group:

$$
4(x^2 - 4x) + 9(y^2 + 2y) = 11
$$

---

### Step 2: Complete the Squares Inside the Parentheses

1. **For the $x$-terms:**

$$
x^2 - 4x = (x - 2)^2 - 2^2 = (x - 2)^2 - 4
$$

2. **For the $y$-terms:**

$$
y^2 + 2y = (y + 1)^2 - 1^2 = (y + 1)^2 - 1
$$

---

### Step 3: Substitute and Simplify

Substitute the completed squares back into the equation:

$$
4[(x - 2)^2 - 4] + 9[(y + 1)^2 - 1] = 11
$$

Distribute the outer factors $4$ and $9$:

$$
4(x - 2)^2 - 16 + 9(y + 1)^2 - 9 = 11
$$

Combine the constant terms on the left:

$$
-16 - 9 = -25
$$

$$
4(x - 2)^2 + 9(y + 1)^2 - 25 = 11
$$

Add $25$ to both sides:

$$
4(x - 2)^2 + 9(y + 1)^2 = 11 + 25 = 36
$$

---

### Step 4: Divide by $36$ to Obtain Canonical Form

Divide every term by $36$ so the right-hand side equals $1$:

$$
\frac{4(x - 2)^2}{36} + \frac{9(y + 1)^2}{36} = \frac{36}{36}
$$

Simplify the fractions:

$$
\frac{(x - 2)^2}{9} + \frac{(y + 1)^2}{4} = 1
$$

Express the denominators as squares:

$$
\frac{(x - 2)^2}{3^2} + \frac{(y + 1)^2}{2^2} = 1
$$

---

### Step 5: Identify the Center and Semiaxis Lengths

Comparing with $\frac{(x - x_0)^2}{a^2} + \frac{(y - y_0)^2}{b^2} = 1$:
- **Center:**

$$
S = (x_0, y_0) = (2, -1)
$$

- **Semiaxis Lengths:**
  - Horizontal semiaxis: $a = \sqrt{9} = 3$
  - Vertical semiaxis: $b = \sqrt{4} = 2$
  The ellipse is elongated horizontally because $a = 3 > 2 = b$.

---

### Step 6: Consistency Check with Center Substitution

Let $F(x, y)$ be the left-hand side of the original equation:

$$
F(x, y) = 4x^2 + 9y^2 - 16x + 18y - 11
$$

Substitute the center coordinates $x = 2$ and $y = -1$:

$$
F(2, -1) = 4(2)^2 + 9(-1)^2 - 16(2) + 18(-1) - 11
$$

Evaluate each term:
- $4(2^2) = 4(4) = 16$
- $9((-1)^2) = 9(1) = 9$
- $-16(2) = -32$
- $+18(-1) = -18$
- $-11$

Sum the values:

$$
F(2, -1) = 16 + 9 - 32 - 18 - 11 = 25 - 61 = -36
$$

#### Why This Value Is Consistent with the Canonical Form:
In Step 3, we showed the exact algebraic identity:

$$
4x^2 + 9y^2 - 16x + 18y - 11 \equiv 4(x - 2)^2 + 9(y + 1)^2 - 36
$$

When we substitute the center $(x, y) = (2, -1)$:
- The squared term $4(2 - 2)^2 = 4(0)^2 = 0$.
- The squared term $9(-1 + 1)^2 = 9(0)^2 = 0$.
The completed squares completely vanish, leaving:

$$
0 + 0 - 36 = -36
$$

This matches the value $-36$ obtained from direct substitution, proving that the center coordinates $(2, -1)$ and the constant $36$ are 100% algebraically consistent.

---

## 5. Final Answer & Conclusion

- **Canonical Form:**

$$
\frac{(x - 2)^2}{9} + \frac{(y + 1)^2}{4} = 1
$$

- **Center:** $S = (2, -1)$
- **Semiaxis Lengths:** $a = 3$ (horizontal) and $b = 2$ (vertical)
- **Consistency Verification:** Evaluating the original left-hand side at the center yields $-36$, which precisely equals the negative of the constant $36$ needed to make the canonical form equal $1$.

---

## 6. Quick Verification

Verify the 4 cardinal vertices of the ellipse:
1. East vertex: $(2 + 3, -1) = (5, -1)$
   $F(5, -1) = 4(25) + 9(1) - 16(5) + 18(-1) - 11 = 100 + 9 - 80 - 18 - 11 = 109 - 109 = 0$. (Holds)
2. West vertex: $(2 - 3, -1) = (-1, -1)$
   $F(-1, -1) = 4(1) + 9(1) - 16(-1) + 18(-1) - 11 = 4 + 9 + 16 - 18 - 11 = 29 - 29 = 0$. (Holds)
3. North vertex: $(2, -1 + 2) = (2, 1)$
   $F(2, 1) = 4(4) + 9(1) - 16(2) + 18(1) - 11 = 16 + 9 - 32 + 18 - 11 = 43 - 43 = 0$. (Holds)
4. South vertex: $(2, -1 - 2) = (2, -3)$
   $F(2, -3) = 4(4) + 9(9) - 16(2) + 18(-3) - 11 = 16 + 81 - 32 - 54 - 11 = 97 - 97 = 0$. (Holds)
All four vertices satisfy the original general equation.

---

## 7. Common Mistakes to Avoid

1. **Forgetting to Distribute the Leading Coefficients:**
   Adding $4$ and $1$ to the right-hand side instead of $4 \times 4 = 16$ and $9 \times 1 = 9$.
2. **Sign Slips in Center Coordinates:**
   Stating the center is $(-2, 1)$ instead of $(2, -1)$.
3. **Misinterpreting the Non-Zero Value at the Center:**
   Expecting $F(2, -1)$ to equal $0$. The center is inside the ellipse, not on its boundary curve! A value of $0$ occurs only on the boundary. At the center, the value must equal $-36$.

---

## 8. How I Would Explain This in Class

> "When an ellipse is shifted away from the origin, its equation is cluttered with linear $x$ and $y$ terms. Completing the square gathers those stray terms into $(x - 2)^2$ and $(y + 1)^2$, which tells you that the center of the ellipse was moved to $(2, -1)$. And when you stand right at that center, the distance from both ellipse brackets drops to zero, revealing the $-36$ that balances out on the boundary."

