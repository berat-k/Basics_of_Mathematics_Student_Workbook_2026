# Problem 05: Row Echelon Form and Number of Solutions

## 1. The Original Problem

For the augmented matrix

$$
\left[\begin{array}{ccc|c}
1 & 2 & -1 & 3 \\\\
0 & 1 & 2 & 1 \\\\
0 & 0 & 0 & 0
\end{array}\right]
$$

determine the number of solutions and write them in parametric form. Explain how you know how many variables may be chosen freely.

---

## 2. What Are We Trying to Find?

We need to:
1. Analyze the given row echelon form to determine the rank of the coefficient matrix $A$ and the rank of the augmented matrix $[A \mid b]$.
2. Determine whether the system is consistent and identify the total number of solutions.
3. Rigorously explain the algebraic rule governing how many variables can be chosen freely.
4. Express the basic (bound) variables in terms of the free variable parameter.
5. Provide the full solution set in parametric form.

---

## 3. Before Calculating: What Idea Do We Need?

- **Pivots and Rank:**
  In a matrix already in row echelon form:
  - The leading non-zero entry in each row is called a **pivot**.
  - The number of pivots equals the **rank** of the matrix: $\text{rank}(A) = r$.
- **Rouché–Capelli Theorem & Freedom Criterion:**
  - If $\text{rank}(A) = \text{rank}([A \mid b]) = r$, the system is consistent.
  - If $r = n$ (where $n$ is the number of variables), the solution is unique.
  - If $r < n$, there are **infinitely many solutions**.
  - The number of free variables (degrees of freedom) is precisely:

$$
\text{Number of free variables} = n - \text{rank}(A) = n - r
$$

- **Identifying Free vs. Bound Variables:**
  - Variables corresponding to columns with a pivot are **basic (bound) variables**.
  - Variables corresponding to columns without a pivot are **free variables** (parameters).

---

## 4. Step-by-Step Solution

### Step 1: Identify Pivots and Column Roles

Examine the $3 \times 4$ augmented matrix:

$$
\left[\begin{array}{ccc|c}
\mathbf{1} & 2 & -1 & 3 \\\\
0 & \mathbf{1} & 2 & 1 \\\\
0 & 0 & 0 & 0
\end{array}\right]
$$

- **Row 1:** The leading entry is in Column 1 (pivot $= 1$). Variable $x_1$ is bound.
- **Row 2:** The leading entry is in Column 2 (pivot $= 1$). Variable $x_2$ is bound.
- **Row 3:** All entries are zero ($0 = 0$). No contradiction is present, so the system is consistent.
- **Column 3:** Contains no pivot. Therefore, variable $x_3$ is a **free variable**.

### Step 2: Determine Ranks and Number of Free Variables

- Total number of unknowns: $n = 3$ (representing $x_1, x_2, x_3$).
- Rank of coefficient matrix: $\text{rank}(A) = 2$ (two non-zero rows).
- Rank of augmented matrix: $\text{rank}([A \mid b]) = 2$.
- Because $\text{rank}(A) = \text{rank}([A \mid b]) = 2 < 3$, the system has **infinitely many solutions**.
- The number of variables that may be chosen freely is:

$$
n - \text{rank}(A) = 3 - 2 = 1
$$

Thus, exactly **one** variable may be chosen freely. We assign $x_3 = t$, where $t \in \mathbb{R}$.

### Step 3: Back-Substitution to Solve for Bound Variables

1. **Solve for $x_2$ from Row 2:**

$$
0x_1 + 1x_2 + 2x_3 = 1 \implies x_2 + 2t = 1 \implies x_2 = 1 - 2t
$$

2. **Solve for $x_1$ from Row 1:**

$$
1x_1 + 2x_2 - 1x_3 = 3
$$

Substitute $x_2 = 1 - 2t$ and $x_3 = t$:

$$
x_1 + 2(1 - 2t) - t = 3
$$

Expand and simplify:

$$
x_1 + 2 - 4t - t = 3 \implies x_1 + 2 - 5t = 3 \implies x_1 = 1 + 5t
$$

---

## 5. Final Answer & Conclusion

- **Number of Solutions:** The system has **infinitely many solutions**.
- **Number of Free Variables:** Exactly **one** variable ($x_3$) can be chosen freely because $n - \text{rank}(A) = 3 - 2 = 1$.
- **Parametric Form:**
  Setting $x_3 = t$ for any $t \in \mathbb{R}$:

$$
\begin{cases}
x_1 = 1 + 5t, \\\\
x_2 = 1 - 2t, \\\\
x_3 = t,
\end{cases}
\quad t \in \mathbb{R}
$$

In vector form:

$$
\begin{pmatrix} x_1 \\\\ x_2 \\\\ x_3 \end{pmatrix} = \begin{pmatrix} 1 \\\\ 1 \\\\ 0 \end{pmatrix} + t \begin{pmatrix} 5 \\\\ -2 \\\\ 1 \end{pmatrix}, \quad t \in \mathbb{R}
$$

---

## 6. Quick Verification

Substitute the parametric solution into the system's rows to verify consistency for all $t$:

1. **Row 1:**

$$
x_1 + 2x_2 - x_3 = (1 + 5t) + 2(1 - 2t) - t = 1 + 5t + 2 - 4t - t = 3
$$

The result is identically $3$, matching the right-hand side.

2. **Row 2:**

$$
x_2 + 2x_3 = (1 - 2t) + 2t = 1
$$

The result is identically $1$, matching the right-hand side.

3. **Row 3:**
$0x_1 + 0x_2 + 0x_3 = 0$, which matches $0$.

Check for concrete values:
- For $t = 0$: $(x_1, x_2, x_3) = (1, 1, 0) \implies 1 + 2(1) - 0 = 3$ and $1 + 2(0) = 1$. Correct.
- For $t = 1$: $(x_1, x_2, x_3) = (6, -1, 1) \implies 6 + 2(-1) - 1 = 3$ and $-1 + 2(1) = 1$. Correct.

---

## 7. Common Mistakes to Avoid

1. **Thinking That All Zero Rows Mean No Solution:**
   A row $(0, 0, 0 \mid 0)$ represents $0 = 0$, which is always true and means redundancy, not a contradiction.
2. **Counting the Total Number of Rows Instead of Pivots:**
   The number of free variables is determined by $n - \text{rank}(A)$, not by the number of original equations minus variables. Always count pivots in row echelon form.
3. **Sign Errors in Back-Substitution:**
   Computing $x_1 + 2 - 5t = 3 \implies x_1 = 3 - 2 + 5t = 1 + 5t$. A frequent slip is writing $1 - 5t$.

---

## 8. How I Would Explain This in Class

> "Because the matrix is already in echelon form, we immediately scan the diagonal: columns 1 and 2 have leading ones, while column 3 has none. With 3 variables and 2 pivots, our degrees of freedom are $3 - 2 = 1$. That means $x_3$ gets to be our parameter $t$, and back-substituting gives $x_2 = 1 - 2t$ and $x_1 = 1 + 5t$, tracing out a one-dimensional line in 3D space."
