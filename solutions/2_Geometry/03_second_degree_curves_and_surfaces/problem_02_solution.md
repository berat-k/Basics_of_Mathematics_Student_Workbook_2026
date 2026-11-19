# Problem 02: Circle by Completing the Square

## 1. The Original Problem

Reduce

$$
x^2 + y^2 - 6x + 4y - 3 = 0
$$

to canonical form. Find the center and radius, then substitute two simple points from the circle into both forms of the equation.

---

## 2. What Are We Trying to Find?

We need to:
1. Apply the algebraic method of completing the square to both $x$ and $y$ variables.
2. Transform the general second-degree equation into the standard canonical circle form: $(x - x_0)^2 + (y - y_0)^2 = R^2$.
3. Extract the coordinates of the center $S(x_0, y_0)$ and the radius $R$.
4. Select two convenient points on the circumference.
5. Check both points by substituting them into both the canonical form and the original general form.

---

## 3. Before Calculating: What Idea Do We Need?

- **Completing the Square Identity:**
  For any quadratic expression $u^2 + 2ku$:

$$
u^2 + 2ku = (u + k)^2 - k^2
$$

- **Canonical Form of a Circle:**
  A circle centered at $S(x_0, y_0)$ with radius $R > 0$ is defined by:

$$
(x - x_0)^2 + (y - y_0)^2 = R^2
$$

- **Selecting Cardinal Points:**
  Setting $x = x_0$ isolates $(y - y_0)^2 = R^2 \implies y = y_0 \pm R$, giving the north and south poles.
  Setting $y = y_0$ isolates $(x - x_0)^2 = R^2 \implies x = x_0 \pm R$, giving the east and west poles.

---

## 4. Step-by-Step Solution

### Step 1: Group Variables and Move the Constant

Rearrange the general equation $x^2 + y^2 - 6x + 4y - 3 = 0$ by grouping $x$-terms and $y$-terms:

$$
(x^2 - 6x) + (y^2 + 4y) = 3
$$

---

### Step 2: Complete the Squares

1. **Complete the square for the $x$-terms:**
   - The linear coefficient is $-6$, so take half: $\frac{-6}{2} = -3$.
   - Square it: $(-3)^2 = 9$.

$$
x^2 - 6x = (x - 3)^2 - 9
$$

2. **Complete the square for the $y$-terms:**
   - The linear coefficient is $+4$, so take half: $\frac{4}{2} = 2$.
   - Square it: $2^2 = 4$.

$$
y^2 + 4y = (y + 2)^2 - 4
$$

---

### Step 3: Write the Canonical Form

Substitute the completed squares back into the grouped equation:

$$
[(x - 3)^2 - 9] + [(y + 2)^2 - 4] = 3
$$

Move the constant subtracted terms to the right-hand side:

$$
(x - 3)^2 + (y + 2)^2 = 3 + 9 + 4
$$

Simplify the right-hand side:

$$
(x - 3)^2 + (y + 2)^2 = 16
$$

Express $16$ as $4^2$:

$$
(x - 3)^2 + (y + 2)^2 = 4^2
$$

---

### Step 4: Identify Center and Radius

Comparing with the standard equation $(x - x_0)^2 + (y - y_0)^2 = R^2$:
- **Center:**

$$
S = (x_0, y_0) = (3, -2)
$$

- **Radius:**

$$
R = \sqrt{16} = 4
$$

---

### Step 5: Choose Two Points and Substitute into Both Forms

#### Point 1: North Pole ($x = 3$)
Set $x = 3$ in the canonical form:

$$
(3 - 3)^2 + (y + 2)^2 = 16 \implies 0 + (y + 2)^2 = 16 \implies y + 2 = 4 \implies y = 2
$$

Let **Point 1** be $P_1(3, 2)$.
- **Check in Canonical Form:**

$$
(3 - 3)^2 + (2 + 2)^2 = 0^2 + 4^2 = 0 + 16 = 16
$$

  Matches $16 = 16$. (Verified)
- **Check in Original General Form ($x^2 + y^2 - 6x + 4y - 3 = 0$):**

$$
3^2 + 2^2 - 6(3) + 4(2) - 3 = 9 + 4 - 18 + 8 - 3 = (9 + 4 + 8) - (18 + 3) = 21 - 21 = 0
$$

  Matches $0 = 0$. (Verified)

---

#### Point 2: East Pole ($y = -2$)
Set $y = -2$ in the canonical form:

$$
(x - 3)^2 + (-2 + 2)^2 = 16 \implies (x - 3)^2 + 0 = 16 \implies x - 3 = 4 \implies x = 7
$$

Let **Point 2** be $P_2(7, -2)$.
- **Check in Canonical Form:**

$$
(7 - 3)^2 + (-2 + 2)^2 = 4^2 + 0^2 = 16 + 0 = 16
$$

  Matches $16 = 16$. (Verified)
- **Check in Original General Form ($x^2 + y^2 - 6x + 4y - 3 = 0$):**

$$
7^2 + (-2)^2 - 6(7) + 4(-2) - 3 = 49 + 4 - 42 - 8 - 3 = (49 + 4) - (42 + 8 + 3) = 53 - 53 = 0
$$

  Matches $0 = 0$. (Verified)

---

## 5. Final Answer & Conclusion

- **Canonical Form:**

$$
(x - 3)^2 + (y + 2)^2 = 16 \quad (\text{or } (x - 3)^2 + (y + 2)^2 = 4^2)
$$

- **Center:** $S = (3, -2)$
- **Radius:** $R = 4$
- **Two Verified Points:**
  - $P_1(3, 2)$ satisfies both canonical form ($16 = 16$) and general form ($0 = 0$).
  - $P_2(7, -2)$ satisfies both canonical form ($16 = 16$) and general form ($0 = 0$).

---

## 6. Quick Verification

Expand the canonical form directly back to general form:

$$
(x - 3)^2 + (y + 2)^2 = 16 \implies (x^2 - 6x + 9) + (y^2 + 4y + 4) = 16
$$

Group variables:

$$
x^2 + y^2 - 6x + 4y + 13 = 16
$$

Subtract $16$ from both sides:

$$
x^2 + y^2 - 6x + 4y - 3 = 0
$$

This perfectly reproduces the original general equation, proving algebraic equivalence.

---

## 7. Common Mistakes to Avoid

1. **Sign Confusion in Center Coordinates:**
   Writing center as $(-3, 2)$. Remember the standard form is $(x - x_0)^2 + (y - y_0)^2$, so $(x - 3)$ means $x_0 = +3$ and $(y + 2) = (y - (-2))$ means $y_0 = -2$.
2. **Forgetting to Add Squared Offsets to the Right-Hand Side:**
   Writing $R^2 = 3$ instead of $3 + 9 + 4 = 16$. The completed squares require adding $9$ and $4$ to both sides.
3. **Taking Radius as $R^2$:**
   Declaring the radius to be $16$ instead of $R = \sqrt{16} = 4$.

---

## 8. How I Would Explain This in Class

> "Completing the square is like cleaning up a messy equation so its geometric personality becomes obvious. In $x^2 - 6x$, the $-6x$ tells us the circle was nudged 3 units to the right, and the $+4y$ tells us it was nudged 2 units down. By bundling them into $(x - 3)^2$ and $(y + 2)^2$ and balancing the extra numbers on the other side, the equation proudly reveals its center at $(3, -2)$ and its radius of 4."

