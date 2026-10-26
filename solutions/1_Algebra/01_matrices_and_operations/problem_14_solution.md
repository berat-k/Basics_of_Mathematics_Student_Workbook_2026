# Problem 14: Rotation Matrices

## 1. The Original Problem

The matrix for a rotation through an angle $\theta$ is

$$
R(\theta) = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}
$$

Compute $R(\alpha)R(\beta)$ and, using the angle-sum formulas for sine and cosine, show that

$$
R(\alpha)R(\beta) = R(\alpha+\beta)
$$

Explain the result geometrically.

---

## 2. What Are We Trying to Find?

We want to:
1. Carry out the matrix multiplication $R(\alpha)R(\beta)$ symbolically.
2. Apply the trigonometric angle-sum identities for sine and cosine to simplify the entries.
3. Conclude that the product equals $R(\alpha+\beta)$.
4. Explain the geometric meaning of this result.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Rotation Matrix $R(\theta)$:**
  Rotates any vector in the Cartesian plane counterclockwise by an angle $\theta$ around the origin $(0, 0)$.
- **Trigonometric Angle-Addition Identities:**

$$
\cos(\alpha + \beta) = \cos\alpha\cos\beta - \sin\alpha\sin\beta
$$

$$
\sin(\alpha + \beta) = \sin\alpha\cos\beta + \cos\alpha\sin\beta
$$

- **Geometric Composition:**
  Matrix multiplication corresponds to the sequential composition of linear transformations.

---

## 4. Step-by-Step Solution

### Step 1: Write Down the Factor Matrices

$$
R(\alpha) = \begin{pmatrix} \cos\alpha & -\sin\alpha \\ \sin\alpha & \cos\alpha \end{pmatrix}, \qquad R(\beta) = \begin{pmatrix} \cos\beta & -\sin\beta \\ \sin\beta & \cos\beta \end{pmatrix}
$$

### Step 2: Multiply the Matrices Entry-by-Entry
Compute the product $R(\alpha)R(\beta)$:
- **Entry (1, 1):**
  $$(\cos\alpha)(\cos\beta) + (-\sin\alpha)(\sin\beta) = \cos\alpha\cos\beta - \sin\alpha\sin\beta$$
- **Entry (1, 2):**
  $$(\cos\alpha)(-\sin\beta) + (-\sin\alpha)(\cos\beta) = -\cos\alpha\sin\beta - \sin\alpha\cos\beta = -(\sin\alpha\cos\beta + \cos\alpha\sin\beta)$$
- **Entry (2, 1):**
  $$(\sin\alpha)(\cos\beta) + (\cos\alpha)(\sin\beta) = \sin\alpha\cos\beta + \cos\alpha\sin\beta$$
- **Entry (2, 2):**
  $$(\sin\alpha)(-\sin\beta) + (\cos\alpha)(\cos\beta) = -\sin\alpha\sin\beta + \cos\alpha\cos\beta = \cos\alpha\cos\beta - \sin\alpha\sin\beta$$

Thus, the product matrix is:

$$
R(\alpha)R(\beta) = \begin{pmatrix} \cos\alpha\cos\beta - \sin\alpha\sin\beta & -(\sin\alpha\cos\beta + \cos\alpha\sin\beta) \\ \sin\alpha\cos\beta + \cos\alpha\sin\beta & \cos\alpha\cos\beta - \sin\alpha\sin\beta \end{pmatrix}
$$

### Step 3: Substitute the Angle-Addition Formulas
Substitute the trigonometric identities into each of the four entries:
1. $(1, 1) = \cos(\alpha + \beta)$
2. $(1, 2) = -\sin(\alpha + \beta)$
3. $(2, 1) = \sin(\alpha + \beta)$
4. $(2, 2) = \cos(\alpha + \beta)$

This gives:

$$
R(\alpha)R(\beta) = \begin{pmatrix} \cos(\alpha+\beta) & -\sin(\alpha+\beta) \\ \sin(\alpha+\beta) & \cos(\alpha+\beta) \end{pmatrix} = R(\alpha+\beta)
$$

This completes the mathematical proof. $\blacksquare$

---

## 5. Geometric Explanation

1. **Composition of Rotations:**
   The action of the product matrix $(R(\alpha)R(\beta))v = R(\alpha)(R(\beta)v)$ corresponds geometrically to:
   - First, rotating vector $v$ counterclockwise by an angle $\beta$ about the origin,
   - Then, rotating the resulting vector counterclockwise by an angle $\alpha$ about the same origin.
2. **Angle Addition:**
   Because both transformations rotate about the identical center point $(0, 0)$, the two rotational angles simply combine: rotating by $\beta$ followed by rotating by $\alpha$ achieves a net rotation by angle $\alpha + \beta$.
3. **Commutativity of 2D Rotations:**
   Since $\alpha + \beta = \beta + \alpha$:

$$
R(\alpha)R(\beta) = R(\alpha+\beta) = R(\beta+\alpha) = R(\beta)R(\alpha)
$$

   Planar rotations always commute with each other, which is a special property not shared by general 3D rotations or general matrices.

---

## 6. Quick Verification

Let us verify with specific numeric angles: $\alpha = 30^\circ$, $\beta = 60^\circ \implies \alpha + \beta = 90^\circ$.

$$
R(30^\circ) = \begin{pmatrix} \frac{\sqrt{3}}{2} & -\frac{1}{2} \\ \frac{1}{2} & \frac{\sqrt{3}}{2} \end{pmatrix}, \qquad R(60^\circ) = \begin{pmatrix} \frac{1}{2} & -\frac{\sqrt{3}}{2} \\ \frac{\sqrt{3}}{2} & \frac{1}{2} \end{pmatrix}
$$

Multiply:

$$
R(30^\circ)R(60^\circ) = \begin{pmatrix} \frac{\sqrt{3}}{4} - \frac{\sqrt{3}}{4} & -\frac{3}{4} - \frac{1}{4} \\ \frac{1}{4} + \frac{3}{4} & -\frac{\sqrt{3}}{4} + \frac{\sqrt{3}}{4} \end{pmatrix} = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}
$$

Notice that:

$$
R(90^\circ) = \begin{pmatrix} \cos 90^\circ & -\sin 90^\circ \\ \sin 90^\circ & \cos 90^\circ \end{pmatrix} = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}
$$

Both results match perfectly.

---

## 7. Common Mistakes to Avoid

1. **Sign errors in the top-right entry:** Be careful with signs: $-\cos\alpha\sin\beta - \sin\alpha\cos\beta = -(\sin\alpha\cos\beta + \cos\alpha\sin\beta) = -\sin(\alpha+\beta)$.
2. **Assuming 3D rotations commute:** This property ($R(\alpha)R(\beta) = R(\beta)R(\alpha)$) holds for planar (2D) rotations, but rotations in 3D around different axes do **not** commute in general.

---

## 8. How I Would Explain This in Class

> "Multiplying two 2D rotation matrices $R(\alpha)$ and $R(\beta)$ corresponds to rotating a point first by $\beta$ and then rotating that result by $\alpha$ about the origin. By calculating the matrix product and applying the trigonometric angle-sum formulas, the product simplifies directly to $R(\alpha+\beta)$. Geometrically, this means rotating by $\beta$ and then by $\alpha$ around the same center is completely equivalent to a single rotation by the total angle $\alpha+\beta$."
