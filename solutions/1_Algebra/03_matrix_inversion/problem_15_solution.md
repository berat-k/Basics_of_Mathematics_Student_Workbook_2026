# Problem 15: Two Methods for Solving the Same System

## 1. The Original Problem

For

$$
A = \begin{pmatrix} 2 & 1 \\\\ 1 & 3 \end{pmatrix}, \qquad b = \begin{pmatrix} 7 \\\\ 8 \end{pmatrix}
$$

solve $Ax = b$ in two ways:

1. Using $A^{-1}b$,
2. Using Gaussian elimination.

Compare both solutions, the number of essential steps, and state which method was simpler in this example.

---

## 2. What Are We Trying to Find?

We need to:
1. Solve the system $Ax = b$ using the inverse matrix method $x = A^{-1}b$.
2. Solve the same system using Gaussian elimination on the augmented matrix $[A \mid b]$.
3. Confirm that both computational pathways arrive at the identical solution vector $x$.
4. Compare the computational complexity, number of arithmetic steps, and determine which method is simpler for a single small system versus a multi-system setting.

---

## 3. Before Calculating: What Idea Do We Need?

- **Method 1 (Inverse Matrix Method):**
  If $A$ is invertible, $x = A^{-1}b$.
  - Requires computing $\det A$, computing the adjugate matrix, forming $A^{-1}$, and then carrying out matrix-vector multiplication $A^{-1}b$.
- **Method 2 (Gaussian Elimination):**
  Forms the augmented matrix $[A \mid b]$ and applies elementary row operations to reduce it to row echelon form, followed by back-substitution.
  - Avoids calculating the full matrix inverse $A^{-1}$ entirely, focusing directly on finding the specific vector $x$.

---

## 4. Step-by-Step Solution

### Method 1: Solving via the Inverse Matrix $x = A^{-1}b$

Our system is:

$$
A = \begin{pmatrix} 2 & 1 \\\\ 1 & 3 \end{pmatrix}, \qquad b = \begin{pmatrix} 7 \\\\ 8 \end{pmatrix}
$$

1. **Step 1: Compute the Determinant of $A$:**

$$
\det A = (2)(3) - (1)(1) = 6 - 1 = 5
$$

   Since $\det A = 5 \neq 0$, the inverse exists.
2. **Step 2: Compute $A^{-1}$:**
   Swap diagonal entries ($2 \leftrightarrow 3$), negate off-diagonal entries ($1 \to -1$), and divide by $\det A = 5$:

$$
A^{-1} = \frac{1}{5} \begin{pmatrix} 3 & -1 \\\\ -1 & 2 \end{pmatrix}
$$

3. **Step 3: Compute $x = A^{-1}b$:**

$$
x = \frac{1}{5} \begin{pmatrix} 3 & -1 \\\\ -1 & 2 \end{pmatrix} \begin{pmatrix} 7 \\\\ 8 \end{pmatrix}
$$

   Evaluate the matrix-vector dot products:
   - Top entry: $(3)(7) + (-1)(8) = 21 - 8 = 13$
   - Bottom entry: $(-1)(7) + (2)(8) = -7 + 16 = 9$

   Divide by $5$:

$$
x = \begin{pmatrix} \frac{13}{5} \\\\ \frac{9}{5} \end{pmatrix} = \begin{pmatrix} 2.6 \\\\ 1.8 \end{pmatrix}
$$

---

### Method 2: Solving via Gaussian Elimination

Set up the augmented matrix $[A \mid b]$:

$$
\left(\begin{array}{cc|c} 2 & 1 & 7 \\\\ 1 & 3 & 8 \end{array}\right)
$$

1. **Step 1: Swap Rows to Obtain a Pivot of $1$ ($R_1 \leftrightarrow R_2$):**

$$
\left(\begin{array}{cc|c} 1 & 3 & 8 \\\\ 2 & 1 & 7 \end{array}\right)
$$

2. **Step 2: Eliminate Entry Under the First Pivot ($R_2 \leftarrow R_2 - 2R_1$):**
   - Left side: $(2 - 2(1), \, 1 - 2(3)) = (0, \, 1 - 6) = (0, -5)$
   - Right side: $7 - 2(8) = 7 - 16 = -9$

   The matrix is now in row echelon form:

$$
\left(\begin{array}{cc|c} 1 & 3 & 8 \\\\ 0 & -5 & -9 \end{array}\right)
$$

3. **Step 3: Back-Substitution:**
   - From Row 2:

$$
-5 x_2 = -9 \implies x_2 = \frac{9}{5} = 1.8
$$

   - Substitute $x_2 = \frac{9}{5}$ into Row 1 ($x_1 + 3x_2 = 8$):

$$
x_1 + 3\left(\frac{9}{5}\right) = 8 \implies x_1 + \frac{27}{5} = 8
$$

$$
x_1 = 8 - \frac{27}{5} = \frac{40 - 27}{5} = \frac{13}{5} = 2.6
$$

Both methods yield the exact same solution:

$$
x = \begin{pmatrix} \frac{13}{5} \\\\ \frac{9}{5} \end{pmatrix}
$$

---

### Comparison of the Two Methods

| Feature | Method 1: Inverse Matrix ($A^{-1}b$) | Method 2: Gaussian Elimination |
| :--- | :--- | :--- |
| **Number of Steps** | 3 steps: (1) compute $\det A$, (2) build $A^{-1}$, (3) multiply $A^{-1}b$. | 3 steps: (1) row swap, (2) row elimination, (3) back-substitution. |
| **Arithmetic Load** | Requires computing 4 matrix entries plus vector multiplication (8 multiplications, 5 additions). | Requires only 1 row operation and simple 1-variable back-substitution (4 multiplications, 2 additions). |
| **Simplicity in This Example** | **Gaussian elimination is simpler.** It operates entirely on integers until the final division, avoiding fractions in the intermediate steps. |
| **Multi-System Efficiency** | Highly efficient if solving $Ax = b_k$ for many different vectors $b_k$, since $A^{-1}$ is computed only once. | Less efficient for multiple $b_k$ if elimination must be repeated from scratch each time. |

---

## 5. Final Answer & Conclusion

- **The Solution Vector:**

$$
x = \begin{pmatrix} \frac{13}{5} \\\\ \frac{9}{5} \end{pmatrix} = \begin{pmatrix} 2.6 \\\\ 1.8 \end{pmatrix}
$$

- **Comparison & Conclusion:**
  - Both methods yield the exact same unique solution vector $x = (13/5, 9/5)^T$.
  - For solving this single specific system, **Gaussian elimination was simpler** because it avoids finding the 4 entries of $A^{-1}$ and works directly with the augmented vector. However, if the system had to be solved for many different vectors $b$, the inverse matrix method would be superior.

---

## 6. Quick Verification

Substitute $x_1 = \frac{13}{5}$ and $x_2 = \frac{9}{5}$ back into the original equations:
- **Equation 1:** $2x_1 + x_2 = 2\left(\frac{13}{5}\right) + \frac{9}{5} = \frac{26 + 9}{5} = \frac{35}{5} = 7$ (Matches $b_1 = 7$)
- **Equation 2:** $x_1 + 3x_2 = \frac{13}{5} + 3\left(\frac{9}{5}\right) = \frac{13 + 27}{5} = \frac{40}{5} = 8$ (Matches $b_2 = 8$)

The solution satisfies both equations perfectly.

---

## 7. Common Mistakes to Avoid

1. **Fraction Algebra Slips:**
   When subtracting $\frac{27}{5}$ from $8$, forgetting to convert $8$ to common denominator: $8 = \frac{40}{5}$, so $\frac{40 - 27}{5} = \frac{13}{5}$.
2. **Assuming One Method is Universally Better:**
   Believing that finding the inverse is always required to solve a system. In professional numerical linear algebra, large systems are almost never solved by inverting matrices; elimination ($LU$ factorization) is vastly faster and numerically more stable.

---

## 8. How I Would Explain This in Class

> "We solved this system in two ways. First, using the inverse matrix $x = A^{-1}b$, we computed $A^{-1}$ with rows $(3/5, -1/5)$ and $(-1/5, 2/5)$ and multiplied by $b = (7, 8)^T$ to get $(13/5, 9/5)^T$. Second, using Gaussian elimination on the augmented matrix $[A \mid b]$, a single row elimination gave $-5x_2 = -9$, which immediately yields $x_2 = 9/5$ and $x_1 = 13/5$. While both methods agree, Gaussian elimination was simpler here because it solved the system directly without calculating the full inverse matrix."