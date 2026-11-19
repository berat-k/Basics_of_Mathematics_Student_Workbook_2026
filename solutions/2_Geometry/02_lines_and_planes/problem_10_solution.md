# Problem 10: Projection of a Point onto a Plane

## 1. The Original Problem

Find the orthogonal projection of $P = (2, 1, 3)$ onto the plane $x + y + z = 3$, and then find the reflection of $P$ across this plane. Check that the midpoint of the segment joining the point and its reflection lies on the plane.

---

## 2. What Are We Trying to Find?

We need to:
1. Construct the normal line passing through point $P(2, 1, 3)$ perpendicular to the plane $\Pi: x + y + z = 3$.
2. Compute the coordinates of the orthogonal projection point $P'$ (the foot of the perpendicular).
3. Compute the coordinates of the reflection point $P''$ of $P$ across the plane.
4. Calculate the midpoint $M$ of the line segment $[P P'']$ connecting the original point and its reflection.
5. Verify that the midpoint $M$ satisfies the plane equation, confirming that $M = P'$.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Normal Line Through a Point:**
  The normal vector to plane $\Pi: x + y + z = 3$ is $n = (1, 1, 1)$.
  The line $\mathcal{N}$ passing through $P(2, 1, 3)$ perpendicular to $\Pi$ is parameterized by:

$$
X(t) = P + t n = (2 + t, 1 + t, 3 + t)
$$

- **Orthogonal Projection ($P'$):**
  The orthogonal projection $P'$ is the intersection point of the normal line $\mathcal{N}$ with the plane $\Pi$.
- **Geometric Reflection ($P''$):**
  The reflection $P''$ across the plane is located twice as far along the normal line as the projection $P'$:

$$
P'' = P + 2(P' - P) = 2P' - P
$$

  In terms of the parameter $t$, if $P'$ occurs at $t = t_0$, then $P''$ occurs at $t = 2t_0$.
- **Midpoint Property:**
  By definition of symmetric reflection across a mirror plane, the midpoint of the segment joining an object point and its reflection image must lie exactly on the mirror plane itself:

$$
M = \frac{P + P''}{2} = P' \in \Pi
$$

---

## 4. Step-by-Step Solution

### Step 1: Set Up the Normal Line

The plane has equation:

$$
x + y + z = 3 \implies n = (1, 1, 1)
$$

The line passing through $P(2, 1, 3)$ in direction $n$ is:

$$
\begin{cases}
x = 2 + t, \\\\
y = 1 + t, \\\\
z = 3 + t
\end{cases}
$$

### Step 2: Find the Orthogonal Projection $P'$

Substitute the parametric line equations into the plane equation $x + y + z = 3$:

$$
(2 + t) + (1 + t) + (3 + t) = 3
$$

Combine like terms:

$$
3t + 6 = 3 \implies 3t = 3 - 6 \implies 3t = -3 \implies t = -1
$$

Now substitute $t = -1$ into the normal line coordinates to find $P'$:

$$
P' = (2 + (-1), 1 + (-1), 3 + (-1)) = (1, 0, 2)
$$

The orthogonal projection of $P$ onto the plane is $P'(1, 0, 2)$.

---

### Step 3: Find the Reflection Point $P''$

Since the projection occurs at $t = -1$, the reflection across the plane occurs by traveling twice that parameter distance:

$$
t_{\text{refl}} = 2(-1) = -2
$$

Substitute $t = -2$ into the line equations:

$$
P'' = (2 + (-2), 1 + (-2), 3 + (-2)) = (0, -1, 1)
$$

Equivalently, using the vector formula $P'' = 2P' - P$:

$$
P'' = 2(1, 0, 2) - (2, 1, 3) = (2, 0, 4) - (2, 1, 3) = (0, -1, 1)
$$

The reflection of $P$ across the plane is $P''(0, -1, 1)$.

---

### Step 4: Check That the Midpoint Lies on the Plane

Compute the midpoint $M$ of the segment connecting $P(2, 1, 3)$ and $P''(0, -1, 1)$:

$$
M = \frac{P + P''}{2} = \left( \frac{2 + 0}{2}, \frac{1 + (-1)}{2}, \frac{3 + 1}{2} \right) = \left( \frac{2}{2}, \frac{0}{2}, \frac{4}{2} \right) = (1, 0, 2)
$$

Notice that $M = (1, 0, 2)$, which is identically the projection point $P'$.

Now substitute $M(1, 0, 2)$ into the plane equation $x + y + z = 3$:

$$
1 + 0 + 2 = 3
$$

Matches $3 = 3$. The midpoint $M$ lies on the plane.

---

## 5. Final Answer & Conclusion

- **Orthogonal Projection:**

$$
P' = (1, 0, 2)
$$

- **Reflected Point:**

$$
P'' = (0, -1, 1)
$$

- **Midpoint Verification:**
  $M = \frac{P + P''}{2} = (1, 0, 2) = P'$.
  Substituting $M$ into $x + y + z = 3$ yields $1 + 0 + 2 = 3$, confirming that the midpoint lies squarely on the plane.

---

## 6. Quick Verification

1. **Verify Distance Equality:**
  - Distance from $P$ to $P'$: $\|P - P'\| = \|(2-1, 1-0, 3-2)\| = \|(1, 1, 1)\| = \sqrt{1^2 + 1^2 + 1^2} = \sqrt{3}$.
  - Distance from $P''$ to $P'$: $\|P'' - P'\| = \|(0-1, -1-0, 1-2)\| = \|(-1, -1, -1)\| = \sqrt{(-1)^2 + (-1)^2 + (-1)^2} = \sqrt{3}$.
  Both points are at the exact same distance $\sqrt{3}$ from the plane.

2. **Verify Perpendicularity:**
   The vector $\overrightarrow{P'' P} = P - P'' = (2, 2, 2) = 2(1, 1, 1) = 2n$.
   Because the segment connecting $P$ and $P''$ is parallel to the normal vector $n$, the reflection is strictly perpendicular to the plane.

---

## 7. Common Mistakes to Avoid

1. **Sign Errors When Solving for $t$:**
   Computing $3t + 6 = 3 \implies 3t = 9 \implies t = 3$. Remember that moving $+6$ to the other side gives $3 - 6 = -3$.
2. **Confusing Projection with Reflection:**
   Stopping at $P'(1, 0, 2)$ and forgetting to find the reflected point $P''(0, -1, 1)$.
3. **Midpoint Formula Errors:**
   Subtracting instead of adding when finding the midpoint ($P - P''$ instead of $\frac{P + P''}{2}$).

---

## 8. How I Would Explain This in Class

> "Imagine the plane $x + y + z = 3$ is a mirror hanging on a wall. To find where your eye at $P(2, 1, 3)$ looks into the mirror, you shoot a laser straight into the glass at a 90-degree angle; it hits the surface at $P'(1, 0, 2)$, which is your projection. If you keep traveling that exact same distance behind the glass, you reach your reflection image at $P''(0, -1, 1)$. Naturally, the glass sits right at the exact halfway midpoint between you and your reflection."
