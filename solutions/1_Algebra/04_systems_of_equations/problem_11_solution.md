# Problem 11: A Parameter in a System of Three Equations

## 1. The Original Problem

Analyze the number of solutions depending on $t$:

$$
\begin{cases}
x + y + z = 1, \\\\
x + ty + z = 2, \\\\
x + y + tz = 3.
\end{cases}
$$

Use elimination and separately analyze the parameter values for which a standard calculation step ceases to be valid.

---

## 2. What Are We Trying to Find?

We need to:
1. Set up the augmented matrix $[A \mid b]$ depending on the real parameter $t$.
2. Perform Gaussian elimination using elementary row operations that do not divide by parameter expressions.
3. Identify the critical value of $t$ where back-substitution or division by the pivot becomes invalid (i.e., division by zero).
4. Separately analyze the critical value to determine whether the system is consistent or inconsistent.
5. Provide the exact explicit solution for all values of $t$ where a unique solution exists.

---

## 3. Before Calculating: What Idea Do We Need?

- **Safe Elimination with Parameters:**
  When reducing a parametric system, avoid multiplying or dividing rows by expressions containing $t$ until the echelon form is reached. Subtracting multiple of a row with numerical coefficients (like $R_2 - R_1$) is always safe for any real $t$.
- **The Critical Pivot Condition:**
  In echelon form, if a pivot expression takes the form $(t - 1)$, we cannot divide by it if $t = 1$. We must branch into two distinct cases:
  1. $t = 1$ (the degenerate/singular case).
  2. $t \neq 1$ (the regular/invertible case).
- **Determinant Check:**
  The determinant of the coefficient matrix is:

$$
\det(A) = \det \begin{pmatrix} 1 & 1 & 1 \\\\ 1 & t & 1 \\\\ 1 & 1 & t \end{pmatrix} = (t - 1)^2
$$

  The determinant vanishes precisely when $t = 1$.

---

## 4. Step-by-Step Solution

### Step 1: Set Up the Augmented Matrix

Write down the $3 \times 4$ augmented matrix:

$$
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 1 \\\\
1 & t & 1 & 2 \\\\
1 & 1 & t & 3
\end{array}\right]
$$

### Step 2: Perform Safe Forward Elimination

Using Row 1 as the pivot row, eliminate the first entry of Rows 2 and 3:

1. **Operation $R_2 \leftarrow R_2 - R_1$:**
   - Column 1: $1 - 1 = 0$
   - Column 2: $t - 1$
   - Column 3: $1 - 1 = 0$
   - Right-hand side: $2 - 1 = 1$

2. **Operation $R_3 \leftarrow R_3 - R_1$:**
   - Column 1: $1 - 1 = 0$
   - Column 2: $1 - 1 = 0$
   - Column 3: $t - 1$
   - Right-hand side: $3 - 1 = 2$

The matrix is already in upper triangular (echelon) form:

$$
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 1 \\\\
0 & t - 1 & 0 & 1 \\\\
0 & 0 & t - 1 & 2
\end{array}\right]
$$

### Step 3: Identify Where Standard Calculation Ceases to Be Valid

The diagonal pivot entries in Rows 2 and 3 are both $(t - 1)$.
To solve for $y$ and $z$, standard back-substitution requires dividing by $(t - 1)$:

$$
y = \frac{1}{t - 1}, \qquad z = \frac{2}{t - 1}
$$

This division is **undefined** when the denominator is zero:

$$
t - 1 = 0 \iff t = 1
$$

Therefore, $t = 1$ is the critical parameter value that must be analyzed separately.

---

### Step 4: Analysis of Case 1 ($t = 1$)

Substitute $t = 1$ directly into the row-reduced augmented matrix:

$$
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 1 \\\\
0 & 0 & 0 & 1 \\\\
0 & 0 & 0 & 2
\end{array}\right]
$$

- Row 2 translates to: $0x + 0y + 0z = 1 \implies 0 = 1$.
- Row 3 translates to: $0x + 0y + 0z = 2 \implies 0 = 2$.

Both rows yield direct contradictions ($0 = 1$ and $0 = 2$).
- Ranks: $\text{rank}(A) = 1$, but $\text{rank}([A \mid b]) = 3$.
- Because $\text{rank}(A) < \text{rank}([A \mid b])$, the system is **inconsistent**.
- **Conclusion for $t = 1$:** **No solution**.

---

### Step 5: Analysis of Case 2 ($t \neq 1$)

When $t \neq 1$, $t - 1 \neq 0$, so division by $t - 1$ is fully valid.

1. **Solve for $z$ from Row 3:**

$$
(t - 1)z = 2 \implies z = \frac{2}{t - 1}
$$

2. **Solve for $y$ from Row 2:**

$$
(t - 1)y = 1 \implies y = \frac{1}{t - 1}
$$

3. **Solve for $x$ from Row 1:**

$$
x + y + z = 1 \implies x = 1 - y - z
$$

Substitute the expressions for $y$ and $z$:

$$
x = 1 - \frac{1}{t - 1} - \frac{2}{t - 1} = 1 - \frac{3}{t - 1} = \frac{(t - 1) - 3}{t - 1} = \frac{t - 4}{t - 1}
$$

All three variables are uniquely determined.
- Ranks: $\text{rank}(A) = \text{rank}([A \mid b]) = 3 = n$.
- **Conclusion for $t \neq 1$:** **Exactly one unique solution**.

---

## 5. Final Answer & Conclusion

- **If $t = 1$:** **No solution** (the system is inconsistent, leading to contradictions $0 = 1$ and $0 = 2$).
- **If $t \neq 1$:** **Exactly one unique solution**, given by:

$$
x = \frac{t - 4}{t - 1}, \quad y = \frac{1}{t - 1}, \quad z = \frac{2}{t - 1}
$$

In vector form:

$$
\begin{pmatrix} x \\\\ y \\\\ z \end{pmatrix} = \frac{1}{t - 1} \begin{pmatrix} t - 4 \\\\ 1 \\\\ 2 \end{pmatrix}
$$

- The case of infinitely many solutions **never occurs** for any real value of $t$.

---

## 6. Quick Verification

### Numerical Test with $t = 2$
For $t = 2$:
- $x = \frac{2 - 4}{2 - 1} = -2$
- $y = \frac{1}{2 - 1} = 1$
- $z = \frac{2}{2 - 1} = 2$

Candidate point: $(x, y, z) = (-2, 1, 2)$. Substitute into the original system:
1. Equation 1: $x + y + z = -2 + 1 + 2 = 1$ (Matches 1)
2. Equation 2: $x + 2y + z = -2 + 2(1) + 2 = 2$ (Matches 2)
3. Equation 3: $x + y + 2z = -2 + 1 + 2(2) = -1 + 4 = 3$ (Matches 3)
All three equations hold perfectly.

### Algebraic Identity Check for General $t \neq 1$
1. $x + y + z = \frac{(t-4) + 1 + 2}{t-1} = \frac{t-1}{t-1} = 1$
2. $x + ty + z = \frac{(t-4) + t(1) + 2}{t-1} = \frac{2t - 2}{t-1} = \frac{2(t-1)}{t-1} = 2$
3. $x + y + tz = \frac{(t-4) + 1 + t(2)}{t-1} = \frac{3t - 3}{t-1} = \frac{3(t-1)}{t-1} = 3$
The algebraic solution is 100% verified for all $t \neq 1$.

---

## 7. Common Mistakes to Avoid

1. **Dividing by $(t - 1)$ Without Qualification:**
   Writing $y = \frac{1}{t-1}$ and $z = \frac{2}{t-1}$ immediately without stating the requirement that $t \neq 1$. When $t = 1$, this represents division by zero.
2. **Assuming $\det(A) = 0$ Always Means Infinitely Many Solutions:**
   When the determinant is zero, the system can either have infinitely many solutions or no solution. Here, at $t = 1$, the right-hand side produces non-zero constants against zero rows, resulting in no solution.
3. **Algebraic Simplification Errors:**
   Miscalculating $1 - \frac{3}{t-1}$ as $\frac{t-2}{t-1}$ instead of $\frac{t-4}{t-1}$.

---

## 8. How I Would Explain This in Class

> "When we subtract the first equation from the second and third, the variables uncouple almost like magic, giving $(t-1)y = 1$ and $(t-1)z = 2$. At this point, we must stop and ask: 'When would dividing break math?' The answer is when $t = 1$, where the equations demand $0 = 1$ and $0 = 2$, which is impossible. For every other number, dividing is completely legal, yielding a single tidy point."
