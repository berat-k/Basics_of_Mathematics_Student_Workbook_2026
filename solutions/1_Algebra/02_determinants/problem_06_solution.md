# Problem 06: Parameter and Invertibility

## 1. The Original Problem

For

$$
A(t) = \begin{pmatrix} t & 1 \\\\ 2 & t \end{pmatrix}
$$

find all values of $t$ for which the matrix is not invertible. Explain how your answer is related to the determinant being zero.

---

## 2. What Are We Trying to Find?

We need to:
1. Express $\det A(t)$ algebraically as a function of the real parameter $t$.
2. Determine all specific values of $t$ that make $A(t)$ non-invertible (singular).
3. Connect the algebraic condition $\det A(t) = 0$ to the geometric and structural concept of linear dependence between the rows and columns.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Determinant of $A(t)$:**
  For a $2 \times 2$ matrix:

$$
\det\begin{pmatrix} a & b \\\\ c & d \end{pmatrix} = ad - bc
$$

- **The Invertibility Theorem:**
  A square matrix $M$ fails to have an inverse if and only if its determinant vanishes:

$$
M \text{ is not invertible (singular)} \iff \det M = 0
$$

  - When $\det M \neq 0$, the inverse formula $M^{-1} = \frac{1}{\det M} \text{adj}(M)$ is well-defined because division by $\det M$ is permitted.
  - When $\det M = 0$, the transformation collapses area down to zero, meaning multiple distinct input vectors map to the same output vector (e.g., $A(t)x = 0$ has non-trivial solutions). Thus, the transformation is not injective and cannot be inverted.

---

## 4. Step-by-Step Solution

### Step 1: Compute $\det A(t)$

Apply the $2 \times 2$ determinant formula to matrix $A(t)$:

$$
\det A(t) = (t)(t) - (1)(2) = t^2 - 2
$$

### Step 2: Set the Determinant to Zero

A matrix is not invertible if and only if its determinant is zero:

$$
\det A(t) = 0 \iff t^2 - 2 = 0
$$

Solve this quadratic equation for $t$:

$$
t^2 = 2 \implies t = \sqrt{2} \quad \text{or} \quad t = -\sqrt{2}
$$

Thus, there are exactly two parameter values for which $A(t)$ is not invertible: $t = \pm\sqrt{2}$.

### Step 3: Explain the Connection with Determinant Being Zero

Why does $\det A(t) = 0$ mean non-invertible?
Let us examine the rows of $A(t)$ at the critical values $t = \pm\sqrt{2}$:
1. **Case $t = \sqrt{2}$:**

$$
A(\sqrt{2}) = \begin{pmatrix} \sqrt{2} & 1 \\\\ 2 & \sqrt{2} \end{pmatrix}
$$

   Compare Row 1 and Row 2:

$$
\text{Row 2} = (2, \sqrt{2}) = \sqrt{2} \cdot (\sqrt{2}, 1) = \sqrt{2} \cdot \text{Row 1}
$$

   Row 2 is a direct scalar multiple of Row 1! The rows are linearly dependent.
2. **Case $t = -\sqrt{2}$:**

$$
A(-\sqrt{2}) = \begin{pmatrix} -\sqrt{2} & 1 \\\\ 2 & -\sqrt{2} \end{pmatrix}
$$

   Compare Row 1 and Row 2:

$$
\text{Row 2} = (2, -\sqrt{2}) = -\sqrt{2} \cdot (-\sqrt{2}, 1) = -\sqrt{2} \cdot \text{Row 1}
$$

   Row 2 is again a scalar multiple of Row 1, showing linear dependence.

When rows are linearly dependent, the matrix has rank $1 < 2$. Geometrically, the matrix maps the entire 2D Cartesian plane onto a single 1D line passing through the origin. All points along the orthogonal line are squashed into the origin $(0, 0)$. Since different inputs produce identical outputs, the map is not bijective, and no inverse matrix $A(t)^{-1}$ can exist.

---

## 5. Final Answer & Conclusion

- The matrix $A(t)$ is not invertible for:

$$
t = \sqrt{2} \qquad \text{and} \qquad t = -\sqrt{2}
$$

- For all other values $t \in \mathbb{R} \setminus \{-\sqrt{2}, \sqrt{2}\}$, $\det A(t) \neq 0$ and the matrix is invertible, with explicit inverse:

$$
A(t)^{-1} = \frac{1}{t^2 - 2} \begin{pmatrix} t & -1 \\\\ -2 & t \end{pmatrix}
$$

---

## 6. Quick Verification

Substitute $t = \sqrt{2}$ and attempt to solve $A(\sqrt{2}) x = \mathbf{0}$:

$$
\begin{pmatrix} \sqrt{2} & 1 \\\\ 2 & \sqrt{2} \end{pmatrix} \begin{pmatrix} x_1 \\\\ x_2 \end{pmatrix} = \begin{pmatrix} 0 \\\\ 0 \end{pmatrix} \implies \sqrt{2} x_1 + x_2 = 0 \implies x_2 = -\sqrt{2} x_1
$$

Choosing $x_1 = 1$ yields the non-zero vector $x = (1, -\sqrt{2})^T$ satisfying $A(\sqrt{2}) x = 0$.
Since the kernel contains non-zero vectors, $A(\sqrt{2})$ cannot be injective, which independently proves that no inverse exists.

---

## 7. Common Mistakes to Avoid

1. **Forgetting the Negative Root:**
   Writing $t^2 = 2 \implies t = \sqrt{2}$ while forgetting the negative root $t = -\sqrt{2}$.
2. **Confusing Non-Invertible with Invertible:**
   The problem specifically asks when the matrix is **not** invertible, which corresponds to $\det A(t) = 0$, not $\det A(t) \neq 0$.

---

## 8. How I Would Explain This in Class

> "The determinant of this $2 \times 2$ matrix is $t^2 - 2$. Invertibility fails precisely when the determinant drops to zero, which happens when $t^2 = 2$, giving $t = \pm\sqrt{2}$. At these two critical values, the second row is an exact scalar multiple ($\pm\sqrt{2}$) of the first row, squashing the entire two-dimensional plane into a single line so that information is destroyed and cannot be reversed."