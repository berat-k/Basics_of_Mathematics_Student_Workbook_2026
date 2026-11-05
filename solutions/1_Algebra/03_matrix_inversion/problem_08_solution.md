# Problem 08: Inverse of a Transformation

## 1. The Original Problem

The matrix

$$
S = \begin{pmatrix} 2 & 0 \\\\ 0 & \frac{1}{2} \end{pmatrix}
$$

describes a scaling of the plane. Find $S^{-1}$ and explain geometrically what the inverse transformation does. Check the action of the pair $S, S^{-1}$ on one simple vector.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the algebraic inverse matrix $S^{-1}$.
2. Explain the geometric meaning of the transformation represented by $S$ and how $S^{-1}$ undoes it.
3. Choose a simple test vector $v \in \mathbb{R}^2$ and verify by direct calculation that applying $S$ and then $S^{-1}$ returns the original vector $v$: $S^{-1}(Sv) = v$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Geometric Action of a Diagonal Matrix:**
  A diagonal matrix:

$$
D = \begin{pmatrix} \lambda_1 & 0 \\\\ 0 & \lambda_2 \end{pmatrix}
$$

  scales the horizontal coordinate $x$ by a factor of $\lambda_1$ and the vertical coordinate $y$ by a factor of $\lambda_2$:

$$
D \begin{pmatrix} x \\\\ y \end{pmatrix} = \begin{pmatrix} \lambda_1 x \\\\ \lambda_2 y \end{pmatrix}
$$

- **The Geometric Inverse:**
  The inverse transformation must completely undo these scaling factors:
  - If a transformation stretches coordinates by a factor of $\lambda$, the inverse transformation must compress coordinates by $\frac{1}{\lambda}$.
  - The inverse of a diagonal matrix is therefore obtained by taking the reciprocal of each non-zero diagonal element:

$$
D^{-1} = \begin{pmatrix} \frac{1}{\lambda_1} & 0 \\\\ 0 & \frac{1}{\lambda_2} \end{pmatrix}
$$

---

## 4. Step-by-Step Solution

### Step 1: Compute the Algebraic Inverse $S^{-1}$

Given:

$$
S = \begin{pmatrix} 2 & 0 \\\\ 0 & \frac{1}{2} \end{pmatrix}
$$

1. Calculate the determinant:

$$
\det S = (2)\left(\frac{1}{2}\right) - (0)(0) = 1
$$

   Since $\det S = 1 \neq 0$, the inverse exists.
2. Invert the diagonal matrix by taking the reciprocal of each diagonal entry:
   - Reciprocal of $2$: $\frac{1}{2}$
   - Reciprocal of $\frac{1}{2}$: $\frac{1}{1/2} = 2$

$$
S^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\\\ 0 & 2 \end{pmatrix}
$$

### Step 2: Geometric Explanation of $S$ and $S^{-1}$

1. **What $S$ does to the plane:**
   For any point $(x, y)^T$:

$$
S \begin{pmatrix} x \\\\ y \end{pmatrix} = \begin{pmatrix} 2x \\\\ \frac{1}{2}y \end{pmatrix}
$$

   - It **doubles** the horizontal distance from the $y$-axis (horizontal stretch by a factor of $2$).
   - It **halves** the vertical distance from the $x$-axis (vertical compression by a factor of $\frac{1}{2}$).
   - Notice that because $\det S = 1$, the overall area of shapes is preserved (areas do not change size, but shapes become wider and flatter).
2. **What $S^{-1}$ does geometrically:**
   For any point $(x', y')^T$:

$$
S^{-1} \begin{pmatrix} x' \\\\ y' \end{pmatrix} = \begin{pmatrix} \frac{1}{2}x' \\\\ 2y' \end{pmatrix}
$$

   - It **halves** the horizontal distance (compresses horizontally by a factor of $\frac{1}{2}$).
   - It **doubles** the vertical distance (stretches vertically by a factor of $2$).
   - Geometrically, $S^{-1}$ completely reverses the distortion introduced by $S$, restoring the original aspect ratio and coordinates of every point in the plane.

---

## 5. Final Answer & Conclusion

- **Inverse Matrix:**

$$
S^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\\\ 0 & 2 \end{pmatrix}
$$

- **Geometric Meaning:** $S$ stretches the $x$-axis by $2$ and compresses the $y$-axis by $\frac{1}{2}$. Its inverse $S^{-1}$ reverses this by compressing the $x$-axis by $\frac{1}{2}$ and stretching the $y$-axis by $2$.

---

## 6. Quick Verification

Choose a concrete vector, for example:

$$
v = \begin{pmatrix} 4 \\\\ 6 \end{pmatrix}
$$

1. Apply the forward transformation $S$:

$$
w = Sv = \begin{pmatrix} 2 & 0 \\\\ 0 & \frac{1}{2} \end{pmatrix} \begin{pmatrix} 4 \\\\ 6 \end{pmatrix} = \begin{pmatrix} 2(4) \\\\ \frac{1}{2}(6) \end{pmatrix} = \begin{pmatrix} 8 \\\\ 3 \end{pmatrix}
$$

   The vector was stretched horizontally to $8$ and shrunk vertically to $3$.
2. Apply the inverse transformation $S^{-1}$ to the result $w$:

$$
S^{-1} w = \begin{pmatrix} \frac{1}{2} & 0 \\\\ 0 & 2 \end{pmatrix} \begin{pmatrix} 8 \\\\ 3 \end{pmatrix} = \begin{pmatrix} \frac{1}{2}(8) \\\\ 2(3) \end{pmatrix} = \begin{pmatrix} 4 \\\\ 6 \end{pmatrix} = v
$$

The composite action $S^{-1}(Sv) = v$ perfectly restores the original vector.
Also, the matrix product gives:

$$
S^{-1} S = \begin{pmatrix} \frac{1}{2} & 0 \\\\ 0 & 2 \end{pmatrix} \begin{pmatrix} 2 & 0 \\\\ 0 & \frac{1}{2} \end{pmatrix} = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} = I
$$

---

## 7. Common Mistakes to Avoid

1. **Inverting via Negation:**
   Negating diagonal entries (writing $-2$ and $-1/2$) instead of taking reciprocals. Negating coordinates reflects them across the axes; inversion of scaling requires taking **reciprocals** ($\frac{1}{\lambda}$), not negatives.
2. **Forgetting Off-Diagonal Zeros:**
   Trying to apply full cofactor expansion when the matrix is purely diagonal. Diagonal matrices invert element-by-element along the diagonal in one step.

---

## 8. How I Would Explain This in Class

> "Matrix $S$ acts as a geometric distorting filter: it doubles every $x$-coordinate and cuts every $y$-coordinate in half. To completely undo this and return to our original shape, the inverse operation must do the exact opposite: cut $x$ in half and double $y$. Therefore, the inverse matrix has diagonal entries $1/2$ and $2$. If we test this on the vector $(4, 6)^T$, $S$ transforms it into $(8, 3)^T$, and applying $S^{-1}$ immediately returns $(4, 6)^T$, confirming that the inverse restores the exact original geometry."