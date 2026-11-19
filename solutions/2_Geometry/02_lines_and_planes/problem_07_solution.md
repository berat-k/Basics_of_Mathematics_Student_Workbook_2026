# Problem 07: A Line Relative to a Plane

## 1. The Original Problem

For

$$
L: (x, y, z) = (1, 1, 0) + t(1, -1, 0), \qquad \Pi: x + y + z = 2,
$$

determine whether the line intersects the plane at one point, is parallel to it, or lies in it. Explain the role of the dot product of the direction vector and the normal vector.

---

## 2. What Are We Trying to Find?

We need to:
1. Extract the direction vector $v$ of line $L$ and the normal vector $n$ of plane $\Pi$.
2. Compute the scalar dot product $v \cdot n$ and interpret its geometric significance.
3. Determine whether the line intersects the plane at a single point, is strictly parallel to the plane, or lies entirely inside the plane.
4. Thoroughly explain the mathematical role of the dot product $v \cdot n$ as the primary diagnostic tool for classifying line–plane relationships.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Three Relative Positions of a Line and a Plane:**
  In three-dimensional space, a line $L: P_0 + t v$ and a plane $\Pi: n \cdot X = d$ can relate in exactly three mutually exclusive ways:
  1. **Intersect at a single point:** The line pierces through the plane at exactly one point ($v \cdot n \neq 0$).
  2. **Strictly parallel (disjoint):** The line never touches the plane ($v \cdot n = 0$ and $P_0 \notin \Pi$).
  3. **Contained in the plane:** The line lies entirely within the plane ($v \cdot n = 0$ and $P_0 \in \Pi$).
- **The Role of the Dot Product $v \cdot n$:**
  - $n$ is perpendicular to the plane.
  - If $v \cdot n \neq 0$, the line has a non-zero velocity component along the normal direction, meaning parameter $t$ will eventually take the line across the plane's threshold at exactly one moment.
  - If $v \cdot n = 0$, the line runs perpendicular to the normal vector, which means the line's direction is completely parallel to the flat surface of the plane. Whether it touches depends only on where its base point $P_0$ is located.

---

## 4. Step-by-Step Solution

### Step 1: Extract Vectors

From the given descriptions:
- **Line $L$:**
  - Base point: $P_0 = (1, 1, 0)$
  - Direction vector: $v = (1, -1, 0)$
- **Plane $\Pi$ ($1x + 1y + 1z = 2$):**
  - Normal vector: $n = (1, 1, 1)$

---

### Step 2: Compute the Dot Product $v \cdot n$

Compute the scalar dot product between the direction vector of the line and the normal vector of the plane:

$$
v \cdot n = (1)(1) + (-1)(1) + (0)(1) = 1 - 1 + 0 = 0
$$

Because $v \cdot n = 0$, the direction vector $v$ is orthogonal to the normal vector $n$.
Since $n$ is perpendicular to plane $\Pi$, any vector orthogonal to $n$ is **parallel to the plane**.
Therefore, line $L$ is **parallel** to plane $\Pi$. It cannot pierce the plane at a single point.

---

### Step 3: Test Whether the Line Lies in the Plane or Is Disjoint

Since the line is parallel to the plane, it either lies completely inside the plane or never meets it.
To distinguish between these two cases, test whether the base point $P_0(1, 1, 0)$ lies in plane $\Pi$:

Substitute $(x, y, z) = (1, 1, 0)$ into the plane equation $x + y + z = 2$:

$$
1 + 1 + 0 = 2
$$

The equation evaluates to $2 = 2$, which is an exact equality.
Because the anchor point $P_0$ lies in the plane, and the direction vector $v$ is parallel to the plane, **every point on line $L$ lies within plane $\Pi$**:

$$
L \subset \Pi
$$

The line lies completely in the plane.

---

### Step 4: Explain the Role of the Dot Product $v \cdot n$

When we substitute the parametric equations of the line $X(t) = P_0 + t v$ into the plane equation $n \cdot X = d$, we obtain:

$$
n \cdot (P_0 + t v) = d \iff (v \cdot n) t + (n \cdot P_0) = d \iff (v \cdot n) t = d - n \cdot P_0
$$

This is a single linear algebraic equation in the parameter $t$. The dot product $v \cdot n$ acts as the **leading coefficient** of the unknown $t$:
1. **If $v \cdot n \neq 0$:**
   We can divide by $v \cdot n$ to solve uniquely for $t = \frac{d - n \cdot P_0}{v \cdot n}$. This yields **exactly one intersection point**.
2. **If $v \cdot n = 0$:**
   The equation reduces to $0 \cdot t = d - n \cdot P_0$.
   - If $d - n \cdot P_0 \neq 0$, the equation $0 = \text{non-zero}$ is a contradiction (no solution; the line is **strictly parallel**).
   - If $d - n \cdot P_0 = 0$, the equation $0 = 0$ is an identity (satisfied for every $t \in \mathbb{R}$; the line **lies entirely in the plane**).

Thus, $v \cdot n$ is the master switch that determines whether an intersection point exists or whether parallelism occurs.

---

## 5. Final Answer & Conclusion

- **Relative Position:** The line $L$ **lies entirely in the plane $\Pi$** ($L \subset \Pi$).
- **Role of the Dot Product:**
  The dot product $v \cdot n$ measures whether the line has any velocity component entering or leaving the plane. Here, $v \cdot n = 0$ indicates that the line's direction is parallel to the plane. Testing the base point $P_0$ shows it satisfies the plane equation, confirming that the entire line is contained in the plane.

---

## 6. Quick Verification

Substitute the general parametric formula $(x, y, z) = (1 + t, 1 - t, 0)$ into the plane equation $x + y + z = 2$ for an arbitrary parameter $t$:

$$
(1 + t) + (1 - t) + 0 = 1 + t + 1 - t + 0 = 2
$$

The variable $t$ cancels out entirely, yielding $2 = 2$ identically for all $t \in \mathbb{R}$.
Test specific parameter values:
- For $t = 0$: $(1, 1, 0) \implies 1 + 1 + 0 = 2$. (Holds)
- For $t = 1$: $(2, 0, 0) \implies 2 + 0 + 0 = 2$. (Holds)
- For $t = -3$: $(-2, 4, 0) \implies -2 + 4 + 0 = 2$. (Holds)
Every single point on the line unconditionally satisfies the plane equation.

---

## 7. Common Mistakes to Avoid

1. **Concluding "Parallel with No Intersection" as Soon as $v \cdot n = 0$:**
   Stopping at $v \cdot n = 0$ and calling the line parallel without testing whether the line is actually embedded inside the plane.
2. **Confusing Line Direction with Plane Normal:**
   Thinking that $v$ must be parallel to $n$ for the line to lie in the plane. In reality, $v$ must be **perpendicular** to $n$ ($v \cdot n = 0$) to lie in the plane.
3. **Algebraic Slips in $v \cdot n$:**
   Miscalculating $(1)(1) + (-1)(1)$ as $1 + 1 = 2$, which would falsely lead to a claim of a single intersection point.

---

## 8. How I Would Explain This in Class

> "Imagine plane $\Pi$ is the surface of a frozen lake and vector $n$ is a flagpole standing straight up out of the ice. If you throw a spear in direction $v$ such that $v \cdot n = 0$, the spear flies at a 90-degree angle to the flagpole—meaning it travels completely parallel to the ice without gaining or losing height. To find out if the spear is flying through the air or sliding along the ice, you just check your starting height: since your hand was at $(1, 1, 0)$, which is already on the ice, the spear slides entirely on the frozen surface."

