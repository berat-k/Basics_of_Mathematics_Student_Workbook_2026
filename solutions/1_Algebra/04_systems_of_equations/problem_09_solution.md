# Problem 09: A System from a Sum Condition

## 1. The Original Problem

Find numbers $x, y$ satisfying

$$
x + y = 10, \qquad 2x + 5y = 32.
$$

Solve the system and explain geometrically why the solution is unique.

---

## 2. What Are We Trying to Find?

We need to:
1. Translate the two linear conditions into a standard linear system.
2. Solve for the unknown numbers $x$ and $y$ using Gaussian elimination.
3. Provide a rigorous geometric interpretation in $\mathbb{R}^2$, showing how the equations represent lines and why their slopes guarantee a single unique intersection point.

---

## 3. Before Calculating: What Idea Do We Need?

- **Algebraic System Representation:**
  The system consists of two equations in two unknowns:

$$
\begin{cases}
x + y = 10, \\\\
2x + 5y = 32
\end{cases}
$$

- **Geometric Meaning of Linear Equations in 2D:**
  In the Cartesian plane $\mathbb{R}^2$, an equation of the form $ax + by = c$ defines a straight line.
  - The solution set of the system corresponds to the set of all points $(x, y)$ where the two lines intersect.
  - Two lines in $\mathbb{R}^2$ have: exactly one intersection point if their slopes are distinct (non-parallel lines); no intersection points if their slopes are equal but intercepts differ (parallel lines); or infinitely many intersection points if they coincide.
- **Determinant Criterion:**
  For the coefficient matrix:

$$
A = \begin{pmatrix} 1 & 1 \\\\ 2 & 5 \end{pmatrix}
$$

  its determinant is $\det(A) = 1(5) - 1(2) = 3 \neq 0$. An invertible coefficient matrix guarantees a unique solution.

---

## 4. Step-by-Step Solution

### Step 1: Form the Augmented Matrix

Write down the $2 \times 3$ augmented matrix:

$$
\left[\begin{array}{cc|c}
1 & 1 & 10 \\\\
2 & 5 & 32
\end{array}\right]
$$

### Step 2: Perform Row Elimination

Eliminate the $x$-term in Row 2 using the elementary row operation $R_2 \leftarrow R_2 - 2R_1$:

- First column: $2 - 2(1) = 0$
- Second column: $5 - 2(1) = 3$
- Right-hand side: $32 - 2(10) = 32 - 20 = 12$

The matrix is now in row echelon form:

$$
\left[\begin{array}{cc|c}
1 & 1 & 10 \\\\
0 & 3 & 12
\end{array}\right]
$$

### Step 3: Back-Substitution

1. **Solve for $y$ from Row 2:**

$$
3y = 12 \implies y = \frac{12}{3} = 4
$$

2. **Solve for $x$ from Row 1:**

$$
x + y = 10
$$

Substitute $y = 4$:

$$
x + 4 = 10 \implies x = 10 - 4 = 6
$$

---

### Step 4: Geometric Explanation of Uniqueness

Convert both linear equations into slope-intercept form ($y = mx + k$):

1. **First Line ($L_1$):**

$$
x + y = 10 \implies y = -x + 10
$$

   - Slope: $m_1 = -1$
   - $y$-intercept: $(0, 10)$
   - Normal vector: $n_1 = (1, 1)$

2. **Second Line ($L_2$):**

$$
2x + 5y = 32 \implies 5y = -2x + 32 \implies y = -\frac{2}{5}x + \frac{32}{5} = -0.4x + 6.4
$$

   - Slope: $m_2 = -\frac{2}{5} = -0.4$
   - $y$-intercept: $(0, 6.4)$
   - Normal vector: $n_2 = (2, 5)$

Because the slopes are strictly distinct:

$$
m_1 = -1 \neq -0.4 = m_2
$$

the two normal vectors $n_1$ and $n_2$ are not parallel (linearly independent). In Euclidean plane geometry, any two straight lines with different slopes cannot run parallel; they must intersect at **exactly one unique point**. That point of concurrency is $(6, 4)$.

---

## 5. Final Answer & Conclusion

- **The Numbers:**

$$
x = 6, \quad y = 4
$$

- **Vector Form:**

$$
\begin{pmatrix} x \\\\ y \end{pmatrix} = \begin{pmatrix} 6 \\\\ 4 \end{pmatrix}
$$

- **Geometric Conclusion:**
  The equations describe two straight lines in $\mathbb{R}^2$ with distinct slopes ($m_1 = -1$ and $m_2 = -0.4$). Because the lines are non-parallel, they intersect at precisely one point: $(6, 4)$.

---

## 6. Quick Verification

Substitute $x = 6$ and $y = 4$ into both original equations:

1. **First Equation:**

$$
x + y = 6 + 4 = 10
$$

Matches the right-hand side ($10 = 10$). Correct.

2. **Second Equation:**

$$
2x + 5y = 2(6) + 5(4) = 12 + 20 = 32
$$

Matches the right-hand side ($32 = 32$). Correct.

Both conditions are verified.

---

## 7. Common Mistakes to Avoid

1. **Confusing Sum Constraints with Multiplications:**
   Accidentally treating $x+y=10$ as a single variable substitution without setting up the full system.
2. **Arithmetic Errors in Division:**
   Dividing $3y = 12$ incorrectly or confusing signs during elimination.
3. **Omitting the Geometric Reason for Uniqueness:**
   Simply stating "the solution is unique because we found numbers" instead of explaining that distinct slopes mean the lines must cross at exactly one geometric point.

---

## 8. How I Would Explain This in Class

> "Every linear equation in two unknowns draws a straight line across the coordinate plane. The first line slopes downwards steeply at an angle with slope $-1$, while the second slopes downwards gently with slope $-0.4$. Because their slopes are different, the lines cannot be parallel—they are destined to cross at exactly one unique meeting point, which our algebra reveals to be $(6, 4)$."
