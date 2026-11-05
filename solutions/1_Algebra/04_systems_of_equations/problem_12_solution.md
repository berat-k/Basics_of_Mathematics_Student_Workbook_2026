# Problem 12: Homogeneous System

## 1. The Original Problem

Solve

$$
\begin{cases}
x + 2y - z = 0, \\\\
2x + 4y - 2z = 0, \\\\
x - y + 2z = 0.
\end{cases}
$$

Give all solutions in parametric form and explain why $(0, 0, 0)$ always satisfies a homogeneous system.

---

## 2. What Are We Trying to Find?

We need to:
1. Explain theoretically why the zero vector $(0, 0, 0)$ is always guaranteed to satisfy any homogeneous system.
2. Set up the augmented matrix for the system and reduce it to row echelon form.
3. Identify the rank and the number of free variables.
4. Solve for the basic variables in terms of the free parameter.
5. State the complete solution set in vector parametric form.

---

## 3. Before Calculating: What Idea Do We Need?

- **Definition of a Homogeneous System:**
  A linear system is called **homogeneous** when all constant terms on the right-hand side are zero:

$$
A x = \mathbf{0}
$$

- **The Trivial Solution ($x = \mathbf{0}$):**
  A homogeneous system can **never be inconsistent** because substituting $x = 0, y = 0, z = 0$ into the left-hand side yields:

$$
A \mathbf{0} = \begin{pmatrix} \sum a_{1j} \cdot 0 \\\\ \sum a_{2j} \cdot 0 \\\\ \sum a_{3j} \cdot 0 \end{pmatrix} = \begin{pmatrix} 0 \\\\ 0 \\\\ 0 \end{pmatrix} = \mathbf{0}
$$

  Because each term in each linear equation is multiplied by zero, the sum is identically zero. Thus, $\mathbf{0} = (0, 0, 0)^T$ is always a solution (called the **trivial solution**).
- **Non-Trivial Solutions:**
  A homogeneous system has non-trivial (non-zero) solutions if and only if $\text{rank}(A) < n$ (which, for square systems, is equivalent to $\det(A) = 0$). In this case, the solution set forms a subspace (the null space of $A$).

---

## 4. Step-by-Step Solution

### Step 1: Why $(0, 0, 0)$ Always Satisfies the System

Consider any equation in the system, written in general linear form:

$$
a_i x + b_i y + c_i z = 0
$$

When we substitute $x = 0, y = 0,$ and $z = 0$:

$$
a_i(0) + b_i(0) + c_i(0) = 0 + 0 + 0 = 0
$$

This equality holds regardless of what values the coefficients $a_i, b_i, c_i$ take. Because this holds for all equations simultaneously, the origin $(0, 0, 0)$ is unconditionally a solution to every homogeneous system.

---

### Step 2: Set Up the Augmented Matrix

Write down the $3 \times 4$ augmented matrix:

$$
\left[\begin{array}{ccc|c}
1 & 2 & -1 & 0 \\\\
2 & 4 & -2 & 0 \\\\
1 & -1 & 2 & 0
\end{array}\right]
$$

### Step 3: Perform Row Elimination

1. **Operation $R_2 \leftarrow R_2 - 2R_1$:**
   - Notice that Row 2 is exactly twice Row 1:
   - $(2, 4, -2 \mid 0) - 2(1, 2, -1 \mid 0) = (0, 0, 0 \mid 0)$
   Row 2 is completely redundant.

2. **Operation $R_3 \leftarrow R_3 - R_1$:**
   - Column 1: $1 - 1 = 0$
   - Column 2: $-1 - 2 = -3$
   - Column 3: $2 - (-1) = 2 + 1 = 3$
   - Right-hand side: $0 - 0 = 0$

The matrix is now:

$$
\left[\begin{array}{ccc|c}
1 & 2 & -1 & 0 \\\\
0 & 0 & 0 & 0 \\\\
0 & -3 & 3 & 0
\end{array}\right]
$$

### Step 4: Arrange into Row Echelon Form

Swap Row 2 and Row 3, then divide the new Row 2 by $-3$:

$$
R_2 \leftrightarrow R_3 \implies
\left[\begin{array}{ccc|c}
1 & 2 & -1 & 0 \\\\
0 & -3 & 3 & 0 \\\\
0 & 0 & 0 & 0
\end{array}\right]
\xrightarrow{R_2 \leftarrow -\frac{1}{3} R_2}
\left[\begin{array}{ccc|c}
1 & 2 & -1 & 0 \\\\
0 & 1 & -1 & 0 \\\\
0 & 0 & 0 & 0
\end{array}\right]
$$

### Step 5: Solve for Bound Variables

- Pivot columns: Column 1 ($x$) and Column 2 ($y$).
- Free column: Column 3 ($z$).
- Rank: $\text{rank}(A) = 2$.
- Number of free variables: $n - \text{rank}(A) = 3 - 2 = 1$.
- Let $z = t$, where $t \in \mathbb{R}$.

Now perform back-substitution:
1. **From Row 2:**

$$
y - z = 0 \implies y = z = t
$$

2. **From Row 1:**

$$
x + 2y - z = 0
$$

Substitute $y = t$ and $z = t$:

$$
x + 2(t) - t = 0 \implies x + t = 0 \implies x = -t
$$

---

## 5. Final Answer & Conclusion

- **Why $(0, 0, 0)$ is always a solution:**
  Multiplying any coefficients by zero produces zero, so the trivial vector $x = \mathbf{0}$ satisfies $A \mathbf{0} = \mathbf{0}$ for every linear system with a zero right-hand side.
- **Complete Solution Set:**
  Because $\text{rank}(A) = 2 < 3$, non-trivial solutions exist. With free parameter $z = t \in \mathbb{R}$, the solution set is:

$$
\begin{cases}
x = -t, \\\\
y = t, \\\\
z = t,
\end{cases}
\quad t \in \mathbb{R}
$$

In vector form:

$$
\begin{pmatrix} x \\\\ y \\\\ z \end{pmatrix} = t \begin{pmatrix} -1 \\\\ 1 \\\\ 1 \end{pmatrix}, \quad t \in \mathbb{R}
$$

Geometrically, this represents a line in $\mathbb{R}^3$ passing through the origin $(0, 0, 0)$ in the direction of the vector $(-1, 1, 1)^T$. Setting $t = 0$ returns the trivial solution $(0, 0, 0)^T$.

---

## 6. Quick Verification

Substitute the general parametric solution $(-t, t, t)$ into each of the original equations:

1. **Equation 1:**

$$
x + 2y - z = (-t) + 2(t) - t = -t + 2t - t = 0
$$

Matches 0. Correct.

2. **Equation 2:**

$$
2x + 4y - 2z = 2(-t) + 4(t) - 2(t) = -2t + 4t - 2t = 0
$$

Matches 0. Correct.

3. **Equation 3:**

$$
x - y + 2z = (-t) - (t) + 2(t) = -2t + 2t = 0
$$

Matches 0. Correct.

Testing for a concrete non-zero value, let $t = 1 \implies (x, y, z) = (-1, 1, 1)$:
- Eq 1: $-1 + 2(1) - 1 = 0$
- Eq 2: $2(-1) + 4(1) - 2(1) = -2 + 4 - 2 = 0$
- Eq 3: $-1 - 1 + 2(1) = 0$
All hold identically.

---

## 7. Common Mistakes to Avoid

1. **Claiming a Homogeneous System Has "No Solution":**
   A homogeneous system can never have no solution; $(0, 0, 0)$ is always an automatic solution.
2. **Stopping at the Trivial Solution:**
   Thinking $(0, 0, 0)$ is the only answer without checking the rank. When $\text{rank}(A) < n$, there are infinitely many non-trivial solutions in addition to $(0, 0, 0)$.
3. **Sign Errors in Row Operations:**
   In $R_3 \leftarrow R_3 - R_1$, calculating $2 - (-1)$ as $2 - 1 = 1$ instead of $2 + 1 = 3$.

---

## 8. How I Would Explain This in Class

> "A homogeneous system is like an equation where every term has a variable attached and the total is zero: if you set every single variable to zero, every term collapses to zero, which means the origin $(0, 0, 0)$ is always guaranteed to work. But because our second equation was just a duplicate of the first, our constraints collapse into a single line through the origin, giving infinitely many non-zero solutions along the direction $(-1, 1, 1)$."
