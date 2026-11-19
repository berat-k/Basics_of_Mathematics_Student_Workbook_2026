# Problem 09: Distances

## 1. The Original Problem

Compute:

1. The distance from $P = (2, 3)$ to the line $3x + 4y - 10 = 0$,
2. The distance from $Q = (2, -1, 3)$ to the plane $2x - 2y + z - 4 = 0$.

Compare the two formulas and explain their common connection with the normal direction.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the perpendicular distance from 2D point $P(2, 3)$ to the line $3x + 4y - 10 = 0$ in $\mathbb{R}^2$.
2. Compute the perpendicular distance from 3D point $Q(2, -1, 3)$ to the plane $2x - 2y + z - 4 = 0$ in $\mathbb{R}^3$.
3. Compare the algebraic structure of both distance formulas.
4. Explain the unified geometric mechanism connecting both formulas to scalar projection onto the normal unit vector.

---

## 3. Before Calculating: What Idea Do We Need?

- **Distance from a Point to a Line in $\mathbb{R}^2$:**
  For a point $P(x_0, y_0)$ and a line $L: ax + by + c = 0$, the shortest distance is:

$$
d(P, L) = \frac{|a x_0 + b y_0 + c|}{\sqrt{a^2 + b^2}}
$$

- **Distance from a Point to a Plane in $\mathbb{R}^3$:**
  For a point $Q(x_0, y_0, z_0)$ and a plane $\Pi: ax + by + cz + d = 0$, the shortest distance is:

$$
d(Q, \Pi) = \frac{|a x_0 + b y_0 + c z_0 + d|}{\sqrt{a^2 + b^2 + c^2}}
$$

- **The Common Geometric Mechanism (Normal Projection):**
  In any dimension, a hyperplane (line in 2D, plane in 3D) is defined by a normal vector $n$. The shortest distance from an external point $X_0$ to the hyperplane is measured along the line passing through $X_0$ parallel to $n$.
  If $X_1$ is any point lying on the hyperplane, the distance is simply the absolute value of the scalar projection of the displacement vector $\overrightarrow{X_1 X_0}$ onto the normal vector $n$:

$$
d = \frac{|n \cdot (X_0 - X_1)|}{\|n\|} = \frac{|\text{evaluated equation}|}{\|n\|}
$$

---

## 4. Step-by-Step Solution

### Step 1: Distance from $P(2, 3)$ to the Line $3x + 4y - 10 = 0$

1. **Identify the coefficients and coordinates:**
   - Equation of line: $3x + 4y - 10 = 0 \implies a = 3, b = 4, c = -10$.
   - Normal vector: $n = (3, 4)$.
   - Point: $P(x_0, y_0) = (2, 3)$.

2. **Compute the numerator (absolute evaluation at $P$):**

$$
|a x_0 + b y_0 + c| = |3(2) + 4(3) - 10| = |6 + 12 - 10| = |8| = 8
$$

3. **Compute the denominator (norm of normal vector):**

$$
\|n\| = \sqrt{a^2 + b^2} = \sqrt{3^2 + 4^2} = \sqrt{9 + 16} = \sqrt{25} = 5
$$

4. **Calculate the distance:**

$$
d(P, L) = \frac{8}{5} = 1.6
$$

---

### Step 2: Distance from $Q(2, -1, 3)$ to the Plane $2x - 2y + z - 4 = 0$

1. **Identify the coefficients and coordinates:**
   - Equation of plane: $2x - 2y + z - 4 = 0 \implies a = 2, b = -2, c = 1, d = -4$.
   - Normal vector: $n = (2, -2, 1)$.
   - Point: $Q(x_0, y_0, z_0) = (2, -1, 3)$.

2. **Compute the numerator (absolute evaluation at $Q$):**

$$
|a x_0 + b y_0 + c z_0 + d| = |2(2) - 2(-1) + 1(3) - 4| = |4 + 2 + 3 - 4| = |5| = 5
$$

3. **Compute the denominator (norm of normal vector):**

$$
\|n\| = \sqrt{a^2 + b^2 + c^2} = \sqrt{2^2 + (-2)^2 + 1^2} = \sqrt{4 + 4 + 1} = \sqrt{9} = 3
$$

4. **Calculate the distance:**

$$
d(Q, \Pi) = \frac{5}{3} \approx 1.667
$$

---

### Step 3: Compare the Two Formulas and Explain the Normal Connection

1. **Structural Comparison:**
   Both formulas are structurally identical:

$$
d = \frac{|\text{Substitute point coordinates into equation}|}{\text{Length of the normal vector}} = \frac{|F(P_0)|}{\|n\|}
$$

   - In 2D: $n = (a, b)$ has length $\sqrt{a^2 + b^2}$.
   - In 3D: $n = (a, b, c)$ has length $\sqrt{a^2 + b^2 + c^2}$.
   The only difference is the addition of the $z$-coordinate term in 3D.

2. **The Common Geometric Connection with the Normal Direction:**
   - By definition, the shortest distance from an external point to a flat surface is measured along the perpendicular path (along the normal direction).
   - If we normalize the equation by dividing every term by $\|n\|$, the equation becomes the **Hesse normal form**:

$$
\frac{n}{\|n\|} \cdot X - d_0 = 0 \iff \hat{n} \cdot X - d_0 = 0
$$

   where $\hat{n}$ is a unit normal vector ($\|\hat{n}\| = 1$).
   - When we plug any point $P_0$ into the Hesse form, the resulting value $|\hat{n} \cdot P_0 - d_0|$ directly measures the scalar length of the perpendicular segment dropped from $P_0$ onto the surface.
   - Therefore, both formulas are simply computing the magnitude of the projection of the displacement vector onto the unit normal vector $\hat{n}$.

---

## 5. Final Answer & Conclusion

- **Distance to the Line:**

$$
d(P, L) = \frac{8}{5} = 1.6
$$

- **Distance to the Plane:**

$$
d(Q, \Pi) = \frac{5}{3} \approx 1.667
$$

- **Comparative Conclusion:** Both formulas represent the exact same geometric operation: evaluating the linear constraint at the target point and dividing by the length of the normal vector, which computes the scalar projection of the displacement onto the unit normal direction $\hat{n}$.

---

## 6. Quick Verification

Verify the 2D distance by finding the foot of the perpendicular on the line $L$:
- Line through $P(2, 3)$ in direction $n(3, 4)$: $(x, y) = (2 + 3t, 3 + 4t)$.
- Substitute into $3x + 4y - 10 = 0$:
  $3(2 + 3t) + 4(3 + 4t) - 10 = 0 \implies 6 + 9t + 12 + 16t - 10 = 0 \implies 25t + 8 = 0 \implies t = -8/25$.
- Distance is the length of displacement vector $\Delta = t n$:

$$
d = |t| \|n\| = \left| -\frac{8}{25} \right| \cdot 5 = \frac{8}{25} \times 5 = \frac{8}{5}
$$

Matches $8/5 = 1.6$ exactly.

---

## 7. Common Mistakes to Avoid

1. **Forgetting the Absolute Value:**
   Leaving $2 - 2 + \dots$ without the absolute value bars. Distances are geometric lengths and must always be strictly non-negative ($d \ge 0$).
2. **Dividing by the Coordinates of the Point Instead of the Normal:**
   Computing $\sqrt{x_0^2 + y_0^2}$ in the denominator instead of the coefficients of the equation $\sqrt{a^2 + b^2}$.
3. **Double Negative Slips in the Plane Equation:**
   Evaluating $-2y_0$ at $y_0 = -1$ as $-2$ instead of $-2(-1) = +2$.

---

## 8. How I Would Explain This in Class

> "Whether you are dropping a perpendicular line from a point to a 2D line on paper, or dropping a plumb line from a point to a 3D floor, the physics is identical: the shortest route is always along the normal vector. The equation's numerator measures how far off the target your point is, and dividing by the length of the normal vector scales that error measurement into true physical inches or meters."

