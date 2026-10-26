# Problem 05: Row Operations

## 1. The Original Problem

For

$$
A = \begin{pmatrix} 1 & 2 & 3 \\\\ 2 & 1 & 0 \\\\ -1 & 4 & 2 \end{pmatrix}
$$

find $\det A$ by simplifying the matrix with row operations. At each step, indicate whether and how the determinant changes.

---

## 2. What Are We Trying to Find?

We need to:
1. Apply elementary row operations to reduce matrix $A$ to an upper triangular form $U$.
2. Explicitly track how each individual row operation affects (or preserves) the determinant.
3. Compute the determinant of the resulting triangular matrix by multiplying its diagonal entries.
4. Conclude the value of $\det A$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Effects of Elementary Row Operations on Determinants:**
  - **Replacement ($R_i \leftarrow R_i + c R_j$ with $i \neq j$):** Adding a scalar multiple of one row to another row **does not change** the determinant:

$$
\det(\text{new matrix}) = \det(\text{old matrix})
$$

  - **Interchange ($R_i \leftrightarrow R_j$):** Swapping two rows multiplies the determinant by $-1$:

$$
\det(\text{new matrix}) = -\det(\text{old matrix})
$$

  - **Scaling ($R_i \leftarrow c R_i$ with $c \neq 0$):** Multiplying a row by a non-zero scalar $c$ scales the determinant by $c$:

$$
\det(\text{new matrix}) = c \cdot \det(\text{old matrix})
$$

- **Strategy:** If we restrict our operations exclusively to row replacements ($R_i \leftarrow R_i + c R_j$), the determinant remains strictly invariant at every step!

---

## 4. Step-by-Step Solution

### Step 1: Create Zeros in the First Column Under Pivot $a_{11} = 1$

Our starting matrix is:

$$
A = \begin{pmatrix} 1 & 2 & 3 \\\\ 2 & 1 & 0 \\\\ -1 & 4 & 2 \end{pmatrix}
$$

1. **Operation 1: $R_2 \leftarrow R_2 - 2R_1$**
   - *Determinant Effect:* Row replacement. Determinant is **unchanged**.
   - Calculate new Row 2:
     - Entry 1: $2 - 2(1) = 0$
     - Entry 2: $1 - 2(2) = 1 - 4 = -3$
     - Entry 3: $0 - 2(3) = 0 - 6 = -6$
     - $R_2' = (0, -3, -6)$

2. **Operation 2: $R_3 \leftarrow R_3 + R_1$**
   - *Determinant Effect:* Row replacement. Determinant is **unchanged**.
   - Calculate new Row 3:
     - Entry 1: $-1 + 1 = 0$
     - Entry 2: $4 + 2 = 6$
     - Entry 3: $2 + 3 = 5$
     - $R_3' = (0, 6, 5)$

After these two operations, the matrix is:

$$
A_1 = \begin{pmatrix} 1 & 2 & 3 \\\\ 0 & -3 & -6 \\\\ 0 & 6 & 5 \end{pmatrix}, \qquad \det A = \det A_1
$$

### Step 2: Create Zero in the Second Column Under Pivot $a_{22} = -3$

To eliminate entry $a_{32} = 6$ in the third row, add $2 \times R_2$ to $R_3$:

3. **Operation 3: $R_3 \leftarrow R_3 + 2R_2$**
   - *Determinant Effect:* Row replacement. Determinant is **unchanged**.
   - Calculate new Row 3:
     - Entry 1: $0 + 2(0) = 0$
     - Entry 2: $6 + 2(-3) = 6 - 6 = 0$
     - Entry 3: $5 + 2(-6) = 5 - 12 = -7$
     - $R_3'' = (0, 0, -7)$

The resulting matrix is in upper triangular form:

$$
U = \begin{pmatrix} 1 & 2 & 3 \\\\ 0 & -3 & -6 \\\\ 0 & 0 & -7 \end{pmatrix}, \qquad \det A = \det U
$$

### Step 3: Compute the Determinant of $U$

Matrix $U$ is upper triangular. By the triangular matrix property, its determinant is the product of the diagonal entries:

$$
\det U = u_{11} \cdot u_{22} \cdot u_{33} = (1) \cdot (-3) \cdot (-7) = 21
$$

Since all row operations were replacements that preserved the determinant:

$$
\det A = \det U = 21
$$

---

## 5. Final Answer & Conclusion

- **Summary of Operations:**
  1. $R_2 \leftarrow R_2 - 2R_1$: determinant unchanged.
  2. $R_3 \leftarrow R_3 + R_1$: determinant unchanged.
  3. $R_3 \leftarrow R_3 + 2R_2$: determinant unchanged.
- **Upper Triangular Form:**

$$
U = \begin{pmatrix} 1 & 2 & 3 \\\\ 0 & -3 & -6 \\\\ 0 & 0 & -7 \end{pmatrix}
$$

- **Final Determinant Value:**

$$
\det A = 1 \cdot (-3) \cdot (-7) = 21
$$

---

## 6. Quick Verification

Verify independently using Sarrus' rule on the original matrix $A$:
- Downward diagonals:
  - $(1)(1)(2) = 2$
  - $(2)(0)(-1) = 0$
  - $(3)(2)(4) = 24$
  - Sum $= 2 + 0 + 24 = 26$
- Upward diagonals:
  - $(-1)(1)(3) = -3$
  - $(4)(0)(1) = 0$
  - $(2)(2)(2) = 8$
  - Sum $= (-3) + 0 + 8 = 5$
- Determinant: $26 - 5 = 21$.
The values match identically.

---

## 7. Common Mistakes to Avoid

1. **Confusing Row Operations with Scaling:**
   Writing $R_2 \leftarrow 2R_1 - R_2$ instead of $R_2 \leftarrow R_2 - 2R_1$. The operation $2R_1 - R_2$ implicitly multiplies Row 2 by $-1$, which flips the sign of the determinant! The target row $R_i$ must have a coefficient of $+1$.
2. **Forgetting to Track Row Swaps:**
   If you swap two rows during elimination, you must include a factor of $(-1)$. Here, no row swap was necessary.

---

## 8. How I Would Explain This in Class

> "Gaussian elimination is often the fastest way to compute large determinants because adding a multiple of one row to another preserves the determinant exactly. Using row replacements alone, we clear column 1 to get rows $(0, -3, -6)$ and $(0, 6, 5)$, and then add twice row 2 to row 3 to get $(0, 0, -7)$. This brings $A$ into upper triangular form with diagonal entries $1, -3,$ and $-7$. Since no operation changed the determinant, $\det A$ is simply the diagonal product: $1 \cdot (-3) \cdot (-7) = 21$."
