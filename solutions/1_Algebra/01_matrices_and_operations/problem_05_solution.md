### 1. Compute $Ax$

Using standard row-by-column multiplication:

$$Ax = \begin{pmatrix} 2 & -1 \\ 1 & 3 \end{pmatrix} \begin{pmatrix} 4 \\ 2 \end{pmatrix} = \begin{pmatrix} (2)(4) + (-1)(2) \\ (1)(4) + (3)(2) \end{pmatrix} = \begin{pmatrix} 8 - 2 \\ 4 + 6 \end{pmatrix} = \begin{pmatrix} 6 \\ 10 \end{pmatrix}$$

---

### 2. Express $Ax$ as a Linear Combination of Columns

The columns of matrix $A$ are:


$$\mathbf{a}_1 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}, \quad \mathbf{a}_2 = \begin{pmatrix} -1 \\ 3 \end{pmatrix}$$

Using the entries of vector $x = \begin{pmatrix} 4 \\ 2 \end{pmatrix}$ as weights (coefficients):

$$Ax = 4 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 2 \begin{pmatrix} -1 \\ 3 \end{pmatrix}$$

**Verification:**


$$4 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 2 \begin{pmatrix} -1 \\ 3 \end{pmatrix} = \begin{pmatrix} 8 \\ 4 \end{pmatrix} + \begin{pmatrix} -2 \\ 6 \end{pmatrix} = \begin{pmatrix} 8 - 2 \\ 4 + 6 \end{pmatrix} = \begin{pmatrix} 6 \\ 10 \end{pmatrix}$$
