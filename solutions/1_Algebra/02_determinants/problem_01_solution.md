# Problem 01: Determinant of a 2×2 Matrix

## 1. The Original Problem

Compute:

$$
\det\begin{pmatrix} 3 & -2 \\\\ 5 & 4 \end{pmatrix}, \qquad \det\begin{pmatrix} 1 & 7 \\\\ 2 & 14 \end{pmatrix}
$$

Which matrix is invertible? Justify your answer.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the numerical determinant of the first matrix $A$:

$$
A = \begin{pmatrix} 3 & -2 \\\\ 5 & 4 \end{pmatrix}
$$

2. Compute the numerical determinant of the second matrix $B$:

$$
B = \begin{pmatrix} 1 & 7 \\\\ 2 & 14 \end{pmatrix}
$$

3. Determine which of these two matrices is invertible and which is singular (non-invertible).
4. Provide a precise mathematical justification linking the determinant value to matrix invertibility.

---

## 3. Before Calculating: What Idea Do We Need?

- **The $2 \times 2$ Determinant Formula:**
  For any $2 \times 2$ matrix:

$$
M = \begin{pmatrix} a & b \\\\ c & d \end{pmatrix}
$$

  its determinant is defined as the product of the main diagonal minus the product of the anti-diagonal:

$$
\det M = ad - bc
$$

- **Invertibility Criterion:**
  A square matrix $M$ is invertible if and only if its determinant is non-zero:

$$
M \text{ is invertible} \iff \det M \neq 0
$$

  - If $\det M \neq 0$, the inverse $M^{-1}$ exists and is given explicitly by:

$$
M^{-1} = \frac{1}{\det M} \begin{pmatrix} d & -b \\\\ -c & a \end{pmatrix}
$$

  - If $\det M = 0$, the rows (and columns) are linearly dependent; the transformation collapses the 2D plane into a line or a point, meaning information is irreversibly lost and no inverse function can exist.

---

## 4. Step-by-Step Solution

### Step 1: Compute the Determinant of Matrix $A$

For matrix $A$, the entries are $a = 3$, $b = -2$, $c = 5$, and $d = 4$:

$$
A = \begin{pmatrix} 3 & -2 \\\\ 5 & 4 \end{pmatrix}
$$

Applying the formula:

$$
\det A = (3)(4) - (-2)(5)
$$

Watch the negative signs carefully:

$$
\det A = 12 - (-10) = 12 + 10 = 22
$$

### Step 2: Compute the Determinant of Matrix $B$

For matrix $B$, the entries are $a = 1$, $b = 7$, $c = 2$, and $d = 14$:

$$
B = \begin{pmatrix} 1 & 7 \\\\ 2 & 14 \end{pmatrix}
$$

Applying the formula:

$$
\det B = (1)(14) - (7)(2) = 14 - 14 = 0
$$

### Step 3: Determine Invertibility and Justify

1. **For Matrix $A$:**
   Since $\det A = 22 \neq 0$, matrix $A$ is **invertible**. Its column vectors and row vectors are linearly independent.
2. **For Matrix $B$:**
   Since $\det B = 0$, matrix $B$ is **not invertible** (it is singular).
   Notice the structural dependency: Row 2 is exactly twice Row 1:

$$
\text{Row 2} = (2, 14) = 2 \cdot (1, 7) = 2 \cdot \text{Row 1}
$$

   Because the rows are collinear, the matrix does not have full rank ($\text{rank}(B) = 1 < 2$).

---

## 5. Final Answer & Conclusion

- **Determinant Values:**

$$
\det A = 22, \qquad \det B = 0
$$

- **Conclusion:**
  - Matrix $A$ is **invertible** because its determinant is non-zero ($22 \neq 0$).
  - Matrix $B$ is **not invertible** because its determinant is zero ($\det B = 0$).

---

## 6. Quick Verification

- **Explicit Inverse Check for $A$:**

$$
A^{-1} = \frac{1}{22} \begin{pmatrix} 4 & 2 \\\\ -5 & 3 \end{pmatrix}
$$

  Multiply $A$ by $A^{-1}$:

$$
A A^{-1} = \begin{pmatrix} 3 & -2 \\\\ 5 & 4 \end{pmatrix} \cdot \frac{1}{22} \begin{pmatrix} 4 & 2 \\\\ -5 & 3 \end{pmatrix} = \frac{1}{22} \begin{pmatrix} 12 + 10 & 6 - 6 \\\\ 20 - 20 & 10 + 12 \end{pmatrix} = \frac{1}{22} \begin{pmatrix} 22 & 0 \\\\ 0 & 22 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix}
$$

  The inverse exists and works.
- **Row Dependency Check for $B$:**
  Performing Gaussian elimination on $B$:

$$
R_2 \leftarrow R_2 - 2R_1 \implies \begin{pmatrix} 1 & 7 \\\\ 0 & 0 \end{pmatrix}
$$

  A row of zeros appears, confirming rank 1 and determinant 0.

---

## 7. Common Mistakes to Avoid

1. **Sign Errors with Negative Entries:**
   In $ad - bc$, forgetting that subtracting a negative yields addition: $3(4) - (-2)(5) = 12 - (-10) = +22$, not $12 - 10 = 2$.
2. **Reversing the Invertibility Condition:**
   Mistakenly thinking that $\det M = 0$ means invertible. Remember: $\det M$ appears in the denominator of the inverse formula ($M^{-1} = \frac{1}{\det M} \text{adj}(M)$). Division by zero is undefined!

---

## 8. How I Would Explain This in Class

> "To find a $2 \times 2$ determinant, we multiply the main diagonal and subtract the anti-diagonal: $ad - bc$. For the first matrix, $12 - (-10) = 22$, which is non-zero, meaning the transformation preserves 2D area and can be completely reversed—so it is invertible. For the second matrix, $14 - 14 = 0$ because Row 2 is just twice Row 1; the transformation squashes the plane onto a single line, destroying information, so it cannot have an inverse."