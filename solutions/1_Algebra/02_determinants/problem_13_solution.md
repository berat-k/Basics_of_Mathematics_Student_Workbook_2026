# Problem 13: Determinant by Elimination

## 1. The Original Problem

Compute the determinant

$$
A = \begin{pmatrix} 1 & 2 & 3 \\\\ 2 & 5 & 7 \\\\ 1 & 0 & 2 \end{pmatrix}
$$

using elimination. Record the effect of every row operation used on the value of the determinant.

---

## 2. What Are We Trying to Find?

We need to:
1. Carry out Gaussian elimination to reduce matrix $A$ to an upper triangular form $U$.
2. Record explicitly the exact impact of each elementary row operation on the determinant's value.
3. Compute the determinant of the resulting triangular matrix as the product of its diagonal elements.
4. Deduce the value of $\det A$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Elimination as a Determinant Calculator:**
  Gaussian elimination transforms any square matrix into an upper triangular matrix $U$, whose determinant is simply the product of its diagonal entries $\prod u_{ii}$.
- **Tracking Row Operation Effects:**
  - **Type I (Replacement):** $R_i \leftarrow R_i + c R_j$ ($i \neq j$).
    *Multiplier on determinant:* $\times 1$ (no change).
  - **Type II (Interchange):** $R_i \leftrightarrow R_j$.
    *Multiplier on determinant:* $\times (-1)$ (sign change).
  - **Type III (Scaling):** $R_i \leftarrow c R_i$ ($c \neq 0$).
    *Multiplier on determinant:* $\times c$.
- **Goal:**
  If we only use Type I row replacements, the determinant remains strictly invariant: $\det A = \det U$.

---

## 4. Step-by-Step Solution

### Step 1: Clear Column 1 Below the First Pivot $a_{11} = 1$

Our starting matrix is:

$$
A = \begin{pmatrix} 1 & 2 & 3 \\\\ 2 & 5 & 7 \\\\ 1 & 0 & 2 \end{pmatrix}
$$

1. **Operation 1: $R_2 \leftarrow R_2 - 2R_1$**
   - *Operation Type:* Row replacement ($c = -2$).
   - *Effect on Determinant:* **Unchanged** (multiplier = $1$).
   - Compute new Row 2:
     - Entry 1: $2 - 2(1) = 0$
     - Entry 2: $5 - 2(2) = 5 - 4 = 1$
     - Entry 3: $7 - 2(3) = 7 - 6 = 1$
     - $R_2' = (0, 1, 1)$

2. **Operation 2: $R_3 \leftarrow R_3 - R_1$**
   - *Operation Type:* Row replacement ($c = -1$).
   - *Effect on Determinant:* **Unchanged** (multiplier = $1$).
   - Compute new Row 3:
     - Entry 1: $1 - 1 = 0$
     - Entry 2: $0 - 2 = -2$
     - Entry 3: $2 - 3 = -1$
     - $R_3' = (0, -2, -1)$

After Step 1, the intermediate matrix is:

$$
A_1 = \begin{pmatrix} 1 & 2 & 3 \\\\ 0 & 1 & 1 \\\\ 0 & -2 & -1 \end{pmatrix}, \qquad \det A = \det A_1
$$

### Step 2: Clear Column 2 Below the Second Pivot $a_{22} = 1$

We use Row 2 to eliminate the $-2$ in position $(3, 2)$:

3. **Operation 3: $R_3 \leftarrow R_3 + 2R_2$**
   - *Operation Type:* Row replacement ($c = +2$).
   - *Effect on Determinant:* **Unchanged** (multiplier = $1$).
   - Compute new Row 3:
     - Entry 1: $0 + 2(0) = 0$
     - Entry 2: $-2 + 2(1) = 0$
     - Entry 3: $-1 + 2(1) = 1$
     - $R_3'' = (0, 0, 1)$

The matrix is now transformed into upper triangular form:

$$
U = \begin{pmatrix} 1 & 2 & 3 \\\\ 0 & 1 & 1 \\\\ 0 & 0 & 1 \end{pmatrix}, \qquad \det A = \det U
$$

### Step 3: Compute the Determinant of $U$

Matrix $U$ is upper triangular. Its determinant equals the product of its diagonal entries:

$$
\det U = u_{11} \cdot u_{22} \cdot u_{33} = (1) \cdot (1) \cdot (1) = 1
$$

Because all operations performed were row replacements that preserved the determinant without any sign flips or scaling factors:

$$
\det A = \det U = 1
$$

---

## 5. Final Answer & Conclusion

- **Log of Elementary Row Operations:**
  1. $R_2 \leftarrow R_2 - 2R_1$: effect $\times 1$ (unchanged).
  2. $R_3 \leftarrow R_3 - R_1$: effect $\times 1$ (unchanged).
  3. $R_3 \leftarrow R_3 + 2R_2$: effect $\times 1$ (unchanged).
- **Upper Triangular Form:**

$$
U = \begin{pmatrix} 1 & 2 & 3 \\\\ 0 & 1 & 1 \\\\ 0 & 0 & 1 \end{pmatrix}
$$

- **Final Determinant Value:**

$$
\det A = 1 \cdot 1 \cdot 1 = 1
$$

---

## 6. Quick Verification

Verify independently using Sarrus' rule on the original matrix $A$:
- Downward diagonals:
  - $1 \cdot 5 \cdot 2 = 10$
  - $2 \cdot 7 \cdot 1 = 14$
  - $3 \cdot 2 \cdot 0 = 0$
  - Sum $= 10 + 14 + 0 = 24$
- Upward diagonals:
  - $1 \cdot 5 \cdot 3 = 15$
  - $0 \cdot 7 \cdot 1 = 0$
  - $2 \cdot 2 \cdot 2 = 8$
  - Sum $= 15 + 0 + 8 = 23$
- Determinant: $24 - 23 = 1$.
The elimination method and Sarrus' rule agree completely.

---

## 7. Common Mistakes to Avoid

1. **Unrecorded Row Swaps:**
   If pivoting requires swapping rows to avoid a zero pivot, forgetting to multiply by $(-1)$ results in the wrong sign. Here, the pivots were naturally non-zero, so no swap was needed.
2. **Confusing Row Operations:**
   Accidentally using $R_3 \leftarrow 2R_2 - R_3$, which implicitly multiplies $R_3$ by $-1$. The row being modified must retain coefficient $+1$ for the multiplier to be $1$.

---

## 8. How I Would Explain This in Class

> "Gaussian elimination reduces the determinant calculation to multiplying diagonal entries. We eliminate the entries under the first pivot using $R_2 - 2R_1$ and $R_3 - R_1$, which produces rows $(0, 1, 1)$ and $(0, -2, -1)$ while preserving the determinant. Then adding twice Row 2 to Row 3 eliminates the $-2$, yielding $(0, 0, 1)$. The resulting triangular matrix has diagonal entries $1, 1,$ and $1$, giving $\det A = 1 \cdot 1 \cdot 1 = 1$."
