# Problem 04: Triangular Matrix

## 1. The Original Problem

Without expanding the determinant, compute

$$
\det\begin{pmatrix} 2 & 4 & 1 \\\\ 0 & -3 & 5 \\\\ 0 & 0 & 7 \end{pmatrix}
$$

State the rule for an arbitrary triangular matrix and explain it using this example.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the determinant of the given upper triangular matrix without performing a full expansion from scratch.
2. Formulate the general rule/theorem for the determinant of any triangular matrix (upper triangular, lower triangular, or diagonal).
3. Provide a clear mathematical explanation (via induction/cofactor expansion) demonstrating why this rule works.

---

## 3. Before Calculating: What Idea Do We Need?

- **Definition of Upper Triangular Matrix:**
  A matrix $T = (t_{ij})$ is upper triangular if all entries below the main diagonal are zero: $t_{ij} = 0$ whenever $i > j$.
- **The Triangular Determinant Rule:**
  The determinant of any triangular matrix is simply the product of its main diagonal entries:

$$
\det T = \prod_{i=1}^n t_{ii} = t_{11} \cdot t_{22} \cdots t_{nn}
$$

  This rule holds equally for upper triangular, lower triangular, and diagonal matrices.

---

## 4. Step-by-Step Solution

### Step 1: Identify the Matrix Structure and Diagonal Entries

The matrix is:

$$
T = \begin{pmatrix} 2 & 4 & 1 \\\\ 0 & -3 & 5 \\\\ 0 & 0 & 7 \end{pmatrix}
$$

Notice that all entries below the main diagonal are zeros: $t_{21} = 0$, $t_{31} = 0$, and $t_{32} = 0$.
The entries along the main diagonal are:
- $t_{11} = 2$
- $t_{22} = -3$
- $t_{33} = 7$

### Step 2: Apply the Diagonal Product Rule

According to the rule:

$$
\det T = t_{11} \cdot t_{22} \cdot t_{33} = (2) \cdot (-3) \cdot (7)
$$

Multiply the numbers:

$$
\det T = -6 \cdot 7 = -42
$$

### Step 3: Explain Why the Rule Works Using This Example

Why does the determinant reduce purely to the diagonal product?
Consider expanding along the **first column** of $T$, which contains entries $(2, 0, 0)^T$:

$$
\det T = 2 \cdot \begin{vmatrix} -3 & 5 \\\\ 0 & 7 \end{vmatrix} - 0 \cdot \begin{vmatrix} 4 & 1 \\\\ 0 & 7 \end{vmatrix} + 0 \cdot \begin{vmatrix} 4 & 1 \\\\ -3 & 5 \end{vmatrix}
$$

The zeros in the column cause all cofactors except the first to vanish completely:

$$
\det T = 2 \cdot \begin{vmatrix} -3 & 5 \\\\ 0 & 7 \end{vmatrix}
$$

Now look at the remaining $2 \times 2$ determinant: it is also upper triangular! Its value is:

$$
\begin{vmatrix} -3 & 5 \\\\ 0 & 7 \end{vmatrix} = (-3)(7) - (5)(0) = (-3)(7)
$$

Substituting back:

$$
\det T = 2 \cdot [(-3) \cdot 7] = -42
$$

At every stage of cofactor expansion along the first column, only the diagonal entry survives and multiplies the smaller triangular submatrix. Hence, by induction, the determinant of any $n \times n$ triangular matrix is always the product of all its $n$ diagonal entries.

---

## 5. Final Answer & Conclusion

- **Calculated Determinant:**

$$
\det\begin{pmatrix} 2 & 4 & 1 \\\\ 0 & -3 & 5 \\\\ 0 & 0 & 7 \end{pmatrix} = (2)(-3)(7) = -42
$$

- **General Rule:** For any $n \times n$ upper triangular, lower triangular, or diagonal matrix $T$:

$$
\det T = t_{11} t_{22} \cdots t_{nn}
$$

- **Conclusion:** The off-diagonal entries above the diagonal have zero influence on the determinant because in Laplace expansion along the first column, their corresponding minors are multiplied by zero.

---

## 6. Quick Verification

Verify using Sarrus' rule:
- Downward diagonals:
  - $(2)(-3)(7) = -42$
  - $(4)(5)(0) = 0$
  - $(1)(0)(0) = 0$
  - Sum $= -42$
- Upward diagonals:
  - $(0)(-3)(1) = 0$
  - $(0)(5)(2) = 0$
  - $(7)(0)(4) = 0$
  - Sum $= 0$
- Result: $-42 - 0 = -42$. Exact match!

---

## 7. Common Mistakes to Avoid

1. **Wasting Time on Full Expansion:**
   Writing out all 6 Sarrus terms or general 3x3 cofactor formulas. Recognizing triangular structure saves time and eliminates algebra errors.
2. **Assuming the Rule Holds for Almost-Triangular Matrices:**
   If even a single entry below the main diagonal is non-zero (e.g., $t_{31} \neq 0$), the matrix is NOT triangular, and the simple diagonal product rule fails.

---

## 8. How I Would Explain This in Class

> "Because this matrix has only zeros below the main diagonal, expanding down the first column eliminates every term except the top-left entry $2$, leaving a smaller $2 \times 2$ triangular determinant. Expanding that submatrix down its first column isolates $-3 \cdot 7$. This chain reaction shows that for any triangular matrix, all off-diagonal values vanish in the expansion, leaving only the product of the diagonal elements: $2 \cdot (-3) \cdot 7 = -42$."
