# Problem 04: Infinitely Many Solutions

## 1. The Original Problem

Solve

$$
\begin{cases}
x + y + z = 2, \\\\
2x + 2y + 2z = 4, \\\\
x - y + z = 0.
\end{cases}
$$

Give the solution in parametric form, identify a free variable, and for one chosen parameter value check that the resulting point really satisfies the system.

---

## 2. What Are We Trying to Find?

We need to:
1. Set up the augmented matrix $[A \mid b]$ and reduce it to row echelon form.
2. Determine the rank of the system to identify the number of free variables.
3. Express the bound variables in terms of the chosen free parameter $t$.
4. State the complete solution set in vector parametric form.
5. Pick a concrete numerical parameter value (e.g., $t = 2$), compute the corresponding point, and verify that it satisfies all three equations.

---

## 3. Before Calculating: What Idea Do We Need?

- **Pivots and Free Variables:**
  In row echelon form, columns containing leading entries (pivots) correspond to **basic (bound) variables**. Columns without pivots correspond to **free variables** (parameters) that can take any real value.
- **Degrees of Freedom:**
  By the rank-nullity concept, the number of free variables equals the total number of unknowns minus the rank:

$$
\text{number of free variables} = n - \text{rank}(A)
$$

  Here, $n = 3$. If $\text{rank}(A) = 2$, we have $3 - 2 = 1$ free variable, describing a line in 3D space.
- **Redundant Equations:**
  Notice that the second equation $2x + 2y + 2z = 4$ is simply $2$ times the first equation $x + y + z = 2$. It provides no new information and will eliminate entirely to a row of zeros.

---

## 4. Step-by-Step Solution

### Step 1: Set Up the Augmented Matrix

Write down the $3 \times 4$ augmented matrix:

$$
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 2 \\\\
2 & 2 & 2 & 4 \\\\
1 & -1 & 1 & 0
\end{array}\right]
$$

### Step 2: Row Elimination

Use Row 1 to eliminate the first column in Rows 2 and 3:

1. **Operation $R_2 \leftarrow R_2 - 2R_1$:**
   - $(2, 2, 2 \mid 4) - 2(1, 1, 1 \mid 2) = (0, 0, 0 \mid 0)$
   The second row becomes entirely zeros, reflecting the redundancy.

2. **Operation $R_3 \leftarrow R_3 - R_1$:**
   - First entry: $1 - 1 = 0$
   - Second entry: $-1 - 1 = -2$
   - Third entry: $1 - 1 = 0$
   - Constant entry: $0 - 2 = -2$
   - Row 3 becomes: $(0, -2, 0 \mid -2)$

The matrix is now:

$$
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 2 \\\\
0 & 0 & 0 & 0 \\\\
0 & -2 & 0 & -2
\end{array}\right]
$$

### Step 3: Rearrange into Row Echelon Form

Swap Row 2 and Row 3 so that the non-zero row is above the zero row, and divide Row 2 by $-2$:

$$
R_2 \leftrightarrow R_3 \implies
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 2 \\\\
0 & -2 & 0 & -2 \\\\
0 & 0 & 0 & 0
\end{array}\right]
\xrightarrow{R_2 \leftarrow -\frac{1}{2} R_2}
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 2 \\\\
0 & 1 & 0 & 1 \\\\
0 & 0 & 0 & 0
\end{array}\right]
$$

### Step 4: Identify Free Variables and Solve

- The pivot columns are Column 1 (variable $x$) and Column 2 (variable $y$).
- Column 3 (variable $z$) has no pivot; therefore, $z$ is the **free variable**.
- Let $z = t$, where $t \in \mathbb{R}$ is an arbitrary parameter.

Now solve for the bound variables from bottom to top:

1. **From Row 2:**

$$
1 \cdot y + 0 \cdot z = 1 \implies y = 1
$$

Notice that $y$ has a fixed value of $1$, regardless of the choice of $t$.

2. **From Row 1:**

$$
x + y + z = 2
$$

Substitute $y = 1$ and $z = t$:

$$
x + 1 + t = 2 \implies x = 1 - t
$$

---

## 5. Final Answer & Conclusion

The system has **infinitely many solutions**.
The free variable is $z$. Setting $z = t \in \mathbb{R}$, the solution in scalar parametric form is:

$$
\begin{cases}
x = 1 - t, \\\\
y = 1, \\\\
z = t,
\end{cases}
\quad t \in \mathbb{R}
$$

In vector form, the solution set forms a straight line in $\mathbb{R}^3$:

$$
\begin{pmatrix} x \\\\ y \\\\ z \end{pmatrix} = \begin{pmatrix} 1 - t \\\\ 1 \\\\ t \end{pmatrix} = \begin{pmatrix} 1 \\\\ 1 \\\\ 0 \end{pmatrix} + t \begin{pmatrix} -1 \\\\ 0 \\\\ 1 \end{pmatrix}, \quad t \in \mathbb{R}
$$

---

## 6. Quick Verification

### Verification with Chosen Parameter $t = 2$

Choose $t = 2$. The corresponding candidate point is:

$$
x = 1 - 2 = -1, \quad y = 1, \quad z = 2
$$

Substitute $(x, y, z) = (-1, 1, 2)$ into all three original equations:

1. **Equation 1:**
   $x + y + z = (-1) + 1 + 2 = 2$
   Matches the right-hand side ($2 = 2$). Correct.

2. **Equation 2:**
   $2x + 2y + 2z = 2(-1) + 2(1) + 2(2) = -2 + 2 + 4 = 4$
   Matches the right-hand side ($4 = 4$). Correct.

3. **Equation 3:**
   $x - y + z = (-1) - 1 + 2 = -2 + 2 = 0$
   Matches the right-hand side ($0 = 0$). Correct.

### General Algebraic Verification

Substitute the general expressions $x = 1 - t, y = 1, z = t$ into the equations:
- $x + y + z = (1 - t) + 1 + t = 2$ (Holds identically for all $t$)
- $2x + 2y + 2z = 2(1 - t) + 2(1) + 2t = 2 - 2t + 2 + 2t = 4$ (Holds identically for all $t$)
- $x - y + z = (1 - t) - 1 + t = 0$ (Holds identically for all $t$)

The parametric solution is completely verified.

---

## 7. Common Mistakes to Avoid

1. **Assuming All Variables Must Depend on $t$:**
   Here, $y = 1$ is constant. It is completely valid for some variables in an infinite solution set to remain fixed constants while others vary with $t$.
2. **Forgetting to State the Domain:**
   Omitting the statement that $t \in \mathbb{R}$ leaves the definition of the parameter incomplete.
3. **Missing the Geometric Picture:**
   Failing to realize that the first two equations represent the exact same plane, and the third equation represents an intersecting plane, yielding a 1D line of intersection.

---

## 8. How I Would Explain This in Class

> "When we perform elimination, the second row disappears completely into $0 = 0$ because equation 2 was just equation 1 in disguise. With three variables but only two genuinely independent constraints, one variable is completely free to roam. We let $z = t$, which forces $y$ to stay fixed at $1$ and makes $x$ adjust as $1 - t$, forming a straight line of solutions in space."
