# Problem 02: Distance as the Length of a Vector

## 1. The Original Problem

The points are $A = (1, 2, 3)$ and $B = (4, -2, 6)$.

1. Construct $\overrightarrow{AB}$.
2. Compute its length.
3. Compute the distance between the points using the coordinate formula.
4. Explain why both calculations give the same result.

---

## 2. What Are We Trying to Find?

We need to:
1. Construct the displacement vector $\overrightarrow{AB}$ directed from initial point $A$ to terminal point $B$.
2. Calculate the Euclidean norm (length) $\|\overrightarrow{AB}\|$.
3. Compute the geometric distance $d(A, B)$ using the standard Cartesian distance formula between two 3D points.
4. Provide a conceptual explanation demonstrating why the two calculations are mathematically and geometrically identical.

---

## 3. Before Calculating: What Idea Do We Need?

- **Vector from Two Points:**
  The displacement vector $\overrightarrow{AB}$ from initial point $A(x_A, y_A, z_A)$ to terminal point $B(x_B, y_B, z_B)$ is given by the difference of their position vectors:

$$
\overrightarrow{AB} = B - A = (x_B - x_A, y_B - y_A, z_B - z_A)
$$

- **Vector Length (Euclidean Norm):**
  For any vector $v = (v_1, v_2, v_3) \in \mathbb{R}^3$, its length is defined by the 3D Pythagorean theorem:

$$
\|v\| = \sqrt{v_1^2 + v_2^2 + v_3^2}
$$

- **Point-to-Point Distance Formula:**
  The distance $d(A, B)$ between points $A$ and $B$ in Cartesian coordinates is:

$$
d(A, B) = \sqrt{(x_B - x_A)^2 + (y_B - y_A)^2 + (z_B - z_A)^2}
$$

- **Conceptual Bridge:**
  The distance formula is nothing other than the norm of the displacement vector $\overrightarrow{AB}$.

---

## 4. Step-by-Step Solution

### Step 1: Construct the Vector $\overrightarrow{AB}$

Subtract the coordinates of the initial point $A(1, 2, 3)$ from the terminal point $B(4, -2, 6)$:

$$
\overrightarrow{AB} = B - A = (4 - 1, -2 - 2, 6 - 3) = (3, -4, 3)
$$

### Step 2: Compute the Length of $\overrightarrow{AB}$

Apply the Euclidean norm formula to $\overrightarrow{AB} = (3, -4, 3)$:

$$
\|\overrightarrow{AB}\| = \sqrt{3^2 + (-4)^2 + 3^2}
$$

Compute the squares:

$$
3^2 = 9, \quad (-4)^2 = 16, \quad 3^2 = 9
$$

Sum the squares:

$$
9 + 16 + 9 = 34
$$

Take the square root:

$$
\|\overrightarrow{AB}\| = \sqrt{34} \approx 5.831
$$

---

### Step 3: Compute the Distance Using the Coordinate Formula

Apply the Cartesian distance formula directly to points $A(1, 2, 3)$ and $B(4, -2, 6)$:

$$
d(A, B) = \sqrt{(4 - 1)^2 + (-2 - 2)^2 + (6 - 3)^2}
$$

Evaluate each coordinate difference:

$$
4 - 1 = 3, \quad -2 - 2 = -4, \quad 6 - 3 = 3
$$

Square the differences and sum them:

$$
d(A, B) = \sqrt{(3)^2 + (-4)^2 + (3)^2} = \sqrt{9 + 16 + 9} = \sqrt{34} \approx 5.831
$$

---

### Step 4: Explain Why Both Calculations Give the Same Result

The two calculations are identical because of how vectors and distance are fundamentally defined:
1. The displacement vector $\overrightarrow{AB}$ packages the three coordinate changes ($\Delta x = x_B - x_A$, $\Delta y = y_B - y_A$, $\Delta z = z_B - z_A$) along the coordinate axes into a single geometric object.
2. The distance between two points is defined as the length of the straight-line segment connecting them.
3. The segment $[AB]$ is precisely the geometric representation of the vector $\overrightarrow{AB}$.
4. Therefore, calculating $d(A, B)$ using coordinates is literally computing $\sqrt{(\Delta x)^2 + (\Delta y)^2 + (\Delta z)^2}$, which is by definition the Euclidean norm $\|\overrightarrow{AB}\|$. The distance formula is simply the vector length formula expressed in terms of endpoints.

---

## 5. Final Answer & Conclusion

- **Displacement Vector:**

$$
\overrightarrow{AB} = (3, -4, 3)
$$

- **Vector Length:**

$$
\|\overrightarrow{AB}\| = \sqrt{34}
$$

- **Distance Between Points:**

$$
d(A, B) = \sqrt{34}
$$

- **Conclusion:** The distance between two points in Euclidean space is inherently the length of the displacement vector connecting them: $d(A, B) \equiv \|\overrightarrow{AB}\|$.

---

## 6. Quick Verification

Calculate the vector in the reverse direction $\overrightarrow{BA}$:

$$
\overrightarrow{BA} = A - B = (1 - 4, 2 - (-2), 3 - 6) = (-3, 4, -3) = -\overrightarrow{AB}
$$

Compute its length:

$$
\|\overrightarrow{BA}\| = \sqrt{(-3)^2 + 4^2 + (-3)^2} = \sqrt{9 + 16 + 9} = \sqrt{34}
$$

Because distance is symmetric ($d(A, B) = d(B, A)$) and vector length satisfies $\|-\overrightarrow{AB}\| = \|\overrightarrow{AB}\|$, the length $\sqrt{34}$ is confirmed from both directions.

---

## 7. Common Mistakes to Avoid

1. **Subtracting in the Wrong Direction:**
   Calculating $A - B$ instead of $B - A$. While $\|\overrightarrow{BA}\| = \|\overrightarrow{AB}\|$, the vector direction is reversed ($\overrightarrow{BA} = -\overrightarrow{AB}$).
2. **Squaring Negative Numbers Incorrectly:**
   Writing $(-4)^2 = -16$. Squaring any real number yields a non-negative quantity: $(-4)^2 = +16$.
3. **Approximating Too Early:**
   Leaving the answer as $\approx 5.83$ without giving the exact radical form $\sqrt{34}$.

---

## 8. How I Would Explain This in Class

> "When we subtract point $A$ from point $B$, we find the exact step vector $(3, -4, 3)$ required to walk from $A$ to $B$. The distance formula you learned in high school isn't a new formula—it is just the 3D Pythagorean theorem applied to the components of that exact step vector. That is why taking the length of $\overrightarrow{AB}$ and measuring the distance between $A$ and $B$ are really just two names for the exact same calculation."

