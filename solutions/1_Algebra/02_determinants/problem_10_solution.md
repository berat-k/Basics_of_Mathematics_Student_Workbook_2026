# Problem 10: Detecting Dependence

## 1. The Original Problem

Without carrying out a full determinant calculation, explain why

$$
\det\begin{pmatrix} 1 & 2 & 3 \\\\ 2 & 4 & 6 \\\\ 0 & 1 & 5 \end{pmatrix} = 0
$$

Identify a specific dependence between the rows and connect it with noninvertibility of the matrix.

---

## 2. What Are We Trying to Find?

We need to:
1. Explain why the determinant is zero by inspection without expanding via Sarrus or Laplace cofactors.
2. Identify and state the exact linear dependence relationship connecting the rows of the matrix.
3. Formulate the logical connection showing why row dependence causes both $\det = 0$ and failure of matrix invertibility.

---

## 3. Before Calculating: What Idea Do We Need?

- **Linear Dependence of Rows:**
  A set of vectors is linearly dependent if one vector can be written as a linear combination of the others (or in the simplest case, if one row is a scalar multiple of another).
- **Row Operations and Determinants:**
  If Row $i$ is proportional to Row $j$ ($R_i = c R_j$), then subtracting $c R_j$ from $R_i$ creates a row entirely of zeros ($R_i \leftarrow R_i - c R_j = \mathbf{0}$) without altering the value of the determinant.
- **The Invertible Matrix Theorem:**
  For any $n \times n$ matrix $A$, the following statements are logically equivalent:
  - $\det A \neq 0$
  - The rows of $A$ are linearly independent
  - $\text{rank}(A) = n$ (full rank)
  - $A$ is invertible ($A^{-1}$ exists)
  - The null space of $A$ contains only the zero vector: $\ker(A) = \{\mathbf{0}\}$

  Consequently, if rows are linearly dependent, then $\text{rank}(A) < n$, $\det A = 0$, and $A$ cannot be inverted.

---

## 4. Step-by-Step Solution

### Step 1: Identify the Specific Row Dependence

Let the rows of the matrix be denoted by $R_1, R_2, R_3$:

$$
R_1 = (1, 2, 3), \qquad R_2 = (2, 4, 6), \qquad R_3 = (0, 1, 5)
$$

Compare Row 1 and Row 2 entry by entry:
- First entry: $2 = 2 \cdot 1$
- Second entry: $4 = 2 \cdot 2$
- Third entry: $6 = 2 \cdot 3$

Every entry of Row 2 is exactly twice the corresponding entry of Row 1:

$$
R_2 = 2 R_1 \iff R_2 - 2 R_1 = (0, 0, 0)
$$

This is a non-trivial linear combination equaling the zero vector, proving that the rows are linearly dependent.

### Step 2: Connect the Row Dependence to $\det = 0$

Perform the elementary row operation $R_2 \leftarrow R_2 - 2R_1$:
- Because adding a multiple of one row to another does not change the determinant:

$$
\det\begin{pmatrix} 1 & 2 & 3 \\\\ 2 & 4 & 6 \\\\ 0 & 1 & 5 \end{pmatrix} = \det\begin{pmatrix} 1 & 2 & 3 \\\\ 0 & 0 & 0 \\\\ 0 & 1 & 5 \end{pmatrix}
$$

- Expanding the determinant along the second row:

$$
\det = -0 \cdot M_{21} + 0 \cdot M_{22} - 0 \cdot M_{23} = 0
$$

Any matrix containing an all-zero row has determinant zero. Therefore, the original determinant must be $0$.

### Step 3: Connect Row Dependence to Non-Invertibility

Why does this linear dependence prevent the matrix from having an inverse?
1. **Rank Deficiency:**
   Since Row 2 is redundant, the row space is spanned by at most two vectors ($R_1$ and $R_3$). The dimension of the row space (rank) is at most $2$, which is strictly less than the matrix dimension $3$:

$$
\text{rank}(A) \le 2 < 3
$$

2. **Loss of Injectivity (Non-Trivial Kernel):**
   By the Rank-Nullity Theorem:

$$
\text{dim}(\ker A) = 3 - \text{rank}(A) \ge 3 - 2 = 1
$$

   There exists at least one non-zero vector $x \in \mathbb{R}^3$ such that $Ax = \mathbf{0}$.
3. **Geometric Area/Volume Collapse:**
   The linear transformation $x \mapsto Ax$ collapses the entire 3-dimensional space into a 2-dimensional plane (or line). A transformation that squashes 3D volume down to 0 loses information irreversibly; points cannot be uniquely traced back to their origins.
4. **Conclusion:**
   A non-injective map cannot have an inverse. Hence, the matrix is not invertible.

---

## 5. Final Answer & Conclusion

- **Linear Dependence:** $R_2 = 2 R_1$ (Row 2 is twice Row 1).
- **Determinant Value:** $\det = 0$.
- **Invertibility:** The matrix is **not invertible** (it is singular) because its rows are linearly dependent, its rank is less than 3, its determinant is 0, and its null space is non-trivial.

---

## 6. Quick Verification

To verify that $Ax = \mathbf{0}$ has non-trivial solutions, consider column dependency or solve $Ax = 0$:
Row 1 gives $x_1 + 2x_2 + 3x_3 = 0$.
Row 3 gives $x_2 + 5x_3 = 0 \implies x_2 = -5x_3$.
Substitute into Row 1: $x_1 + 2(-5x_3) + 3x_3 = x_1 - 7x_3 = 0 \implies x_1 = 7x_3$.
Set $x_3 = 1$:

$$
x = \begin{pmatrix} 7 \\\\ -5 \\\\ 1 \end{pmatrix}
$$

Multiply $A$ by $x$:

$$
\begin{pmatrix} 1 & 2 & 3 \\\\ 2 & 4 & 6 \\\\ 0 & 1 & 5 \end{pmatrix} \begin{pmatrix} 7 \\\\ -5 \\\\ 1 \end{pmatrix} = \begin{pmatrix} 7 - 10 + 3 \\\\ 14 - 20 + 6 \\\\ 0 - 5 + 5 \end{pmatrix} = \begin{pmatrix} 0 \\\\ 0 \\\\ 0 \end{pmatrix}
$$

Since a non-zero vector maps to zero, $A$ is undeniably non-invertible.

---

## 7. Common Mistakes to Avoid

1. **Jumping Straight to Sarrus:**
   The problem specifically instructs: *"Without carrying out a full determinant calculation"*. Computing $3! = 6$ diagonal terms ignores the pedagogical goal of recognizing structural dependency.
2. **Confusing Proportionality with Equality:**
   Rows do not need to be identical for the determinant to vanish; any proportional rows ($R_2 = c R_1$) or linear combination ($R_3 = c_1 R_1 + c_2 R_2$) causes $\det = 0$.

---

## 8. How I Would Explain This in Class

> "Looking at the matrix, we immediately notice that Row 2 is exactly twice Row 1: $(2, 4, 6) = 2 \cdot (1, 2, 3)$. Subtracting twice the first row from the second creates an entire row of zeros without changing the determinant, proving instantly that $\det = 0$. Because one row is redundant, the matrix squashes 3D space into a 2D plane, meaning multiple points map to the same output—destroying information and making an inverse impossible."
