# Problem 02: Formula for a 2×2 Matrix

## 1. The Original Problem

Find the inverse of

$$
A = \begin{pmatrix} 3 & 2 \\\\ 5 & 4 \end{pmatrix}
$$

using the formula for a $2 \times 2$ matrix. At the end, check the result by computing one product with $A$.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the determinant of matrix $A$ to verify that it is invertible ($\det A \neq 0$).
2. Form the adjugate matrix by swapping main diagonal entries and negating off-diagonal entries.
3. Compute the explicit inverse matrix $A^{-1}$ using the classical $2 \times 2$ inverse formula.
4. Verify the inverse by directly calculating the product $A A^{-1}$ and confirming that it produces the identity matrix $I$.

---

## 3. Before Calculating: What Idea Do We Need?

- **The $2 \times 2$ Inverse Formula:**
  For any general $2 \times 2$ matrix:

$$
M = \begin{pmatrix} a & b \\\\ c & d \end{pmatrix}
$$

  if its determinant $\det M = ad - bc \neq 0$, the inverse exists and is given explicitly by:

$$
M^{-1} = \frac{1}{\det M} \begin{pmatrix} d & -b \\\\ -c & a \end{pmatrix} = \frac{1}{ad - bc} \begin{pmatrix} d & -b \\\\ -c & a \end{pmatrix}
$$

- **Recipe for the Matrix Part:**
  - **Swap** the two entries on the main diagonal ($a \leftrightarrow d$).
  - **Negate** (change the sign of) the two entries on the off-diagonal ($b \to -b$, $c \to -c$).
  - **Divide** every entry by the determinant scalar $ad - bc$.

---

## 4. Step-by-Step Solution

### Step 1: Compute the Determinant of $A$

Our matrix is:

$$
A = \begin{pmatrix} 3 & 2 \\\\ 5 & 4 \end{pmatrix}
$$

Identify the entries: $a = 3$, $b = 2$, $c = 5$, and $d = 4$.
Calculate the determinant:

$$
\det A = ad - bc = (3)(4) - (2)(5) = 12 - 10 = 2
$$

Since $\det A = 2 \neq 0$, matrix $A$ is non-singular and its inverse $A^{-1}$ exists.

### Step 2: Apply the $2 \times 2$ Inversion Recipe

1. Swap main diagonal entries ($3$ and $4$):
   $a_{11}' = 4$, $a_{22}' = 3$.
2. Negate off-diagonal entries ($2$ and $5$):
   $a_{12}' = -2$, $a_{21}' = -5$.
3. Form the adjugate matrix:

$$
\text{adj}(A) = \begin{pmatrix} 4 & -2 \\\\ -5 & 3 \end{pmatrix}
$$

4. Multiply by $\frac{1}{\det A} = \frac{1}{2}$:

$$
A^{-1} = \frac{1}{2} \begin{pmatrix} 4 & -2 \\\\ -5 & 3 \end{pmatrix}
$$

Distributing the scalar factor $\frac{1}{2}$ into the entries gives:

$$
A^{-1} = \begin{pmatrix} 2 & -1 \\\\ -\frac{5}{2} & \frac{3}{2} \end{pmatrix}
$$

---

## 5. Final Answer & Conclusion

- **The Inverse Matrix:**

$$
A^{-1} = \frac{1}{2} \begin{pmatrix} 4 & -2 \\\\ -5 & 3 \end{pmatrix} = \begin{pmatrix} 2 & -1 \\\\ -\frac{5}{2} & \frac{3}{2} \end{pmatrix}
$$

- **Conclusion:** Matrix $A$ is invertible with determinant $2$. The inverse is obtained directly by scaling the adjugate matrix by the reciprocal of the determinant.

---

## 6. Quick Verification

Multiply $A$ by $A^{-1}$ using the scalar-factored form for clean arithmetic:

$$
A A^{-1} = \begin{pmatrix} 3 & 2 \\\\ 5 & 4 \end{pmatrix} \left[ \frac{1}{2} \begin{pmatrix} 4 & -2 \\\\ -5 & 3 \end{pmatrix} \right] = \frac{1}{2} \left[ \begin{pmatrix} 3 & 2 \\\\ 5 & 4 \end{pmatrix} \begin{pmatrix} 4 & -2 \\\\ -5 & 3 \end{pmatrix} \right]
$$

Evaluate the row-by-column dot products:
- **Row 1, Column 1:** $(3)(4) + (2)(-5) = 12 - 10 = 2$
- **Row 1, Column 2:** $(3)(-2) + (2)(3) = -6 + 6 = 0$
- **Row 2, Column 1:** $(5)(4) + (4)(-5) = 20 - 20 = 0$
- **Row 2, Column 2:** $(5)(-2) + (4)(3) = -10 + 12 = 2$

Substitute back:

$$
A A^{-1} = \frac{1}{2} \begin{pmatrix} 2 & 0 \\\\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} = I
$$

The product yields the exact identity matrix $I$, confirming the inverse is correct.

---

## 7. Common Mistakes to Avoid

1. **Mixing Up Swapping and Negating:**
   Accidentally negating the main diagonal and swapping the off-diagonal. The rule is strictly: **swap** the diagonal elements, **negate** the off-diagonal elements.
2. **Forgetting to Divide by the Determinant:**
   Leaving the answer as the adjugate matrix $\text{adj}(A)$ without multiplying by $\frac{1}{\det A}$.
3. **Premature Fraction Arithmetic:**
   Working with fractions during the verification step makes calculation slower and prone to slips. Keeping the scalar $\frac{1}{2}$ out front until the final step keeps all matrix multiplication in clean integers.

---

## 8. How I Would Explain This in Class

> "To invert a $2 \times 2$ matrix, we first compute its determinant: $3(4) - 2(5) = 2$. Then we swap the main diagonal entries to get $4$ and $3$, change the signs of the off-diagonal entries to get $-2$ and $-5$, and divide the resulting matrix by $2$. Multiplying $A$ by our candidate inverse produces $(1/2) \cdot 2I = I$, proving immediately that our result is the exact inverse."