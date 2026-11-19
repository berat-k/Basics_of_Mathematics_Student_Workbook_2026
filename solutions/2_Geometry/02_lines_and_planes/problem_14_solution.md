# Problem 14: Contrast: Intersection and Parallelism

## 1. The Original Problem

From the point $P = (0, 0, 1)$, two lines are drawn with direction vectors

$$
v_1 = (2, 1, -1), \qquad v_2 = (2, 1, 0).
$$

For each line, analyze its position relative to the plane $z = 0$.

For the line that intersects the plane, find the intersection point. For the other line, explain how you can recognize parallelism without solving an equation.

---

## 2. What Are We Trying to Find?

We need to:
1. Write the parametric equations of the two lines $L_1$ and $L_2$ sharing the common initial point $P(0, 0, 1)$.
2. Analyze the position of line $L_1$ relative to the plane $z = 0$ (the $xy$-coordinate plane).
3. Compute the exact intersection point where line $L_1$ meets the plane $z = 0$.
4. Analyze the position of line $L_2$ relative to the plane $z = 0$.
5. Explain how parallelism for line $L_2$ can be recognized immediately by inspection of coordinates without setting up or solving any algebraic equation.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Plane $z = 0$ (The $xy$-Plane):**
  The equation $z = 0$ describes the horizontal coordinate floor in $\mathbb{R}^3$. Its normal vector is the vertical unit vector:

$$
n = (0, 0, 1)
$$

- **Physical Meaning of the $z$-Component in a Direction Vector:**
  For any line $X(t) = P + t v$, the rate of change of height (vertical motion) with respect to parameter $t$ is governed exclusively by the third coordinate $v_z$:

$$
z(t) = z_P + t v_z
$$

  - If $v_z \neq 0$, the line has vertical velocity, meaning it climbs or descends across all height levels, guaranteeing it must cross the horizontal floor $z = 0$ at some value of $t$.
  - If $v_z = 0$, the line has zero vertical velocity, meaning its height remains permanently constant: $z(t) = z_P$ for all $t$. If $z_P \neq 0$, the line is strictly parallel to the floor $z = 0$ and never meets it.

---

## 4. Step-by-Step Solution

### Step 1: Set Up the Equations of Both Lines

Both lines start from $P(0, 0, 1)$:

1. **Line $L_1$ with direction $v_1 = (2, 1, -1)$:**

$$
L_1: (x, y, z) = (0, 0, 1) + t(2, 1, -1) \iff \begin{cases} x = 2t \\\\ y = t \\\\ z = 1 - t \end{cases}
$$

2. **Line $L_2$ with direction $v_2 = (2, 1, 0)$:**

$$
L_2: (x, y, z) = (0, 0, 1) + s(2, 1, 0) \iff \begin{cases} x = 2s \\\\ y = s \\\\ z = 1 \end{cases}
$$

---

### Step 2: Analyze Line $L_1$ and Find Its Intersection Point

1. **Relative Position Analysis:**
   - Normal vector to the plane $z = 0$ is $n = (0, 0, 1)$.
   - Dot product with direction $v_1$:

$$
v_1 \cdot n = (2)(0) + (1)(0) + (-1)(1) = -1 \neq 0
$$

   Since $v_1 \cdot n \neq 0$, line $L_1$ is not parallel to the plane; it **intersects the plane at exactly one point**.

2. **Find the Intersection Point:**
   Set the $z$-coordinate of line $L_1$ equal to $0$:

$$
z = 1 - t = 0 \implies t = 1
$$

   Substitute $t = 1$ into the $x$ and $y$ equations of line $L_1$:
   - $x = 2(1) = 2$
   - $y = 1$
   - $z = 1 - 1 = 0$

   Therefore, the intersection point is:

$$
I = (2, 1, 0)
$$

---

### Step 3: Analyze Line $L_2$ and Explain Parallelism Without Calculation

1. **Relative Position Analysis:**
   Compute the dot product with the plane normal $n = (0, 0, 1)$:

$$
v_2 \cdot n = (2)(0) + (1)(0) + (0)(1) = 0
$$

   Because $v_2 \cdot n = 0$, the line is parallel to the plane.
   The base point $P(0, 0, 1)$ has $z = 1 \neq 0$, so $P$ does not lie on the plane.
   Therefore, line $L_2$ is **strictly parallel** to the plane $z = 0$ (they never intersect: $L_2 \cap \Pi = \emptyset$).

2. **Recognizing Parallelism Without Solving an Equation:**
   - The plane is the horizontal coordinate plane $z = 0$ (every point on the plane has height $0$).
   - The direction vector $v_2 = (2, 1, \mathbf{0})$ has a **$z$-component of zero** ($v_z = 0$).
   - This means that traveling along line $L_2$ produces horizontal movement in $x$ and $y$, but causes **zero change in height** ($\Delta z = 0$).
   - Since the line originates at height $z = 1$, every single point on line $L_2$ remains fixed at altitude $z = 1$ for all parameter values:

$$
z(s) = 1 + 0s \equiv 1 \quad \text{for all } s \in \mathbb{R}
$$

   - Because $1 \neq 0$ permanently, the line floats at a constant altitude of $1$ unit above the floor $z = 0$, making it parallel by inspection without setting up an equation.

---

## 5. Final Answer & Conclusion

- **Line $L_1$:**
  - Relative position: **Intersects the plane at exactly one point**.
  - Intersection point:

$$
I = (2, 1, 0)
$$

- **Line $L_2$:**
  - Relative position: **Strictly parallel to the plane** (no common points).
  - Inspection explanation: The direction vector $v_2 = (2, 1, 0)$ has $v_z = 0$, meaning the line never changes height and remains permanently fixed at elevation $z = 1$, strictly parallel to the floor $z = 0$.

---

## 6. Quick Verification

Verify both points in their respective line descriptions:
1. For line $L_1$ at $t = 1$:
   $(0, 0, 1) + 1(2, 1, -1) = (2, 1, 0)$.
   The $z$-coordinate is $0$, verifying that the intersection point $(2, 1, 0)$ lies in the plane $z = 0$.
2. For line $L_2$:
   The distance from any point on $L_2$ to the plane $z = 0$ is:

$$
d((2s, s, 1), \Pi) = \frac{|1 - 0|}{\sqrt{0^2 + 0^2 + 1^2}} = \frac{1}{1} = 1
$$

   Because the distance is a constant $1$ for all $s$, the line never approaches or recedes from the plane, confirming strict parallelism.

---

## 7. Common Mistakes to Avoid

1. **Solving Unnecessary Equations for Line 2:**
   Writing $1 + 0s = 0 \implies 0s = -1$ and going through algebraic contradiction steps when the prompt explicitly asks to explain how parallelism can be recognized *without* solving an equation.
2. **Missing the Geometric Interpretation of $z = 0$:**
   Treating $z = 0$ as an abstract algebraic formula rather than recognizing it simply as the horizontal ground plane of the coordinate system.
3. **Sign Errors with $v_1$:**
   Writing $z = 1 + t$ instead of $z = 1 - t$ for line $L_1$, which would yield $t = -1$ and an incorrect intersection point $(-2, -1, 0)$.

---

## 8. How I Would Explain This in Class

> "Imagine you are standing on the 1st floor of a building with a laser pointer at height $z = 1$, and the plane $z = 0$ is the ground floor. If you aim your laser pointer downwards with direction $(2, 1, -1)$, the negative $z$-step guarantees the beam will dive down and strike the ground floor at coordinate $(2, 1, 0)$. But if you aim with direction $(2, 1, 0)$, the zero in the $z$-slot means the beam shines perfectly level with the horizon, forever staying at height 1 without ever touching the floor."

