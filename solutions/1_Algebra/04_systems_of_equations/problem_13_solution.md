# Problem 13: Does Every Equation Add New Information?

## 1. The Original Problem

Consider the system

$$
x_1 + x_2 = 10, \qquad x_2 + x_3 = 8, \qquad x_1 - x_3 = 2.
$$

Solve it and check whether all three equations are independently necessary to describe the solution set. If one follows from the others, show this by calculation.

---

## 2. What Are We Trying to Find?

We need to:
1. Determine whether the three given equations are linearly independent or whether one equation is redundant (follows from the other two).
2. Show by explicit algebraic calculation how one equation is obtained directly as a linear combination of the other two.
3. Solve the system completely using Gaussian elimination.
4. Express the solution set in parametric vector form and state the number of free variables.

---

## 3. Before Calculating: What Idea Do We Need?

- **Linear Dependence and Redundancy:**
  An equation is **redundant** if it can be derived by multiplying the other equations by constants and adding them together (a linear combination).
  If Equation 3 can be expressed as:

$$
E_3 = c_1 E_1 + c_2 E_2
$$

  then any assignment of variables that satisfies $E_1$ and $E_2$ is automatically guaranteed to satisfy $E_3$. Consequently, $E_3$ adds no new restriction to the solution space.
- **Matrix Rank and Free Variables:**
  If one equation is redundant, the coefficient matrix will have a rank strictly less than 3 ($\text{rank}(A) = 2 < 3$). In Gaussian elimination, this redundancy produces a complete row of zeros: $(0, 0, 0 \mid 0)$.
  The solution set will not be a single point, but an infinite line of solutions with $n - \text{rank}(A) = 3 - 2 = 1$ free variable.

---

## 4. Step-by-Step Solution

### Step 1: Algebraic Demonstration of Redundancy

Label the three equations:
- $E_1: x_1 + x_2 = 10$
- $E_2: x_2 + x_3 = 8$
- $E_3: x_1 - x_3 = 2$

Subtract Equation $E_2$ from Equation $E_1$:

$$
(x_1 + x_2) - (x_2 + x_3) = 10 - 8
$$

Simplify the left-hand side:

$$
x_1 + x_2 - x_2 - x_3 = x_1 - x_3
$$

Simplify the right-hand side:

$$
10 - 8 = 2
$$

This results in:

$$
x_1 - x_3 = 2
$$

which is **identical** to Equation $E_3$.
Therefore:

$$
E_3 = E_1 - E_2
$$

Because Equation 3 is a direct consequence of Equations 1 and 2, it provides no new information. The three equations are **not independently necessary**; Equation 3 is redundant.

---

### Step 2: Form the Augmented Matrix

Set up the system as an augmented matrix:

$$
\left[\begin{array}{ccc|c}
1 & 1 & 0 & 10 \\\\
0 & 1 & 1 & 8 \\\\
1 & 0 & -1 & 2
\end{array}\right]
$$

### Step 3: Perform Gaussian Elimination

1. **Eliminate entry $(3, 1)$ using $R_3 \leftarrow R_3 - R_1$:**
   - Column 1: $1 - 1 = 0$
   - Column 2: $0 - 1 = -1$
   - Column 3: $-1 - 0 = -1$
   - Right-hand side: $2 - 10 = -8$

The matrix becomes:

$$
\left[\begin{array}{ccc|c}
1 & 1 & 0 & 10 \\\\
0 & 1 & 1 & 8 \\\\
0 & -1 & -1 & -8
\end{array}\right]
$$

2. **Eliminate entry $(3, 2)$ using $R_3 \leftarrow R_3 + R_2$:**
   - Column 1: $0 + 0 = 0$
   - Column 2: $-1 + 1 = 0$
   - Column 3: $-1 + 1 = 0$
   - Right-hand side: $-8 + 8 = 0$

The augmented matrix in row echelon form is:

$$
\left[\begin{array}{ccc|c}
1 & 1 & 0 & 10 \\\\
0 & 1 & 1 & 8 \\\\
0 & 0 & 0 & 0
\end{array}\right]
$$

Row 3 reduces completely to zeros ($0 = 0$), confirming the redundancy discovered in Step 1.

---

### Step 4: Parameterize and Solve

- The pivot columns are Column 1 ($x_1$) and Column 2 ($x_2$).
- Column 3 ($x_3$) has no pivot; therefore, $x_3$ is the free variable.
- Set $x_3 = t$, where $t \in \mathbb{R}$.
- Ranks: $\text{rank}(A) = \text{rank}([A \mid b]) = 2 < 3$.
- Number of free variables: $3 - 2 = 1$.

Now perform back-substitution:
1. **From Row 2:**

$$
x_2 + x_3 = 8 \implies x_2 = 8 - x_3 = 8 - t
$$

2. **From Row 1:**

$$
x_1 + x_2 = 10 \implies x_1 = 10 - x_2 = 10 - (8 - t) = 2 + t
$$

---

## 5. Final Answer & Conclusion

- **Redundancy Analysis:**
  All three equations are **not independently necessary**. Equation 3 follows directly from Equations 1 and 2 via the linear combination:

$$
E_3 = E_1 - E_2
$$

- **Solution Set:**
  The system has **infinitely many solutions**. With free parameter $x_3 = t \in \mathbb{R}$, the solution set is:

$$
\begin{cases}
x_1 = 2 + t, \\\\
x_2 = 8 - t, \\\\
x_3 = t,
\end{cases}
\quad t \in \mathbb{R}
$$

In vector form:

$$
\begin{pmatrix} x_1 \\\\ x_2 \\\\ x_3 \end{pmatrix} = \begin{pmatrix} 2 \\\\ 8 \\\\ 0 \end{pmatrix} + t \begin{pmatrix} 1 \\\\ -1 \\\\ 1 \end{pmatrix}, \quad t \in \mathbb{R}
$$

Geometrically, this describes a line of intersection in $\mathbb{R}^3$.

---

## 6. Quick Verification

Substitute the parametric solution into all three original equations:

1. **Equation 1:**

$$
x_1 + x_2 = (2 + t) + (8 - t) = 10
$$

Matches 10. Correct.

2. **Equation 2:**

$$
x_2 + x_3 = (8 - t) + t = 8
$$

Matches 8. Correct.

3. **Equation 3:**

$$
x_1 - x_3 = (2 + t) - t = 2
$$

Matches 2. Correct.

Test with concrete values:
- For $t = 0$: $(x_1, x_2, x_3) = (2, 8, 0) \implies 2 + 8 = 10, 8 + 0 = 8, 2 - 0 = 2$. All true.
- For $t = 3$: $(x_1, x_2, x_3) = (5, 5, 3) \implies 5 + 5 = 10, 5 + 3 = 8, 5 - 3 = 2$. All true.

---

## 7. Common Mistakes to Avoid

1. **Assuming 3 Equations with 3 Unknowns Always Yields a Single Point:**
   Having three equations does not guarantee a unique solution; if one equation is linearly dependent on the others, the effective number of constraints is only 2.
2. **Sign Errors When Subtracting $E_2$:**
   Writing $10 - 8 = -2$ or subtracting $(x_2 + x_3)$ without distributing the negative sign, which would wrongly produce $x_1 + x_3$ instead of $x_1 - x_3$.
3. **Overlooking the Free Variable:**
   Arbitrarily setting $x_3 = 0$ and reporting only the single point $(2, 8, 0)$ as the answer, ignoring the full infinite family of solutions.

---

## 8. How I Would Explain This in Class

> "Imagine someone tells you that Alice plus Bob have 10 dollars, and Bob plus Charlie have 8 dollars. If they then proudly tell you that Alice has 2 more dollars than Charlie, they haven't given you any new information—you could have deduced that yourself just by subtracting the second statement from the first! In matrix algebra, that third redundant clue collapses into a row of zeros, revealing that an entire line of solutions exists."
