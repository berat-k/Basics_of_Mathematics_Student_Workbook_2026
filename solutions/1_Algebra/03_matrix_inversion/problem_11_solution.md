# Problem 11: Parameter and Invertibility

## 1. The Original Problem

For

$$
A(t) = \begin{pmatrix} 1 & t \\\\ t & 1 \end{pmatrix}
$$

find all $t$ for which the matrix is invertible, and then give a formula for $A(t)^{-1}$. Explain what happens to this formula at the excluded values.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the determinant $\det A(t)$ as an algebraic function of parameter $t$.
2. Determine all real values of $t$ for which $A(t)$ is invertible ($\det A(t) \neq 0$).
3. Derive an explicit closed-form expression for the inverse matrix $A(t)^{-1}$ for all permitted values of $t$.
4. Analyze and explain what happens to this formula—both algebraically and geometrically—at the excluded values of $t$.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Invertibility Criterion for $A(t)$:**
  A parameter-dependent matrix $A(t)$ is invertible if and only if its determinant is non-zero:

$$
A(t) \text{ is invertible} \iff \det A(t) \neq 0
$$

- **The $2 \times 2$ Inverse Formula:**
  When $\det A(t) \neq 0$:

$$
A(t)^{-1} = \frac{1}{\det A(t)} \begin{pmatrix} d & -b \\\\ -c & a \end{pmatrix}
$$

- **Singularities (Excluded Values):**
  The values of $t$ that make $\det A(t) = 0$ make the denominator vanish. At these values, the rows (and columns) become collinear, squashing 2D area down to zero.

---

## 4. Step-by-Step Solution

### Step 1: Compute the Determinant of $A(t)$

Given:

$$
A(t) = \begin{pmatrix} 1 & t \\\\ t & 1 \end{pmatrix}
$$

Compute the determinant:

$$
\det A(t) = (1)(1) - (t)(t) = 1 - t^2
$$

### Step 2: Determine Values of $t$ for Invertibility

The matrix $A(t)$ is invertible if and only if $\det A(t) \neq 0$:

$$
1 - t^2 \neq 0 \iff t^2 \neq 1 \iff t \neq 1 \quad \text{and} \quad t \neq -1
$$

Thus, matrix $A(t)$ is invertible for all real numbers except $t = 1$ and $t = -1$:

$$
t \in \mathbb{R} \setminus \{-1, 1\}
$$

### Step 3: Derive the Formula for $A(t)^{-1}$

For any $t \neq \pm 1$, apply the $2 \times 2$ inverse formula:
1. Swap main diagonal entries: $1 \leftrightarrow 1$ (unchanged).
2. Negate off-diagonal entries: $t \to -t$.
3. Divide by the determinant $1 - t^2$:

$$
A(t)^{-1} = \frac{1}{1 - t^2} \begin{pmatrix} 1 & -t \\\\ -t & 1 \end{pmatrix}
$$

Distributing the scalar yields the entry-wise formula:

$$
A(t)^{-1} = \begin{pmatrix} \frac{1}{1 - t^2} & -\frac{t}{1 - t^2} \\\\ -\frac{t}{1 - t^2} & \frac{1}{1 - t^2} \end{pmatrix}
$$

### Step 4: Explain What Happens at the Excluded Values

The excluded values are $t = 1$ and $t = -1$.
Let us analyze what happens at each of these points:

#### Case 1: At $t = 1$
- **Algebraic Effect:**
  Substituting $t = 1$ into the denominator gives $1 - (1)^2 = 0$. The inverse formula requires dividing by zero:

$$
\frac{1}{0} \begin{pmatrix} 1 & -1 \\\\ -1 & 1 \end{pmatrix}
$$

  Division by zero is undefined, so the formula fails completely.

- **Structural & Geometric Meaning:**
  Substituting $t = 1$ into $A(t)$ gives:

$$
A(1) = \begin{pmatrix} 1 & 1 \\\\ 1 & 1 \end{pmatrix}
$$

  Notice that Row 1 and Row 2 are completely identical: $R_1 = R_2$.
  The matrix has rank $1 < 2$. The transformation collapses every vector in the plane onto the line $y = x$:

$$
A(1) \begin{pmatrix} x \\\\ y \end{pmatrix} = \begin{pmatrix} x + y \\\\ x + y \end{pmatrix} = (x + y) \begin{pmatrix} 1 \\\\ 1 \end{pmatrix}
$$

  Any vector along the line $x + y = 0$ (such as $(1, -1)^T$) is squashed to $(0, 0)^T$. Because this collapse cannot be reversed, no inverse exists.

#### Case 2: At $t = -1$
- **Algebraic Effect:**
  Substituting $t = -1$ into the denominator gives $1 - (-1)^2 = 0$, again causing division by zero.

- **Structural & Geometric Meaning:**
  Substituting $t = -1$ into $A(t)$ gives:

$$
A(-1) = \begin{pmatrix} 1 & -1 \\\\ -1 & 1 \end{pmatrix}
$$

  Here Row 2 is the exact negative of Row 1: $R_2 = -R_1$.
  The matrix again has rank $1$. The entire 2D plane is squashed onto the line $y = -x$:

$$
A(-1) \begin{pmatrix} x \\\\ y \end{pmatrix} = (x - y) \begin{pmatrix} 1 \\\\ -1 \end{pmatrix}
$$

  Vectors along the line $x - y = 0$ (such as $(1, 1)^T$) are sent to $(0, 0)^T$. This dimensional collapse destroys all ability to invert the transformation.

---

## 5. Final Answer & Conclusion

- **Invertibility Condition:**

$$
t \in \mathbb{R} \setminus \{-1, 1\} \quad (t \neq 1 \text{ and } t \neq -1)
$$

- **Inverse Matrix Formula:**

$$
A(t)^{-1} = \frac{1}{1 - t^2} \begin{pmatrix} 1 & -t \\\\ -t & 1 \end{pmatrix}
$$

- **Behavior at Excluded Values ($t = \pm 1$):**
  At $t = \pm 1$, the determinant becomes zero, making the denominator $1 - t^2 = 0$. The rows become collinear ($R_1 = \pm R_2$), collapsing the 2D plane into a 1D line, destroying injectivity, and causing the inverse formula to break down via division by zero.

---

## 6. Quick Verification

Multiply $A(t)$ by $A(t)^{-1}$ for an arbitrary $t \neq \pm 1$:

$$
A(t) A(t)^{-1} = \begin{pmatrix} 1 & t \\\\ t & 1 \end{pmatrix} \left[ \frac{1}{1 - t^2} \begin{pmatrix} 1 & -t \\\\ -t & 1 \end{pmatrix} \right] = \frac{1}{1 - t^2} \begin{pmatrix} 1 & t \\\\ t & 1 \end{pmatrix} \begin{pmatrix} 1 & -t \\\\ -t & 1 \end{pmatrix}
$$

Evaluate the matrix entries:
- Position $(1, 1)$: $(1)(1) + (t)(-t) = 1 - t^2$
- Position $(1, 2)$: $(1)(-t) + (t)(1) = -t + t = 0$
- Position $(2, 1)$: $(t)(1) + (1)(-t) = t - t = 0$
- Position $(2, 2)$: $(t)(-t) + (1)(1) = -t^2 + 1 = 1 - t^2$

Substitute these back:

$$
A(t) A(t)^{-1} = \frac{1}{1 - t^2} \begin{pmatrix} 1 - t^2 & 0 \\\\ 0 & 1 - t^2 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} = I
$$

The identity holds for all $t \neq \pm 1$.

---

## 7. Common Mistakes to Avoid

1. **Missing the Negative Root:**
   Solving $t^2 = 1$ and concluding only $t = 1$, forgetting that $(-1)^2 = 1$ as well.
2. **Ignoring the Geometric Meaning of the Excluded Values:**
   Simply stating "the denominator is zero" without explaining that $t = \pm 1$ represents the geometric collapse of the 2D plane to a line ($R_1 = \pm R_2$).

---

## 8. How I Would Explain This in Class

> "The determinant of $A(t)$ is $1 - t^2$. For the matrix to be invertible, this determinant cannot be zero, which means $t \neq \pm 1$. For all other values, the inverse formula divides by $1 - t^2$ and swaps the diagonal while negating $t$. At $t = 1$ and $t = -1$, the formula divides by zero because the rows become identical ($R_1 = R_2$) or opposite ($R_1 = -R_2$), squashing the entire two-dimensional plane onto a single line and making an inverse impossible."