# Problem 08: Two Systems with the Same Coefficient Matrix

## 1. The Original Problem

Solve by elimination the two systems

$$
\begin{cases}
2x + y = 5, \\\\
x - y = 1,
\end{cases}
\qquad
\begin{cases}
2x + y = 1, \\\\
x - y = 4.
\end{cases}
$$

Compare the successive elimination steps. Which part of the calculation is the same in both cases, and why?

---

## 2. What Are We Trying to Find?

We need to:
1. Solve both $2 \times 2$ linear systems using Gaussian elimination.
2. Demonstrate how both systems can be solved simultaneously by attaching multiple right-hand sides into a single multi-augmented matrix $[A \mid b_1 \mid b_2]$.
3. Explicitly compute the solution vectors for both systems.
4. Compare the sequence of elimination operations step-by-step.
5. Explain conceptually why the operations on the left side are identical regardless of the constants on the right side.

---

## 3. Before Calculating: What Idea Do We Need?

- **Decoupling the Coefficient Matrix from the Constants:**
  Notice that both systems share the exact same coefficient matrix:

$$
A = \begin{pmatrix} 2 & 1 \\\\ 1 & -1 \end{pmatrix}
$$

  Only the right-hand sides differ:

$$
b_1 = \begin{pmatrix} 5 \\\\ 1 \end{pmatrix}, \qquad b_2 = \begin{pmatrix} 1 \\\\ 4 \end{pmatrix}
$$

- **Multi-Augmented Matrix $[A \mid b_1 \mid b_2]$:**
  Because the row operations required to eliminate entries depend exclusively on the entries of $A$, we can append multiple right-hand sides and perform the row reductions simultaneously.
- **Independence of Pivot Operations:**
  The multipliers used in Gaussian elimination (such as subtracting $2 \times \text{Row 1}$ from $\text{Row 2}$) are determined entirely by the ratios of elements within $A$. The right-hand side values do not dictate which operations are chosen; they only follow along under those same operations.

---

## 4. Step-by-Step Solution

### Step 1: Set Up the Simultaneous Augmented Matrix

Combine the common matrix $A$ with both right-hand sides $b_1$ and $b_2$:

$$
\left[\begin{array}{cc|c|c}
2 & 1 & 5 & 1 \\\\
1 & -1 & 1 & 4
\end{array}\right]
$$

### Step 2: Perform Elimination Simultaneously

1. **Row Swap ($R_1 \leftrightarrow R_2$):**
   Place the pivot $1$ into the top-left position to simplify arithmetic:

$$
\left[\begin{array}{cc|c|c}
1 & -1 & 1 & 4 \\\\
2 & 1 & 5 & 1
\end{array}\right]
$$

2. **Elimination Step ($R_2 \leftarrow R_2 - 2R_1$):**
  - Left-hand side (Matrix $A$): Column 1 gives $2 - 2(1) = 0$; Column 2 gives $1 - 2(-1) = 1 + 2 = 3$.
  - Right-hand side 1 ($b_1$): Entry gives $5 - 2(1) = 3$.
  - Right-hand side 2 ($b_2$): Entry gives $1 - 2(4) = 1 - 8 = -7$.

The echelon form for both systems simultaneously is:

$$
\left[\begin{array}{cc|c|c}
1 & -1 & 1 & 4 \\\\
0 & 3 & 3 & -7
\end{array}\right]
$$

---

### Step 3: Back-Substitution for System 1 ($b_1 = (5, 1)^T$)

The reduced equations for the first system are:

$$
\begin{cases}
x - y = 1 \\\\
3y = 3
\end{cases}
$$

1. From the second equation:

$$
3y = 3 \implies y = 1
$$

2. From the first equation:

$$
x - 1 = 1 \implies x = 2
$$

Solution for System 1:

$$
\begin{pmatrix} x \\\\ y \end{pmatrix} = \begin{pmatrix} 2 \\\\ 1 \end{pmatrix}
$$

---

### Step 4: Back-Substitution for System 2 ($b_2 = (1, 4)^T$)

The reduced equations for the second system are:

$$
\begin{cases}
x - y = 4 \\\\
3y = -7
\end{cases}
$$

1. From the second equation:

$$
3y = -7 \implies y = -\frac{7}{3}
$$

2. From the first equation:

$$
x - \left(-\frac{7}{3}\right) = 4 \implies x + \frac{7}{3} = \frac{12}{3} \implies x = \frac{5}{3}
$$

Solution for System 2:

$$
\begin{pmatrix} x \\\\ y \end{pmatrix} = \begin{pmatrix} 5/3 \\\\ -7/3 \end{pmatrix}
$$

---

### Step 5: Compare the Steps and Explain Why

- **What is identical:**
  Every row operation applied to the left side (swapping rows, subtracting $2R_1$ from $R_2$) is exactly the same for both systems. The resulting echelon coefficient matrix:

$$
\begin{pmatrix} 1 & -1 \\\\ 0 & 3 \end{pmatrix}
$$

  is identical.
- **Why it is identical:**
  The goal of Gaussian elimination is to systematically zero out off-diagonal entries in the coefficient matrix $A$. The choices of which row to swap and which scalar multiplier to subtract depend purely on the entries of $A$ (here, $a_{21}/a_{11} = 2/1 = 2$). The right-hand side vectors never dictate these multipliers; they are merely transformed passively by the exact same row operations.

---

## 5. Final Answer & Conclusion

- **Solution to System 1:**

$$
x = 2, \quad y = 1
$$

- **Solution to System 2:**

$$
x = \frac{5}{3}, \quad y = -\frac{7}{3}
$$

- **Comparative Conclusion:**
  The row reduction on the coefficient matrix $A$ is 100% identical in both problems because the elimination steps depend exclusively on $A$, not on the right-hand sides. Solving multiple systems with a shared coefficient matrix can therefore always be batched into a single multi-column augmented matrix $[A \mid b_1 \mid b_2 \mid \cdots \mid b_k]$.

---

## 6. Quick Verification

1. **Verify System 1 with $(x, y) = (2, 1)$:**
   - Eq 1: $2(2) + 1 = 4 + 1 = 5$ (Matches 5)
   - Eq 2: $2 - 1 = 1$ (Matches 1)
   Both satisfied.

2. **Verify System 2 with $(x, y) = (5/3, -7/3)$:**
   - Eq 1: $2\left(\frac{5}{3}\right) + \left(-\frac{7}{3}\right) = \frac{10 - 7}{3} = \frac{3}{3} = 1$ (Matches 1)
   - Eq 2: $\frac{5}{3} - \left(-\frac{7}{3}\right) = \frac{5 + 7}{3} = \frac{12}{3} = 4$ (Matches 4)
   Both satisfied.

---

## 7. Common Mistakes to Avoid

1. **Solving the Systems Completely Independently:**
   Performing Gaussian elimination twice from scratch wastes effort and misses the core insight that the row operations are completely reusable.
2. **Sign Slips in Fractions:**
   In System 2, calculating $x - (-7/3) = 4$ as $x - 7/3 = 4 \implies x = 19/3$. Be meticulous with double negatives.
3. **Thinking Right-Hand Sides Affect Pivot Choices:**
   Confusing row operations on $A$ with values on the right-hand side. The right-hand side numbers never decide which row operations to perform.

---

## 8. How I Would Explain This in Class

> "Think of the matrix $A$ as the recipe and the vector $b$ as the ingredients on your counter. Changing the ingredients from $(5, 1)$ to $(1, 4)$ does not change the recipe instructions: you still swap the two rows and subtract twice the first row from the second. Because the left side follows the exact same steps every time, we can place both right-hand sides side-by-side in one augmented matrix and execute the elimination just once!"
