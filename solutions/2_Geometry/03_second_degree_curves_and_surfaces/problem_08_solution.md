# Problem 08: Sphere

## 1. The Original Problem

Reduce

$$
x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0
$$

to canonical form. Find the center and radius. Give two points on the sphere and check them in the equation.

---

## 2. What Are We Trying to Find?

We need to:
1. Apply completing the square simultaneously across all three spatial variables $x, y,$ and $z$.
2. Reduce the general equation into standard canonical sphere form: $(x - x_0)^2 + (y - y_0)^2 + (z - z_0)^2 = R^2$.
3. Identify the center coordinates $S(x_0, y_0, z_0)$ and the radius $R$.
4. Select two concrete points lying on the surface of the sphere.
5. Verify both points by substituting them into both the canonical form and the original general equation.

---

## 3. Before Calculating: What Idea Do We Need?

- **Canonical Form of a Sphere in $\mathbb{R}^3$:**
  A sphere centered at $S(x_0, y_0, z_0)$ with radius $R > 0$ is defined as the locus of all points at constant Euclidean distance $R$ from $S$:

$$
(x - x_0)^2 + (y - y_0)^2 + (z - z_0)^2 = R^2
$$

- **Completing the Square in 3D:**
  The 2D circle technique generalizes directly to 3D by completing squares for $x$, $y$, and $z$ independently:
  - $x^2 - 2hx = (x - h)^2 - h^2$
  - $y^2 - 2ky = (y - k)^2 - k^2$
  - $z^2 - 2lz = (z - l)^2 - l^2$
- **Choosing Cardinal Poles:**
  Moving distance $R$ from the center along any coordinate axis yields convenient integer points on the sphere:
  - $(x_0 \pm R, y_0, z_0)$
  - $(x_0, y_0 \pm R, z_0)$
  - $(x_0, y_0, z_0 \pm R)$

---

## 4. Step-by-Step Solution

### Step 1: Group Variables and Move the Constant

Rearrange $x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0$ by grouping related variables:

$$
(x^2 - 4x) + (y^2 + 2y) + (z^2 - 6z) = 2
$$

---

### Step 2: Complete the Squares

1. **For the $x$-terms:**

$$
x^2 - 4x = (x - 2)^2 - 2^2 = (x - 2)^2 - 4
$$

2. **For the $y$-terms:**

$$
y^2 + 2y = (y + 1)^2 - 1^2 = (y + 1)^2 - 1
$$

3. **For the $z$-terms:**

$$
z^2 - 6z = (z - 3)^2 - 3^2 = (z - 3)^2 - 9
$$

---

### Step 3: Formulate the Canonical Equation

Substitute the completed squares back into the equation:

$$
[(x - 2)^2 - 4] + [(y + 1)^2 - 1] + [(z - 3)^2 - 9] = 2
$$

Move all subtracted numerical constants to the right-hand side:

$$
(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 2 + 4 + 1 + 9
$$

Sum the constants:

$$
2 + 4 + 1 + 9 = 16
$$

Thus, the canonical form is:

$$
(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16
$$

Express the right-hand side as a square:

$$
(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 4^2
$$

---

### Step 4: Identify Center and Radius

Comparing with $(x - x_0)^2 + (y - y_0)^2 + (z - z_0)^2 = R^2$:
- **Center:**

$$
S = (x_0, y_0, z_0) = (2, -1, 3)
$$

- **Radius:**

$$
R = \sqrt{16} = 4
$$

---

### Step 5: Choose Two Points and Substitute into Both Equations

#### Point 1: Shift Along the $x$-Axis ($x = x_0 + R = 2 + 4 = 6$)
Keep $y = -1$ and $z = 3$:

$$
P_1 = (6, -1, 3)
$$

- **Check in Canonical Form:**

$$
(6 - 2)^2 + (-1 + 1)^2 + (3 - 3)^2 = 4^2 + 0^2 + 0^2 = 16 + 0 + 0 = 16
$$

  Matches $16 = 16$. (Verified)
- **Check in Original General Form ($x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0$):**

$$
6^2 + (-1)^2 + 3^2 - 4(6) + 2(-1) - 6(3) - 2 = 36 + 1 + 9 - 24 - 2 - 18 - 2
$$

$$
(36 + 1 + 9) - (24 + 2 + 18 + 2) = 46 - 46 = 0
$$

  Matches $0 = 0$. (Verified)

---

#### Point 2: Shift Along the $z$-Axis ($z = z_0 + R = 3 + 4 = 7$)
Keep $x = 2$ and $y = -1$:

$$
P_2 = (2, -1, 7)
$$

- **Check in Canonical Form:**

$$
(2 - 2)^2 + (-1 + 1)^2 + (7 - 3)^2 = 0^2 + 0^2 + 4^2 = 0 + 0 + 16 = 16
$$

  Matches $16 = 16$. (Verified)
- **Check in Original General Form ($x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0$):**

$$
2^2 + (-1)^2 + 7^2 - 4(2) + 2(-1) - 6(7) - 2 = 4 + 1 + 49 - 8 - 2 - 42 - 2
$$

$$
(4 + 1 + 49) - (8 + 2 + 42 + 2) = 54 - 54 = 0
$$

  Matches $0 = 0$. (Verified)

---

## 5. Final Answer & Conclusion

- **Canonical Form:**

$$
(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16 \quad (\text{or } 4^2)
$$

- **Center:**

$$
S = (2, -1, 3)
$$

- **Radius:**

$$
R = 4
$$

- **Two Points on the Sphere:**
  - $P_1(6, -1, 3)$ satisfies canonical form ($16 = 16$) and general form ($0 = 0$).
  - $P_2(2, -1, 7)$ satisfies canonical form ($16 = 16$) and general form ($0 = 0$).

---

## 6. Quick Verification

Expand the canonical form back to the general form:

$$
(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16
$$

$$
(x^2 - 4x + 4) + (y^2 + 2y + 1) + (z^2 - 6z + 9) = 16
$$

Combine constants on the left:

$$
x^2 + y^2 + z^2 - 4x + 2y - 6z + 14 = 16
$$

Subtract $16$ from both sides:

$$
x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0
$$

The result perfectly matches the original given equation.

---

## 7. Common Mistakes to Avoid

1. **Sign Reversals in Center Coordinates:**
   Writing the center as $(-2, 1, -3)$. The canonical factors are $(x - x_0), (y - y_0), (z - z_0)$, giving $S(2, -1, 3)$.
2. **Missing Terms in the Right-Hand Sum:**
   Forgetting the original constant $2$, or omitting one of the squared offsets ($4, 1, 9$).
3. **Squaring Negatives Incorrectly:**
   Evaluating $(-1)^2 = -1$ when checking points. $(-1)^2 = +1$.

---

## 8. How I Would Explain This in Class

> "Moving from a 2D circle to a 3D sphere requires zero new formulas—you just perform the exact same completing-the-square trick on the new $z$-coordinate. Grouping $x, y,$ and $z$ into their own perfect squares bundles the messy coefficients into $(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16$, telling us instantly that we have a solid basketball centered at $(2, -1, 3)$ with a radius of exactly 4."

