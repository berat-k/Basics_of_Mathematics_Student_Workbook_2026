# Problem 05: A 3×3 Matrix

## 1. The Original Problem

Use Gauss–Jordan elimination to find the inverse of

$$
A = \begin{pmatrix} 1 & 1 & 0 \\\\ 0 & 1 & 1 \\\\ 1 & 0 & 1 \end{pmatrix}
$$

Check the result by multiplication.

---

## 2. What Are We Trying to Find?

We need to:
1. Construct the $3 \times 6$ augmented matrix $[A \mid I_3]$.
2. Perform systematic Gaussian elimination forward and backward to reduce the left $3 \times 3$ block to $I_3$.
3. Extract the inverse matrix $A^{-1}$ from the right block.
4. Verify the result by explicitly computing the product $A A^{-1}$ and confirming that it yields $I_3$.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Gauss–Jordan Algorithm for $3 \times 3$:**
  Form the augmented matrix:

$$
[A \mid I] = \left(\begin{array}{ccc|ccc}
a_{11} & a_{12} & a_{13} & 1 & 0 & 0 \\\\
a_{21} & a_{22} & a_{23} & 0 & 1 & 0 \\\\
a_{31} & a_{32} & a_{33} & 0 & 0 & 1
\end{array}\right)
$$

  - **Phase 1 (Forward Elimination):** Use row operations to create zeros below each diagonal pivot, producing an upper triangular matrix on the left.
  - **Phase 2 (Normalization & Backward Elimination):** Scale pivots to $+1$ and eliminate entries above the diagonal pivots, transforming the left side into the reduced row echelon form $I_3$.
  - The right block simultaneously transforms into $A^{-1}$.

---

## 4. Step-by-Step Solution

### Step 1: Initial Augmented Matrix

Write $A$ and $I_3$ side by side:

$$
[A \mid I] = \left(\begin{array}{ccc|ccc}
1 & 1 & 0 & 1 & 0 & 0 \\\\
0 & 1 & 1 & 0 & 1 & 0 \\\\
1 & 0 & 1 & 0 & 0 & 1
\end{array}\right)
$$

### Step 2: Clear Column 1 Below the First Pivot

The entry in position $(2, 1)$ is already $0$.
Eliminate the $1$ in position $(3, 1)$ using the operation:

$$
R_3 \leftarrow R_3 - R_1
$$

- Left block: $(1 - 1, \, 0 - 1, \, 1 - 0) = (0, -1, 1)$
- Right block: $(0 - 1, \, 0 - 0, \, 1 - 0) = (-1, 0, 1)$

The augmented matrix becomes:

$$
\left(\begin{array}{ccc|ccc}
1 & 1 & 0 & 1 & 0 & 0 \\\\
0 & 1 & 1 & 0 & 1 & 0 \\\\
0 & -1 & 1 & -1 & 0 & 1
\end{array}\right)
$$

### Step 3: Clear Column 2 Below the Second Pivot

Eliminate the $-1$ in position $(3, 2)$ using Row 2 ($R_2 = (0, 1, 1 \mid 0, 1, 0)$):

$$
R_3 \leftarrow R_3 + R_2
$$

- Left block: $(0 + 0, \, -1 + 1, \, 1 + 1) = (0, 0, 2)$
- Right block: $(-1 + 0, \, 0 + 1, \, 1 + 0) = (-1, 1, 1)$

The augmented matrix becomes:

$$
\left(\begin{array}{ccc|ccc}
1 & 1 & 0 & 1 & 0 & 0 \\\\
0 & 1 & 1 & 0 & 1 & 0 \\\\
0 & 0 & 2 & -1 & 1 & 1
\end{array}\right)
$$

### Step 4: Normalize the Third Pivot to $+1$

Scale Row 3 by $\frac{1}{2}$:

$$
R_3 \leftarrow \frac{1}{2} R_3
$$

The augmented matrix becomes:

$$
\left(\begin{array}{ccc|ccc}
1 & 1 & 0 & 1 & 0 & 0 \\\\
0 & 1 & 1 & 0 & 1 & 0 \\\\
0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2}
\end{array}\right)
$$

### Step 5: Clear Column 3 Above the Third Pivot

Eliminate entry $a_{23} = 1$ in Row 2 using Row 3:

$$
R_2 \leftarrow R_2 - R_3
$$

- Left block: $(0 - 0, \, 1 - 0, \, 1 - 1) = (0, 1, 0)$
- Right block:
  - Entry 1: $0 - \left(-\frac{1}{2}\right) = \frac{1}{2}$
  - Entry 2: $1 - \frac{1}{2} = \frac{1}{2}$
  - Entry 3: $0 - \frac{1}{2} = -\frac{1}{2}$
  - New Row 2 right: $\left(\frac{1}{2}, \, \frac{1}{2}, \, -\frac{1}{2}\right)$

Entry $a_{13}$ is already $0$. The augmented matrix becomes:

$$
\left(\begin{array}{ccc|ccc}
1 & 1 & 0 & 1 & 0 & 0 \\\\
0 & 1 & 0 & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\\\
0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2}
\end{array}\right)
$$

### Step 6: Clear Column 2 Above the Second Pivot

Eliminate entry $a_{12} = 1$ in Row 1 using Row 2:

$$
R_1 \leftarrow R_1 - R_2
$$

- Left block: $(1 - 0, \, 1 - 1, \, 0 - 0) = (1, 0, 0)$
- Right block:
  - Entry 1: $1 - \frac{1}{2} = \frac{1}{2}$
  - Entry 2: $0 - \frac{1}{2} = -\frac{1}{2}$
  - Entry 3: $0 - \left(-\frac{1}{2}\right) = \frac{1}{2}$
  - New Row 1 right: $\left(\frac{1}{2}, \, -\frac{1}{2}, \, \frac{1}{2}\right)$

The augmented matrix has reached fully reduced row echelon form $[I_3 \mid A^{-1}]$:

$$
\left(\begin{array}{ccc|ccc}
1 & 0 & 0 & \frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\\\
0 & 1 & 0 & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\\\
0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2}
\end{array}\right)
$$

---

## 5. Final Answer & Conclusion

- **The Inverse Matrix:**

$$
A^{-1} = \frac{1}{2} \begin{pmatrix} 1 & -1 & 1 \\\\ 1 & 1 & -1 \\\\ -1 & 1 & 1 \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\\\ \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\\\ -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{pmatrix}
$$

- **Conclusion:** Through a structured 5-step Gauss–Jordan elimination, matrix $A$ was successfully inverted.

---

## 6. Quick Verification

Multiply $A$ by $A^{-1}$, keeping the scalar factor $\frac{1}{2}$ outside:

$$
A A^{-1} = \begin{pmatrix} 1 & 1 & 0 \\\\ 0 & 1 & 1 \\\\ 1 & 0 & 1 \end{pmatrix} \left[ \frac{1}{2} \begin{pmatrix} 1 & -1 & 1 \\\\ 1 & 1 & -1 \\\\ -1 & 1 & 1 \end{pmatrix} \right] = \frac{1}{2} \begin{pmatrix} 1 & 1 & 0 \\\\ 0 & 1 & 1 \\\\ 1 & 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & -1 & 1 \\\\ 1 & 1 & -1 \\\\ -1 & 1 & 1 \end{pmatrix}
$$

Compute the nine entry products:
- **Row 1:**
  - $(1)(1) + (1)(1) + (0)(-1) = 1 + 1 + 0 = 2$
  - $(1)(-1) + (1)(1) + (0)(1) = -1 + 1 + 0 = 0$
  - $(1)(1) + (1)(-1) + (0)(1) = 1 - 1 + 0 = 0$
- **Row 2:**
  - $(0)(1) + (1)(1) + (1)(-1) = 0 + 1 - 1 = 0$
  - $(0)(-1) + (1)(1) + (1)(1) = 0 + 1 + 1 = 2$
  - $(0)(1) + (1)(-1) + (1)(1) = 0 - 1 + 1 = 0$
- **Row 3:**
  - $(1)(1) + (0)(1) + (1)(-1) = 1 + 0 - 1 = 0$
  - $(1)(-1) + (0)(1) + (1)(1) = -1 + 0 + 1 = 0$
  - $(1)(1) + (0)(-1) + (1)(1) = 1 + 0 + 1 = 2$

Combine with the scalar factor:

$$
A A^{-1} = \frac{1}{2} \begin{pmatrix} 2 & 0 & 0 \\\\ 0 & 2 & 0 \\\\ 0 & 0 & 2 \end{pmatrix} = \begin{pmatrix} 1 & 0 & 0 \\\\ 0 & 1 & 0 \\\\ 0 & 0 & 1 \end{pmatrix} = I_3
$$

The result matches the $3 \times 3$ identity matrix exactly.

---

## 7. Common Mistakes to Avoid

1. **Premature Backward Elimination:**
   Trying to eliminate entries above diagonal pivots before the matrix is fully upper triangular. Always complete forward elimination (echelon form) before starting backward elimination.
2. **Fraction Errors in Right Block:**
   Carrying out messy fraction arithmetic across rows. Factoring out $\frac{1}{2}$ at the end or working carefully with halves avoids sign and addition mistakes.

---

## 8. How I Would Explain This in Class

> "Because this is a $3 \times 3$ matrix, we cannot use the short $2 \times 2$ formula; we augment $A$ with the $3 \times 3$ identity matrix $[A \mid I]$. Forward elimination clears column 1 with $R_3 - R_1$, then column 2 with $R_3 + R_2$, producing a pivot of $2$ in the bottom right corner. Normalizing the bottom row by dividing by $2$ and working backwards to eliminate the upper off-diagonal entries leaves $I$ on the left and the inverse matrix $A^{-1}$ with rows $(1/2, -1/2, 1/2)$, $(1/2, 1/2, -1/2)$, and $(-1/2, 1/2, 1/2)$ cleanly on the right."