# Problem 12: A Parameter Revealed by a Row Operation

## 1. The Original Problem

For

$$
A(t) = \begin{pmatrix} 1 & 2 & 3 \\\\ 2 & 4 & t \\\\ 0 & 1 & 1 \end{pmatrix}
$$

find the values of $t$ for which the matrix is not invertible.

Before computing the determinant, perform the operation

$$
R_2 \leftarrow R_2 - 2R_1
$$

and use the resulting structure. At the end, explain what special thing happens to the rows for the value of the parameter you found.

---

## 2. What Are We Trying to Find?

We need to:
1. Apply the row operation $R_2 \leftarrow R_2 - 2R_1$ to simplify matrix $A(t)$ into a new matrix $B(t)$.
2. Use the simplified structure of $B(t)$ to compute $\det A(t)$ easily.
3. Solve the equation $\det A(t) = 0$ to find the exact parameter value $t$ for which $A(t)$ is not invertible.
4. Explain the specific geometric and algebraic phenomenon that occurs among the rows of $A(t)$ at this critical value of $t$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Determinant Invariance Under Row Addition:**
  The replacement operation $R_2 \leftarrow R_2 - 2R_1$ leaves the determinant strictly unchanged:

$$
\det B(t) = \det A(t)
$$

- **Exploiting Zero Entries in Laplace Expansion:**
  By eliminating the first two entries of Row 2, Row 2 will contain two zeros and a single non-zero expression depending on $t$. Expanding along Row 2 will reduce the entire $3 \times 3$ determinant calculation to a single, trivial $2 \times 2$ minor.
- **Invertibility Criterion:**
  A matrix is not invertible if and only if $\det A(t) = 0$.

---

## 4. Step-by-Step Solution

### Step 1: Perform the Specified Row Operation $R_2 \leftarrow R_2 - 2R_1$

Our starting matrix is:

$$
A(t) = \begin{pmatrix} 1 & 2 & 3 \\\\ 2 & 4 & t \\\\ 0 & 1 & 1 \end{pmatrix}
$$

Row 1 is $(1, 2, 3)$, and Row 2 is $(2, 4, t)$.
Calculate the updated Row 2:
- First entry: $2 - 2(1) = 0$
- Second entry: $4 - 2(2) = 0$
- Third entry: $t - 2(3) = t - 6$

Thus, the transformed matrix $B(t)$ is:

$$
B(t) = \begin{pmatrix} 1 & 2 & 3 \\\\ 0 & 0 & t - 6 \\\\ 0 & 1 & 1 \end{pmatrix}
$$

Because row replacement does not alter the determinant:

$$
\det A(t) = \det B(t)
$$

### Step 2: Compute the Determinant Using the Resulting Structure

Row 2 of $B(t)$ has zeros in the first two positions: $(0, 0, t - 6)$.
We expand along **Row 2**:

$$
\det B(t) = (-1)^{2+1}(0) \cdot M_{21} + (-1)^{2+2}(0) \cdot M_{22} + (-1)^{2+3}(t - 6) \cdot M_{23}
$$

The sign for position $(2, 3)$ is $(-1)^{2+3} = (-1)^5 = -1$.
The minor $M_{23}$ is formed by deleting Row 2 and Column 3:

$$
M_{23} = \begin{vmatrix} 1 & 2 \\\\ 0 & 1 \end{vmatrix} = (1)(1) - (2)(0) = 1
$$

Therefore:

$$
\det A(t) = -(t - 6) \cdot 1 = 6 - t
$$

### Step 3: Find the Value of $t$ for Non-Invertibility

A matrix fails to be invertible if and only if its determinant is zero:

$$
\det A(t) = 0 \iff 6 - t = 0 \iff t = 6
$$

Thus, the matrix is not invertible exclusively when $t = 6$.

### Step 4: Explain What Happens to the Rows When $t = 6$

Substitute $t = 6$ back into the original matrix:

$$
A(6) = \begin{pmatrix} 1 & 2 & 3 \\\\ 2 & 4 & 6 \\\\ 0 & 1 & 1 \end{pmatrix}
$$

Observe Row 1 and Row 2:

$$
R_1 = (1, 2, 3), \qquad R_2 = (2, 4, 6)
$$

Notice that:

$$
R_2 = 2 \cdot (1, 2, 3) = 2 R_1
$$

Row 2 is an **exact scalar multiple** of Row 1.
When we perform $R_2 \leftarrow R_2 - 2R_1$ on $A(6)$, the entire second row collapses to zero:

$$
R_2' = (0, 0, 6 - 6) = (0, 0, 0)
$$

The presence of an entire row of zeros immediately shows that the rank of the matrix drops to $2 < 3$. The row vectors are linearly dependent, collapsing the 3D volume to zero and rendering the matrix non-invertible.

---

## 5. Final Answer & Conclusion

- **Transformed Matrix:**

$$
B(t) = \begin{pmatrix} 1 & 2 & 3 \\\\ 0 & 0 & t - 6 \\\\ 0 & 1 & 1 \end{pmatrix}
$$

- **Determinant Expression:** $\det A(t) = 6 - t$
- **Non-Invertible Value:** $t = 6$
- **Row Phenomenon at $t = 6$:** Row 2 becomes an exact duplicate of Row 1 scaled by 2 ($R_2 = 2R_1$). This creates a linear dependency that produces an all-zero row upon elimination, dropping the rank to 2 and causing non-invertibility.

---

## 6. Quick Verification

Verify $\det A(t)$ independently using Laplace expansion along Column 1 of the original matrix $A(t)$:

$$
\det A(t) = 1 \cdot \begin{vmatrix} 4 & t \\\\ 1 & 1 \end{vmatrix} - 2 \cdot \begin{vmatrix} 2 & 3 \\\\ 1 & 1 \end{vmatrix} + 0 \cdot \begin{vmatrix} 2 & 3 \\\\ 4 & t \end{vmatrix}
$$

Evaluate the $2 \times 2$ determinants:

$$
\begin{vmatrix} 4 & t \\\\ 1 & 1 \end{vmatrix} = 4(1) - t(1) = 4 - t
$$

$$
\begin{vmatrix} 2 & 3 \\\\ 1 & 1 \end{vmatrix} = 2(1) - 3(1) = -1
$$

Combine:

$$
\det A(t) = (4 - t) - 2(-1) = 4 - t + 2 = 6 - t
$$

Setting $6 - t = 0$ confirms $t = 6$ without any doubt.

---

## 7. Common Mistakes to Avoid

1. **Sign Error on the Cofactor of Entry $(2, 3)$:**
   The checkerboard sign pattern for a $3 \times 3$ matrix is:

$$
\begin{pmatrix} + & - & + \\\\ - & + & - \\\\ + & - & + \end{pmatrix}
$$

   Position $(2, 3)$ has a negative sign: $(-1)^{2+3} = -1$. Forgetting this negative sign leads to $t - 6$ instead of $6 - t$. (Although setting both to zero gives $t = 6$, the formula for the determinant would be incorrect).
2. **Missing the Linear Dependence Insight:**
   Just computing the number $t = 6$ without explaining the row relationship ($R_2 = 2R_1$) misses the primary conceptual point of the problem.

---

## 8. How I Would Explain This in Class

> "Subtracting twice Row 1 from Row 2 does not change the determinant, but it leaves Row 2 with two zeros: $(0, 0, t-6)$. Expanding along this row gives $-(t-6) \cdot 1 = 6 - t$. For the matrix to fail invertibility, the determinant must be zero, meaning $t = 6$. At $t = 6$, Row 2 is $(2, 4, 6)$, which is exactly twice Row 1; this linear dependence causes Row 2 to vanish completely during elimination, squashing the matrix's rank and volume down to zero."