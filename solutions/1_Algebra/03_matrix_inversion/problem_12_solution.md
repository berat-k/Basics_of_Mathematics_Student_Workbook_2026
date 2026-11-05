# Problem 12: Finding Inverses Without Starting from Scratch

## 1. The Original Problem

It is known that

$$
A^{-1} = \begin{pmatrix} 2 & -1 \\\\ -3 & 2 \end{pmatrix}
$$

Without finding $A$, compute:

$$
(3A)^{-1}, \qquad (A^T)^{-1}, \qquad \text{and} \qquad (A^2)^{-1}
$$

Justify each result using the appropriate property.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute $(3A)^{-1}$ directly from $A^{-1}$ using the scalar multiple inversion property.
2. Compute $(A^T)^{-1}$ directly from $A^{-1}$ using the transpose inversion property.
3. Compute $(A^2)^{-1}$ directly from $A^{-1}$ using the power/product inversion property.
4. Strictly avoid finding matrix $A$ itself, justifying every calculation through algebraic properties of inverse matrices.

---

## 3. Before Calculating: What Idea Do We Need?

For any invertible matrix $A$ and non-zero scalar $c \neq 0$:
1. **Inverse of a Scalar Multiple:**

$$
(c A)^{-1} = \frac{1}{c} A^{-1}
$$

   *Why:* $(cA)\left(\frac{1}{c} A^{-1}\right) = \left(c \cdot \frac{1}{c}\right) (A A^{-1}) = 1 \cdot I = I$.
2. **Inverse of a Transpose (Commutativity of Inverse and Transpose):**

$$
(A^T)^{-1} = (A^{-1})^T
$$

   *Why:* Taking transposes of $A A^{-1} = I$ gives $(A A^{-1})^T = I^T \implies (A^{-1})^T A^T = I$.
3. **Inverse of a Power / Product:**

$$
(A^2)^{-1} = (A \cdot A)^{-1} = A^{-1} \cdot A^{-1} = (A^{-1})^2
$$

   *Why:* By the product inversion property, $(XY)^{-1} = Y^{-1} X^{-1}$. Setting $X = Y = A$ yields $A^{-1} A^{-1} = (A^{-1})^2$.

---

## 4. Step-by-Step Solution

We are given:

$$
A^{-1} = \begin{pmatrix} 2 & -1 \\\\ -3 & 2 \end{pmatrix}
$$

### Step 1: Compute $(3A)^{-1}$

- **Property Used:** $(c A)^{-1} = \frac{1}{c} A^{-1}$ with $c = 3$.
- Applying the property:

$$
(3A)^{-1} = \frac{1}{3} A^{-1} = \frac{1}{3} \begin{pmatrix} 2 & -1 \\\\ -3 & 2 \end{pmatrix}
$$

- Distribute the scalar $\frac{1}{3}$ into each entry:

$$
(3A)^{-1} = \begin{pmatrix} \frac{2}{3} & -\frac{1}{3} \\\\ -1 & \frac{2}{3} \end{pmatrix}
$$

### Step 2: Compute $(A^T)^{-1}$

- **Property Used:** $(A^T)^{-1} = (A^{-1})^T$.
- The transpose of a matrix swaps its rows and columns:
  - Row 1 of $A^{-1}$ is $(2, -1) \implies$ becomes Column 1 of $(A^{-1})^T$.
  - Row 2 of $A^{-1}$ is $(-3, 2) \implies$ becomes Column 2 of $(A^{-1})^T$.
- Applying the property:

$$
(A^T)^{-1} = \begin{pmatrix} 2 & -1 \\\\ -3 & 2 \end{pmatrix}^T = \begin{pmatrix} 2 & -3 \\\\ -1 & 2 \end{pmatrix}
$$

### Step 3: Compute $(A^2)^{-1}$

- **Property Used:** $(A^2)^{-1} = (A^{-1})^2 = A^{-1} \cdot A^{-1}$.
- Multiply $A^{-1}$ by itself:

$$
(A^2)^{-1} = \begin{pmatrix} 2 & -1 \\\\ -3 & 2 \end{pmatrix} \begin{pmatrix} 2 & -1 \\\\ -3 & 2 \end{pmatrix}
$$

- Compute the entries:
  - **Row 1, Column 1:** $(2)(2) + (-1)(-3) = 4 + 3 = 7$
  - **Row 1, Column 2:** $(2)(-1) + (-1)(2) = -2 - 2 = -4$
  - **Row 2, Column 1:** $(-3)(2) + (2)(-3) = -6 - 6 = -12$
  - **Row 2, Column 2:** $(-3)(-1) + (2)(2) = 3 + 4 = 7$

$$
(A^2)^{-1} = \begin{pmatrix} 7 & -4 \\\\ -12 & 7 \end{pmatrix}
$$

---

## 5. Final Answer & Conclusion

- **Results:**

$$
(3A)^{-1} = \begin{pmatrix} \frac{2}{3} & -\frac{1}{3} \\\\ -1 & \frac{2}{3} \end{pmatrix}
$$

$$
(A^T)^{-1} = \begin{pmatrix} 2 & -3 \\\\ -1 & 2 \end{pmatrix}
$$

$$
(A^2)^{-1} = \begin{pmatrix} 7 & -4 \\\\ -12 & 7 \end{pmatrix}
$$

- **Conclusion:** All three inverses were computed strictly using algebraic properties of inverse matrices without determining a single entry of matrix $A$.

---

## 6. Quick Verification

To verify our results, we can find $A$ by inverting $A^{-1}$:
- $\det(A^{-1}) = (2)(2) - (-1)(-3) = 4 - 3 = 1$.

$$
A = (A^{-1})^{-1} = \frac{1}{1} \begin{pmatrix} 2 & 1 \\\\ 3 & 2 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\\\ 3 & 2 \end{pmatrix}
$$

Now test our answers against $A$:
1. For $3A$:

$$
3A = \begin{pmatrix} 6 & 3 \\\\ 9 & 6 \end{pmatrix} \implies (3A)^{-1} = \frac{1}{9} \begin{pmatrix} 6 & -3 \\\\ -9 & 6 \end{pmatrix} = \begin{pmatrix} \frac{2}{3} & -\frac{1}{3} \\\\ -1 & \frac{2}{3} \end{pmatrix}
$$

2. For $A^T$:

$$
A^T = \begin{pmatrix} 2 & 3 \\\\ 1 & 2 \end{pmatrix} \implies (A^T)^{-1} = \begin{pmatrix} 2 & -3 \\\\ -1 & 2 \end{pmatrix}
$$

3. For $A^2$:

$$
A^2 = \begin{pmatrix} 7 & 4 \\\\ 12 & 7 \end{pmatrix} \implies (A^2)^{-1} = \begin{pmatrix} 7 & -4 \\\\ -12 & 7 \end{pmatrix}
$$

All properties hold with absolute consistency.

---

## 7. Common Mistakes to Avoid

1. **Multiplying the Scalar by 3 Instead of $1/3$:**
   Thinking $(3A)^{-1} = 3 A^{-1}$. If you scale a matrix by $3$, its inverse must scale by the reciprocal $\frac{1}{3}$ to undo the magnification.
2. **Squaring Matrix Entries Individually:**
   Mistakenly squaring each entry of $A^{-1}$ individually instead of performing matrix multiplication. Matrix squaring $(A^{-1})^2$ requires full row-by-column product $A^{-1} \cdot A^{-1}$.

---

## 8. How I Would Explain This in Class

> "We do not need to calculate $A$ because the inverse distributes elegantly over scalars, transposes, and powers. Scaling $A$ by $3$ means its inverse is scaled by $1/3$, giving $(1/3) A^{-1}$. The transpose and inverse operations commute, so $(A^T)^{-1}$ is simply the transpose of $A^{-1}$, swapping its off-diagonal entries. Finally, inverting $A^2$ is simply squaring $A^{-1}$, which we evaluate by multiplying $A^{-1}$ by itself to get rows $(7, -4)$ and $(-12, 7)$."