# Problem 02: Gaussian Elimination — One Solution

## 1. The Original Problem

Solve using Gaussian elimination:

$$
\begin{cases}
x + y + z = 6, \\\\
2x - y + z = 3, \\\\
x + 2y - z = 2
\end{cases}
$$

After solving, substitute the result into all equations and check consistency.

---

## 2. What Are We Trying to Find?

We need to:
1. Represent the system as an augmented matrix $[A \mid b]$.
2. Apply elementary row operations to transform the augmented matrix into upper triangular (row echelon) form.
3. Use back-substitution to find the unique numerical values of $x, y,$ and $z$.
4. Check consistency by substituting the calculated solution vector back into all three original scalar equations.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Augmented Matrix:**
  We combine the coefficient matrix $A$ and the constant vector $b$ into a single array $[A \mid b]$ of size $3 \times 4$.
- **Elementary Row Operations:**
  Gaussian elimination relies on three operations that do not change the solution set:
  1. Multiplying a row by a non-zero scalar ($R_i \leftarrow c R_i$).
  2. Adding a multiple of one row to another ($R_i \leftarrow R_i + c R_j$).
  3. Swapping two rows ($R_i \leftrightarrow R_j$).
- **Row Echelon Form & Back-Substitution:**
  By creating zeros below the main diagonal, the last equation contains only one variable, which we solve directly and back-substitute upwards into the preceding equations.

---

## 4. Step-by-Step Solution

### Step 1: Set Up the Augmented Matrix

Extract the coefficients and constant terms into the augmented matrix:

$$
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\\\
2 & -1 & 1 & 3 \\\\
1 & 2 & -1 & 2
\end{array}\right]
$$

### Step 2: Eliminate $x$ from the Second and Third Rows

The pivot in the first column is $a_{11} = 1$. We use Row 1 to clear the entries below it.

1. **Clear entry $(2, 1)$ using $R_2 \leftarrow R_2 - 2R_1$:**
   - First column: $2 - 2(1) = 0$
   - Second column: $-1 - 2(1) = -3$
   - Third column: $1 - 2(1) = -1$
   - Constant term: $3 - 2(6) = 3 - 12 = -9$
   - New Row 2: $(0, -3, -1 \mid -9)$

2. **Clear entry $(3, 1)$ using $R_3 \leftarrow R_3 - R_1$:**
   - First column: $1 - 1 = 0$
   - Second column: $2 - 1 = 1$
   - Third column: $-1 - 1 = -2$
   - Constant term: $2 - 6 = -4$
   - New Row 3: $(0, 1, -2 \mid -4)$

The augmented matrix now becomes:

$$
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\\\
0 & -3 & -1 & -9 \\\\
0 & 1 & -2 & -4
\end{array}\right]
$$

### Step 3: Eliminate $y$ from the Third Row

To make calculations simpler and avoid fractions, swap Row 2 and Row 3 so the pivot in column 2 is $1$:

$$
R_2 \leftrightarrow R_3 \implies
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\\\
0 & 1 & -2 & -4 \\\\
0 & -3 & -1 & -9
\end{array}\right]
$$

Now eliminate the entry in position $(3, 2)$ using $R_3 \leftarrow R_3 + 3R_2$:
- First column: $0 + 3(0) = 0$
- Second column: $-3 + 3(1) = 0$
- Third column: $-1 + 3(-2) = -1 - 6 = -7$
- Constant term: $-9 + 3(-4) = -9 - 12 = -21$

The augmented matrix is now in row echelon form:

$$
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\\\
0 & 1 & -2 & -4 \\\\
0 & 0 & -7 & -21
\end{array}\right]
$$

### Step 4: Perform Back-Substitution

Now translate the triangular matrix back into equations and solve from bottom to top:

1. **Solve for $z$ from Row 3:**

$$
-7z = -21 \implies z = \frac{-21}{-7} = 3
$$

2. **Solve for $y$ from Row 2:**

$$
y - 2z = -4
$$

Substitute $z = 3$:

$$
y - 2(3) = -4 \implies y - 6 = -4 \implies y = 2
$$

3. **Solve for $x$ from Row 1:**

$$
x + y + z = 6
$$

Substitute $y = 2$ and $z = 3$:

$$
x + 2 + 3 = 6 \implies x + 5 = 6 \implies x = 1
$$

---

## 5. Final Answer & Conclusion

The system has a unique solution:

$$
x = 1, \quad y = 2, \quad z = 3
$$

Written in vector form:

$$
\begin{pmatrix} x \\\\ y \\\\ z \end{pmatrix} = \begin{pmatrix} 1 \\\\ 2 \\\\ 3 \end{pmatrix}
$$

Because the coefficient matrix has full rank ($\text{rank}(A) = 3$), the three planes defined by the equations intersect at exactly one point in three-dimensional space.

---

## 6. Quick Verification

Substitute $x = 1, y = 2, z = 3$ back into each of the original equations:

1. **Equation 1:**
   $x + y + z = 1 + 2 + 3 = 6$
   Matches the right-hand side ($6 = 6$). Correct.

2. **Equation 2:**
   $2x - y + z = 2(1) - 2 + 3 = 2 - 2 + 3 = 3$
   Matches the right-hand side ($3 = 3$). Correct.

3. **Equation 3:**
   $x + 2y - z = 1 + 2(2) - 3 = 1 + 4 - 3 = 2$
   Matches the right-hand side ($2 = 2$). Correct.

All three equations are satisfied simultaneously, confirming consistency and the correctness of the solution.

---

## 7. Common Mistakes to Avoid

1. **Arithmetic Errors in Row Operations:**
   Forgetting to apply the multiplier to the constant column on the right-hand side (e.g., computing $3 - 2(6)$ as $3 - 6 = -3$ instead of $-9$).
2. **Minus Sign Errors in Back-Substitution:**
   Making sign mistakes when moving terms across the equals sign, such as writing $y = -4 - 6 = -10$ instead of $y = -4 + 6 = 2$.
3. **Checking Only One Equation:**
   Checking only the first equation after solving. A calculation error in Row 3 might still accidentally satisfy Row 1; all three equations must be checked.

---

## 8. How I Would Explain This in Class

> "Gaussian elimination works by creating a cascade of zeros below the diagonal so each subsequent equation has one fewer variable than the last. Once we reach a single equation with only $z$, we find $z = 3$ and pass that value upward like dominoes falling in reverse to find $y = 2$ and $x = 1$. Finally, plugging $(1, 2, 3)$ into all three original equations guarantees that no arithmetic errors slipped in."
