# Problem 06: Transpose

## 1. The Original Problem

For the matrices:

$$
A = \begin{pmatrix} 1 & 2 & 3 \\\\ 4 & 5 & 6 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & 0 \\\\ 2 & 1 \\\\ -1 & 3 \end{pmatrix}
$$

compute $A^T$, $B^T$, and $AB$. Then verify in this example that:

$$
(AB)^T = B^T A^T
$$

---

## 2. What Are We Trying to Find?

We need to:
1. Find the transpose of $A$ and the transpose of $B$.
2. Compute the product $AB$.
3. Compute the transpose of this product, $(AB)^T$.
4. Multiply the transposed matrices in reverse order, $B^T A^T$.
5. Confirm and explain the foundational rule $(AB)^T = B^T A^T$.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Transpose Operation ($M^T$):**
  Transposing a matrix swaps its rows and columns: the rows of $M$ become the columns of $M^T$, and $(M^T)_{ij} = M_{ji}$. If $M$ is $m \times n$, $M^T$ is $n \times m$.
- **Reversal of Product Order Under Transpose:**

$$
(AB)^T = B^T A^T
$$

  The order of factors must flip! If $A$ is $2 \times 3$ and $B$ is $3 \times 2$, then $(AB)$ is $2 \times 2$, so $(AB)^T$ is $2 \times 2$. On the right side, $B^T$ ($2 \times 3$) times $A^T$ ($3 \times 2$) is well-defined and gives $2 \times 2$. Attempting $A^T B^T$ would multiply a $3 \times 2$ by a $2 \times 3$, yielding a $3 \times 3$ matrix—completely different and incompatible!

---

## 4. Step-by-Step Solution

### Step 1: Compute the Transposes $A^T$ and $B^T$
- $A$ is $2 \times 3$, with Row 1 = $(1, 2, 3)$ and Row 2 = $(4, 5, 6)$.
  Writing rows as columns gives the $3 \times 2$ matrix:

$$
A^T = \begin{pmatrix} 1 & 4 \\\\ 2 & 5 \\\\ 3 & 6 \end{pmatrix}
$$

- $B$ is $3 \times 2$, with Row 1 = $(1, 0)$, Row 2 = $(2, 1)$, and Row 3 = $(-1, 3)$.
  Writing rows as columns gives the $2 \times 3$ matrix:

$$
B^T = \begin{pmatrix} 1 & 2 & -1 \\\\ 0 & 1 & 3 \end{pmatrix}
$$

### Step 2: Compute the Product $AB$
$A$ ($2 \times 3$) and $B$ ($3 \times 2$) produce a $2 \times 2$ matrix:
- **Row 1, Column 1:** $1(1) + 2(2) + 3(-1) = 1 + 4 - 3 = 2$
- **Row 1, Column 2:** $1(0) + 2(1) + 3(3) = 0 + 2 + 9 = 11$
- **Row 2, Column 1:** $4(1) + 5(2) + 6(-1) = 4 + 10 - 6 = 8$
- **Row 2, Column 2:** $4(0) + 5(1) + 6(3) = 0 + 5 + 18 = 23$

$$
AB = \begin{pmatrix} 2 & 11 \\\\ 8 & 23 \end{pmatrix}
$$

### Step 3: Compute $(AB)^T$
Transposing the $2 \times 2$ matrix $AB$ swaps its off-diagonal entries:

$$
(AB)^T = \begin{pmatrix} 2 & 8 \\\\ 11 & 23 \end{pmatrix}
$$

### Step 4: Compute $B^T A^T$
Multiply $B^T$ ($2 \times 3$) by $A^T$ ($3 \times 2$):
- **Row 1 of $B^T$ with Column 1 of $A^T$:**
  $$1(1) + 2(2) + (-1)(3) = 1 + 4 - 3 = 2$$
- **Row 1 of $B^T$ with Column 2 of $A^T$:**
  $$1(4) + 2(5) + (-1)(6) = 4 + 10 - 6 = 8$$
- **Row 2 of $B^T$ with Column 1 of $A^T$:**
  $$0(1) + 1(2) + 3(3) = 0 + 2 + 9 = 11$$
- **Row 2 of $B^T$ with Column 2 of $A^T$:**
  $$0(4) + 1(5) + 3(6) = 0 + 5 + 18 = 23$$

$$
B^T A^T = \begin{pmatrix} 2 & 8 \\\\ 11 & 23 \end{pmatrix}
$$

---

## 5. Final Answer & Conclusion

- The transposes are:

$$
A^T = \begin{pmatrix} 1 & 4 \\\\ 2 & 5 \\\\ 3 & 6 \end{pmatrix}, \qquad B^T = \begin{pmatrix} 1 & 2 & -1 \\\\ 0 & 1 & 3 \end{pmatrix}
$$

- The products are:

$$
AB = \begin{pmatrix} 2 & 11 \\\\ 8 & 23 \end{pmatrix}, \qquad (AB)^T = \begin{pmatrix} 2 & 8 \\\\ 11 & 23 \end{pmatrix}, \qquad B^T A^T = \begin{pmatrix} 2 & 8 \\\\ 11 & 23 \end{pmatrix}
$$

- **Conclusion:** Both calculations yield the exact same matrix, verifying that $(AB)^T = B^T A^T$.
- **Why the order reverses:** In $AB$, entry $(i, j)$ is the dot product of (Row $i$ of $A$) and (Column $j$ of $B$). When transposed to $(AB)^T$, that dot product sits at position $(j, i)$. To get that same dot product in row $j$, column $i$ from transposes, the $j$-th row of the first matrix must be Column $j$ of $B$ (which is Row $j$ of $B^T$), and the $i$-th column must be Row $i$ of $A$ (which is Column $i$ of $A^T$). Thus $B^T$ must come first.

---

## 6. Quick Verification

Subtract the two results:

$$
(AB)^T - B^T A^T = \begin{pmatrix} 2 & 8 \\\\ 11 & 23 \end{pmatrix} - \begin{pmatrix} 2 & 8 \\\\ 11 & 23 \end{pmatrix} = \begin{pmatrix} 0 & 0 \\\\ 0 & 0 \end{pmatrix}
$$

The identity holds with complete mathematical exactness.

---

## 7. Common Mistakes to Avoid

1. **Forgetting to reverse the factors:** Writing $(AB)^T = A^T B^T$. In our problem, $A^T B^T$ is a $3 \times 3$ matrix, whereas $(AB)^T$ is $2 \times 2$! They cannot even have the same dimensions.
2. **Confusing transposition with inversion:** Transposing is flipping rows and columns, not taking reciprocals or inverses.

---

## 8. How I Would Explain This in Class

> "Transposing swaps the rows and columns of a matrix. When we multiply two matrices and transpose the result, the order of multiplication must reverse: $(AB)^T = B^T A^T$. In our calculation, $(AB)^T$ and $B^T A^T$ both yield the exact same $2 \times 2$ matrix with rows $(2, 8)$ and $(11, 23)$, confirming that row-column dot products match only when factor order is flipped."
