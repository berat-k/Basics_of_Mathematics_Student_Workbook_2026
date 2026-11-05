# Problem 01: From a System to a Matrix

## 1. The Original Problem

Write the system

$$
\begin{cases}
2x - y + z = 4, \\\\
x + 3y - 2z = 1, \\\\
3x + y + z = 7
\end{cases}
$$

in the form $Ax = b$.

Identify the coefficient matrix, the vector of unknowns, and the right-hand side vector. Explain how each row of the matrix corresponds to one equation.

---

## 2. What Are We Trying to Find?

We need to:
1. Translate the scalar system of three linear equations into the compact matrix-vector representation $Ax = b$.
2. Explicitly write out and identify:
   - The coefficient matrix $A$,
   - The vector of unknown variables $x$,
   - The constant right-hand side vector $b$.
3. Explain the algebraic connection between the row vectors of matrix $A$ and the individual scalar equations of the system via matrix-vector multiplication.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Matrix Form of a Linear System ($Ax = b$):**
  A system of $m$ linear equations in $n$ unknowns can be represented as:

$$
A x = b
$$

  where:
  - $A$ is an $m \times n$ matrix whose entries are the coefficients of the variables.
  - $x$ is an $n \times 1$ column vector containing the unknown variables in order.
  - $b$ is an $m \times 1$ column vector containing the constants from the right-hand side.
- **The Row-Vector Dot Product Meaning:**
  Under the rules of matrix multiplication, the $i$-th component of the product $Ax$ is the dot product of the $i$-th row of $A$ with the vector of unknowns $x$:

$$
(\text{Row } i \text{ of } A) \cdot x = b_i
$$

  Setting this dot product equal to the $i$-th entry of $b$ precisely reconstructs the $i$-th equation of the system.

---

## 4. Step-by-Step Solution

### Step 1: Align the Equations and Coefficients

Align the variables $x, y, z$ in vertical columns and write out all coefficients explicitly:
- Equation 1: $2(x) + (-1)(y) + 1(z) = 4$
- Equation 2: $1(x) + 3(y) + (-2)(z) = 1$
- Equation 3: $3(x) + 1(y) + 1(z) = 7$

### Step 2: Form the Matrix Components

1. **The Coefficient Matrix $A$:**
   Extract the coefficients from each equation into a $3 \times 3$ matrix:

$$
A = \begin{pmatrix} 2 & -1 & 1 \\\\ 1 & 3 & -2 \\\\ 3 & 1 & 1 \end{pmatrix}
$$

2. **The Vector of Unknowns $x$:**
   Place the three variables into a $3 \times 1$ column vector:

$$
x = \begin{pmatrix} x \\\\ y \\\\ z \end{pmatrix}
$$

3. **The Right-Hand Side Vector $b$:**
   Place the constant terms into a $3 \times 1$ column vector:

$$
b = \begin{pmatrix} 4 \\\\ 1 \\\\ 7 \end{pmatrix}
$$

### Step 3: Write the Complete Matrix Equation

Combining the components gives the matrix equation $Ax = b$:

$$
\begin{pmatrix} 2 & -1 & 1 \\\\ 1 & 3 & -2 \\\\ 3 & 1 & 1 \end{pmatrix} \begin{pmatrix} x \\\\ y \\\\ z \end{pmatrix} = \begin{pmatrix} 4 \\\\ 1 \\\\ 7 \end{pmatrix}
$$

### Step 4: Explain the Row-to-Equation Correspondence

When we perform matrix-vector multiplication on the left-hand side, each row of matrix $A$ pairs with the vector $x$ to form a single scalar dot product:

1. **Row 1 Correspondence:**
   The first row of $A$ is $(2, -1, 1)$. Taking its dot product with $(x, y, z)^T$ yields:

$$
(2)(x) + (-1)(y) + (1)(z) = 2x - y + z
$$

   Equating this to the first entry of $b$ reproduces the first equation: $2x - y + z = 4$.

2. **Row 2 Correspondence:**
   The second row of $A$ is $(1, 3, -2)$. Its dot product with $(x, y, z)^T$ yields:

$$
(1)(x) + (3)(y) + (-2)(z) = x + 3y - 2z
$$

   Equating this to the second entry of $b$ reproduces the second equation: $x + 3y - 2z = 1$.

3. **Row 3 Correspondence:**
   The third row of $A$ is $(3, 1, 1)$. Its dot product with $(x, y, z)^T$ yields:

$$
(3)(x) + (1)(y) + (1)(z) = 3x + y + z
$$

   Equating this to the third entry of $b$ reproduces the third equation: $3x + y + z = 7$.

Thus, each horizontal row of $A$ together with the corresponding entry of $b$ represents one complete linear hyperplane constraint in 3D space.

---

## 5. Final Answer & Conclusion

- **The Matrix Form ($Ax = b$):**

$$
\begin{pmatrix} 2 & -1 & 1 \\\\ 1 & 3 & -2 \\\\ 3 & 1 & 1 \end{pmatrix} \begin{pmatrix} x \\\\ y \\\\ z \end{pmatrix} = \begin{pmatrix} 4 \\\\ 1 \\\\ 7 \end{pmatrix}
$$

- **Identified Components:**
  - Coefficient matrix:

$$
A = \begin{pmatrix} 2 & -1 & 1 \\\\ 1 & 3 & -2 \\\\ 3 & 1 & 1 \end{pmatrix}
$$

  - Vector of unknowns: $x = (x, y, z)^T$
  - Right-hand side vector: $b = (4, 1, 7)^T$
- **Conclusion:** Matrix notation packages the entire multi-equation system into a single algebraic equation, where each equation corresponds to the dot product of one row of $A$ with the unknown vector $x$.

---

## 6. Quick Verification

Multiply the matrix $A$ by the vector $x$ directly:

$$
Ax = \begin{pmatrix} 2 & -1 & 1 \\\\ 1 & 3 & -2 \\\\ 3 & 1 & 1 \end{pmatrix} \begin{pmatrix} x \\\\ y \\\\ z \end{pmatrix} = \begin{pmatrix} 2x - y + z \\\\ x + 3y - 2z \\\\ 3x + y + z \end{pmatrix}
$$

Setting $Ax = b$ gives:

$$
\begin{pmatrix} 2x - y + z \\\\ x + 3y - 2z \\\\ 3x + y + z \end{pmatrix} = \begin{pmatrix} 4 \\\\ 1 \\\\ 7 \end{pmatrix}
$$

Because two vectors are equal if and only if their corresponding entries are equal, this vector equation is mathematically identical to the original system of three scalar equations.

---

## 7. Common Mistakes to Avoid

1. **Sign Errors with Negative Coefficients:**
   Dropping minus signs when extracting entries, such as writing $+1$ instead of $-1$ for $-y$, or $+2$ instead of $-2$ for $-2z$.
2. **Scrambling Variable Order:**
   If an equation has terms written out of order (e.g., $z + 2x - y = 4$), placing coefficients into the matrix without first arranging variables in standard order ($x, y, z$).
3. **Writing Row Vectors Instead of Column Vectors:**
   Writing $x$ or $b$ horizontally as row vectors $(x, y, z)$ without a transpose. In $Ax = b$, $x$ and $b$ must be vertical column vectors for matrix multiplication to be dimensionally valid ($3 \times 3$ times $3 \times 1$ equals $3 \times 1$).

---

## 8. How I Would Explain This in Class

> "To write a linear system in matrix form $Ax = b$, we collect the coefficients of $x, y,$ and $z$ into a grid called the coefficient matrix $A$, stack the variables into a column vector $x$, and put the constants on the right into vector $b$. When we multiply $A$ by $x$, the rule of row-by-column multiplication takes the dot product of each row with $(x, y, z)^T$, which reconstructs each original equation line by line."