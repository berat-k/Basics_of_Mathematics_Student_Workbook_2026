# Problem 14: A Matrix That Is Its Own Inverse

## 1. The Original Problem

Assume that a square matrix $A$ satisfies

$$
A^2 = I
$$

Show that

$$
A^{-1} = A
$$

Then give an example of a $2 \times 2$ matrix different from $I$ and $-I$ that satisfies this condition, and verify it by multiplication.

---

## 2. What Are We Trying to Find?

We need to:
1. Provide a rigorous, step-by-step mathematical proof demonstrating that any matrix satisfying $A^2 = I$ must have $A$ as its own inverse ($A^{-1} = A$).
2. Construct a concrete $2 \times 2$ real matrix $A$ such that $A^2 = I$, with the strict constraint that $A \neq I_2$ and $A \neq -I_2$.
3. Verify by direct matrix multiplication that the constructed example satisfies $A \cdot A = I_2$.
4. Give a geometric interpretation of matrices that are their own inverses (involutions / reflections).

---

## 3. Before Calculating: What Idea Do We Need?

- **The Mathematical Definition of Inverse:**
  For any square matrix $A$, a matrix $B$ is the inverse of $A$ if and only if:

$$
AB = I \qquad \text{and} \qquad BA = I
$$

  Because matrix inverses are unique, if we can find any matrix $B$ such that $AB = I$, then necessarily $B = A^{-1}$.
- **Involutory Matrices:**
  A matrix satisfying $A^2 = I$ (or equivalently $A = A^{-1}$) is called an **involutory matrix** or an **involution**.
- **Geometric Meaning:**
  An involution is a transformation that is its own undoing. Geometrically, this represents a **reflection** across a line or plane. Reflecting an object across a mirror line flips it; reflecting it a second time across the same line restores its original orientation. Thus, reflecting twice is doing nothing ($A^2 = I$).
  - Common reflections in $\mathbb{R}^2$ include reflection across the $x$-axis $(x, y) \mapsto (x, -y)$ and reflection across the line $y = x$, given by $(x, y) \mapsto (y, x)$.

---

## 4. Step-by-Step Solution

### Step 1: Proof that $A^2 = I \implies A^{-1} = A$

1. By assumption, the matrix $A$ satisfies:

$$
A^2 = I
$$

2. By the definition of matrix powers, $A^2$ means multiplying $A$ by itself:

$$
A \cdot A = I
$$

3. This equation shows that when matrix $A$ is multiplied by $A$, the product is the identity matrix $I$.
4. Recall the foundational definition of the inverse matrix: A matrix $B$ is the inverse of $A$ (written $B = A^{-1}$) if and only if $AB = I$ and $BA = I$.
5. In our equation, the matrix acting in the role of $B$ is $A$ itself:

$$
A \cdot (A) = I \qquad \text{and} \qquad (A) \cdot A = I
$$

6. Since the inverse of an invertible matrix is unique, matrix $A$ must be its own inverse:

$$
A^{-1} = A
$$

This completes the proof.

### Step 2: Construct a $2 \times 2$ Example (Different from $I$ and $-I$)

We need a $2 \times 2$ matrix $A$ such that $A^2 = I$, but $A \neq I_2$ and $A \neq -I_2$.

Consider the geometric reflection across the diagonal line $y = x$:
- Basis vector $e_1 = (1, 0)^T$ maps to $(0, 1)^T$.
- Basis vector $e_2 = (0, 1)^T$ maps to $(1, 0)^T$.

Writing these columns into a matrix yields:

$$
A = \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix}
$$

Let us check our constraints:
- $A \neq I_2$ (its diagonal entries are $0$, not $1$).
- $A \neq -I_2$ (its entries are non-negative).

### Step 3: Verify the Example by Direct Multiplication

Multiply matrix $A$ by itself:

$$
A^2 = A \cdot A = \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix} \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix}
$$

Compute each row-by-column product:
- **Row 1, Column 1:** $(0)(0) + (1)(1) = 0 + 1 = 1$
- **Row 1, Column 2:** $(0)(1) + (1)(0) = 0 + 0 = 0$
- **Row 2, Column 1:** $(1)(0) + (0)(1) = 0 + 0 = 0$
- **Row 2, Column 2:** $(1)(1) + (0)(0) = 1 + 0 = 1$

Putting the entries together:

$$
A^2 = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} = I_2
$$

The calculation verifies that $A^2 = I$, and therefore $A^{-1} = A$.

---

## 5. Final Answer & Conclusion

- **Proof:** From $A \cdot A = I$, the definition of matrix inversion guarantees that $A^{-1} = A$.
- **Example Matrix:**

$$
A = \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix}
$$

- **Verification:** Direct multiplication confirms:

$$
A \cdot A = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} = I
$$

- **Conclusion:** Any geometric reflection matrix is an involution satisfying $A^{-1} = A$.

---

## 6. Quick Verification

Verify using the determinant formula for our constructed example:
- $\det A = (0)(0) - (1)(1) = -1$.
- Swap diagonal entries ($0 \leftrightarrow 0$) and negate off-diagonal entries ($1 \to -1$):

$$
A^{-1} = \frac{1}{-1} \begin{pmatrix} 0 & -1 \\\\ -1 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix} = A
$$

The formula independently confirms that $A^{-1} = A$.

---

## 7. Common Mistakes to Avoid

1. **Circular Arguments:**
   Multiplying both sides of $A^2 = I$ by $A^{-1}$ without first establishing that $A^{-1}$ exists. It is cleaner and more rigorous to state $A \cdot A = I$ and invoke the direct definition of an inverse matrix.
2. **Choosing $I$ or $-I$:**
   The problem explicitly forbids $I$ and $-I$. Be sure your example has off-diagonal entries or mixed signs on the diagonal (such as reflections with determinants $-1$).

---

## 8. How I Would Explain This in Class

> "By definition, the inverse of a matrix $A$ is whatever matrix multiplies $A$ to produce the identity. If $A^2 = I$, then $A \cdot A = I$, so $A$ itself is doing the job of the inverse, meaning $A^{-1} = A$. Geometrically, this describes any reflection: reflecting across the line $y = x$ swaps coordinates using the matrix with rows $(0, 1)$ and $(1, 0)$, and doing it a second time swaps them right back to where they started, so multiplying $A$ by itself gives $I$."