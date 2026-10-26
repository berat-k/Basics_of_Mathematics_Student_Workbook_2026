# Problem 08: Row Operations and Their Reversibility

## 1. The Original Problem

For

$$
A = \begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & 1 \\ -1 & 1 & 3 \end{pmatrix}
$$

perform, in order:
1. $R_2\leftarrow R_2-2R_1$,
2. $R_3\leftarrow R_3+R_1$,
3. interchange $R_2$ and $R_3$.

Write the matrix after each step. Then, for each of the three operations, state an operation that reverses it.

---

## 2. What Are We Trying to Find?

We want to apply three elementary row operations to a $3 \times 3$ matrix sequentially, record the matrix state after every single operation, identify the reverse operation for each step, and verify that these operations preserve all information by reconstructing the original matrix.

---

## 3. Before Calculating: What Idea Do We Need?

- **Elementary Row Operations:**
  These are the basic tools of Gaussian elimination:
  1. Adding a scalar multiple of one row to another ($R_i \leftarrow R_i + c R_j$).
  2. Swapping two rows ($R_i \leftrightarrow R_j$).
  3. Scaling a row by a non-zero constant ($R_i \leftarrow c R_i$).
- **Reversibility:**
  Elementary row operations never destroy information; each one can be completely undone by an inverse row operation of the same kind. This is why row-reducing an augmented matrix does not change the solution set of a linear system.

---

## 4. Step-by-Step Solution

We start with the original matrix:

$$
A = \begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & 1 \\ -1 & 1 & 3 \end{pmatrix}
$$

### Step 1: Perform $R_2 \leftarrow R_2 - 2R_1$
We subtract twice row 1 from row 2.
- $R_1 = (1, 2, -1)$, so $2R_1 = (2, 4, -2)$.
- Subtract from current $R_2 = (2, 4, 1)$:
  $$\text{New } R_2 = (2 - 2, 4 - 4, 1 - (-2)) = (0, 0, 3).$$
- Rows 1 and 3 remain unchanged.

The matrix after Step 1 is:

$$
A_1 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ -1 & 1 & 3 \end{pmatrix}
$$

### Step 2: Perform $R_3 \leftarrow R_3 + R_1$
We add row 1 to row 3.
- $R_1 = (1, 2, -1)$.
- Add to current $R_3 = (-1, 1, 3)$:
  $$\text{New } R_3 = (-1 + 1, 1 + 2, 3 + (-1)) = (0, 3, 2).$$
- Rows 1 and 2 remain unchanged.

The matrix after Step 2 is:

$$
A_2 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ 0 & 3 & 2 \end{pmatrix}
$$

### Step 3: Interchange $R_2$ and $R_3$ ($R_2 \leftrightarrow R_3$)
We swap the second and third rows:
- The new second row is $(0, 3, 2)$.
- The new third row is $(0, 0, 3)$.

The matrix after Step 3 is:

$$
A_3 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 2 \\ 0 & 0 & 3 \end{pmatrix}
$$

*(Note: $A_3$ is now in upper triangular row echelon form.)*

---

## 5. Reversing the Operations

Each elementary row operation has an exact inverse operation that restores the previous state:

1. **Forward:** $R_2 \leftarrow R_2 - 2R_1$
   - **Reverse:** $R_2 \leftarrow R_2 + 2R_1$ *(add $2R_1$ back to $R_2$)*
2. **Forward:** $R_3 \leftarrow R_3 + R_1$
   - **Reverse:** $R_3 \leftarrow R_3 - R_1$ *(subtract $R_1$ from $R_3$)*
3. **Forward:** $R_2 \leftrightarrow R_3$
   - **Reverse:** $R_2 \leftrightarrow R_3$ *(swap the same rows again)*

---

## 6. Quick Verification (Reconstructing $A$)

Let us verify by applying the reverse operations to $A_3$ in reverse order:

1. Apply $R_2 \leftrightarrow R_3$ to $A_3$:

$$
\begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 2 \\ 0 & 0 & 3 \end{pmatrix} \xrightarrow{R_2 \leftrightarrow R_3} \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ 0 & 3 & 2 \end{pmatrix} = A_2
$$

2. Apply $R_3 \leftarrow R_3 - R_1$ to $A_2$:

$$
R_3 = (0, 3, 2) - (1, 2, -1) = (-1, 1, 3)
$$

$$
\begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ 0 & 3 & 2 \end{pmatrix} \xrightarrow{R_3 \leftarrow R_3 - R_1} \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ -1 & 1 & 3 \end{pmatrix} = A_1
$$

3. Apply $R_2 \leftarrow R_2 + 2R_1$ to $A_1$:

$$
R_2 = (0, 0, 3) + 2(1, 2, -1) = (2, 4, 1)
$$

$$
\begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ -1 & 1 & 3 \end{pmatrix} \xrightarrow{R_2 \leftarrow R_2 + 2R_1} \begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & 1 \\ -1 & 1 & 3 \end{pmatrix} = A
$$

The original matrix $A$ is restored perfectly.

---

## 7. Common Mistakes to Avoid

1. **Sign mistakes during subtraction:** In Step 1, $1 - 2(-1) = 1 + 2 = 3$, not $-1$.
2. **Applying reverse operations in forward order:** To undo a sequence of transformations, you must apply the inverses in **reverse chronological order** (last undone first).
3. **Overwriting rows prematurely:** When performing $R_2 \leftarrow R_2 - 2R_1$, row 1 itself does not change; only row 2 is modified.

---

## 8. How I Would Explain This in Class

> "We applied three elementary row operations to $A$: subtracting twice the first row from the second, adding the first row to the third, and finally swapping rows 2 and 3. This transforms the matrix into row echelon form $\begin{pmatrix}1&2&-1\\0&3&2\\0&0&3\end{pmatrix}$. Because each row operation has an exact inverse—adding what was subtracted or swapping back—no information is lost, and we can completely restore the original matrix."
