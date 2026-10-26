# Problem 08: Determinant of a Product

## 1. The Original Problem

Let $A, B$ be square matrices such that $\det A = 3$ and $\det B = -5$. Compute:

$$
\det(AB), \qquad \det(BA), \qquad \text{and, if it exists, } \det(A^{-1}B)
$$

Explain why the first two results are equal even though usually $AB \neq BA$.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the numerical determinant of the matrix product $AB$.
2. Compute the numerical determinant of the reversed matrix product $BA$.
3. Check whether $A^{-1}$ exists, and if so, compute $\det(A^{-1}B)$.
4. Explain clearly why $\det(AB) = \det(BA)$ always holds, despite the fact that matrix multiplication is generally non-commutative ($AB \neq BA$).

---

## 3. Before Calculating: What Idea Do We Need?

- **The Multiplicative Property of Determinants:**
  For any two $n \times n$ square matrices $X$ and $Y$:

$$
\det(XY) = \det X \cdot \det Y
$$

  Geometrically, the volume scaling factor of the composite transformation $X \circ Y$ is the product of the individual scaling factors of $X$ and $Y$.
- **Commutativity of Scalar Multiplication:**
  While matrix multiplication is non-commutative ($AB \neq BA$), the determinants $\det A$ and $\det B$ are ordinary real numbers (scalars). Real numbers strictly commute under multiplication: $a \cdot b = b \cdot a$.
- **Determinant of an Inverse Matrix:**
  If $\det A \neq 0$, matrix $A$ is invertible, and from $A A^{-1} = I$, we take determinants:

$$
\det(A A^{-1}) = \det(I) \implies \det A \cdot \det(A^{-1}) = 1 \implies \det(A^{-1}) = \frac{1}{\det A}
$$

---

## 4. Step-by-Step Solution

### Step 1: Compute $\det(AB)$
Using the multiplicative property:

$$
\det(AB) = \det A \cdot \det B
$$

Substitute the given numerical values $\det A = 3$ and $\det B = -5$:

$$
\det(AB) = (3) \cdot (-5) = -15
$$

### Step 2: Compute $\det(BA)$
Using the multiplicative property again:

$$
\det(BA) = \det B \cdot \det A
$$

Substitute the values:

$$
\det(BA) = (-5) \cdot (3) = -15
$$

### Step 3: Compute $\det(A^{-1}B)$
First, check whether $A^{-1}$ exists:
Since $\det A = 3 \neq 0$, matrix $A$ is non-singular, and its inverse $A^{-1}$ is guaranteed to exist.
The determinant of $A^{-1}$ is:

$$
\det(A^{-1}) = \frac{1}{\det A} = \frac{1}{3}
$$

Now compute $\det(A^{-1}B)$ using the multiplicative property:

$$
\det(A^{-1}B) = \det(A^{-1}) \cdot \det B = \left(\frac{1}{3}\right) \cdot (-5) = -\frac{5}{3}
$$

### Step 4: Explain Why $\det(AB) = \det(BA)$ While $AB \neq BA$

The matrices $AB$ and $BA$ are usually completely different matrices with different entries:

$$
AB \neq BA \quad \text{(matrix multiplication is non-commutative)}
$$

However, the determinant is a scalar-valued function mapping matrices into the field of real numbers: $\det: \mathbb{R}^{n \times n} \to \mathbb{R}$.
Once we evaluate the determinants:

$$
\det(AB) = (\det A)(\det B) \qquad \text{and} \qquad \det(BA) = (\det B)(\det A)
$$

Both expressions are simple products of real numbers. Because multiplication in $\mathbb{R}$ is commutative ($x y = y x$ for all $x, y \in \mathbb{R}$):

$$
(\det A)(\det B) = (\det B)(\det A) = (3)(-5) = (-5)(3) = -15
$$

Therefore, $\det(AB)$ and $\det(BA)$ must always be equal. Geometrically, both transformations scale $n$-dimensional volumes by the exact same total factor of $15$ and reverse orientation (due to the minus sign), even if they distort space along different axes.

---

## 5. Final Answer & Conclusion

- $\det(AB) = -15$
- $\det(BA) = -15$
- $\det(A^{-1}B) = -\frac{5}{3}$
- **Conclusion:** While $AB \neq BA$ as transformations on $\mathbb{R}^n$, their overall volume scaling factor and orientation change are identical because the determinants are scalars, and real scalar multiplication is commutative.

---

## 6. Quick Verification

Let $A$ and $B$ be diagonal test matrices:

$$
A = \begin{pmatrix} 3 & 0 \\\\ 0 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} -5 & 0 \\\\ 0 & 1 \end{pmatrix}
$$

Then $\det A = 3$ and $\det B = -5$. Multiplying:

$$
AB = \begin{pmatrix} -15 & 0 \\\\ 0 & 1 \end{pmatrix} \implies \det(AB) = -15
$$

$$
BA = \begin{pmatrix} -15 & 0 \\\\ 0 & 1 \end{pmatrix} \implies \det(BA) = -15
$$

For the inverse product:

$$
A^{-1} = \begin{pmatrix} 1/3 & 0 \\\\ 0 & 1 \end{pmatrix} \implies A^{-1}B = \begin{pmatrix} -5/3 & 0 \\\\ 0 & 1 \end{pmatrix} \implies \det(A^{-1}B) = -\frac{5}{3}
$$

The formulas hold with complete mathematical consistency.

---

## 7. Common Mistakes to Avoid

1. **Confusing Matrices with Scalars:**
   Assuming that because $AB \neq BA$, their determinants must also be different: $\det(AB) \neq \det(BA)$. This is false; determinants are numbers, and numbers commute.
2. **Assuming $A^{-1}$ Always Exists:**
   If $\det A$ had been $0$, $A^{-1}$ would not exist, and $\det(A^{-1}B)$ would be undefined. Always verify that $\det A \neq 0$ before computing $\det(A^{-1})$.

---

## 8. How I Would Explain This in Class

> "Because the determinant of a product is the product of the determinants, $\det(AB)$ is $\det A \cdot \det B$ and $\det(BA)$ is $\det B \cdot \det A$. Even though the matrix products $AB$ and $BA$ are different transformations, their determinants are just real numbers: $3 \cdot (-5)$ and $(-5) \cdot 3$, which both equal $-15$ because multiplication of numbers is commutative. Finally, since $\det A = 3 \neq 0$, the inverse exists with $\det(A^{-1}) = 1/3$, giving $\det(A^{-1}B) = (1/3)(-5) = -5/3$."