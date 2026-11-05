# Problem 10: Inverse of a Diagonal Matrix

## 1. The Original Problem

Given

$$
D = \begin{pmatrix} 2 & 0 & 0 \\\\ 0 & -3 & 0 \\\\ 0 & 0 & 5 \end{pmatrix}, \qquad E = \begin{pmatrix} 2 & 0 & 0 \\\\ 0 & 0 & 0 \\\\ 0 & 0 & 5 \end{pmatrix}
$$

Without using Gauss–Jordan elimination, decide which matrix is invertible. For the invertible matrix, give the inverse and check the result by multiplication.

---

## 2. What Are We Trying to Find?

We need to:
1. Determine by structural inspection which of the two diagonal matrices ($D$ or $E$) is invertible, without performing full Gaussian elimination.
2. State the necessary and sufficient condition for a diagonal matrix to be invertible.
3. For the invertible matrix, write down its inverse immediately using the diagonal reciprocal rule.
4. Verify the inverse by calculating the product with the original matrix to produce $I_3$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Invertibility of a Diagonal Matrix:**
  For any $n \times n$ diagonal matrix:

$$
M = \begin{pmatrix} d_1 & 0 & \cdots & 0 \\\\ 0 & d_2 & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & d_n \end{pmatrix}
$$

  its determinant is the product of all diagonal entries:

$$
\det M = d_1 \cdot d_2 \cdots d_n
$$

  Therefore:

$$
M \text{ is invertible} \iff \det M \neq 0 \iff d_i \neq 0 \text{ for every } i = 1, \dots, n
$$

  A diagonal matrix is invertible **if and only if none of its diagonal entries are zero**.
- **Explicit Inverse of an Invertible Diagonal Matrix:**
  When all $d_i \neq 0$, the inverse is also a diagonal matrix whose entries are simply the scalar reciprocals of the original diagonal entries:

$$
M^{-1} = \begin{pmatrix} \frac{1}{d_1} & 0 & \cdots & 0 \\\\ 0 & \frac{1}{d_2} & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \frac{1}{d_n} \end{pmatrix}
$$

---

## 4. Step-by-Step Solution

### Step 1: Analyze Matrix $D$

Matrix $D$ is:

$$
D = \begin{pmatrix} 2 & 0 & 0 \\\\ 0 & -3 & 0 \\\\ 0 & 0 & 5 \end{pmatrix}
$$

- Main diagonal entries: $d_{11} = 2$, $d_{22} = -3$, $d_{33} = 5$.
- Determinant: $\det D = (2)(-3)(5) = -30$.
- Since all diagonal entries are non-zero ($\det D = -30 \neq 0$), matrix $D$ has full rank ($3$) and is **invertible**.

### Step 2: Analyze Matrix $E$

Matrix $E$ is:

$$
E = \begin{pmatrix} 2 & 0 & 0 \\\\ 0 & 0 & 0 \\\\ 0 & 0 & 5 \end{pmatrix}
$$

- Main diagonal entries: $e_{11} = 2$, $e_{22} = 0$, $e_{33} = 5$.
- Notice that the entry in position $(2, 2)$ is $0$.
- Consequently, the entire second row is a zero vector:

$$
R_2 = (0, 0, 0)
$$

- Determinant: $\det E = (2)(0)(5) = 0$.
- Because it contains an all-zero row, $\text{rank}(E) \le 2 < 3$, and any vector with a non-zero $y$-component along the $y$-axis maps to the origin: $E(0, 1, 0)^T = (0, 0, 0)^T$.
- Since $\det E = 0$, matrix $E$ is **not invertible** (it is singular).

### Step 3: Write Down the Inverse Matrix $D^{-1}$

Using the diagonal reciprocal rule, invert each non-zero diagonal entry:
- $\frac{1}{d_{11}} = \frac{1}{2}$
- $\frac{1}{d_{22}} = \frac{1}{-3} = -\frac{1}{3}$
- $\frac{1}{d_{33}} = \frac{1}{5}$

Therefore:

$$
D^{-1} = \begin{pmatrix} \frac{1}{2} & 0 & 0 \\\\ 0 & -\frac{1}{3} & 0 \\\\ 0 & 0 & \frac{1}{5} \end{pmatrix}
$$

---

## 5. Final Answer & Conclusion

- **Invertibility Decision:**
  - Matrix $D$ is **invertible** because all its diagonal entries are non-zero ($\det D = -30 \neq 0$).
  - Matrix $E$ is **not invertible** because diagonal entry $e_{22} = 0$, creating an all-zero row ($\det E = 0$).
- **The Inverse Matrix of $D$:**

$$
D^{-1} = \begin{pmatrix} \frac{1}{2} & 0 & 0 \\\\ 0 & -\frac{1}{3} & 0 \\\\ 0 & 0 & \frac{1}{5} \end{pmatrix}
$$

---

## 6. Quick Verification

Multiply $D$ by $D^{-1}$:

$$
D D^{-1} = \begin{pmatrix} 2 & 0 & 0 \\\\ 0 & -3 & 0 \\\\ 0 & 0 & 5 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & 0 & 0 \\\\ 0 & -\frac{1}{3} & 0 \\\\ 0 & 0 & \frac{1}{5} \end{pmatrix}
$$

Because both matrices are diagonal, multiplying them amounts to multiplying corresponding diagonal entries:
- Position $(1, 1)$: $2 \cdot \frac{1}{2} = 1$
- Position $(2, 2)$: $(-3) \cdot \left(-\frac{1}{3}\right) = 1$
- Position $(3, 3)$: $5 \cdot \frac{1}{5} = 1$
- All off-diagonal entries remain $0$.

$$
D D^{-1} = \begin{pmatrix} 1 & 0 & 0 \\\\ 0 & 1 & 0 \\\\ 0 & 0 & 1 \end{pmatrix} = I_3
$$

The product yields the exact identity matrix $I_3$.

---

## 7. Common Mistakes to Avoid

1. **Wasting Time on Gauss–Jordan:**
   Setting up a large $[D \mid I_3]$ augmented matrix. The structure of diagonal matrices already decouples each coordinate; recognizing this saves time and eliminates arithmetic mistakes.
2. **Missing a Zero Diagonal Entry:**
   Assuming a diagonal matrix is always invertible without checking whether any diagonal entry is $0$. A single zero on the diagonal immediately forces the determinant to zero.

---

## 8. How I Would Explain This in Class

> "A diagonal matrix scales each coordinate axis independently. For a diagonal matrix to be invertible, none of its diagonal scaling factors can be zero, because a zero scaling factor completely squashes that axis down to a point. Therefore, matrix $E$ cannot be inverted because $e_{22} = 0$, while matrix $D$ is invertible with non-zero diagonal entries $2, -3,$ and $5$. To undo scaling by $2, -3,$ and $5$, the inverse must simply scale by their reciprocals: $1/2, -1/3,$ and $1/5$, which immediately gives $D^{-1}$."
