# Problem 06: A System with a Parameter — Which Cases Actually Occur?

## 1. The Original Problem

Analyze, depending on the parameter $a$, the system

$$
\begin{cases}
x + y = 2, \\\\
ax + ay = 4.
\end{cases}
$$

Among the three possibilities — exactly one solution, infinitely many solutions, no solution — determine which actually occur and for which values of $a$. If one type cannot occur, explain why.

---

## 2. What Are We Trying to Find?

We need to:
1. Perform Gaussian elimination on the parametric system.
2. Characterize the system's behavior for all real values of $a \in \mathbb{R}$.
3. Explicitly determine:
   - For which value(s) of $a$ there are infinitely many solutions.
   - For which value(s) of $a$ there is no solution.
   - Whether the "exactly one solution" case can ever occur, and prove why or why not.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Three Possibilities for Linear Systems:**
  For any linear system over $\mathbb{R}$, exactly one of three mutually exclusive cases must hold:
  1. Exactly one solution ($\text{rank}(A) = \text{rank}([A \mid b]) = n$).
  2. Infinitely many solutions ($\text{rank}(A) = \text{rank}([A \mid b]) < n$).
  3. No solution ($\text{rank}(A) < \text{rank}([A \mid b])$).
- **The Role of the Determinant in $2 \times 2$ Systems:**
  For a square system $Ax = b$ with $n = 2$, a unique solution exists if and only if $\det(A) \neq 0$.
  The coefficient matrix is:

$$
A = \begin{pmatrix} 1 & 1 \\\\ a & a \end{pmatrix}
$$

  Notice that the second row is $a$ times the first row. The determinant is:

$$
\det(A) = (1)(a) - (1)(a) = 0 \quad \text{for all } a \in \mathbb{R}
$$

  Because $\det(A) = 0$ identically for every value of $a$, the coefficient matrix is permanently singular ($\text{rank}(A) \le 1 < 2$).
- **Parametric Row Elimination:**
  Subtracting $a \times R_1$ from $R_2$ isolates the parameter in the right-hand side of Row 2: $4 - 2a$.

---

## 4. Step-by-Step Solution

### Step 1: Write the Augmented Matrix

Set up the augmented matrix depending on parameter $a$:

$$
\left[\begin{array}{cc|c}
1 & 1 & 2 \\\\
a & a & 4
\end{array}\right]
$$

### Step 2: Perform Row Elimination

Eliminate the first entry of Row 2 using the elementary row operation $R_2 \leftarrow R_2 - a R_1$:

- Entry $(2, 1)$: $a - a(1) = 0$
- Entry $(2, 2)$: $a - a(1) = 0$
- Right-hand side entry: $4 - a(2) = 4 - 2a$

The row-reduced augmented matrix is:

$$
\left[\begin{array}{cc|c}
1 & 1 & 2 \\\\
0 & 0 & 4 - 2a
\end{array}\right]
$$

### Step 3: Analyze the Parameter Cases

The second row represents the equation:

$$
0 \cdot x + 0 \cdot y = 4 - 2a \iff 0 = 4 - 2a
$$

#### Case 1: $4 - 2a = 0 \iff a = 2$

When $a = 2$:
- The second row becomes $(0, 0 \mid 0)$, which represents the tautology $0 = 0$.
- The augmented matrix becomes:

$$
\left[\begin{array}{cc|c}
1 & 1 & 2 \\\\
0 & 0 & 0
\end{array}\right]
$$

- Ranks: $\text{rank}(A) = 1$ and $\text{rank}([A \mid b]) = 1$.
- Because $\text{rank}(A) = \text{rank}([A \mid b]) = 1 < 2$, the system is consistent with $n - \text{rank}(A) = 2 - 1 = 1$ free variable.
- Choosing $y = t \in \mathbb{R}$, we obtain $x = 2 - t$.
- **Result:** There are **infinitely many solutions**.

#### Case 2: $4 - 2a \neq 0 \iff a \neq 2$

When $a \neq 2$:
- The right-hand side $4 - 2a$ is non-zero.
- The second row represents $0 = 4 - 2a \neq 0$, which is an impossible contradiction.
- Ranks: $\text{rank}(A) = 1$, but $\text{rank}([A \mid b]) = 2$.
- Because $\text{rank}(A) < \text{rank}([A \mid b])$, the system is inconsistent.
- Note that this holds for all $a \neq 2$, including $a = 0$ where the second equation is $0 = 4$.
- **Result:** There is **no solution**.

### Step 4: Explain Why Exactly One Solution Cannot Occur

For a system of $2$ linear equations in $2$ unknowns to have exactly one solution, the coefficient matrix $A$ must have full rank ($\text{rank}(A) = 2$), which requires $\det(A) \neq 0$.

For this system:

$$
\det(A) = \det \begin{pmatrix} 1 & 1 \\\\ a & a \end{pmatrix} = 1 \cdot a - 1 \cdot a = 0
$$

The determinant is zero for **every** real number $a \in \mathbb{R}$. The rows $(1, 1)$ and $(a, a)$ are linearly dependent for every choice of $a$. Consequently, $\text{rank}(A) \le 1 < 2$ always.

Because full rank is impossible, the case of **exactly one solution can NEVER occur** for any real value of $a$.

---

## 5. Final Answer & Conclusion

- **Infinitely many solutions:** Occurs if and only if $a = 2$.
  The solution set is $\{ (2 - t, t) \mid t \in \mathbb{R} \}$.
- **No solution:** Occurs for all $a \in \mathbb{R} \setminus \{2\}$ (that is, $a \neq 2$).
- **Exactly one solution:** **Never occurs** for any value of $a$, because $\det(A) = 0$ for all $a \in \mathbb{R}$, meaning the coefficient rows are always parallel.

---

## 6. Quick Verification

1. **Test $a = 2$:**
   System becomes:
   - Eq 1: $x + y = 2$
   - Eq 2: $2x + 2y = 4 \iff x + y = 2$
   Both equations represent the identical line. Every point on the line satisfies the system. Infinitely many solutions confirmed.

2. **Test $a = 1$:**
   System becomes:
   - Eq 1: $x + y = 2$
   - Eq 2: $x + y = 4$
   The sum of two numbers cannot simultaneously be $2$ and $4$. Contradiction ($2 = 4$). No solution confirmed.

3. **Test $a = 0$:**
   System becomes:
   - Eq 1: $x + y = 2$
   - Eq 2: $0x + 0y = 4 \iff 0 = 4$
   Impossible. No solution confirmed.

---

## 7. Common Mistakes to Avoid

1. **Assuming All Three Theoretical Cases Must Always Occur:**
   Beginners often assume that every parametric problem must have values for "unique", "infinite", and "none". As this problem proves, structural geometric constraints can permanently rule out one or more cases.
2. **Dividing by $a$ or $(4 - 2a)$ Prematurely:**
   Multiplying or dividing rows by expressions containing parameters without first testing whether those expressions can be zero.
3. **Overlooking $a = 0$:**
   Treating $a = 0$ as a special separate anomaly. In fact, $a = 0$ is just part of the $a \neq 2$ case where $0 = 4$ is inconsistent.

---

## 8. How I Would Explain This in Class

> "Students often expect that every system with a parameter will showcase all three textbook cases, but look at the left-hand side: the coefficients are always proportional ($x+y$ and $ax+ay$), so the lines are permanently parallel for every $a$. They can never cross at a single point! If $a = 2$, the second line falls right on top of the first, giving infinitely many solutions; for any other $a$, the lines stay apart, giving no solution at all."
