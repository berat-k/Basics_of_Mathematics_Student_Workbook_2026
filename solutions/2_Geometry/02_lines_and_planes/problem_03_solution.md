# Problem 03: Plane Through a Point with a Given Normal Vector

## 1. The Original Problem

Find the equation of the plane through $P = (1, -2, 3)$ and perpendicular to $n = (2, 1, -1)$. Check the result by substituting the point $P$ and explain the role of the normal vector.

---

## 2. What Are We Trying to Find?

We need to:
1. Construct the scalar Cartesian equation of the plane passing through point $P(1, -2, 3)$ with given normal vector $n = (2, 1, -1)$.
2. Verify the resulting equation by substituting the coordinates of point $P$.
3. Explain the fundamental geometric role that the normal vector plays in determining and defining a plane in 3D space.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Point-Normal Equation of a Plane:**
  A plane $\Pi$ in $\mathbb{R}^3$ passing through an anchor point $P(x_0, y_0, z_0)$ and perpendicular to a non-zero normal vector $n = (a, b, c)$ consists of all points $X(x, y, z)$ such that the displacement vector $\overrightarrow{PX} = X - P$ is orthogonal to $n$:

$$
n \cdot (X - P) = 0
$$

- **General Cartesian Form ($ax + by + cz = d$):**
  Expanding the dot product gives:

$$
a(x - x_0) + b(y - y_0) + c(z - z_0) = 0 \iff ax + by + cz = d
$$

  where the constant $d$ is given by:

$$
d = a x_0 + b y_0 + c z_0 = n \cdot P
$$

- **The Geometric Role of the Normal Vector:**
  In three-dimensional space, an infinite number of different planes can pass through a single point $P$. The normal vector $n$ acts as an orientation anchor: by demanding that all movement within the plane remains strictly perpendicular to $n$, the normal vector eliminates all rotational freedom, locking the plane into one unique spatial tilt.

---

## 4. Step-by-Step Solution

### Step 1: Set Up the Vector Orthogonality Condition

Let $X(x, y, z)$ be an arbitrary point lying on the plane.
The displacement vector from $P(1, -2, 3)$ to $X$ is:

$$
\overrightarrow{PX} = X - P = (x - 1, y - (-2), z - 3) = (x - 1, y + 2, z - 3)
$$

Since the plane is perpendicular to $n = (2, 1, -1)$, we must have:

$$
n \cdot \overrightarrow{PX} = 0
$$

---

### Step 2: Expand and Simplify the Equation

Write out the dot product with components:

$$
(2)(x - 1) + (1)(y + 2) + (-1)(z - 3) = 0
$$

Expand each product:

$$
2x - 2 + y + 2 - z + 3 = 0
$$

Combine the constant terms:

$$
(-2) + 2 + 3 = 3
$$

Thus, the equation simplifies to:

$$
2x + y - z + 3 = 0
$$

Equivalently, writing the constant term on the right-hand side:

$$
2x + y - z = -3
$$

---

### Step 3: Check by Substituting Point $P$

Substitute $x = 1, y = -2, z = 3$ into the left-hand side of $2x + y - z = -3$:

$$
2(1) + (-2) - (3) = 2 - 2 - 3 = -3
$$

The left-hand side evaluates to $-3$, exactly matching the right-hand side.
Point $P$ satisfies the equation.

---

### Step 4: Explain the Role of the Normal Vector

1. **Fixing the Orientation in Space:**
   A single point $P$ tells us where the plane is anchored in space, but not which way it faces (infinitely many planes pass through $P$, like pages of a book sharing a common spine). The normal vector $n$ specifies the unique direction perpendicular to the entire surface, locking the plane's tilt.
2. **Generating the Equation's Coefficients:**
   The components of the normal vector $(a, b, c) = (2, 1, -1)$ become the exact linear coefficients of the variables $(x, y, z)$ in the Cartesian equation $2x + y - z = d$.
3. **Defining Planar Membership:**
   The normal vector provides a simple universal membership test: a point $X$ lies on the plane if and only if the vector from $P$ to $X$ dots to zero with $n$.

---

## 5. Final Answer & Conclusion

- **Equation of the Plane:**

$$
2x + y - z + 3 = 0 \quad (\text{or } 2x + y - z = -3)
$$

- **Verification:** $2(1) + (-2) - (3) = -3$. The point $P$ satisfies the equation.
- **Role of Normal Vector:** The vector $n = (2, 1, -1)$ provides the linear coefficients of the equation and fixes the plane's spatial tilt by requiring all displacement vectors inside the plane to be perpendicular to $n$.

---

## 6. Quick Verification

Pick two other candidate points on the plane and check their displacement vectors:
1. Let $y = 0, z = 1 \implies 2x + 0 - 1 = -3 \implies 2x = -2 \implies x = -1$.
   Point $A(-1, 0, 1)$ lies on the plane.
2. The displacement vector from $P(1, -2, 3)$ to $A(-1, 0, 1)$ is:

$$
\overrightarrow{PA} = (-1 - 1, 0 - (-2), 1 - 3) = (-2, 2, -2)
$$

3. Compute its dot product with the normal vector $n = (2, 1, -1)$:

$$
n \cdot \overrightarrow{PA} = (2)(-2) + (1)(2) + (-1)(-2) = -4 + 2 + 2 = 0
$$

The displacement within the plane is strictly orthogonal to $n$, confirming the equation's accuracy.

---

## 7. Common Mistakes to Avoid

1. **Sign Errors with Negative Coordinates:**
   Writing $(y - 2)$ instead of $(y - (-2)) = (y + 2)$ for the second coordinate of point $P(1, -2, 3)$.
2. **Confusing Normal Vectors with Direction Vectors:**
   Trying to write a parametric equation with $n$ as a direction vector. A line needs a direction vector; a plane needs a **normal vector** to define its single Cartesian equation.
3. **Miscalculating the Constant $d$:**
   Computing $d = -2 + 2 - 3 = -3$ but flipping the sign when moving across the equals sign, writing $2x + y - z = 3$ instead of $-3$.

---

## 8. How I Would Explain This in Class

> "Imagine holding a flat sheet of plywood on the tip of your finger at point $P(1, -2, 3)$: it can tilt in any direction you like. To freeze it in place, you plant a rigid stick $n = (2, 1, -1)$ perpendicular to the board. The mathematical rule for the board is simple: any ant crawling on the plywood from point $P$ to a point $(x, y, z)$ must walk at a 90-degree angle to the stick. That simple right-angle condition $(X - P) \cdot n = 0$ gives us the equation $2x + y - z = -3$."

