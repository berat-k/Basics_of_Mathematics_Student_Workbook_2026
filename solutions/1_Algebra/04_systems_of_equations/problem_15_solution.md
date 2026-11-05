# Problem 15: Classifying Three Systems

## 1. The Original Problem

For each of the following systems, perform only as much elimination as necessary to recognize its type:

1. 

$$
\begin{cases}
x + y = 2, \\\\
x - y = 0,
\end{cases}
$$

2. 

$$
\begin{cases}
x + y = 2, \\\\
2x + 2y = 4,
\end{cases}
$$

3. 

$$
\begin{cases}
x + y = 2, \\\\
2x + 2y = 5.
\end{cases}
$$

For each, justify the classification: one solution, infinitely many solutions, or no solution.

---

## 2. What Are We Trying to Find?

We need to:
1. Apply minimal Gaussian elimination to each of the three $2 \times 2$ systems.
2. Stop the elimination process at the earliest point where the structural type of the system becomes obvious.
3. Rigorously classify each system into one of the three foundational categories:
   - Exactly one unique solution.
   - Infinitely many solutions.
   - No solution (inconsistent).
4. Provide justification for each classification using rank, pivot positions, and geometric interpretation.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Three Structural Patterns in Echelon Form:**
  After applying row operations to a $2 \times 2$ system $[A \mid b]$:
  1. **Two non-zero pivots on the diagonal:**

$$
\left[\begin{array}{cc|c} * & * & * \\\\ 0 & * & * \end{array}\right] \implies \text{rank}(A) = \text{rank}([A \mid b]) = 2 = n \implies \textbf{Exactly One Solution}
$$

  2. **A complete row of zeros:**

$$
\left[\begin{array}{cc|c} * & * & * \\\\ 0 & 0 & 0 \end{array}\right] \implies \text{rank}(A) = \text{rank}([A \mid b]) = 1 < 2 \implies \textbf{Infinitely Many Solutions}
$$

  3. **A zero row with a non-zero constant ($0 = c$ with $c \neq 0$):**

$$
\left[\begin{array}{cc|c} * & * & * \\\\ 0 & 0 & c \end{array}\right] \implies \text{rank}(A) = 1 < 2 = \text{rank}([A \mid b]) \implies \textbf{No Solution}
$$

- **Minimal Effort Principle:**
  Once the pivot structure of the echelon form is visible, full back-substitution is unnecessary to determine the *number* of solutions.

---

## 4. Step-by-Step Solution

### System 1: Analysis

$$
\begin{cases}
x + y = 2 \\\\
x - y = 0
\end{cases}
$$

1. **Augmented Matrix:**

$$
\left[\begin{array}{cc|c}
1 & 1 & 2 \\\\
1 & -1 & 0
\end{array}\right]
$$

2. **Single Elimination Step ($R_2 \leftarrow R_2 - R_1$):**
   - Column 1: $1 - 1 = 0$
   - Column 2: $-1 - 1 = -2$
   - Right-hand side: $0 - 2 = -2$

The matrix becomes:

$$
\left[\begin{array}{cc|c}
1 & 1 & 2 \\\\
0 & -2 & -2
\end{array}\right]
$$

3. **Classification and Justification:**
   - There are two pivots: $a_{11} = 1$ in Row 1 and $a_{22} = -2$ in Row 2.
   - The rank of $A$ is $2$, which equals the number of unknowns ($n = 2$).
   - The augmented matrix also has rank $2$.
   - **Classification:** **Exactly one solution** (Unique solution: $y = 1, x = 1$).
   - **Geometric Meaning:** Two straight lines with distinct slopes ($m_1 = -1, m_2 = 1$) meeting at a single point $(1, 1)$.

---

### System 2: Analysis

$$
\begin{cases}
x + y = 2 \\\\
2x + 2y = 4
\end{cases}
$$

1. **Augmented Matrix:**

$$
\left[\begin{array}{cc|c}
1 & 1 & 2 \\\\
2 & 2 & 4
\end{array}\right]
$$

2. **Single Elimination Step ($R_2 \leftarrow R_2 - 2R_1$):**
   - Column 1: $2 - 2(1) = 0$
   - Column 2: $2 - 2(1) = 0$
   - Right-hand side: $4 - 2(2) = 0$

The matrix becomes:

$$
\left[\begin{array}{cc|c}
1 & 1 & 2 \\\\
0 & 0 & 0
\end{array}\right]
$$

3. **Classification and Justification:**
   - Row 2 consists entirely of zeros, representing the identity $0 = 0$.
   - The system is consistent: $\text{rank}(A) = \text{rank}([A \mid b]) = 1$.
   - Because $\text{rank}(A) = 1 < 2 = n$, there is $n - \text{rank}(A) = 2 - 1 = 1$ free variable.
   - **Classification:** **Infinitely many solutions** (The line $\{ (2 - t, t) \mid t \in \mathbb{R} \}$).
   - **Geometric Meaning:** Both equations represent the exact same line; every point on the line satisfies the system.

---

### System 3: Analysis

$$
\begin{cases}
x + y = 2 \\\\
2x + 2y = 5
\end{cases}
$$

1. **Augmented Matrix:**

$$
\left[\begin{array}{cc|c}
1 & 1 & 2 \\\\
2 & 2 & 5
\end{array}\right]
$$

2. **Single Elimination Step ($R_2 \leftarrow R_2 - 2R_1$):**
   - Column 1: $2 - 2(1) = 0$
   - Column 2: $2 - 2(1) = 0$
   - Right-hand side: $5 - 2(2) = 5 - 4 = 1$

The matrix becomes:

$$
\left[\begin{array}{cc|c}
1 & 1 & 2 \\\\
0 & 0 & 1
\end{array}\right]
$$

3. **Classification and Justification:**
   - Row 2 translates to $0 \cdot x + 0 \cdot y = 1 \implies 0 = 1$, which is an impossible contradiction.
   - Ranks: $\text{rank}(A) = 1$, but $\text{rank}([A \mid b]) = 2$.
   - Because $\text{rank}(A) < \text{rank}([A \mid b])$, the system is inconsistent.
   - **Classification:** **No solution**.
   - **Geometric Meaning:** Two distinct parallel lines ($y = -x + 2$ and $y = -x + 2.5$) that never intersect.

---

## 5. Final Answer & Conclusion

| System | Echelon Form (Rows) | Rank Criterion | Geometric Interpretation | Classification |
| :--- | :--- | :--- | :--- | :--- |
| **System 1** | $(1, 1 \mid 2)$ and $(0, -2 \mid -2)$ | $\text{rank}(A) = \text{rank}([A \mid b]) = 2 = n$ | Non-parallel lines intersecting at $(1, 1)$ | **Exactly one solution** |
| **System 2** | $(1, 1 \mid 2)$ and $(0, 0 \mid 0)$ | $\text{rank}(A) = \text{rank}([A \mid b]) = 1 < n$ | Coincident (identical) lines | **Infinitely many solutions** |
| **System 3** | $(1, 1 \mid 2)$ and $(0, 0 \mid 1)$ | $\text{rank}(A) = 1 < 2 = \text{rank}([A \mid b])$ | Distinct parallel lines | **No solution** |

---

## 6. Quick Verification

1. **System 1:** Determinant of coefficient matrix $A$ is $\det(A) = 1(-1) - 1(1) = -2 \neq 0$. Non-zero determinant guarantees a unique solution.
2. **System 2:** Second equation is $2(x + y) = 4 \iff x + y = 2$. Identical to Equation 1. Infinitely many solutions confirmed.
3. **System 3:** Second equation divided by $2$ gives $x + y = 2.5$. The first equation requires $x + y = 2$. A sum cannot be both $2$ and $2.5$. Contradiction confirmed.

---

## 7. Common Mistakes to Avoid

1. **Calculating Further Than Necessary:**
   Computing the exact numerical coordinates for all systems when the question only asks to determine the *type* of system.
2. **Confusing Row $(0 \quad 0 \mid 0)$ with $(0 \quad 0 \mid 1)$:**
   A row of pure zeros means consistency with a free variable; a row with a non-zero right-hand side means contradiction and no solution.
3. **Confusing No Solution with Zero Solution:**
   Thinking "no solution" means $(0, 0)$. $(0, 0)$ gives $0+0=0 \neq 5$, so it is not a solution.

---

## 8. How I Would Explain This in Class

> "This problem demonstrates the three fundamental fates of any linear system in miniature: after just a single subtraction, System 1 gives pivots in both columns (two lines crossing at a point), System 2 vanishes into $0 = 0$ (the exact same line written twice), and System 3 produces $0 = 1$ (parallel lines that can never touch). By looking only at the echelon structure, you can diagnose the system's fate in seconds."
