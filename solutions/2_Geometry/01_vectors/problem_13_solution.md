# Problem 13: Do Four Points Lie in One Plane?

## 1. The Original Problem

Given

$$
A = (0, 0, 0), \qquad B = (1, 2, 0), \qquad C = (0, 1, 1), \qquad D = (2, 5, 1).
$$

1. Construct $\overrightarrow{AB}$ and $\overrightarrow{AC}$.
2. Find $n = \overrightarrow{AB} \times \overrightarrow{AC}$.
3. Construct $\overrightarrow{AD}$ and check whether $\overrightarrow{AD} \cdot n = 0$.
4. Based on this, decide whether $D$ lies in the plane determined by $A, B, C$, and justify the criterion.

---

## 2. What Are We Trying to Find?

We need to:
1. Construct the displacement vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ from the origin $A$.
2. Compute the plane normal vector $n = \overrightarrow{AB} \times \overrightarrow{AC}$.
3. Construct the displacement vector $\overrightarrow{AD}$ to the fourth point and evaluate the scalar product $\overrightarrow{AD} \cdot n$.
4. Determine whether the four points $A, B, C, D$ are coplanar (lie in a single plane).
5. Rigorously justify the geometric criterion connecting the dot-cross combination (scalar triple product) to planarity.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Plane Determined by Three Points:**
  Three non-collinear points $A, B, C$ uniquely define a plane $\mathcal{P}$. The normal vector to this plane is:

$$
n = \overrightarrow{AB} \times \overrightarrow{AC}
$$

- **The Coplanarity Condition for a Fourth Point:**
  Point $D$ lies in plane $\mathcal{P}$ if and only if the displacement vector $\overrightarrow{AD}$ lies entirely in $\mathcal{P}$.
  Because $n$ is perpendicular to every vector lying in $\mathcal{P}$:

$$
D \in \mathcal{P} \iff \overrightarrow{AD} \cdot n = 0
$$

- **The Scalar Triple Product and Volume:**
  The combined expression $\overrightarrow{AD} \cdot (\overrightarrow{AB} \times \overrightarrow{AC})$ is the **scalar triple product** $[\overrightarrow{AD}, \overrightarrow{AB}, \overrightarrow{AC}]$.
  Its absolute value equals the volume of the parallelepiped spanned by the three vectors:

$$
V = | \overrightarrow{AD} \cdot (\overrightarrow{AB} \times \overrightarrow{AC}) |
$$

  If $V = 0$, the parallelepiped has zero height (it collapses flat into a 2D plane), which proves the four points are coplanar.

---

## 4. Step-by-Step Solution

### Step 1: Construct Vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$

Subtract the coordinates of $A(0, 0, 0)$ from $B(1, 2, 0)$ and $C(0, 1, 1)$:

$$
\overrightarrow{AB} = B - A = (1 - 0, 2 - 0, 0 - 0) = (1, 2, 0)
$$

$$
\overrightarrow{AC} = C - A = (0 - 0, 1 - 0, 1 - 0) = (0, 1, 1)
$$

---

### Step 2: Compute $n = \overrightarrow{AB} \times \overrightarrow{AC}$

Set up the formal cross product determinant:

$$
n = \det \begin{pmatrix} i & j & k \\\\ 1 & 2 & 0 \\\\ 0 & 1 & 1 \end{pmatrix}
$$

Expand along the first row:

$$
n = i \det \begin{pmatrix} 2 & 0 \\\\ 1 & 1 \end{pmatrix} - j \det \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} + k \det \begin{pmatrix} 1 & 2 \\\\ 0 & 1 \end{pmatrix}
$$

Evaluate each component:
- $i$-component: $(2)(1) - (0)(1) = 2 - 0 = 2$
- $j$-component: $- [ (1)(1) - (0)(0) ] = - (1 - 0) = -1$
- $k$-component: $(1)(1) - (2)(0) = 1 - 0 = 1$

Therefore, the normal vector is:

$$
n = (2, -1, 1)
$$

---

### Step 3: Construct $\overrightarrow{AD}$ and Check $\overrightarrow{AD} \cdot n$

1. **Construct $\overrightarrow{AD}$:**

$$
\overrightarrow{AD} = D - A = (2 - 0, 5 - 0, 1 - 0) = (2, 5, 1)
$$

2. **Compute the dot product $\overrightarrow{AD} \cdot n$:**

$$
\overrightarrow{AD} \cdot n = (2)(2) + (5)(-1) + (1)(1) = 4 - 5 + 1 = 0
$$

The dot product is identically zero:

$$
\overrightarrow{AD} \cdot n = 0
$$

---

### Step 4: Decision and Justification of the Criterion

1. **Decision:**
   **Yes**, the fourth point $D(2, 5, 1)$ lies in the plane determined by $A, B,$ and $C$.
   All four points $A, B, C, D$ are **coplanar**.

2. **Justification of the Criterion:**
   - The normal vector $n = \overrightarrow{AB} \times \overrightarrow{AC}$ is, by construction, perpendicular to the entire plane containing $A, B,$ and $C$.
   - Any point $X$ in space belongs to this plane if and only if the direction from $A$ to $X$ is perpendicular to $n$, which means $\overrightarrow{AX} \cdot n = 0$.
   - Because $\overrightarrow{AD} \cdot n = 0$, the vector $\overrightarrow{AD}$ has zero component in the normal direction (it does not stick out of the plane).
   - Equivalently, in terms of linear combinations, $\overrightarrow{AD}$ can be expressed purely in terms of the planar vectors:

$$
\overrightarrow{AD} = 2\overrightarrow{AB} + 1\overrightarrow{AC} = 2(1, 2, 0) + 1(0, 1, 1) = (2, 4 + 1, 1) = (2, 5, 1)
$$

   Because $\overrightarrow{AD}$ is a linear combination of $\overrightarrow{AB}$ and $\overrightarrow{AC}$, point $D$ lies entirely within the plane spanned by $A, B,$ and $C$.

---

## 5. Final Answer & Conclusion

- **Vectors:**

$$
\overrightarrow{AB} = (1, 2, 0), \qquad \overrightarrow{AC} = (0, 1, 1), \qquad \overrightarrow{AD} = (2, 5, 1)
$$

- **Normal Vector:**

$$
n = (2, -1, 1)
$$

- **Dot Product Evaluation:** $\overrightarrow{AD} \cdot n = 4 - 5 + 1 = 0$.
- **Conclusion:** Point $D$ **lies in the plane** determined by $A, B,$ and $C$. The four points are coplanar because the displacement $\overrightarrow{AD}$ has zero projection along the plane's normal vector.

---

## 6. Quick Verification

Compute the volume determinant directly via the $3 \times 3$ scalar triple product:

$$
\det \begin{pmatrix} 1 & 2 & 0 \\\\ 0 & 1 & 1 \\\\ 2 & 5 & 1 \end{pmatrix}
$$

Expand along the first column:

$$
1 \cdot \det \begin{pmatrix} 1 & 1 \\\\ 5 & 1 \end{pmatrix} + 2 \cdot \det \begin{pmatrix} 2 & 0 \\\\ 1 & 1 \end{pmatrix} = 1(1 - 5) + 2(2 - 0) = -4 + 4 = 0
$$

The determinant is exactly zero. A zero determinant proves that the three vectors are linearly dependent, confirming that the volume of the spanned solid is zero and that all four points lie in the same 2D plane.

---

## 7. Common Mistakes to Avoid

1. **Constructing Vectors from Wrong Reference Points:**
   Mixing base vertices, such as computing $\overrightarrow{AB}$, $\overrightarrow{AC}$, but then taking $\overrightarrow{BD}$ instead of $\overrightarrow{AD}$. While $\overrightarrow{BD} \cdot n = 0$ is also true, keeping $A$ as the common origin keeps the triple product clean.
2. **Assuming $\overrightarrow{AD} \cdot n \neq 0$ Means Only $D$ Is Wrong:**
   If $\overrightarrow{AD} \cdot n \neq 0$, the four points are non-coplanar (they form a 3D tetrahedron of non-zero volume).
3. **Minus Sign Slips:**
   Computing $(5)(-1)$ as $+5$, which would give $4 + 5 + 1 = 10 \neq 0$, falsely concluding that the points are not coplanar.

---

## 8. How I Would Explain This in Class

> "Three points always lie on a flat plane, just like a three-legged stool never wobbles. To see if a fourth leg $D$ rests flat on that same plane, we construct a vertical flagpole $n$ sticking straight out of the stool. If the arrow pointing from the base to point $D$ forms a perfect 90-degree angle with the flagpole ($\overrightarrow{AD} \cdot n = 0$), then $D$ is completely flat against the stool surface with zero wobble."

