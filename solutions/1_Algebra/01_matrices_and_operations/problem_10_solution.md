# Problem 10: Columns of a Matrix Product

## 1. The Original Problem

Given

$$

A=\begin{pmatrix}1&2&0\\0&1&1\end{pmatrix},\qquad B=\begin{pmatrix}1&2\\-1&0\\3&1\end{pmatrix}.

$$

Denote the columns of $B$ by $b_1,b_2$.

1. Compute $Ab_1$ and $Ab_2$.
2. Compute the matrix $AB$.
3. Compare the results and explain why the columns of $AB$ are exactly the vectors $Ab_1$ and $Ab_2$.

---

## 2. What Are We Trying to Find?

We want to:
1. Multiply matrix $A$ individually by each column vector of $B$ ($b_1$ and $b_2$).
2. Compute the full product matrix $AB$.
3. Connect the two results to demonstrate that the columns of $AB$ are literally the images of the columns of $B$ under matrix $A$.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Column-by-Column Definition of Matrix Multiplication:**
  If a matrix $B$ is viewed as a block of column vectors $B = \begin{pmatrix} b_1 & b_2 & \\ dots & b_p \end{pmatrix}$, then multiplying $A$ by $B$ is equivalent to distributing $A$ across each column:

$$

AB = A \begin{pmatrix} b_1 & b_2 & \\ dots & b_p \end{pmatrix} = \begin{pmatrix} A b_1 & A b_2 & \\ dots & A b_p \end{pmatrix}.

$$

- Each column of the product is simply the matrix $A$ acting on the corresponding column of $B$.

---

## 4. Step-by-Step Solution

Matrix $A$ is $2 \times 3$ and matrix $B$ is $3 \times 2$.
The two columns of $B$ are:

$$

b_1 = \begin{pmatrix}1\\-1\\3\end{pmatrix},\qquad b_2 = \begin{pmatrix}2\\0\\1\end{pmatrix}.

$$

### Step 1: Compute $Ab_1$ and $Ab_2$
- **For $Ab_1$:**

$$

Ab_1 = \begin{pmatrix}1&2&0\\0&1&1\end{pmatrix}\begin{pmatrix}1\\-1\\3\end{pmatrix} = \begin{pmatrix}1(1) + 2(-1) + 0(3) \\ 0(1) + 1(-1) + 1(3)\end{pmatrix} = \begin{pmatrix}1 - 2 + 0 \\ 0 - 1 + 3\end{pmatrix} = \begin{pmatrix}-1\\2\end{pmatrix}.

$$

- **For $Ab_2$:**

$$

Ab_2 = \begin{pmatrix}1&2&0\\0&1&1\end{pmatrix}\begin{pmatrix}2\\0\\1\end{pmatrix} = \begin{pmatrix}1(2) + 2(0) + 0(1) \\ 0(2) + 1(0) + 1(1)\end{pmatrix} = \begin{pmatrix}2 + 0 + 0 \\ 0 + 0 + 1\end{pmatrix} = \begin{pmatrix}2\\1\end{pmatrix}.

$$

### Step 2: Compute the Full Product Matrix $AB$
$A$ ($2 \times 3$) and $B$ ($3 \times 2$) produce a $2 \times 2$ matrix:
- **Row 1, Column 1:** $1(1) + 2(-1) + 0(3) = 1 - 2 + 0 = -1$
- **Row 1, Column 2:** $1(2) + 2(0) + 0(1) = 2 + 0 + 0 = 2$
- **Row 2, Column 1:** $0(1) + 1(-1) + 1(3) = 0 - 1 + 3 = 2$
- **Row 2, Column 2:** $0(2) + 1(0) + 1(1) = 0 + 0 + 1 = 1$

Putting the entries together:

$$

AB = \begin{pmatrix}-1 & 2 \\ 2 & 1\end{pmatrix}.

$$

### Step 3: Compare and Explain the Relationship
Placing the vectors $Ab_1$ and $Ab_2$ side by side into a matrix:

$$

\begin{pmatrix} Ab_1 & Ab_2 \end{pmatrix} = \begin{pmatrix} \\ begin{pmatrix}-1\\2\end{pmatrix} & \begin{pmatrix}2\\1\end{pmatrix} \end{pmatrix} = \begin{pmatrix}-1 & 2 \\ 2 & 1\end{pmatrix}.

$$

This is identical to $AB$.

**Why this holds:**
By the definition of matrix multiplication, the $(i, j)$-entry of $AB$ is:

$$

(AB)_{ij} = \sum_{k=1}^3 a_{ik} b_{kj}.

$$

The numbers $b_{1j}, b_{2j}, b_{3j}$ are precisely the entries of the $j$-th column vector $b_j$.
Therefore:

$$

\sum_{k=1}^3 a_{ik} b_{kj} = (\text{row } i \text{ of } A) \cdot b_j = (Ab_j)_i.

$$

Because every entry in the $j$-th column of $AB$ equals the corresponding entry in the vector $Ab_j$, the entire $j$-th column of $AB$ is $Ab_j$.

---

## 5. Final Answer & Conclusion

- $Ab_1 = \begin{pmatrix}-1\\2\end{pmatrix}$
- $Ab_2 = \begin{pmatrix}2\\1\end{pmatrix}$
- $AB = \begin{pmatrix}-1 & 2 \\ 2 & 1\end{pmatrix}$
- **Conclusion:** $AB = \begin{pmatrix} Ab_1 & Ab_2 \end{pmatrix}$. Matrix multiplication does not have to be done as independent single-number dot products; it can be understood as applying transformation $A$ to each column of $B$ simultaneously.

---

## 6. Quick Verification

Check the difference:

$$

AB - \begin{pmatrix} Ab_1 & Ab_2 \end{pmatrix} = \begin{pmatrix}-1 & 2 \\ 2 & 1\end{pmatrix} - \begin{pmatrix}-1 & 2 \\ 2 & 1\end{pmatrix} = \begin{pmatrix}0 & 0 \\ 0 & 0\end{pmatrix}.

$$

The identity holds unconditionally.

---

## 7. Common Mistakes to Avoid

1. **Mixing up columns of $B$ with rows of $B$:** $b_1$ is the first vertical column $(1, -1, 3)^T$, not the first horizontal row $(1, 2)$.
2. **Confusing column-perspective with row-perspective:** The columns of $AB$ are $A$ times the columns of $B$. The rows of $AB$ are the rows of $A$ times the matrix $B$.

---

## 8. How I Would Explain This in Class

> "Multiplying two matrices $A$ and $B$ can be seen column by column: the first column of the product is simply $A$ times the first column of $B$, which gives $\begin{pmatrix}-1\\2\end{pmatrix}$, and the second column is $A$ times the second column of $B$, giving $\begin{pmatrix}2\\1\end{pmatrix}$. Placing them together gives the complete product matrix $AB = \begin{pmatrix}-1 & 2 \\ 2 & 1\end{pmatrix}$. This shows that matrix multiplication is just transforming multiple vectors at the same time."
