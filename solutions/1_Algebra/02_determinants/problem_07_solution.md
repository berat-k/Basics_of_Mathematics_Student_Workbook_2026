# Problem 07: Using Properties Instead of Recomputing

## 1. The Original Problem

Suppose that for a $3 \times 3$ matrix, $\det A = -4$. Compute:

$$
\det(2A), \qquad \det(A^T), \qquad \det(A^2), \qquad \det(-A)
$$

Justify each answer using the appropriate property.

---

## 2. What Are We Trying to Find?

We need to determine the numerical values of:
1. $\det(2A)$
2. $\det(A^T)$
3. $\det(A^2)$
4. $\det(-A)$

given only the dimension $n = 3$ and $\det A = -4$, without knowing any individual matrix entries, by systematically citing the exact algebraic determinant property for each transformation.

---

## 3. Before Calculating: What Idea Do We Need?

For any $n \times n$ matrix $A$ and scalar $c \in \mathbb{R}$:
1. **Scalar Multiplication of an $n \times n$ Matrix:**

$$
\det(c A) = c^n \det A
$$

   *Why:* Multiplying a matrix by scalar $c$ multiplies *every one of its $n$ rows* by $c$. By multilinearity, factoring $c$ out from each row produces a factor of $c^n$.
2. **Transpose Property:**

$$
\det(A^T) = \det A
$$

   *Why:* The determinant formula via permutations is symmetric under swapping row and column indices.
3. **Multiplicative Property (Powers):**

$$
\det(AB) = \det A \cdot \det B \implies \det(A^2) = \det(A \cdot A) = (\det A)^2
$$

   *Why:* The volume scaling factor of composing two linear transformations is the product of their individual scaling factors.
4. **Special Case for Negative Matrix:**
   Since $-A = (-1)A$, this is a scalar multiplication with $c = -1$:

$$
\det(-A) = (-1)^n \det A
$$

---

## 4. Step-by-Step Solution

Matrix $A$ has dimension $n = 3$, and its determinant is $\det A = -4$.

### Step 1: Compute $\det(2A)$
- **Property:** For an $n \times n$ matrix, $\det(c A) = c^n \det A$.
- Here $c = 2$ and $n = 3$, so the scaling exponent is $3$:

$$
\det(2A) = 2^3 \det A = 8 \cdot (-4) = -32
$$

### Step 2: Compute $\det(A^T)$
- **Property:** The determinant of a transposed matrix equals the determinant of the original matrix: $\det(A^T) = \det A$.
- Applying directly:

$$
\det(A^T) = \det A = -4
$$

### Step 3: Compute $\det(A^2)$
- **Property:** Determinant of a matrix product is the product of their determinants: $\det(XY) = \det X \cdot \det Y$.
- For $A^2 = A \cdot A$:

$$
\det(A^2) = (\det A)^2 = (-4)^2 = 16
$$

### Step 4: Compute $\det(-A)$
- **Property:** We view $-A$ as scalar multiplication by $c = -1$.
- Since $n = 3$:

$$
\det(-A) = (-1)^3 \det A = (-1) \cdot (-4) = 4
$$

---

## 5. Final Answer & Conclusion

- $\det(2A) = 2^3 \cdot (-4) = -32$
- $\det(A^T) = \det A = -4$
- $\det(A^2) = (-4)^2 = 16$
- $\det(-A) = (-1)^3 \cdot (-4) = 4$

All values are derived directly from the fundamental structural axioms of determinants without requiring the specific entries of $A$.

---

## 6. Quick Verification

Let us construct a concrete $3 \times 3$ diagonal matrix satisfying $\det A = -4$:

$$
A = \begin{pmatrix} -4 & 0 & 0 \\\\ 0 & 1 & 0 \\\\ 0 & 0 & 1 \end{pmatrix} \implies \det A = (-4)(1)(1) = -4
$$

Check each operation:
- For $2A$:

$$
2A = \begin{pmatrix} -8 & 0 & 0 \\\\ 0 & 2 & 0 \\\\ 0 & 0 & 2 \end{pmatrix} \implies \det(2A) = (-8)(2)(2) = -32
$$

- For $A^T$:

$$
A^T = A \implies \det(A^T) = -4
$$

- For $A^2$:

$$
A^2 = \begin{pmatrix} 16 & 0 & 0 \\\\ 0 & 1 & 0 \\\\ 0 & 0 & 1 \end{pmatrix} \implies \det(A^2) = (16)(1)(1) = 16
$$

- For $-A$:

$$
-A = \begin{pmatrix} 4 & 0 & 0 \\\\ 0 & -1 & 0 \\\\ 0 & 0 & -1 \end{pmatrix} \implies \det(-A) = (4)(-1)(-1) = 4
$$

All properties hold consistently.

---

## 7. Common Mistakes to Avoid

1. **The Linear Scaling Myth ($\det(cA) \neq c \det A$):**
   Writing $\det(2A) = 2 \det A = -8$. In $3$ dimensions, scaling a shape by factor $2$ increases its 3D volume by $2^3 = 8$, so the determinant scales by $8$.
2. **Forgetting Dimension Parity on $-A$:**
   Thinking $\det(-A) = -\det A$ is universally true. It is true for odd dimensions ($n = 1, 3, 5$), but for even dimensions ($n = 2, 4$), $\det(-A) = (-1)^n \det A = +\det A$.

---

## 8. How I Would Explain This in Class

> "Because $A$ is a $3 \times 3$ matrix, multiplying the entire matrix by $2$ scales every one of its three rows by $2$, pulling out a factor of $2^3 = 8$, which gives $8 \cdot (-4) = -32$. Transposing leaves the determinant unchanged at $-4$, squaring the matrix squares the volume factor to $(-4)^2 = 16$, and negating the matrix pulls out $(-1)^3 = -1$, yielding $(-1) \cdot (-4) = 4$."