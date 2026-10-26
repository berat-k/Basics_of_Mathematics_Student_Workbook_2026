# Problem 11: Shortening the Calculation with Row Operations

## 1. The Original Problem

Compute

$$
\det\begin{pmatrix} 1 & 2 & 3 \\\\ 1 & 3 & 4 \\\\ 1 & 4 & 6 \end{pmatrix}
$$

by first performing row operations that create as many zeros as possible. State which operations do not change the determinant.

---

## 2. What Are We Trying to Find?

We need to:
1. Apply targeted row operations to introduce zeros in the matrix, making the determinant trivial to evaluate.
2. Explicitly specify which row operations preserve the determinant value unchanged.
3. Compute the final determinant through the resulting simplified (triangular) matrix.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Row Addition Invariance Property:**
  Adding any scalar multiple of one row to another row:

$$
R_i \leftarrow R_i + c R_j \quad (i \neq j)
$$

  **does not change** the value of the determinant:

$$
\det(\text{new matrix}) = \det(\text{old matrix})
$$

- **Observation for Strategic Planning:**
  Notice that every entry in the first column is $1$:

$$
a_{11} = 1, \qquad a_{21} = 1, \qquad a_{31} = 1
$$

  Using $R_1$ as our pivot row, we can immediately wipe out both $a_{21}$ and $a_{31}$ by subtracting $R_1$ from $R_2$ and from $R_3$. Neither operation alters the determinant!

---

## 4. Step-by-Step Solution

### Step 1: Create Zeros in the First Column

Let our starting matrix be:

$$
A = \begin{pmatrix} 1 & 2 & 3 \\\\ 1 & 3 & 4 \\\\ 1 & 4 & 6 \end{pmatrix}
$$

1. **Operation 1: $R_2 \leftarrow R_2 - R_1$**
   - *Type:* Row replacement ($c = -1$).
   - *Determinant Effect:* **Determinant is unchanged.**
   - Calculate new Row 2: $R_2' = (1 - 1, \, 3 - 2, \, 4 - 3) = (0, 1, 1)$

2. **Operation 2: $R_3 \leftarrow R_3 - R_1$**
   - *Type:* Row replacement ($c = -1$).
   - *Determinant Effect:* **Determinant is unchanged.**
   - Calculate new Row 3: $R_3' = (1 - 1, \, 4 - 2, \, 6 - 3) = (0, 2, 3)$

The matrix is now transformed into:

$$
A_1 = \begin{pmatrix} 1 & 2 & 3 \\\\ 0 & 1 & 1 \\\\ 0 & 2 & 3 \end{pmatrix}, \qquad \det A = \det A_1
$$

### Step 2: Create a Zero in the Second Column

Notice entry $a_{32} = 2$ in Row 3. We can eliminate it using Row 2 ($R_2' = (0, 1, 1)$):

3. **Operation 3: $R_3 \leftarrow R_3 - 2R_2$**
   - *Type:* Row replacement ($c = -2$).
   - *Determinant Effect:* **Determinant is unchanged.**
   - Calculate new Row 3: $R_3'' = (0 - 2(0), \, 2 - 2(1), \, 3 - 2(1)) = (0, 0, 1)$

The matrix is now in strict upper triangular form:

$$
U = \begin{pmatrix} 1 & 2 & 3 \\\\ 0 & 1 & 1 \\\\ 0 & 0 & 1 \end{pmatrix}, \qquad \det A = \det U
$$

### Step 3: Compute the Determinant of $U$

For any triangular matrix, the determinant is the product of its diagonal elements:

$$
\det U = u_{11} \cdot u_{22} \cdot u_{33} = (1) \cdot (1) \cdot (1) = 1
$$

Because every single operation performed was a row replacement ($R_i \leftarrow R_i + c R_j$), the determinant remained unchanged throughout the process:

$$
\det A = 1
$$

---

## 5. Final Answer & Conclusion

- **Operations that do not change the determinant:**
  - $R_2 \leftarrow R_2 - R_1$
  - $R_3 \leftarrow R_3 - R_1$
  - $R_3 \leftarrow R_3 - 2R_2$
  All row replacement operations preserve the determinant with multiplier $1$.
- **Upper Triangular Matrix:**

$$
U = \begin{pmatrix} 1 & 2 & 3 \\\\ 0 & 1 & 1 \\\\ 0 & 0 & 1 \end{pmatrix}
$$

- **Final Value:**

$$
\det\begin{pmatrix} 1 & 2 & 3 \\\\ 1 & 3 & 4 \\\\ 1 & 4 & 6 \end{pmatrix} = 1
$$

---

## 6. Quick Verification

Verify independently by Sarrus' rule on the original matrix:
- Downward diagonals:
  - $1 \cdot 3 \cdot 6 = 18$
  - $2 \cdot 4 \cdot 1 = 8$
  - $3 \cdot 1 \cdot 4 = 12$
  - Sum $= 18 + 8 + 12 = 38$
- Upward diagonals:
  - $1 \cdot 3 \cdot 3 = 9$
  - $4 \cdot 4 \cdot 1 = 16$
  - $6 \cdot 1 \cdot 2 = 12$
  - Sum $= 9 + 16 + 12 = 37$
- Determinant: $38 - 37 = 1$.
Both methods give $1$, verifying the row operation result with absolute precision.

---

## 7. Common Mistakes to Avoid

1. **Multiplying a Row by a Factor Without Compensating:**
   If you replace $R_i$ with $c R_i + R_j$ (scaling $R_i$), the determinant is multiplied by $c$. Only $R_i \leftarrow R_i + c R_j$ leaves the determinant unaltered.
2. **Performing Inconsistent Simultaneous Operations:**
   Replacing $R_2 \leftarrow R_2 - R_3$ and $R_3 \leftarrow R_3 - R_2$ simultaneously causes circular dependencies. Always use one fixed pivot row to clear other rows sequentially.

---

## 8. How I Would Explain This in Class

> "Since all three rows start with $1$, subtracting Row 1 from Row 2 gives $(0, 1, 1)$, and subtracting Row 1 from Row 3 gives $(0, 2, 3)$. Neither subtraction changes the determinant. Then, subtracting twice the new Row 2 from Row 3 clears the second column, leaving $(0, 0, 1)$. We now have an upper triangular matrix with only $1$'s on the main diagonal, so the determinant is simply $1 \cdot 1 \cdot 1 = 1$."
