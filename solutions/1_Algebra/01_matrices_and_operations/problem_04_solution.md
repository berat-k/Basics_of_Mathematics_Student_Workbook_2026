### 1. Compute $AB$
$$

A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}, \quad B = \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix}
$$

Multiply row-by-column:
$$

AB = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix} = \begin{pmatrix} (1)(2) + (2)(3) & (1)(0) + (2)(1) \\ (0)(2) + (1)(3) & (0)(0) + (1)(1) \end{pmatrix}
$$

* Top-left entry: $2 + 6 = 8$
* Top-right entry: $0 + 2 = 2$
* Bottom-left entry: $0 + 3 = 3$
* Bottom-right entry: $0 + 1 = 1$
$$

AB = \begin{pmatrix} 8 & 2 \\ 3 & 1 \end{pmatrix}
$$

---

### 2. Compute $BA$

Multiply row-by-column:
$$

BA = \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix} \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} (2)(1) + (0)(0) & (2)(2) + (0)(1) \\ (3)(1) + (1)(0) & (3)(2) + (1)(1) \end{pmatrix}
$$

* Top-left entry: $2 + 0 = 2$
* Top-right entry: $4 + 0 = 4$
* Bottom-left entry: $3 + 0 = 3$
* Bottom-right entry: $6 + 1 = 7$
$$

BA = \begin{pmatrix} 2 & 4 \\ 3 & 7 \end{pmatrix}
$$

---

### 3. Comparison: Is $AB = BA$?
$$

\begin{pmatrix} 8 & 2 \\ 3 & 1 \end{pmatrix} \neq \begin{pmatrix} 2 & 4 \\ 3 & 7 \end{pmatrix}
$$

**No, $AB \neq BA$.**

---

### 4. What Noncommutativity Means

For standard numbers (real or complex numbers), multiplication is **commutative**: the order does not change the result (e.g., $2 \times 3 = 3 \times 2 = 6$).

In contrast, matrix multiplication is generally **noncommutative**: changing the order of the matrices changes the rows and columns that are paired up, leading to different calculations and different final values.

* The order of factors matters: $AB$ represents a different transformation and result than $BA$.
* Even when both products $AB$ and $BA$ are defined and have the exact same shape (as in this case, both being $2 \times 2$), they are not necessarily equal.
