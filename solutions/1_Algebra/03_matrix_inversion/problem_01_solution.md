# Problem 01: Definition of the Inverse

## 1. The Original Problem

For

$$
A = \begin{pmatrix} 2 & 1 \\\\ 1 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & -1 \\\\ -1 & 2 \end{pmatrix}
$$

check, without using a formula, whether $B = A^{-1}$. Compute $AB$ and $BA$ and relate the result to the definition of the inverse.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the matrix product $AB$.
2. Compute the reversed matrix product $BA$.
3. Determine whether both products equal the $2 \times 2$ identity matrix $I$.
4. Connect this calculation directly to the formal mathematical definition of an inverse matrix to conclude whether $B = A^{-1}$, without relying on determinant or adjugate formulas.

---

## 3. Before Calculating: What Idea Do We Need?

- **Definition of the Inverse Matrix:**
  Let $A$ be an $n \times n$ square matrix. An $n \times n$ matrix $B$ is called the **inverse** of $A$ (denoted $A^{-1}$) if and only if:

$$
AB = I_n \qquad \text{and} \qquad BA = I_n
$$

  where $I_n$ is the $n \times n$ identity matrix with ones on the main diagonal and zeros elsewhere:

$$
I_2 = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix}
$$

- **Why We Check Both Products:**
  In general, matrix multiplication is not commutative ($XY \neq YX$). By definition, a true two-sided inverse must satisfy multiplication in both directions.
- **The Definition vs. Formulas:**
  Formulas like $A^{-1} = \frac{1}{\det A}\text{adj}(A)$ are derived tools. The foundational definition of being an inverse is purely operational: multiplying the two matrices must produce the identity.

---

## 4. Step-by-Step Solution

### Step 1: Compute the Product $AB$

We multiply $A$ ($2 \times 2$) by $B$ ($2 \times 2$):

$$
A = \begin{pmatrix} 2 & 1 \\\\ 1 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & -1 \\\\ -1 & 2 \end{pmatrix}
$$

Apply the row-by-column rule:
- **Row 1, Column 1:** $(2)(1) + (1)(-1) = 2 - 1 = 1$
- **Row 1, Column 2:** $(2)(-1) + (1)(2) = -2 + 2 = 0$
- **Row 2, Column 1:** $(1)(1) + (1)(-1) = 1 - 1 = 0$
- **Row 2, Column 2:** $(1)(-1) + (1)(2) = -1 + 2 = 1$

Putting the entries together:

$$
AB = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} = I
$$

### Step 2: Compute the Product $BA$

Now multiply in reverse order, taking $B$ first and $A$ second:

Apply the row-by-column rule:
- **Row 1, Column 1:** $(1)(2) + (-1)(1) = 2 - 1 = 1$
- **Row 1, Column 2:** $(1)(1) + (-1)(1) = 1 - 1 = 0$
- **Row 2, Column 1:** $(-1)(2) + (2)(1) = -2 + 2 = 0$
- **Row 2, Column 2:** $(-1)(1) + (2)(1) = -1 + 2 = 1$

Putting the entries together:

$$
BA = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} = I
$$

### Step 3: Relate to the Definition of the Inverse

According to the mathematical definition of an inverse matrix:
1. $AB = I$ confirms that $B$ acts as a right-inverse of $A$.
2. $BA = I$ confirms that $B$ acts as a left-inverse of $A$.

Because both products evaluate to the identity matrix $I$, matrix $B$ satisfies the definition of the two-sided inverse of $A$ with complete exactness:

$$
B = A^{-1}
$$

---

## 5. Final Answer & Conclusion

- **Matrix Products:**

$$
AB = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} = I, \qquad BA = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} = I
$$

- **Conclusion:** Yes, $B = A^{-1}$. Both products equal the identity matrix, which directly satisfies the foundational definition of matrix inversion without requiring any determinant formula.

---

## 6. Quick Verification

Verify using the standard $2 \times 2$ inverse formula:
- $\det A = (2)(1) - (1)(1) = 2 - 1 = 1$.
- Swap diagonal entries and negate off-diagonal entries:

$$
A^{-1} = \frac{1}{1} \begin{pmatrix} 1 & -1 \\\\ -1 & 2 \end{pmatrix} = \begin{pmatrix} 1 & -1 \\\\ -1 & 2 \end{pmatrix} = B
$$

The formula confirms our multiplication check.

---

## 7. Common Mistakes to Avoid

1. **Checking Only One Direction:**
   Verifying only $AB = I$ and skipping $BA$. While for finite-dimensional square matrices $AB = I$ implies $BA = I$, the definition explicitly requires checking both sides to guarantee a two-sided inverse.
2. **Confusing Inverses with Negation:**
   Thinking the inverse of a matrix is obtained by negating entries. An inverse undoes the transformation via multiplication, producing $I$, not $0$.

---

## 8. How I Would Explain This in Class

> "To verify whether $B$ is the inverse of $A$ without using any formulas, we simply multiply them: if they are true inverses, their product must be the identity matrix $I$. Computing $AB$ gives row-column dot products $(2-1, -2+2)$ and $(1-1, -1+2)$, yielding the identity matrix $I$, and reversing the order $BA$ also gives $I$. Because multiplying in both directions leaves every vector unchanged, $B$ is indeed $A^{-1}$ by definition."
