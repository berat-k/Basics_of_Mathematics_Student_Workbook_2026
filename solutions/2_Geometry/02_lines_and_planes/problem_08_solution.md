# Problem 08: Intersection Point of a Line and a Plane

## 1. The Original Problem

Find the intersection point of

$$
(x, y, z) = (1, 0, 2) + t(1, 2, -1)
$$

with the plane $x + y + z = 4$. Check the result by substituting it into both descriptions.

---

## 2. What Are We Trying to Find?

We need to:
1. Formulate the coordinate parametric equations $x(t), y(t), z(t)$ of the line.
2. Substitute these parametric expressions into the linear Cartesian equation of the plane.
3. Solve the resulting single-variable linear equation for the parameter $t$.
4. Calculate the spatial coordinates of the unique intersection point $I$.
5. Verify the intersection point by checking that it satisfies both the line's parametric equation and the plane's equation.

---

## 3. Before Calculating: What Idea Do We Need?

- **Direct Substitution Method:**
  The most straightforward and reliable way to find where a line meets a plane is to substitute the line's parametric coordinates directly into the plane's equation:
  - If the line is $X(t) = P_0 + t v$ and the plane is $n \cdot X = d$, the intersection parameter $t^*$ is the solution to:

$$
n \cdot (P_0 + t v) = d
$$

- **Single Solution Guarantee:**
  Here, the line's direction is $v = (1, 2, -1)$ and the plane's normal is $n = (1, 1, 1)$.
  Their dot product is:

$$
v \cdot n = (1)(1) + (2)(1) + (-1)(1) = 1 + 2 - 1 = 2 \neq 0
$$

  Because $v \cdot n \neq 0$, the line is not parallel to the plane, guaranteeing **exactly one unique point of intersection**.

---

## 4. Step-by-Step Solution

### Step 1: Write the Parametric Equations of the Line

From $(x, y, z) = (1, 0, 2) + t(1, 2, -1)$, express the coordinates in terms of $t$:

$$
\begin{cases}
x = 1 + t, \\\\
y = 0 + 2t = 2t, \\\\
z = 2 - t
\end{cases}
$$

### Step 2: Substitute into the Plane Equation

The equation of the plane is:

$$
x + y + z = 4
$$

Substitute the parametric expressions for $x, y,$ and $z$:

$$
(1 + t) + (2t) + (2 - t) = 4
$$

---

### Step 3: Solve for the Parameter $t$

Combine like terms on the left-hand side:

$$
(t + 2t - t) + (1 + 2) = 4
$$

$$
2t + 3 = 4
$$

Subtract $3$ from both sides:

$$
2t = 4 - 3 \implies 2t = 1 \implies t = \frac{1}{2} = 0.5
$$

The line pierces the plane at parameter value $t = 1/2$.

---

### Step 4: Compute the Intersection Point

Substitute $t = \frac{1}{2}$ back into the line's parametric coordinate equations:

1. **$x$-coordinate:**

$$
x = 1 + \frac{1}{2} = \frac{3}{2} = 1.5
$$

2. **$y$-coordinate:**

$$
y = 2\left(\frac{1}{2}\right) = 1
$$

3. **$z$-coordinate:**

$$
z = 2 - \frac{1}{2} = \frac{3}{2} = 1.5
$$

Therefore, the point of intersection is:

$$
I = \left( \frac{3}{2}, 1, \frac{3}{2} \right) = (1.5, 1, 1.5)
$$

---

### Step 5: Check the Result in Both Descriptions

1. **Check in the Plane Equation:**
   Substitute $x = 3/2, y = 1, z = 3/2$ into $x + y + z = 4$:

$$
x + y + z = \frac{3}{2} + 1 + \frac{3}{2} = \frac{3 + 3}{2} + 1 = 3 + 1 = 4
$$

   Matches the right-hand side ($4 = 4$). The point lies on the plane.

2. **Check in the Line Description:**
   Verify that point $I$ is produced by the line at $t = 1/2$:

$$
(1, 0, 2) + \frac{1}{2} (1, 2, -1) = (1 + 0.5, 0 + 1, 2 - 0.5) = (1.5, 1, 1.5) = I
$$

   Matches the calculated coordinates. The point lies on the line.

Both checks succeed completely.

---

## 5. Final Answer & Conclusion

- **Intersection Parameter:**

$$
t = \frac{1}{2}
$$

- **Intersection Point:**

$$
I = \left( \frac{3}{2}, 1, \frac{3}{2} \right) = (1.5, 1, 1.5)
$$

- **Verification:**
  - Plane: $1.5 + 1 + 1.5 = 4$ (Satisfied)
  - Line: $(1, 0, 2) + 0.5(1, 2, -1) = (1.5, 1, 1.5)$ (Satisfied)

---

## 6. Quick Verification

Verify using the general projection formula for line-plane intersection:

$$
t = \frac{d - n \cdot P_0}{n \cdot v}
$$

where $P_0 = (1, 0, 2)$, $v = (1, 2, -1)$, $n = (1, 1, 1)$, and $d = 4$:
- $n \cdot P_0 = (1)(1) + (1)(0) + (1)(2) = 1 + 0 + 2 = 3$
- $n \cdot v = (1)(1) + (1)(2) + (1)(-1) = 1 + 2 - 1 = 2$
- $t = \frac{4 - 3}{2} = \frac{1}{2}$

This direct formula reproduces $t = 1/2$ instantly, verifying the algebraic steps.

---

## 7. Common Mistakes to Avoid

1. **Sign Slips in Expanding $z$:**
   Writing $z = 2 + t$ instead of $z = 2 - t$, which would lead to $4t + 3 = 4 \implies t = 1/4$.
2. **Forgetting to Substitute Back to Find Coordinates:**
   Stopping at $t = 1/2$ and reporting the scalar parameter as the final answer instead of providing the 3D point $(3/2, 1, 3/2)$.
3. **Checking Only One Description:**
   Checking only the plane equation. An arithmetic mistake in evaluating $t$ could produce a point on the plane that does not actually belong to the line.

---

## 8. How I Would Explain This in Class

> "Finding where a line hits a plane is like calculating the exact second a laser beam strikes a wall: the parametric equations give the laser's coordinates at any second $t$, and the plane equation represents the surface of the wall. Plugging the laser's coordinates into the wall's equation gives one simple linear equation, which tells us that at exactly $t = 0.5$ seconds, the laser strikes the wall at coordinate $(1.5, 1, 1.5)$."

