# Problem 10: Triangle Area from Vectors

## 1. The Original Problem

The points $A = (0, 0, 0)$, $B = (2, 1, 0)$, and $C = (1, 3, 2)$ form a triangle. Construct $\overrightarrow{AB}$ and $\overrightarrow{AC}$, compute the area of the parallelogram using the cross product, and then find the area of the triangle. Explain the factor $\frac{1}{2}$.

---

## 2. What Are We Trying to Find?

We need to:
1. Construct the displacement vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ from the given coordinates of vertices $A, B,$ and $C$.
2. Compute the cross product $\overrightarrow{AB} \times \overrightarrow{AC}$.
3. Calculate the magnitude (length) of this cross product to find the area of the parallelogram spanned by $\overrightarrow{AB}$ and $\overrightarrow{AC}$.
4. Compute the area of triangle $\Delta ABC$ by applying the factor $\frac{1}{2}$.
5. Provide a geometric justification for why the factor $\frac{1}{2}$ is required.

---

## 3. Before Calculating: What Idea Do We Need?

- **Vector Representation of Sides:**
  Taking vertex $A$ as the reference origin:

$$
\overrightarrow{AB} = B - A, \qquad \overrightarrow{AC} = C - A
$$

- **Parallelogram Area via Cross Product:**
  The magnitude of the cross product of two vectors equals the area of the parallelogram formed by them:

$$
\text{Area}_{\text{parallelogram}} = \|\overrightarrow{AB} \times \overrightarrow{AC}\| = \|\overrightarrow{AB}\| \|\overrightarrow{AC}\| \sin \theta
$$

  where $\theta$ is the interior angle at vertex $A$. The term $\|\overrightarrow{AC}\| \sin \theta$ is precisely the geometric altitude (height) of the parallelogram dropped onto base $\overrightarrow{AB}$.
- **Triangle Area and the Factor $\frac{1}{2}$:**
  A triangle formed by vertices $A, B, C$ occupies exactly half the area of the full parallelogram spanned by $\overrightarrow{AB}$ and $\overrightarrow{AC}$:

$$
\text{Area}_{\Delta ABC} = \frac{1}{2} \|\overrightarrow{AB} \times \overrightarrow{AC}\|
$$

---

## 4. Step-by-Step Solution

### Step 1: Construct Vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$

Subtract the coordinates of vertex $A(0, 0, 0)$ from $B(2, 1, 0)$ and $C(1, 3, 2)$:

$$
\overrightarrow{AB} = B - A = (2 - 0, 1 - 0, 0 - 0) = (2, 1, 0)
$$

$$
\overrightarrow{AC} = C - A = (1 - 0, 3 - 0, 2 - 0) = (1, 3, 2)
$$

### Step 2: Compute the Cross Product $\overrightarrow{AB} \times \overrightarrow{AC}$

Set up the formal determinant:

$$
\overrightarrow{AB} \times \overrightarrow{AC} = \det \begin{pmatrix} i & j & k \\\\ 2 & 1 & 0 \\\\ 1 & 3 & 2 \end{pmatrix}
$$

Expand along the first row:

$$
\overrightarrow{AB} \times \overrightarrow{AC} = i \det \begin{pmatrix} 1 & 0 \\\\ 3 & 2 \end{pmatrix} - j \det \begin{pmatrix} 2 & 0 \\\\ 1 & 2 \end{pmatrix} + k \det \begin{pmatrix} 2 & 1 \\\\ 1 & 3 \end{pmatrix}
$$

Evaluate each $2 \times 2$ determinant:
- $i$-component: $(1)(2) - (0)(3) = 2 - 0 = 2$
- $j$-component: $- [ (2)(2) - (0)(1) ] = - (4 - 0) = -4$
- $k$-component: $(2)(3) - (1)(1) = 6 - 1 = 5$

Thus, the cross product vector is:

$$
\overrightarrow{AB} \times \overrightarrow{AC} = (2, -4, 5)
$$

---

### Step 3: Compute the Area of the Parallelogram

The area of the parallelogram is the Euclidean norm of the cross product:

$$
\text{Area}_{\text{parallelogram}} = \|\overrightarrow{AB} \times \overrightarrow{AC}\| = \|(2, -4, 5)\|
$$

Compute the squares:

$$
2^2 = 4, \quad (-4)^2 = 16, \quad 5^2 = 25
$$

Sum the squares:

$$
4 + 16 + 25 = 45
$$

Take the square root:

$$
\text{Area}_{\text{parallelogram}} = \sqrt{45} = \sqrt{9 \times 5} = 3\sqrt{5} \approx 6.7082
$$

---

### Step 4: Compute the Area of Triangle $\Delta ABC$

Apply the factor $\frac{1}{2}$:

$$
\text{Area}_{\Delta ABC} = \frac{1}{2} \text{Area}_{\text{parallelogram}} = \frac{1}{2} \|\overrightarrow{AB} \times \overrightarrow{AC}\| = \frac{3\sqrt{5}}{2} \approx 3.3541
$$

---

### Step 5: Explain the Factor $\frac{1}{2}$

1. **Geometric Partitioning:**
   Any two vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ with a common starting point $A$ define a four-sided parallelogram whose opposite sides are equal and parallel.
2. **The Diagonal Division:**
   The line segment connecting vertex $B$ to vertex $C$ forms a diagonal of this parallelogram. A well-known geometric property of parallelograms is that any diagonal cuts the parallelogram into two congruent triangles.
3. **Congruence and Area:**
   The two triangles share side $BC$, have side $AB$ congruent to the opposite side, and side $AC$ congruent to its opposite side (SSS congruence). Since congruent figures have identical areas, each triangle must have exactly half the area of the full parallelogram:

$$
\text{Area}_{\text{triangle}} = \frac{1}{2} \times (\text{base} \times \text{height}) = \frac{1}{2} \text{Area}_{\text{parallelogram}}
$$

Thus, the factor $\frac{1}{2}$ geometrically accounts for taking only one of the two congruent halves that constitute the parallelogram.

---

## 5. Final Answer & Conclusion

- **Side Vectors:**

$$
\overrightarrow{AB} = (2, 1, 0), \qquad \overrightarrow{AC} = (1, 3, 2)
$$

- **Cross Product:**

$$
\overrightarrow{AB} \times \overrightarrow{AC} = (2, -4, 5)
$$

- **Parallelogram Area:**

$$
\text{Area}_{\text{parallelogram}} = 3\sqrt{5} \approx 6.708
$$

- **Triangle Area:**

$$
\text{Area}_{\Delta ABC} = \frac{3\sqrt{5}}{2} \approx 3.354
$$

- **Explanation of $\frac{1}{2}$:** The segment $BC$ splits the parallelogram into two congruent triangles of equal area, so the triangle area is exactly half the parallelogram area.

---

## 6. Quick Verification

Verify using Lagrange's Identity:

$$
\|\overrightarrow{AB} \times \overrightarrow{AC}\|^2 = \|\overrightarrow{AB}\|^2 \|\overrightarrow{AC}\|^2 - (\overrightarrow{AB} \cdot \overrightarrow{AC})^2
$$

1. $\|\overrightarrow{AB}\|^2 = 2^2 + 1^2 + 0^2 = 4 + 1 + 0 = 5$
2. $\|\overrightarrow{AC}\|^2 = 1^2 + 3^2 + 2^2 = 1 + 9 + 4 = 14$
3. $\overrightarrow{AB} \cdot \overrightarrow{AC} = (2)(1) + (1)(3) + (0)(2) = 2 + 3 + 0 = 5$

Substitute into the identity:

$$
\|\overrightarrow{AB} \times \overrightarrow{AC}\|^2 = (5)(14) - (5)^2 = 70 - 25 = 45
$$

Taking the square root gives $\sqrt{45} = 3\sqrt{5}$, and dividing by $2$ gives $\frac{3\sqrt{5}}{2}$, verifying the area independently without using the cross product determinant.

---

## 7. Common Mistakes to Avoid

1. **Forgetting to Take the Norm:**
   Reporting the vector $(2, -4, 5)$ as the area. An area is a positive scalar quantity (number of square units), not a directional vector.
2. **Forgetting the $\frac{1}{2}$ Factor:**
   Leaving $3\sqrt{5}$ as the triangle area, which is the area of the entire parallelogram.
3. **Sign Errors in the $j$-Component:**
   Computing the minor determinant $(2)(2) - (0)(1) = 4$, but forgetting the formula's negative sign on $j$, writing $+4$ instead of $-4$.

---

## 8. How I Would Explain This in Class

> "When you cross two vectors, the length of that new arrow tells you the surface area of the entire diamond-shaped parallelogram they trace out in 3D space. But our triangle only uses three corners—cutting that diamond right down the diagonal from $B$ to $C$. Because that diagonal slices the diamond into two identical halves, we simply slap a $\frac{1}{2}$ in front of the parallelogram's area to get the exact area of the triangle."
