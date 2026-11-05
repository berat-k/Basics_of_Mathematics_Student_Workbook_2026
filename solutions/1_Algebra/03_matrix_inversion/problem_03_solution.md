# Problem 03: When Does the Inverse Not Exist?

## 1. The Original Problem

For

$$
A = \begin{pmatrix} 2 & 4 \\\\ 1 & 2 \end{pmatrix}
$$

explain in two ways why $A^{-1}$ does not exist: using the determinant and using dependence between the rows.

---

## 2. What Are We Trying to Find?

We need to demonstrate that matrix $A$ is singular (non-invertible) through two distinct, complementary mathematical perspectives:
1. **Perspective 1 (Algebraic / Determinant):** Show that $\det A = 0$ and explain why an inverse formula cannot exist.
2. **Perspective 2 (Geometric / Row Dependence):** Identify the linear dependence relationship between the rows of $A$ and explain why row dependence prevents the transformation from having an inverse.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Determinant Invertibility Criterion:**
  A square matrix $A$ possesses an inverse if and only if its determinant is non-zero:

$$
A \text{ is invertible} \iff \det A \neq 0
$$

  In the formula $A^{-1} = \frac{1}{\det A}\text{adj}(A)$, the determinant sits in the denominator. When $\det A = 0$, division by zero is undefined, so no inverse matrix can be formed.
- **Row Dependence & Rank:**
  If the row vectors of a matrix are linearly dependent, the matrix fails to have full rank ($\text{rank}(A) < n$).
  - A rank-deficient matrix collapses $n$-dimensional space into a lower-dimensional subspace (e.g., squashing the 2D plane onto a 1D line).
  - This dimensional collapse destroys information: multiple input vectors are mapped to the same output vector (the transformation is not one-to-one / not injective). A non-injective function cannot possess an inverse.

---

## 4. Step-by-Step Solution

### Method 1: Explanation Using the Determinant

Let matrix $A$ be:

$$
A = \begin{pmatrix} 2 & 4 \\\\ 1 & 2 \end{pmatrix}
$$

1. Calculate the determinant using the formula $ad - bc$:

$$
\det A = (2)(2) - (4)(1) = 4 - 4 = 0
$$

2. **Why this prevents the inverse from existing:**
   The explicit formula for the inverse of a $2 \times 2$ matrix requires scaling the adjugate matrix by the reciprocal of the determinant:

$$
A^{-1} = \frac{1}{\det A} \begin{pmatrix} 2 & -4 \\\\ -1 & 2 \end{pmatrix} = \frac{1}{0} \begin{pmatrix} 2 & -4 \\\\ -1 & 2 \end{pmatrix}
$$

   Division by zero is undefined in mathematics. More fundamentally, the determinant measures the factor by which areas are scaled under the linear transformation. A determinant of $0$ indicates that the transformation scales all 2D areas down to zero. Since an area of zero cannot be expanded back to a non-zero area by any subsequent linear map, no inverse transformation can exist.

### Method 2: Explanation Using Dependence Between the Rows

1. Examine the row vectors of $A$:

$$
R_1 = (2, 4), \qquad R_2 = (1, 2)
$$

2. Compare Row 1 and Row 2:

$$
R_1 = (2, 4) = 2 \cdot (1, 2) = 2 R_2
$$

   Row 1 is an **exact scalar multiple** of Row 2. They are collinear vectors pointing in the exact same direction.
3. Rewrite this relationship as a non-trivial linear combination equaling the zero vector:

$$
R_1 - 2 R_2 = (0, 0)
$$

   This proves that the rows of $A$ are **linearly dependent**.
4. **Why row dependence prevents the inverse from existing:**
   Because Row 1 provides no independent directional information beyond Row 2, the row space has dimension $1$:

$$
\text{rank}(A) = 1 < 2
$$

   By the Rank-Nullity Theorem:

$$
\text{dim}(\ker A) = 2 - \text{rank}(A) = 2 - 1 = 1
$$

   This means there exist non-zero vectors $x$ that are mapped directly to the origin $\mathbf{0}$. For example, choose $x = (-2, 1)^T$:

$$
Ax = \begin{pmatrix} 2 & 4 \\\\ 1 & 2 \end{pmatrix} \begin{pmatrix} -2 \\\\ 1 \end{pmatrix} = \begin{pmatrix} 2(-2) + 4(1) \\\\ 1(-2) + 2(1) \end{pmatrix} = \begin{pmatrix} 0 \\\\ 0 \end{pmatrix}
$$

   Both $x = (-2, 1)^T$ and $x = (0, 0)^T$ produce the exact same output $\mathbf{0}$. If an inverse $A^{-1}$ existed, applying it to $\mathbf{0}$ would have to produce both $(-2, 1)^T$ and $(0, 0)^T$ simultaneously, which violates the definition of a mathematical function. Thus, $A$ cannot be inverted.

---

## 5. Final Answer & Conclusion

- **Explanation 1 (Determinant):** $\det A = (2)(2) - (4)(1) = 0$. Since $\det A = 0$, the inverse formula requires division by zero, which is impossible.
- **Explanation 2 (Row Dependence):** Row 1 is twice Row 2 ($R_1 = 2R_2$). The rows are linearly dependent, so the rank drops to 1, squashing the 2D plane onto a 1D line and destroying injectivity.
- **Conclusion:** Both perspectives establish that matrix $A$ is singular and has no inverse.

---

## 6. Quick Verification

Apply Gaussian elimination to matrix $A$:

$$
\begin{pmatrix} 2 & 4 \\\\ 1 & 2 \end{pmatrix} \xrightarrow{R_1 \leftrightarrow R_2} \begin{pmatrix} 1 & 2 \\\\ 2 & 4 \end{pmatrix} \xrightarrow{R_2 \leftarrow R_2 - 2R_1} \begin{pmatrix} 1 & 2 \\\\ 0 & 0 \end{pmatrix}
$$

A row of zeros appears in the echelon form. A square matrix is invertible if and only if its reduced row echelon form is the identity matrix $I$. Because the second row is all zeros, the matrix cannot be reduced to $I$, confirming that $A^{-1}$ does not exist.

---

## 7. Common Mistakes to Avoid

1. **Treating Determinant and Dependence as Unrelated:**
   Thinking that $\det = 0$ is just an arithmetic coincidence separate from geometry. In reality, the determinant is zero *because* the rows are dependent and span zero area.
2. **Assuming Non-Invertible Means "No Solutions" Always:**
   Non-invertibility means the matrix does not have an inverse. A linear system $Ax = b$ with this matrix will either have infinitely many solutions (if $b$ lies on the line spanned by the columns) or no solution at all.

---

## 8. How I Would Explain This in Class

> "First, the determinant formula gives $2(2) - 4(1) = 0$, and because inverting requires dividing by the determinant, division by zero makes an inverse impossible. Second, looking at the rows, Row 1 is $(2, 4)$, which is simply twice Row 2: $(1, 2)$. This dependency means the transformation squashes the entire two-dimensional plane onto a single line, losing a whole dimension of information so that outputs cannot be uniquely traced back to their inputs."
