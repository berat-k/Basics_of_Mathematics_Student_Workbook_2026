# Problem 06: Angle Between Planes

## 1. The Original Problem

Given

$$
\Pi_1: x + y + z = 1, \qquad \Pi_2: x - y = 2.
$$

First use the normal vectors to decide whether the planes are parallel. If not, compute the angle between them and explain why the normal vectors alone are enough for this calculation.

---

## 2. What Are We Trying to Find?

We need to:
1. Extract the normal vectors $n_1$ and $n_2$ directly from the equations of planes $\Pi_1$ and $\Pi_2$.
2. Test whether the planes are parallel by checking if their normal vectors are proportional.
3. Compute the dihedral angle $\alpha$ between the two planes.
4. Explain conceptually why calculating the angle between two infinite 2D planes reduces completely to calculating the angle between their 1D normal vectors.

---

## 3. Before Calculating: What Idea Do We Need?

- **Normal Vectors from General Equations:**
  In a Cartesian plane equation $ax + by + cz = d$, the vector formed by the coefficients $n = (a, b, c)$ is perpendicular to the plane:
  - For $\Pi_1: 1x + 1y + 1z = 1 \implies n_1 = (1, 1, 1)$.
  - For $\Pi_2: 1x - 1y + 0z = 2 \implies n_2 = (1, -1, 0)$.
- **Parallelism Criterion for Planes:**
  Two planes are parallel if and only if their normal lines point in the same (or opposite) direction:

$$
\Pi_1 \parallel \Pi_2 \iff n_1 = k n_2 \quad \text{for some } k \neq 0
$$

- **Angle Between Two Planes (Dihedral Angle):**
  By convention, the angle $\alpha$ between two planes is the acute angle ($\alpha \in [0, \pi/2]$) between their normal lines:

$$
\cos \alpha = \frac{|n_1 \cdot n_2|}{\|n_1\| \|n_2\|}
$$

- **Geometric Invariance Under Normal Rotation:**
  Erecting a perpendicular vector at every point of a plane rotates the plane rigidly by $90^\circ$. Because rigid rotations preserve all angles between geometric objects, the angle between two planes is identical to the angle between their normals.

---

## 4. Step-by-Step Solution

### Step 1: Extract Normal Vectors and Test for Parallelism

Read off the normal vectors from the coefficients:

$$
n_1 = (1, 1, 1), \qquad n_2 = (1, -1, 0)
$$

Check for proportionality ($n_1 = k n_2$):
- For the first coordinate: $1 = k(1) \implies k = 1$
- For the second coordinate: $1 = k(-1) \implies k = -1$
- For the third coordinate: $1 = k(0) \implies 1 = 0$ (Impossible)

Because the ratios of corresponding components are not equal ($1/1 \neq 1/(-1)$), the vectors $n_1$ and $n_2$ are not parallel.
Therefore, the planes $\Pi_1$ and $\Pi_2$ are **not parallel**; they must intersect along a line.

---

### Step 2: Compute the Angle Between the Planes

1. **Compute the dot product $n_1 \cdot n_2$:**

$$
n_1 \cdot n_2 = (1)(1) + (1)(-1) + (1)(0) = 1 - 1 + 0 = 0
$$

2. **Compute the norms $\|n_1\|$ and $\|n_2\|$:**

$$
\|n_1\| = \sqrt{1^2 + 1^2 + 1^2} = \sqrt{3}
$$

$$
\|n_2\| = \sqrt{1^2 + (-1)^2 + 0^2} = \sqrt{1 + 1 + 0} = \sqrt{2}
$$

3. **Compute $\cos \alpha$:**

$$
\cos \alpha = \frac{|n_1 \cdot n_2|}{\|n_1\| \|n_2\|} = \frac{|0|}{\sqrt{3} \cdot \sqrt{2}} = \frac{0}{\sqrt{6}} = 0
$$

4. **Determine the angle $\alpha$:**
   Since $\cos \alpha = 0$ on the interval $[0, \pi/2]$:

$$
\alpha = \frac{\pi}{2} \text{ radians} = 90^\circ
$$

The two planes are **perpendicular** (orthogonal).

---

### Step 3: Why Normal Vectors Alone Are Enough

1. **Dimensional Reduction:**
   A plane is a two-dimensional object defined by an infinite collection of direction vectors. Trying to measure the angle between two planes by comparing in-plane vectors directly would require finding the intersection line, constructing perpendicular vectors to the intersection line in each plane, and measuring the angle between them.
2. **The Rigid Normal Transformation:**
   Every plane has a unique 1D direction perpendicular to it—its normal line. Because the normal line is rigidly attached at a constant $90^\circ$ angle to the plane, tilting a plane by any angle $\alpha$ tilts its normal line by the exact same angle $\alpha$.
3. **Equivalence of Dihedral and Normal Angles:**
   If you view the two planes along their line of intersection (looking down the edge), the planes appear as two intersecting lines, and their normal vectors appear as two rays perpendicular to those lines. In this 2D cross-section, the angle between the two lines is geometrically equal to the angle between the two perpendiculars. Thus, the normal vectors alone contain all the directional information needed to determine the angle.

---

## 5. Final Answer & Conclusion

- **Normal Vectors:**

$$
n_1 = (1, 1, 1), \qquad n_2 = (1, -1, 0)
$$

- **Parallelism:** The planes are **not parallel** because $n_1$ and $n_2$ are not proportional.
- **Angle Between Planes:**

$$
\alpha = \frac{\pi}{2} \text{ rad} = 90^\circ \quad (\text{The planes are perpendicular})
$$

- **Conclusion:** Normal vectors alone are sufficient because each normal vector uniquely locks the 2D spatial tilt of its plane into a single 1D direction, preserving dihedral angles.

---

## 6. Quick Verification

Verify orthogonality using in-plane vectors:
- In plane $\Pi_1$, two vectors are $u_1 = (1, -1, 0)$ and $u_2 = (0, 1, -1)$ (since $n_1 \cdot u_1 = 0$ and $n_1 \cdot u_2 = 0$).
- Notice that $u_1 = (1, -1, 0)$ is precisely the normal vector $n_2$ of plane $\Pi_2$!
Because the normal vector of $\Pi_2$ lies completely inside plane $\Pi_1$, plane $\Pi_1$ must contain a direction that is perpendicular to plane $\Pi_2$.
By definition, if one plane contains a line perpendicular to another plane, the two planes are **perpendicular** ($90^\circ$). This confirms $\alpha = 90^\circ$.

---

## 7. Common Mistakes to Avoid

1. **Confusing Normal Vectors with In-Plane Vectors:**
   Treating $n = (a, b, c)$ as a direction inside the plane rather than pointing out of it.
2. **Missing the Absolute Value in $\cos \alpha$:**
   Writing $\cos \alpha = \frac{n_1 \cdot n_2}{\|n_1\| \|n_2\|}$. If $n_1 \cdot n_2 < 0$, omitting the absolute value yields an obtuse angle ($\alpha > 90^\circ$). By geometric definition, the angle between two planes is always the acute angle ($\le 90^\circ$).
3. **Assuming Missing Variables Mean Zero in the Normal:**
   In $\Pi_2: x - y = 2$, the $z$ coordinate is missing, which means its coefficient is $0$, so $n_2 = (1, -1, 0)$, not $(1, -1)$.

---

## 8. How I Would Explain This in Class

> "Imagine opening a hardcover book. Measuring the angle between the front and back covers directly on the paper can be awkward, but if you tape a pencil sticking straight out of each cover, the angle between those two pencils is identical to the angle between the covers. Here, the two pencils $(1, 1, 1)$ and $(1, -1, 0)$ form a dot product of zero, which immediately reveals that the two covers are opened at a perfect 90-degree right angle."

