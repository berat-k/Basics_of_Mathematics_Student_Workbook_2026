# Problem 09: Area and the Determinant

## 1. The Original Problem

The vectors

$$
u = \begin{pmatrix} 3 \\\\ 1 \end{pmatrix}, \qquad v = \begin{pmatrix} 1 \\\\ 4 \end{pmatrix}
$$

span a parallelogram. Compute its area using a determinant. Then reverse the order of the vectors and explain what changes in the determinant and what does not change in the area.

---

## 2. What Are We Trying to Find?

We need to:
1. Construct the matrix whose columns (or rows) are the vectors $u$ and $v$.
2. Compute the determinant of this matrix and determine the geometric area of the parallelogram spanned by $u$ and $v$.
3. Form the matrix with the vectors reversed in order, $v$ then $u$, and compute its determinant.
4. Explain clearly the distinction between the algebraic determinant (which carries an orientation sign) and the geometric area (which is strictly non-negative).

---

## 3. Before Calculating: What Idea Do We Need?

- **Geometric Interpretation of the $2 \times 2$ Determinant:**
  If two vectors $u = (u_1, u_2)^T$ and $v = (v_1, v_2)^T$ in $\mathbb{R}^2$ form the edges of a parallelogram, the determinant of the matrix $M = [u \mid v]$ equals the **signed area** of that parallelogram:

$$
\text{Signed Area} = \det\begin{pmatrix} u_1 & v_1 \\\\ u_2 & v_2 \end{pmatrix}
$$

- **Physical Geometric Area:**
  Physical area cannot be negative. Therefore, the geometric area is the absolute value of the determinant:

$$
\text{Area} = |\det[u \mid v]|
$$

- **Orientation & Vector Order:**
  - If rotating from the first vector to the second vector goes **counterclockwise**, the orientation is positive: $\det > 0$.
  - If rotating goes **clockwise**, the orientation is negative: $\det < 0$.
  - Reversing the order of vectors swaps two columns (or rows) of the matrix, which multiplies the determinant by $-1$ while leaving the absolute value (the physical area) identical.

---

## 4. Step-by-Step Solution

### Step 1: Compute Area with Order $(u, v)$

Place $u = (3, 1)^T$ as the first column and $v = (1, 4)^T$ as the second column to form matrix $M$:

$$
M = \begin{pmatrix} 3 & 1 \\\\ 1 & 4 \end{pmatrix}
$$

Compute the determinant:

$$
\det M = (3)(4) - (1)(1) = 12 - 1 = 11
$$

Since the determinant is positive ($\det M = 11 > 0$), rotating from $u$ to $v$ follows a standard counterclockwise orientation.
The physical area of the parallelogram is:

$$
\text{Area} = |\det M| = |11| = 11
$$

### Step 2: Reverse the Order of the Vectors $(v, u)$

Place $v$ as the first column and $u$ as the second column to form matrix $N$:

$$
N = \begin{pmatrix} 1 & 3 \\\\ 4 & 1 \end{pmatrix}
$$

Compute the determinant:

$$
\det N = (1)(1) - (3)(4) = 1 - 12 = -11
$$

The physical area of the parallelogram is:

$$
\text{Area} = |\det N| = |-11| = 11
$$

### Step 3: Explain What Changes and What Does Not Change

1. **What changes in the determinant:**
   The sign of the determinant flips from $+11$ to $-11$:

$$
\det[v \mid u] = -\det[u \mid v]
$$

   This change reflects the reversal of geometric orientation. In the $(u, v)$ order, the shortest rotation from $u$ to $v$ is counterclockwise (positive orientation). In the $(v, u)$ order, rotating from $v$ to $u$ goes clockwise (negative orientation).
2. **What does not change in the area:**
   The physical parallelogram itself is completely unchanged in the Euclidean plane. Its vertices remain at $(0, 0)$, $(3, 1)$, $(1, 4)$, and $(4, 5)$. Therefore, its geometric size/area remains exactly $11$:

$$
\text{Area} = |\det M| = |\det N| = 11
$$

---

## 5. Final Answer & Conclusion

- **Area of the Parallelogram:**

$$
\text{Area} = 11
$$

- **Determinants by Vector Order:**

$$
\det[u \mid v] = \det\begin{pmatrix} 3 & 1 \\\\ 1 & 4 \end{pmatrix} = +11
$$

$$
\det[v \mid u] = \det\begin{pmatrix} 1 & 3 \\\\ 4 & 1 \end{pmatrix} = -11
$$

- **Conclusion:** Reversing the order swaps the columns, flipping the algebraic sign of the determinant from $+11$ to $-11$ due to reversed orientation, but leaves the physical geometric area invariant at $|\pm 11| = 11$.

---

## 6. Quick Verification

Verify using the classical vector cross product in $\mathbb{R}^3$ by embedding vectors in the $xy$-plane with $z = 0$:
Let $u = (3, 1, 0)$ and $v = (1, 4, 0)$.

$$
u \times v = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\\\ 3 & 1 & 0 \\\\ 1 & 4 & 0 \end{vmatrix} = \mathbf{k} \cdot [ (3)(4) - (1)(1) ] = 11 \, \mathbf{k}
$$

The magnitude of the cross product is $\|u \times v\| = \|11 \, \mathbf{k}\| = 11$, which matches the parallelogram area perfectly. Reversing the order gives $v \times u = -11 \, \mathbf{k}$, whose magnitude remains $\| -11 \, \mathbf{k} \| = 11$.

---

## 7. Common Mistakes to Avoid

1. **Reporting a Negative Area:**
   Stating that the area is $-11$ when computing $\det[v \mid u]$. Geometric area is always non-negative; you must take the absolute value $|\det|$.
2. **Confusing Rows and Columns:**
   Placing $u$ and $v$ as rows gives matrix $M^T$, which has the exact same determinant because $\det(M^T) = \det M$. Whether vectors are entered as rows or columns, the signed area is identical.

---

## 8. How I Would Explain This in Class

> "The determinant of the matrix formed by two 2D vectors gives the signed area of the parallelogram they span. For vectors $u$ and $v$, the determinant is $3(4) - 1(1) = 11$, so the physical area is $11$. When we reverse the order to $v$ and $u$, we swap the two columns, which changes the orientation from counterclockwise to clockwise and flips the sign of the determinant to $-11$. The geometric shape and its physical area remain completely unchanged at $|-11| = 11$."