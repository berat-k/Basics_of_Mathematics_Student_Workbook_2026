# Problem 14: A System of Equations and the Determinant

## 1. The Original Problem

Consider the system $Ax = b$, where

$$
A = \begin{pmatrix} 1 & 2 \\\\ k & 4 \end{pmatrix}
$$

For which values of $k$ does the system have exactly one solution for every $b$?

For the remaining value, give an example of a right-hand side $b$ for which the system has infinitely many solutions, and an example for which it has no solution.

---

## 2. What Are We Trying to Find?

We need to:
1. Determine the determinant $\det A$ as a function of the parameter $k$.
2. State the condition on $k$ that guarantees a unique solution $x = A^{-1}b$ for every right-hand side vector $b$.
3. For the singular value of $k$ where uniqueness fails, provide:
   - A concrete vector $b$ producing infinitely many solutions (consistent dependent system).
   - A concrete vector $b$ producing no solution (inconsistent system).
4. Explain the geometric meaning of these cases in terms of lines in the 2D plane.

---

## 3. Before Calculating: What Idea Do We Need?

- **Cramer's Rule & Invertibility:**
  A linear system $Ax = b$ with a square matrix $A$ has a unique solution for every vector $b$ if and only if $A$ is invertible:

$$
\text{Unique solution for every } b \iff \det A \neq 0
$$

  When $\det A \neq 0$, the unique solution is explicitly given by $x = A^{-1} b$.
- **The Singular Case ($\det A = 0$):**
  When $\det A = 0$, the rows of $A$ are proportional, representing parallel lines:
  - If the equations are scalar multiples of each other on *both* sides, the lines coincide $\implies$ **infinitely many solutions**.
  - If the left-hand sides are proportional but the right-hand sides are not proportional by the same factor, the lines are parallel and distinct $\implies$ **no solution**.

---

## 4. Step-by-Step Solution

### Step 1: Compute $\det A$ and Find the Condition for Uniqueness

For matrix $A$:

$$
A = \begin{pmatrix} 1 & 2 \\\\ k & 4 \end{pmatrix}
$$

The determinant is:

$$
\det A = (1)(4) - (2)(k) = 4 - 2k
$$

The system has a unique solution for every $b$ if and only if $\det A \neq 0$:

$$
4 - 2k \neq 0 \iff 2k \neq 4 \iff k \neq 2
$$

Thus, for all $k \in \mathbb{R} \setminus \{2\}$, the matrix $A$ is invertible, and $Ax = b$ has exactly one solution for every vector $b$.

### Step 2: Analyze the Remaining Case $k = 2$

When $k = 2$, the matrix is:

$$
A = \begin{pmatrix} 1 & 2 \\\\ 2 & 4 \end{pmatrix}
$$

The system $Ax = b$ corresponds to the two scalar equations:

$$
\begin{aligned}
x_1 + 2x_2 &= b_1 \\\\
2x_1 + 4x_2 &= b_2
\end{aligned}
$$

Notice that the left-hand side of Equation (2) is exactly twice the left-hand side of Equation (1):

$$
2(x_1 + 2x_2) = 2x_1 + 4x_2
$$

Therefore, for the system to be consistent, the right-hand sides must satisfy the exact same proportion:

$$
b_2 = 2 b_1
$$

### Step 3: Example with Infinitely Many Solutions

Choose any vector $b = (b_1, b_2)^T$ satisfying $b_2 = 2b_1$.
Let $b_1 = 1$, so $b_2 = 2$:

$$
b = \begin{pmatrix} 1 \\\\ 2 \end{pmatrix}
$$

The system becomes:

$$
\begin{aligned}
x_1 + 2x_2 &= 1 \\\\
2x_1 + 4x_2 &= 2
\end{aligned}
$$

Dividing the second equation by 2 yields $x_1 + 2x_2 = 1$, which is completely identical to the first equation. Both equations describe the exact same geometric line in $\mathbb{R}^2$.
Any point on this line is a solution:

$$
x_1 = 1 - 2x_2, \qquad x_2 \in \mathbb{R}
$$

In vector form, the infinite solution set is:

$$
x = \begin{pmatrix} 1 - 2t \\\\ t \end{pmatrix} = \begin{pmatrix} 1 \\\\ 0 \end{pmatrix} + t \begin{pmatrix} -2 \\\\ 1 \end{pmatrix}, \quad t \in \mathbb{R}
$$

Thus, there are **infinitely many solutions**.

### Step 4: Example with No Solution

Choose any vector $b = (b_1, b_2)^T$ that violates $b_2 = 2b_1$.
Let $b_1 = 1$ and $b_2 = 0$ (so $b_2 \neq 2$):

$$
b = \begin{pmatrix} 1 \\\\ 0 \end{pmatrix}
$$

The system becomes:

$$
\begin{aligned}
x_1 + 2x_2 &= 1 \\\\
2x_1 + 4x_2 &= 0
\end{aligned}
$$

Multiply the first equation by 2:

$$
2x_1 + 4x_2 = 2
$$

Comparing this with the second equation gives:

$$
2 = 0
$$

This is a direct mathematical contradiction. Geometrically, the two equations represent two strictly parallel lines with identical slopes but different $y$-intercepts. The lines never intersect, so there is **no solution**.

---

## 5. Final Answer & Conclusion

- **Unique solution for every $b$:**

$$
k \neq 2 \quad (k \in \mathbb{R} \setminus \{2\})
$$

- **For the singular value $k = 2$:**
  - **Infinitely many solutions:** choose $b$ such that $b_2 = 2b_1$, for example:

$$
b = \begin{pmatrix} 1 \\\\ 2 \end{pmatrix}
$$

  - **No solution:** choose $b$ such that $b_2 \neq 2b_1$, for example:

$$
b = \begin{pmatrix} 1 \\\\ 0 \end{pmatrix}
$$

---

## 6. Quick Verification

Use Gaussian elimination on the augmented matrix $[A \mid b]$ with $k = 2$:

$$
\left(\begin{array}{cc|c} 1 & 2 & b_1 \\\\ 2 & 4 & b_2 \end{array}\right) \xrightarrow{R_2 \leftarrow R_2 - 2R_1} \left(\begin{array}{cc|c} 1 & 2 & b_1 \\\\ 0 & 0 & b_2 - 2b_1 \end{array}\right)
$$

- For $b = (1, 2)^T$: the bottom row becomes $(0 \quad 0 \mid 2 - 2(1)) = (0 \quad 0 \mid 0)$, which is a valid identity $0 = 0 \implies$ infinitely many solutions.
- For $b = (1, 0)^T$: the bottom row becomes $(0 \quad 0 \mid 0 - 2(1)) = (0 \quad 0 \mid -2)$, which means $0 = -2 \implies$ inconsistent, no solution.

---

## 7. Common Mistakes to Avoid

1. **Assuming $\det A = 0$ Means No Solution Only:**
   $\det A = 0$ does not automatically mean zero solutions; it means the system is not uniquely solvable. It can have either *no solution* or *infinitely many solutions*, depending entirely on whether $b$ lies in the column space of $A$.
2. **Forgetting to Multiply Both Sides:**
   When checking compatibility for $k = 2$, forgetting that the multiplier $2$ applies to the right-hand side constant as well.

---

## 8. How I Would Explain This in Class

> "The determinant is $4 - 2k$. As long as $k \neq 2$, the determinant is non-zero, meaning the matrix is invertible and the two lines intersect at a single unique point for any right-hand side $b$. When $k = 2$, the determinant is zero because the left-hand sides are parallel. If we set $b = (1, 2)^T$, the right-hand sides match the ratio of $2$, so the two lines merge into one, giving infinitely many solutions. If we set $b = (1, 0)^T$, the lines are parallel and separated, leading to a contradiction ($0 = -2$) and no solution."