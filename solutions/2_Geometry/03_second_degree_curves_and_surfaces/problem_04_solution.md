# Problem 04: Parabola

## 1. The Original Problem

For

$$
y^2 = 12x,
$$

identify the vertex, axis of symmetry, and opening direction. Find points on the parabola for $x = 3$ and use them to make a sketch.

---

## 2. What Are We Trying to Find?

We need to:
1. Identify the coordinates of the vertex $V$.
2. Determine the equation of the axis of symmetry.
3. Determine the direction in which the parabola opens.
4. Calculate the corresponding $y$-values when $x = 3$ to find two points on the parabola.
5. Provide a clear structural sketch layout based on the vertex and calculated points.

---

## 3. Before Calculating: What Idea Do We Need?

- **Canonical Form of a Horizontal Parabola:**
  The standard equation of a parabola with vertex at the origin $V(0, 0)$ opening horizontally is:

$$
y^2 = 2px \quad (\text{or } y^2 = 4fx)
$$

  where:
  - $p > 0$ is the geometric parameter (focal parameter),
  - $f = p/2$ is the focal distance (distance from vertex to focus).
- **Axis of Symmetry:**
  Notice that replacing $y$ with $-y$ leaves the equation invariant:

$$
(-y)^2 = y^2 = 12x
$$

  This algebraic even-power property proves that the curve is perfectly symmetric across the line $y = 0$ (the $x$-axis).
- **Domain and Opening Direction:**
  Since the square of any real number is non-negative ($y^2 \ge 0$), we must have:

$$
12x \ge 0 \implies x \ge 0
$$

  The domain is $x \in [0, \infty)$, meaning all points on the curve have non-negative $x$-coordinates. Therefore, the parabola opens towards the **positive $x$-direction (to the right)**.

---

## 4. Step-by-Step Solution

### Step 1: Identify the Vertex

In the equation $y^2 = 12x$, there are no shifting terms (no $(y - k)^2$ or $(x - h)$).
When $x = 0$, $y^2 = 0 \implies y = 0$.
Thus, the vertex is at the origin:

$$
V = (0, 0)
$$

---

### Step 2: Determine the Axis of Symmetry

Substitute $-y$ for $y$:

$$
(-y)^2 = y^2 = 12x
$$

Because the equation is unchanged when $y$ is negated, the curve is mirror-symmetric across the line:

$$
y = 0 \quad (\text{the } x\text{-axis})
$$

---

### Step 3: Determine the Opening Direction

For any real point $(x, y)$ on the curve:

$$
y^2 \ge 0 \implies 12x \ge 0 \implies x \ge 0
$$

The curve exists only for $x \ge 0$ and extends towards $+\infty$ as $|y|$ grows.
Therefore, the parabola **opens to the right (along the positive $x$-axis)**.

Comparing with $y^2 = 2px$:
- $2p = 12 \implies p = 6$.
- Focal distance: $f = p/2 = 3$.
- Focus: $F = (3, 0)$.
- Directrix line: $x = -3$.

---

### Step 4: Find Points for $x = 3$

Substitute $x = 3$ into $y^2 = 12x$:

$$
y^2 = 12(3) = 36
$$

Take the square root of both sides:

$$
y = \pm \sqrt{36} = \pm 6
$$

Thus, the two points on the parabola corresponding to $x = 3$ are:

$$
P_1 = (3, 6) \quad \text{and} \quad P_2 = (3, -6)
$$

*(Note: Because the focus is at $(3, 0)$, the chord connecting $(3, 6)$ and $(3, -6)$ is the **latus rectum**, having length $6 - (-6) = 12 = 2p$.)*

---

### Step 5: Qualitative Sketch Layout

- **Vertex:** Sharpest turning point at the origin $(0, 0)$.
- **Axis of Symmetry:** The horizontal line $y = 0$.
- **Points on Curve:**
  - Passes through $(0, 0)$.
  - For $x = 3$, it passes through $(3, 6)$ and $(3, -6)$.
  - For $x = 12$, $y^2 = 144 \implies y = \pm 12$, passing through $(12, 12)$ and $(12, -12)$.
- **Opening:** Opens to the right, widening continuously without bound as $x \to \infty$.

---

## 5. Final Answer & Conclusion

- **Vertex:**

$$
V = (0, 0)
$$

- **Axis of Symmetry:**

$$
y = 0 \quad (\text{the } x\text{-axis})
$$

- **Opening Direction:** To the **right** (along the positive $x$-axis, $x \ge 0$).
- **Points for $x = 3$:**

$$
(3, 6) \quad \text{and} \quad (3, -6)
$$

- **Focal Features:** Focus at $(3, 0)$ and directrix at $x = -3$.

---

## 6. Quick Verification

Verify the geometric definition of a parabola: every point on the parabola is equidistant from the focus $F(3, 0)$ and the directrix line $x = -3$.
Test point $P_1(3, 6)$:
- Distance from $P_1(3, 6)$ to focus $F(3, 0)$:

$$
d(P_1, F) = \sqrt{(3 - 3)^2 + (6 - 0)^2} = \sqrt{0 + 36} = 6
$$

- Distance from $P_1(3, 6)$ to vertical directrix line $x = -3$:

$$
d(P_1, \text{directrix}) = |x - (-3)| = |3 + 3| = 6
$$

Since $d(P_1, F) = d(P_1, \text{directrix}) = 6$, the point satisfies the fundamental geometric definition of a parabola.

---

## 7. Common Mistakes to Avoid

1. **Confusing Horizontal and Vertical Parabolas:**
   Thinking $y^2 = 12x$ is a standard upward-opening high school parabola $y = 12x^2$. Here, $y$ is squared, making the parabola horizontal.
2. **Missing the Negative Root:**
   Writing only $y = 6$ for $x = 3$. Because $y^2 = 36$, both $y = +6$ and $y = -6$ are valid solutions due to the vertical symmetry across $y = 0$.
3. **Claiming the Parabola Opens in Both Directions:**
   Confusing the two symmetric branches with two opening directions. The curve has one opening direction: towards positive $x$.

---

## 8. How I Would Explain This in Class

> "When you look at $y^2 = 12x$, notice that $y$ has the square and $x$ is naked. That tells you immediately that this parabola lies sideways on the floor. Because $y^2$ can never be a negative number, $12x$ must be positive, which means the curve has to open toward the positive right-hand side. Plugging in $x = 3$ gives $y^2 = 36$, meaning the curve passes through $(3, 6)$ and $(3, -6)$—a full 12 units wide right above and below its focus."

