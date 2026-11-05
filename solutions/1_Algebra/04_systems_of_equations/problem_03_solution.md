# Problem 03: Inconsistent System

## 1. The Original Problem

Solve or show that the system is inconsistent:

$$
\begin{cases}
x + 2y = 3, \\\\
2x + 4y = 7
\end{cases}
$$

Show how the contradiction appears in the matrix after elimination and interpret it in terms of equations.

---

## 2. What Are We Trying to Find?

We need to:
1. Set up the augmented matrix $[A \mid b]$ for the $2 \times 2$ system.
2. Perform Gaussian elimination to reduce the matrix to row echelon form.
3. Identify the specific row contradiction that proves the system has no solution.
4. Interpret the algebraic contradiction both in terms of scalar equations and through the geometric relationship between two lines in the Cartesian plane.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Row Echelon Contradiction Pattern:**
  If Gaussian elimination produces a row of the form:

$$
\begin{pmatrix} 0 & 0 & \cdots & 0 & \mid & c \end{pmatrix} \quad \text{with } c \neq 0
$$

  this translates to the equation $0x_1 + 0x_2 + \cdots + 0x_n = c$, or simply $0 = c$. Because $0 \neq c$, no choice of variables can ever satisfy this equation, proving the system is **inconsistent** (has no solution).
- **Rouché–Capelli Theorem (Rank Criterion):**
  A linear system $Ax = b$ is consistent if and only if the rank of the coefficient matrix equals the rank of the augmented matrix:

$$
\text{rank}(A) = \text{rank}([A \mid b])
$$

  If $\text{rank}(A) < \text{rank}([A \mid b])$, the system has no solution.
- **Geometric Interpretation in $\mathbb{R}^2$:**
  Each equation represents a straight line. If two lines share the same normal vector (or slope) but have different constant terms, they are strictly parallel and disjoint.

---

## 4. Step-by-Step Solution

### Step 1: Form the Augmented Matrix

Write down the augmented matrix:

$$
\left[\begin{array}{cc|c}
1 & 2 & 3 \\\\
2 & 4 & 7
\end{array}\right]
$$

### Step 2: Perform Row Elimination

We use Row 1 to eliminate the $x$-coefficient in Row 2 via the elementary row operation $R_2 \leftarrow R_2 - 2R_1$:

- First entry: $2 - 2(1) = 0$
- Second entry: $4 - 2(2) = 4 - 4 = 0$
- Right-hand side entry: $7 - 2(3) = 7 - 6 = 1$

The resulting augmented matrix is:

$$
\left[\begin{array}{cc|c}
1 & 2 & 3 \\\\
0 & 0 & 1
\end{array}\right]
$$

### Step 3: Interpret the Resulting Row

Translate Row 2 back into equation form:

$$
0 \cdot x + 0 \cdot y = 1 \implies 0 = 1
$$

This is a mathematical impossibility (contradiction) regardless of the values chosen for $x$ and $y$.

### Step 4: Rank Analysis and Geometric Meaning

1. **Rank Analysis:**
   - The coefficient matrix has one non-zero row: $\text{rank}(A) = 1$.
   - The augmented matrix has two non-zero rows: $\text{rank}([A \mid b]) = 2$.
   - Because $\text{rank}(A) = 1 \neq 2 = \text{rank}([A \mid b])$, the system is inconsistent.

2. **Geometric Analysis:**
   Express both equations in slope-intercept form ($y = mx + k$):
   - From Equation 1: $2y = -x + 3 \implies y = -\frac{1}{2}x + \frac{3}{2}$
   - From Equation 2: $4y = -2x + 7 \implies y = -\frac{1}{2}x + \frac{7}{4}$

   Both lines have identical slope $m = -1/2$, but distinct $y$-intercepts:

$$
\frac{3}{2} = 1.5 \neq 1.75 = \frac{7}{4}
$$

   Two lines in a plane with identical slope and different intercepts are strictly parallel and never intersect.

---

## 5. Final Answer & Conclusion

- **Solution:** The system is **inconsistent**; there is no solution (the solution set is empty: $\emptyset$).
- **Matrix Manifestation:** Elimination produces the contradiction row $(0, 0 \mid 1)$, corresponding to $0 = 1$.
- **Geometric Meaning:** The two equations represent distinct parallel lines in $\mathbb{R}^2$ that share no common point of intersection.

---

## 6. Quick Verification

Multiply the first equation by $2$:

$$
2 \cdot (x + 2y) = 2 \cdot 3 \implies 2x + 4y = 6
$$

Now compare this with the second equation:

$$
2x + 4y = 7
$$

Subtracting the first transformed equation from the second equation directly gives:

$$
(2x + 4y) - (2x + 4y) = 7 - 6 \implies 0 = 1
$$

This algebraic contradiction confirms beyond any doubt that no pair $(x, y)$ can satisfy both equations.

---

## 7. Common Mistakes to Avoid

1. **Confusing "No Solution" with $x = 0, y = 0$:**
   $x = 0, y = 0$ is a valid numerical solution (the origin), not a contradiction. Here, no numbers exist at all.
2. **Confusing $(0, 0 \mid 0)$ with $(0, 0 \mid 1)$:**
   A row of all zeros represents $0 = 0$ (a true statement that introduces free variables and infinitely many solutions). A row of zeros followed by a non-zero number represents $0 = 1$ (a false statement that means no solution).
3. **Stopping Elimination Prematurely:**
   Assuming a system has a solution before checking the right-hand side during elimination.

---

## 8. How I Would Explain This in Class

> "If you buy one apple and two bananas for 3 dollars, then doubling your order to two apples and four bananas must cost exactly 6 dollars. If the cashier asks for 7 dollars, the prices are contradictory and the scenario is impossible. In the matrix, this impossibility shows up as the bottom row $0 = 1$, which geometrically means the two lines run parallel and never cross."
