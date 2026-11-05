# Problem 07: Inverse of a Product

## 1. The Original Problem

For

$$
A = \begin{pmatrix} 1 & 1 \\\\ 0 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 2 & 0 \\\\ 0 & 3 \end{pmatrix}
$$

compute $(AB)^{-1}$ and $B^{-1}A^{-1}$. Check that the results are the same and explain the meaning of the reversed order.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the matrix product $AB$ and find its inverse $(AB)^{-1}$.
2. Invert each matrix individually to find $A^{-1}$ and $B^{-1}$, then compute the product in reverse order: $B^{-1}A^{-1}$.
3. Verify that $(AB)^{-1} = B^{-1}A^{-1}$.
4. Provide a conceptual and operational explanation for why the order of the matrices must reverse when taking the inverse of a product.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Shoes and Socks Property:**
  For any two invertible matrices $A$ and $B$ of the same size, the inverse of their product is:

$$
(AB)^{-1} = B^{-1} A^{-1}
$$

- **Why the Order Reverses:**
  When applying the transformation $AB$ to a vector $x$:

$$
(AB)x = A(Bx)
$$

  $B$ acts first, and $A$ acts second. To undo this chain of operations, the *last* action must be undone *first*:
  1. First apply $A^{-1}$ to undo $A$: $A^{-1}(A(Bx)) = (A^{-1}A)(Bx) = I(Bx) = Bx$.
  2. Then apply $B^{-1}$ to undo $B$: $B^{-1}(Bx) = (B^{-1}B)x = Ix = x$.
  Thus, $(B^{-1}A^{-1})(AB) = B^{-1}(A^{-1}A)B = B^{-1} I B = B^{-1} B = I$.
  Attempting $(A^{-1}B^{-1})(AB)$ would get stuck because $B^{-1}$ and $A$ do not commute in general!

---

## 4. Step-by-Step Solution

### Step 1: Compute $AB$ and $(AB)^{-1}$

Given:

$$
A = \begin{pmatrix} 1 & 1 \\\\ 0 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 2 & 0 \\\\ 0 & 3 \end{pmatrix}
$$

1. Compute the product $AB$:
   - Row 1: $(1)(2) + (1)(0) = 2$, \quad $(1)(0) + (1)(3) = 3$
   - Row 2: $(0)(2) + (1)(0) = 0$, \quad $(0)(0) + (1)(3) = 3$

$$
AB = \begin{pmatrix} 2 & 3 \\\\ 0 & 3 \end{pmatrix}
$$

2. Compute $\det(AB)$:

$$
\det(AB) = (2)(3) - (3)(0) = 6
$$

3. Invert using the $2 \times 2$ formula:

$$
(AB)^{-1} = \frac{1}{6} \begin{pmatrix} 3 & -3 \\\\ 0 & 2 \end{pmatrix} = \begin{pmatrix} \frac{3}{6} & -\frac{3}{6} \\\\ 0 & \frac{2}{6} \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\\\ 0 & \frac{1}{3} \end{pmatrix}
$$

### Step 2: Compute $A^{-1}$, $B^{-1}$, and $B^{-1}A^{-1}$

1. Invert matrix $A$:
   $\det A = (1)(1) - (1)(0) = 1$.

$$
A^{-1} = \frac{1}{1} \begin{pmatrix} 1 & -1 \\\\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & -1 \\\\ 0 & 1 \end{pmatrix}
$$

2. Invert diagonal matrix $B$:
   The inverse of a diagonal matrix is obtained by inverting its diagonal entries:

$$
B^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\\\ 0 & \frac{1}{3} \end{pmatrix}
$$

3. Multiply in reverse order $B^{-1} A^{-1}$:
   - Row 1: $\left(\frac{1}{2}\right)(1) + (0)(0) = \frac{1}{2}$, \quad $\left(\frac{1}{2}\right)(-1) + (0)(1) = -\frac{1}{2}$
   - Row 2: $(0)(1) + \left(\frac{1}{3}\right)(0) = 0$, \quad $(0)(-1) + \left(\frac{1}{3}\right)(1) = \frac{1}{3}$

$$
B^{-1} A^{-1} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\\\ 0 & \frac{1}{3} \end{pmatrix}
$$

Both calculations produce the identical matrix:

$$
(AB)^{-1} = B^{-1} A^{-1} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\\\ 0 & \frac{1}{3} \end{pmatrix}
$$

---

## 5. Final Answer & Conclusion

- **Results:**

$$
(AB)^{-1} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\\\ 0 & \frac{1}{3} \end{pmatrix}, \qquad B^{-1}A^{-1} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\\\ 0 & \frac{1}{3} \end{pmatrix}
$$

- **Meaning of the Reversed Order:**
  In a composition of operations, the second operation applied must be the first one reversed. Because $A$ was applied after $B$, $A^{-1}$ must meet $A$ directly to cancel it out:

$$
(AB)(B^{-1}A^{-1}) = A(B B^{-1})A^{-1} = A I A^{-1} = A A^{-1} = I
$$

---

## 6. Quick Verification

Show that the wrong order $A^{-1} B^{-1}$ gives an incorrect result:

$$
A^{-1} B^{-1} = \begin{pmatrix} 1 & -1 \\\\ 0 & 1 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & 0 \\\\ 0 & \frac{1}{3} \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{3} \\\\ 0 & \frac{1}{3} \end{pmatrix} \neq (AB)^{-1}
$$

Notice that entry $(1, 2)$ is $-\frac{1}{3}$ instead of $-\frac{1}{2}$. Multiplying $(AB)(A^{-1}B^{-1})$ gives:

$$
\begin{pmatrix} 2 & 3 \\\\ 0 & 3 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & -\frac{1}{3} \\\\ 0 & \frac{1}{3} \end{pmatrix} = \begin{pmatrix} 1 & \frac{1}{3} \\\\ 0 & 1 \end{pmatrix} \neq I
$$

This directly demonstrates why the order must reverse.

---

## 7. Common Mistakes to Avoid

1. **Forgetting to Reverse Order:**
   Assuming $(AB)^{-1} = A^{-1} B^{-1}$. This common mistake assumes matrices commute, which is almost never true.
2. **Determinant Miscalculations on Triangular Matrices:**
   For the triangular product $AB$, its determinant is simply the diagonal product $2 \cdot 3 = 6$. Computing the product of individual determinants $\det A \cdot \det B = 1 \cdot 6 = 6$ provides an instant sanity check.

---

## 8. How I Would Explain This in Class

> "When we multiply $AB$, matrix $B$ acts first and $A$ acts second. Think of putting on socks ($B$) and then shoes ($A$). When you want to return to bare feet, you cannot take off your socks first; you must take off your shoes first ($A^{-1}$), and only then your socks ($B^{-1}$). Algebraically, $B^{-1} A^{-1}$ places $A^{-1}$ right next to $A$, canceling it to the identity so that $B^{-1}$ can cancel $B$, yielding $(AB)^{-1} = B^{-1} A^{-1}$ with rows $(1/2, -1/2)$ and $(0, 1/3)$."