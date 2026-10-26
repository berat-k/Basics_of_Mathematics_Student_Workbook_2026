# Problem 15: Combining Determinant Properties

## 1. The Original Problem

Let $A$ and $B$ be invertible $2 \times 2$ matrices with

$$
\det A = -2, \qquad \det B = 3
$$

Without finding the entries of the matrices, compute

$$
\det\left(B^{-1} A^T B\right)
$$

State the determinant properties you use in order and explain why the factors involving $B$ eventually cancel.

---

## 2. What Are We Trying to Find?

We need to:
1. Calculate the exact numerical value of $\det(B^{-1} A^T B)$ without knowing any individual entries of $A$ or $B$.
2. List in sequential order every fundamental determinant property employed during the derivation.
3. Provide a clear mathematical explanation of why the terms involving matrix $B$ cancel out completely, connecting this cancellation to the concept of matrix similarity and orientation preservation.

---

## 3. Before Calculating: What Idea Do We Need?

- **Property 1: Multiplicative Property of Determinants:**
  For any square matrices $X, Y, Z$ of the same dimension:

$$
\det(XYZ) = \det X \cdot \det Y \cdot \det Z
$$

- **Property 2: Determinant of an Inverse Matrix:**
  For any invertible matrix $M$:

$$
\det(M^{-1}) = \frac{1}{\det M}
$$

  *Why:* Since $M M^{-1} = I$, taking determinants gives $\det M \cdot \det(M^{-1}) = \det(I) = 1$. Since $\det M \neq 0$, dividing by $\det M$ yields the identity.
- **Property 3: Determinant of a Transposed Matrix:**
  For any square matrix $M$:

$$
\det(M^T) = \det M
$$

- **Property 4: Commutativity of Real Scalar Multiplication:**
  Even though matrices do not commute in general ($X Y \neq Y X$), their determinants are ordinary real numbers. In $\mathbb{R}$, multiplication is commutative: $x \cdot y = y \cdot x$.

---

## 4. Step-by-Step Solution

### Step 1: Apply the Multiplicative Property

We expand the determinant of the product $B^{-1} \cdot A^T \cdot B$ into the product of three separate scalar determinants:

$$
\det(B^{-1} A^T B) = \det(B^{-1}) \cdot \det(A^T) \cdot \det(B)
$$

### Step 2: Apply the Inverse and Transpose Properties

1. **For $B^{-1}$:**
   Since $\det B = 3 \neq 0$, the inverse exists, and:

$$
\det(B^{-1}) = \frac{1}{\det B} = \frac{1}{3}
$$

2. **For $A^T$:**
   The transpose preserves the determinant:

$$
\det(A^T) = \det A = -2
$$

### Step 3: Substitute and Calculate

Substitute these values back into the expanded expression:

$$
\det(B^{-1} A^T B) = \left(\frac{1}{\det B}\right) \cdot (\det A) \cdot (\det B)
$$

Substitute the numerical values:

$$
\det(B^{-1} A^T B) = \left(\frac{1}{3}\right) \cdot (-2) \cdot (3)
$$

Because real multiplication is associative and commutative:

$$
= (-2) \cdot \left(\frac{1}{3} \cdot 3\right) = (-2) \cdot 1 = -2
$$

### Step 4: Explain Why the Factors Involving $B$ Cancel

There are two complementary perspectives that explain this cancellation:

1. **Algebraic Perspective (Scalar Field Commutativity):**
   The determinant maps matrices into the field of real numbers: $\det: \mathbb{R}^{n \times n} \to \mathbb{R}$.
   In the matrix product $B^{-1} A^T B$, matrix $B$ cannot directly cancel $B^{-1}$ because $A^T$ sits between them ($B^{-1} A^T B \neq A^T B^{-1} B$ in general).
   However, once the determinant operator is applied, we obtain a product of three real scalars:

$$
\frac{1}{\det B} \cdot \det A \cdot \det B
$$

   In the field of real numbers $\mathbb{R}$, multiplication is strictly commutative. We can freely rearrange the scalar terms:

$$
\left(\frac{1}{\det B} \cdot \det B\right) \cdot \det A = 1 \cdot \det A = \det A
$$

   The reciprocal $\frac{1}{\det B}$ multiplies $\det B$ to produce $1$, so $B$ has zero net effect on the final determinant.

2. **Geometric Perspective (Similarity & Change of Basis):**
   The matrix $C = B^{-1} A^T B$ is **similar** to $A^T$. In linear algebra, similarity represents the exact same linear operator expressed under a different choice of coordinate basis (where $B$ acts as the change-of-basis matrix).
   A change of basis transforms coordinates into a new frame (scaling volumes by $\det B$), applies the operator $A^T$ (scaling volumes by $\det A^T$), and converts back to the original frame (scaling volumes by $\det(B^{-1}) = 1/\det B$).
   The volume distortion introduced by entering the new basis is perfectly undone when returning to the original basis. Hence, similar matrices always have identical determinants:

$$
\det(B^{-1} A^T B) = \det(A^T) = \det A
$$

---

## 5. Final Answer & Conclusion

- **Sequential List of Properties Used:**
  1. Multiplicative property: $\det(XYZ) = \det X \cdot \det Y \cdot \det Z$.
  2. Inverse property: $\det(B^{-1}) = \frac{1}{\det B}$.
  3. Transpose property: $\det(A^T) = \det A$.
  4. Commutativity of real numbers: $\frac{1}{\det B} \cdot \det A \cdot \det B = \det A$.
- **Calculated Result:**

$$
\det\left(B^{-1} A^T B\right) = -2
$$

- **Conclusion:** Conjugation by any invertible matrix $B$ does not alter the determinant of a matrix.

---

## 6. Quick Verification

Let us pick simple concrete $2 \times 2$ diagonal matrices with the given determinants:

$$
A = \begin{pmatrix} -2 & 0 \\\\ 0 & 1 \end{pmatrix} \implies \det A = -2
$$

$$
B = \begin{pmatrix} 3 & 0 \\\\ 0 & 1 \end{pmatrix} \implies \det B = 3
$$

Then the inverse and transpose are:

$$
B^{-1} = \begin{pmatrix} 1/3 & 0 \\\\ 0 & 1 \end{pmatrix}, \qquad A^T = \begin{pmatrix} -2 & 0 \\\\ 0 & 1 \end{pmatrix}
$$

Compute $B^{-1} A^T B$:

$$
B^{-1} A^T = \begin{pmatrix} 1/3 & 0 \\\\ 0 & 1 \end{pmatrix} \begin{pmatrix} -2 & 0 \\\\ 0 & 1 \end{pmatrix} = \begin{pmatrix} -2/3 & 0 \\\\ 0 & 1 \end{pmatrix}
$$

$$
(B^{-1} A^T) B = \begin{pmatrix} -2/3 & 0 \\\\ 0 & 1 \end{pmatrix} \begin{pmatrix} 3 & 0 \\\\ 0 & 1 \end{pmatrix} = \begin{pmatrix} -2 & 0 \\\\ 0 & 1 \end{pmatrix}
$$

The determinant is $(-2)(1) - (0)(0) = -2$, confirming our formula exactly.

---

## 7. Common Mistakes to Avoid

1. **Attempting Matrix Cancellation Illegally:**
   Writing $B^{-1} A^T B = B^{-1} B A^T = I A^T = A^T$. Matrix multiplication is **not** commutative! You cannot swap matrices inside the product. Cancellation is only valid **after** applying the determinant function, which converts matrices into commuting scalar numbers.
2. **Confusing Transpose with Inverse:**
   Assuming $\det(A^T) = \frac{1}{\det A}$. The transpose preserves the determinant: $\det(A^T) = \det A$.

---

## 8. How I Would Explain This in Class

> "We cannot cancel $B^{-1}$ and $B$ at the matrix level because $A^T$ sits between them and matrix multiplication does not commute. But when we take the determinant, $\det(B^{-1} A^T B)$ splits into the product of three ordinary numbers: $\det(B^{-1}) \cdot \det(A^T) \cdot \det B$, which is $(1/3) \cdot (-2) \cdot 3$. Since real numbers do commute, the $1/3$ and $3$ cancel each other out to give $1$, leaving simply $\det(A^T) = \det A = -2$."