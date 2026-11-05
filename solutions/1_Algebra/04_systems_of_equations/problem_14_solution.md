# Problem 14: A Small Change in the Right-Hand Side

## 1. The Original Problem

Compare the systems

$$
\begin{cases}
x + y = 2, \\\\
2x - y = 1, \\\\
3x = 3
\end{cases}
\qquad \text{and} \qquad
\begin{cases}
x + y = 2, \\\\
2x - y = 1, \\\\
3x = 3.1.
\end{cases}
$$

Check the consistency of each system and explain why a small change in one number can change the type of the system.

---

## 2. What Are We Trying to Find?

We need to:
1. Perform Gaussian elimination on both overdetermined systems (3 equations, 2 unknowns).
2. Check the consistency of System A and compute its solution if one exists.
3. Check the consistency of System B and identify the contradiction row if inconsistent.
4. Explain geometrically and algebraically why changing a single number slightly from $3$ to $3.1$ fundamentally alters the system from having a unique solution to having no solution.

---

## 3. Before Calculating: What Idea Do We Need?

- **Overdetermined Systems ($m > n$):**
  When there are more equations ($m = 3$) than variables ($n = 2$), the system has redundant constraints.
  - Generically, three random lines in a 2D plane do not meet at a single common point; they form a triangle.
  - An overdetermined system is consistent if and only if the right-hand side vector $b$ belongs to the column space of $A$:

$$
b \in \text{Col}(A) \iff \text{rank}([A \mid b]) = \text{rank}(A)
$$

- **The Geometry of Concurrency:**
  In System A, the first two equations uniquely define the point $(x, y) = (1, 1)$. Adding equation 1 and equation 2 yields:

$$
(x + y) + (2x - y) = 3x, \quad \text{and} \quad 2 + 1 = 3 \implies 3x = 3
$$

  Because Equation 3 is the exact sum of Equations 1 and 2, all three lines pass through the exact same point $(1, 1)$ (concurrent lines).
  Slightly perturbing the constant to $3.1$ shifts the third line parallel to itself, moving it away from the intersection point and destroying concurrency.

---

## 4. Step-by-Step Solution

### Step 1: Analyze System A

The augmented matrix for System A is:

$$
\left[\begin{array}{cc|c}
1 & 1 & 2 \\\\
2 & -1 & 1 \\\\
3 & 0 & 3
\end{array}\right]
$$

Apply Gaussian elimination:
1. **$R_2 \leftarrow R_2 - 2R_1$:**
   - Column 1: $2 - 2(1) = 0$
   - Column 2: $-1 - 2(1) = -3$
   - Right side: $1 - 2(2) = -3$

2. **$R_3 \leftarrow R_3 - 3R_1$:**
   - Column 1: $3 - 3(1) = 0$
   - Column 2: $0 - 3(1) = -3$
   - Right side: $3 - 3(2) = 3 - 6 = -3$

The matrix is now:

$$
\left[\begin{array}{cc|c}
1 & 1 & 2 \\\\
0 & -3 & -3 \\\\
0 & -3 & -3
\end{array}\right]
$$

3. **$R_3 \leftarrow R_3 - R_2$:**
   - $(0, -3 \mid -3) - (0, -3 \mid -3) = (0, 0 \mid 0)$

The row echelon form is:

$$
\left[\begin{array}{cc|c}
1 & 1 & 2 \\\\
0 & -3 & -3 \\\\
0 & 0 & 0
\end{array}\right]
$$

- Ranks: $\text{rank}(A) = 2$, $\text{rank}([A \mid b]) = 2$.
- Because $\text{rank}(A) = \text{rank}([A \mid b]) = n = 2$, **System A is consistent** with a **unique solution**.
- Back-substitution:
  - From Row 2: $-3y = -3 \implies y = 1$.
  - From Row 1: $x + y = 2 \implies x + 1 = 2 \implies x = 1$.
- Unique solution: $(x, y) = (1, 1)$.

---

### Step 2: Analyze System B

The augmented matrix for System B is:

$$
\left[\begin{array}{cc|c}
1 & 1 & 2 \\\\
2 & -1 & 1 \\\\
3 & 0 & 3.1
\end{array}\right]
$$

Apply the exact same row operations:
1. **$R_2 \leftarrow R_2 - 2R_1$:**
   - Yields $(0, -3 \mid -3)$ (identical to System A).

2. **$R_3 \leftarrow R_3 - 3R_1$:**
   - Column 1: $3 - 3(1) = 0$
   - Column 2: $0 - 3(1) = -3$
   - Right side: $3.1 - 3(2) = 3.1 - 6 = -2.9$

The matrix is now:

$$
\left[\begin{array}{cc|c}
1 & 1 & 2 \\\\
0 & -3 & -3 \\\\
0 & -3 & -2.9
\end{array}\right]
$$

3. **$R_3 \leftarrow R_3 - R_2$:**
   - Column 1: $0 - 0 = 0$
   - Column 2: $-3 - (-3) = 0$
   - Right side: $-2.9 - (-3) = -2.9 + 3.0 = 0.1$

The row echelon form is:

$$
\left[\begin{array}{cc|c}
1 & 1 & 2 \\\\
0 & -3 & -3 \\\\
0 & 0 & 0.1
\end{array}\right]
$$

- Row 3 represents: $0x + 0y = 0.1 \implies 0 = 0.1$ (Contradiction).
- Ranks: $\text{rank}(A) = 2$, but $\text{rank}([A \mid b]) = 3$.
- Because $\text{rank}(A) < \text{rank}([A \mid b])$, **System B is inconsistent** (has **no solution**).

---

### Step 3: Why a Small Change Alters the System Type

1. **The Algebraic Perspective:**
   In an overdetermined system ($3 \times 2$), the third equation can only be consistent if its right-hand side is the exact linear combination of the previous right-hand sides dictated by the rows of $A$:

$$
R_3 = R_1 + R_2 \implies b_3 = b_1 + b_2 = 2 + 1 = 3
$$

   Any deviation from $3$—even by $0.1$—breaks the balance:

$$
(x + y) + (2x - y) = 3x = 3 \neq 3.1
$$

   Algebraically, the vector $b = (2, 1, 3.1)^T$ no longer lies in the 2D plane spanned by the columns of $A$ in $\mathbb{R}^3$.

2. **The Geometric Perspective:**
   In $\mathbb{R}^2$, each equation represents a line:
   - Line 1 ($x + y = 2$) and Line 2 ($2x - y = 1$) cross at exactly $(1, 1)$.
   - In System A, Line 3 ($x = 1$) passes directly through $(1, 1)$. All three lines share a single point of concurrency.
   - In System B, Line 3 is shifted slightly to $x = 1.0333...$. It no longer passes through $(1, 1)$. The three lines now intersect pairwise at three distinct points, forming a tiny triangular region with empty mutual intersection.

---

## 5. Final Answer & Conclusion

- **System A:** **Consistent**, with **exactly one unique solution**:

$$
x = 1, \quad y = 1
$$

- **System B:** **Inconsistent**, with **no solution** (contradiction $0 = 0.1$).
- **Explanation:**
  In overdetermined systems, consistency requires the constant vector to lie precisely in the lower-dimensional column space of $A$. In System A, the third equation was an exact linear combination of the first two ($E_3 = E_1 + E_2$). Changing $3$ to $3.1$ perturbs the third line away from the intersection point of the first two lines, creating an impossible contradiction.

---

## 6. Quick Verification

1. **Verify System A with $(1, 1)$:**
   - $x + y = 1 + 1 = 2$ (Matches 2)
   - $2x - y = 2(1) - 1 = 1$ (Matches 1)
   - $3x = 3(1) = 3$ (Matches 3)
   All three hold.

2. **Verify System B Contradiction:**
   From equations 1 and 2, the unique point satisfying both is $(1, 1)$.
   Substitute $(1, 1)$ into equation 3 of System B:
   $3(1) = 3 \neq 3.1$.
   No point satisfying the first two equations can ever satisfy the third.

---

## 7. Common Mistakes to Avoid

1. **Assuming Small Numerical Changes Produce Small Solution Changes:**
   In square non-singular systems, a small change in $b$ produces a small shift in $x$. But in overdetermined systems, a small perturbation in $b$ can destroy consistency entirely, jumping from a unique solution to no solution at all.
2. **Missing the Linear Combination:**
   Failing to notice that $R_1 + R_2 = R_3$ in matrix $A$, which is the structural reason why $b_3$ had to equal $3$.
3. **Rounding Away the Contradiction:**
   Approximating $0 \approx 0.1$ and claiming the system is "almost consistent". In pure mathematics, $0 \neq 0.1$ is an absolute contradiction.

---

## 8. How I Would Explain This in Class

> "Imagine three friends trying to meet at a single spot on a map. Lines 1 and 2 cross at coordinate $(1, 1)$, and in the first problem, the third friend walks right through $(1, 1)$, so all three meet successfully. But in the second problem, changing $3$ to $3.1$ shifts the third friend's path by just a few centimeters to the side; suddenly, the three paths form a tiny triangle with no common meeting point, making a simultaneous meetup completely impossible."
