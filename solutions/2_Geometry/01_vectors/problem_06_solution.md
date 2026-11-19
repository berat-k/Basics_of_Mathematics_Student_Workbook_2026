# Problem 06: Projection and Perpendicular Component

## 1. The Original Problem

Find the projection of $u = (4, 2)$ onto the direction $v = (1, 1)$. Then compute

$$
r = u - \text{proj}_v(u)
$$

and verify that $r \cdot v = 0$. Explain this result geometrically.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the orthogonal projection vector $\text{proj}_v(u)$ of vector $u$ onto the line determined by vector $v$.
2. Compute the residual vector $r = u - \text{proj}_v(u)$ (the orthogonal complement / rejection).
3. Algebraically verify that the residual vector $r$ is orthogonal to the direction vector $v$ by showing $r \cdot v = 0$.
4. Provide a geometric interpretation of this orthogonal decomposition as a right triangle split.

---

## 3. Before Calculating: What Idea Do We Need?

- **Vector Projection Formula:**
  The orthogonal projection of vector $u$ onto a non-zero vector $v$ is the vector parallel to $v$ given by:

$$
\text{proj}_v(u) = \left( \frac{u \cdot v}{\|v\|^2} \right) v = \left( \frac{u \cdot v}{v \cdot v} \right) v
$$

  The scalar factor $\frac{u \cdot v}{v \cdot v}$ determines how many multiples of $v$ make up the projection.
- **Orthogonal Decomposition:**
  Every vector $u$ can be decomposed uniquely relative to a direction $v$ as:

$$
u = u_{\parallel} + u_{\perp}
$$

  where $u_{\parallel} = \text{proj}_v(u)$ is parallel to $v$, and $u_{\perp} = r = u - \text{proj}_v(u)$ is perpendicular to $v$.
- **Geometric Role of $r$:**
  Vector $r$ represents the perpendicular distance vector dropping from the tip of $u$ down to the line spanned by $v$, forming the altitude of a right triangle.

---

## 4. Step-by-Step Solution

### Step 1: Compute the Dot Products $u \cdot v$ and $v \cdot v$

For $u = (4, 2)$ and $v = (1, 1)$:

1. **Dot product $u \cdot v$:**

$$
u \cdot v = (4)(1) + (2)(1) = 4 + 2 = 6
$$

2. **Squared norm $v \cdot v = \|v\|^2$:**

$$
v \cdot v = 1^2 + 1^2 = 1 + 1 = 2
$$

### Step 2: Compute the Projection Vector $\text{proj}_v(u)$

Apply the projection formula:

$$
\text{proj}_v(u) = \left( \frac{u \cdot v}{v \cdot v} \right) v = \left( \frac{6}{2} \right) (1, 1) = 3 (1, 1) = (3, 3)
$$

The projection vector is $(3, 3)$.

---

### Step 3: Compute the Residual Vector $r$

Subtract the projection vector from the original vector $u$:

$$
r = u - \text{proj}_v(u) = (4, 2) - (3, 3) = (4 - 3, 2 - 3) = (1, -1)
$$

---

### Step 4: Verify That $r \cdot v = 0$

Take the dot product of $r = (1, -1)$ with $v = (1, 1)$:

$$
r \cdot v = (1)(1) + (-1)(1) = 1 - 1 = 0
$$

Because the dot product is identically zero, $r$ is verified to be perpendicular to $v$:

$$
r \perp v
$$

---

### Step 5: Geometric Interpretation

Geometrically, this computation splits $u$ into two orthogonal components:
1. **Parallel component ($\text{proj}_v(u) = (3, 3)$):**
   This is the "shadow" cast by vector $u$ onto the line $y = x$ spanned by $v = (1, 1)$ under orthogonal light rays. It captures entirely how much $u$ points in the direction of $v$.
2. **Perpendicular component ($r = (1, -1)$):**
   This vector connects the tip of the shadow $(3, 3)$ to the actual tip of $u = (4, 2)$. Because the light rays are perpendicular to the line, this connecting segment must meet the line at a right angle ($90^\circ$).
3. **Right Triangle Geometry:**
   Together, the vectors $\text{proj}_v(u)$, $r$, and $u$ form a right-angled triangle where:
   - The hypotenuse is $u$.
   - The legs are $\text{proj}_v(u)$ and $r$.
   - The Pythagorean theorem holds: $\|\text{proj}_v(u)\|^2 + \|r\|^2 = \|(3, 3)\|^2 + \|(1, -1)\|^2 = 18 + 2 = 20 = \|(4, 2)\|^2$.

---

## 5. Final Answer & Conclusion

- **Projection of $u$ onto $v$:**

$$
\text{proj}_v(u) = (3, 3)
$$

- **Residual Vector:**

$$
r = (1, -1)
$$

- **Verification:** $r \cdot v = (1)(1) + (-1)(1) = 0$.
- **Geometric Conclusion:** The vector $u = (4, 2)$ is decomposed into two mutually perpendicular vectors: $(3, 3)$ along the line of $v$, and $(1, -1)$ perpendicular to $v$.

---

## 6. Quick Verification

Verify the vector sum:

$$
\text{proj}_v(u) + r = (3, 3) + (1, -1) = (3 + 1, 3 - 1) = (4, 2) = u
$$

Verify Pythagorean theorem:
- $\|u\|^2 = 4^2 + 2^2 = 16 + 4 = 20$
- $\|\text{proj}_v(u)\|^2 = 3^2 + 3^2 = 9 + 9 = 18$
- $\|r\|^2 = 1^2 + (-1)^2 = 1 + 1 = 2$
- $18 + 2 = 20$.
Both conditions hold perfectly.

---

## 7. Common Mistakes to Avoid

1. **Dividing by $\|v\|$ Instead of $\|v\|^2$:**
   Writing $\frac{u \cdot v}{\|v\|} v$. The scalar $\frac{u \cdot v}{\|v\|}$ is the *scalar component* (length with sign); to get a vector of the correct magnitude, one must divide by $\|v\|^2$.
2. **Using $u$ Instead of $v$ in the Denominator:**
   Writing $\frac{u \cdot v}{\|u\|^2} v$, which projects onto $u$ instead of projecting onto $v$.
3. **Subtracting in the Wrong Order:**
   Computing $r = \text{proj}_v(u) - u = (-1, 1)$. While $(-1, 1)$ is also perpendicular to $v$, by definition $r = u - \text{proj}_v(u)$ so that $\text{proj}_v(u) + r = u$.

---

## 8. How I Would Explain This in Class

> "Imagine shining a flashlight straight down onto the diagonal line $y = x$: the shadow that vector $(4, 2)$ casts along that line is its projection, $(3, 3)$. The leftover vector $(1, -1)$ is simply the vertical dropped pin that connects the tip of that shadow back up to the arrow tip. Because the flashlight beam shines at a perfect right angle to the line, that dropped pin must dot to zero with the line."

