# Problem 06: Solving a System Using the Inverse

## 1. The Original Problem

Solve

$$
Ax = b
$$

where

$$
A = \begin{pmatrix} 2 & 1 \\\\ 1 & 3 \end{pmatrix}, \qquad b = \begin{pmatrix} 5 \\\\ 7 \end{pmatrix}
$$

using $x = A^{-1}b$. Then substitute the resulting vector back into the equation and check the result.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the inverse matrix $A^{-1}$ using the $2 \times 2$ formula.
2. Solve the linear system $Ax = b$ by computing the matrix-vector product $x = A^{-1}b$.
3. Substitute the solution vector $x$ back into the original system $Ax$ to verify that it reproduces the right-hand side vector $b$ with complete precision.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Matrix Inversion Method for Linear Systems:**
  Given a linear system $Ax = b$, if $A$ is a square invertible matrix ($\det A \neq 0$), we can multiply both sides on the left by $A^{-1}$:

$$
A^{-1}(Ax) = A^{-1}b \implies (A^{-1}A)x = A^{-1}b \implies Ix = A^{-1}b \implies x = A^{-1}b
$$

- **Why Order Matters:**
  Because matrix multiplication is non-commutative, multiplying on the left by $A^{-1}$ correctly isolates $x$.
- **$2 \times 2$ Inverse Formula:**

$$
A^{-1} = \frac{1}{\det A} \begin{pmatrix} d & -b \\\\ -c & a \end{pmatrix}
$$

---

## 4. Step-by-Step Solution

### Step 1: Compute $A^{-1}$

For the matrix $A$:

$$
A = \begin{pmatrix} 2 & 1 \\\\ 1 & 3 \end{pmatrix}
$$

1. Compute the determinant:

$$
\det A = (2)(3) - (1)(1) = 6 - 1 = 5
$$

   Since $\det A = 5 \neq 0$, the inverse exists.
2. Form the adjugate matrix by swapping diagonal entries ($2 \leftrightarrow 3$) and negating off-diagonal entries ($1 \to -1$):

$$
\text{adj}(A) = \begin{pmatrix} 3 & -1 \\\\ -1 & 2 \end{pmatrix}
$$

3. Divide by the determinant:

$$
A^{-1} = \frac{1}{5} \begin{pmatrix} 3 & -1 \\\\ -1 & 2 \end{pmatrix}
$$

### Step 2: Compute the Solution Vector $x = A^{-1}b$

Multiply $A^{-1}$ by vector $b = (5, 7)^T$:

$$
x = \frac{1}{5} \begin{pmatrix} 3 & -1 \\\\ -1 & 2 \end{pmatrix} \begin{pmatrix} 5 \\\\ 7 \end{pmatrix}
$$

Evaluate the matrix-vector product:
- Top entry: $(3)(5) + (-1)(7) = 15 - 7 = 8$
- Bottom entry: $(-1)(5) + (2)(7) = -5 + 14 = 9$

Combine with the scalar factor $\frac{1}{5}$:

$$
x = \frac{1}{5} \begin{pmatrix} 8 \\\\ 9 \end{pmatrix} = \begin{pmatrix} \frac{8}{5} \\\\ \frac{9}{5} \end{pmatrix}
$$

In decimal form, this corresponds to $x_1 = 1.6$ and $x_2 = 1.8$.

---

## 5. Final Answer & Conclusion

- **The Inverse Matrix:**

$$
A^{-1} = \frac{1}{5} \begin{pmatrix} 3 & -1 \\\\ -1 & 2 \end{pmatrix}
$$

- **The Solution Vector:**

$$
x = \begin{pmatrix} \frac{8}{5} \\\\ \frac{9}{5} \end{pmatrix}
$$

- **Conclusion:** The system has a unique solution obtained directly by applying the inverse matrix operator $A^{-1}$ to the data vector $b$.

---

## 6. Quick Verification

Substitute the solution vector $x = (8/5, 9/5)^T$ back into the original system $Ax$:

$$
Ax = \begin{pmatrix} 2 & 1 \\\\ 1 & 3 \end{pmatrix} \begin{pmatrix} \frac{8}{5} \\\\ \frac{9}{5} \end{pmatrix} = \begin{pmatrix} 2\left(\frac{8}{5}\right) + 1\left(\frac{9}{5}\right) \\\\ 1\left(\frac{8}{5}\right) + 3\left(\frac{9}{5}\right) \end{pmatrix}
$$

Perform the fraction additions:
- First equation: $\frac{16}{5} + \frac{9}{5} = \frac{25}{5} = 5$
- Second equation: $\frac{8}{5} + \frac{27}{5} = \frac{35}{5} = 7$

Putting them together:

$$
Ax = \begin{pmatrix} 5 \\\\ 7 \end{pmatrix} = b
$$

Both original equations are satisfied with absolute precision, confirming our solution.

---

## 7. Common Mistakes to Avoid

1. **Multiplying on the Wrong Side:**
   Writing $x = b A^{-1}$. A column vector ($2 \times 1$) cannot be multiplied on the right by a $2 \times 2$ matrix; dimensionally $(2 \times 1)(2 \times 2)$ is undefined. The inverse must multiply on the left: $x = A^{-1} b$.
2. **Premature Decimals:**
   Converting fractions to rounded decimals prematurely can cause rounding errors. Keeping exact fractions ($\frac{8}{5}, \frac{9}{5}$) ensures exact verification.

---

## 8. How I Would Explain This in Class

> "To solve $Ax = b$ using the inverse matrix, we first compute $A^{-1}$ with rows $(3/5, -1/5)$ and $(-1/5, 2/5)$. Multiplying this matrix on the left of vector $b = (5, 7)^T$ calculates $(1/5) (15 - 7, -5 + 14)^T = (8/5, 9/5)^T$. When we plug these values back into $Ax$, we get $2(8/5) + 9/5 = 5$ and $8/5 + 3(9/5) = 7$, matching vector $b$ perfectly."