# Problem 15: Associativity of Multiplication and Different Calculation Paths

## 1. The Original Problem

Given

$$
A = \begin{pmatrix} 1 & 2 & 0 \\\\ 0 & 1 & 1 \end{pmatrix}, \quad B = \begin{pmatrix} 1 & 0 \\\\ 2 & 1 \\\\ -1 & 3 \end{pmatrix}, \quad C = \begin{pmatrix} 2 & 1 \\\\ 0 & -1 \end{pmatrix}
$$

Compute $(AB)C$ and $A(BC)$. Compare the results and the number of intermediate operations. Explain what associativity of matrix multiplication means in this example.

---

## 2. What Are We Trying to Find?

We want to:
1. Compute the three-matrix product via two different groupings (parenthesizations): $(AB)C$ and $A(BC)$.
2. Compare the final matrices to verify associativity ($(AB)C = A(BC)$).
3. Count and compare the number of scalar multiplications required by each calculation path.
4. Explain what associativity means mathematically and computationally.

---

## 3. Before Calculating: What Idea Do We Need?

- **Associativity of Matrix Multiplication:**
  For any three matrices where the adjacent dimensions are compatible:

$$
(AB)C = A(BC)
$$

  The grouping of parentheses does not alter the mathematical outcome.
- **Computational Cost of Matrix Multiplication:**
  Multiplying an $m \times k$ matrix by a $k \times p$ matrix produces an $m \times p$ matrix. Computing each of the $m \cdot p$ entries requires $k$ scalar multiplications. Therefore, the total number of multiplications is:

$$
\text{Multiplications} = m \cdot k \cdot p
$$

  Depending on which pair is multiplied first, the total number of operations can differ dramatically (the foundation of the *Matrix Chain Multiplication Problem* in computer science).

---

## 4. Step-by-Step Solution

The matrices have dimensions:
- $A$: $2 \times 3$
- $B$: $3 \times 2$
- $C$: $2 \times 2$

Both $(AB)C$ and $A(BC)$ result in a $2 \times 2$ matrix.

### Path 1: Compute $(AB)C$

#### Step 1A: Compute $AB$
Multiply $A$ ($2 \times 3$) by $B$ ($3 \times 2$):
- **Entry (1, 1):** $1(1) + 2(2) + 0(-1) = 1 + 4 + 0 = 5$
- **Entry (1, 2):** $1(0) + 2(1) + 0(3) = 0 + 2 + 0 = 2$
- **Entry (2, 1):** $0(1) + 1(2) + 1(-1) = 0 + 2 - 1 = 1$
- **Entry (2, 2):** $0(0) + 1(1) + 1(3) = 0 + 1 + 3 = 4$

$$
AB = \begin{pmatrix} 5 & 2 \\\\ 1 & 4 \end{pmatrix}
$$

#### Step 1B: Multiply by $C$
Now multiply the resulting $(AB)$ ($2 \times 2$) by $C$ ($2 \times 2$):

$$
(AB)C = \begin{pmatrix} 5 & 2 \\\\ 1 & 4 \end{pmatrix} \begin{pmatrix} 2 & 1 \\\\ 0 & -1 \end{pmatrix}
$$

- **Entry (1, 1):** $5(2) + 2(0) = 10 + 0 = 10$
- **Entry (1, 2):** $5(1) + 2(-1) = 5 - 2 = 3$
- **Entry (2, 1):** $1(2) + 4(0) = 2 + 0 = 2$
- **Entry (2, 2):** $1(1) + 4(-1) = 1 - 4 = -3$

$$
(AB)C = \begin{pmatrix} 10 & 3 \\\\ 2 & -3 \end{pmatrix}
$$

---

### Path 2: Compute $A(BC)$

#### Step 2A: Compute $BC$
Multiply $B$ ($3 \times 2$) by $C$ ($2 \times 2$), resulting in a $3 \times 2$ matrix:
- **Row 1:**
  - $(BC)_{11} = 1(2) + 0(0) = 2$
  - $(BC)_{12} = 1(1) + 0(-1) = 1$
- **Row 2:**
  - $(BC)_{21} = 2(2) + 1(0) = 4 + 0 = 4$
  - $(BC)_{22} = 2(1) + 1(-1) = 2 - 1 = 1$
- **Row 3:**
  - $(BC)_{31} = -1(2) + 3(0) = -2 + 0 = -2$
  - $(BC)_{32} = -1(1) + 3(-1) = -1 - 3 = -4$

$$
BC = \begin{pmatrix} 2 & 1 \\\\ 4 & 1 \\\\ -2 & -4 \end{pmatrix}
$$

#### Step 2B: Multiply $A$ by $(BC)$
Now multiply $A$ ($2 \times 3$) by $(BC)$ ($3 \times 2$):

$$
A(BC) = \begin{pmatrix} 1 & 2 & 0 \\\\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 2 & 1 \\\\ 4 & 1 \\\\ -2 & -4 \end{pmatrix}
$$

- **Entry (1, 1):** $1(2) + 2(4) + 0(-2) = 2 + 8 + 0 = 10$
- **Entry (1, 2):** $1(1) + 2(1) + 0(-4) = 1 + 2 + 0 = 3$
- **Entry (2, 1):** $0(2) + 1(4) + 1(-2) = 0 + 4 - 2 = 2$
- **Entry (2, 2):** $0(1) + 1(1) + 1(-4) = 0 + 1 - 4 = -3$

$$
A(BC) = \begin{pmatrix} 10 & 3 \\\\ 2 & -3 \end{pmatrix}
$$

---

## 5. Comparison of Operations (Multiplication Count)

Using the formula $\text{cost} = m \cdot k \cdot p$ scalar multiplications:

### Path 1: $(AB)C$
1. Step 1 ($AB$): $(2 \times 3) \times (3 \times 2) \implies 2 \cdot 3 \cdot 2 = 12$ multiplications.
2. Step 2 ($(AB)C$): $(2 \times 2) \times (2 \times 2) \implies 2 \cdot 2 \cdot 2 = 8$ multiplications.
- **Total scalar multiplications:** $12 + 8 = \mathbf{20}$.

### Path 2: $A(BC)$
1. Step 1 ($BC$): $(3 \times 2) \times (2 \times 2) \implies 3 \cdot 2 \cdot 2 = 12$ multiplications.
2. Step 2 ($A(BC)$): $(2 \times 3) \times (3 \times 2) \implies 2 \cdot 3 \cdot 2 = 12$ multiplications.
- **Total scalar multiplications:** $12 + 12 = \mathbf{24}$.

**Observation:**
Path 1 requires 20 multiplications, while Path 2 requires 24 multiplications. Computing $(AB)$ first is approximately $17\%$ faster than computing $(BC)$ first.

---

## 6. What Associativity Means in This Context

- **Mathematical Meaning:** Associativity ensures that the final result does not depend on how parentheses are placed: $(AB)C = A(BC)$. We can simply write $ABC$ without ambiguity.
- **Computational Meaning:** Although the mathematical answer is identical, the *cost* of computation depends heavily on the evaluation order. In numerical linear algebra and graphics pipelines, choosing the optimal parenthesization can save millions of operations.
- **Contrast with Commutativity:** Matrix multiplication is associative ($(AB)C = A(BC)$), but **not** commutative ($AB \neq BA$).

---

## 7. Quick Verification

Check the difference:

$$
(AB)C - A(BC) = \begin{pmatrix} 10 & 3 \\\\ 2 & -3 \end{pmatrix} - \begin{pmatrix} 10 & 3 \\\\ 2 & -3 \end{pmatrix} = \begin{pmatrix} 0 & 0 \\\\ 0 & 0 \end{pmatrix}
$$

Both paths match with 100% precision.

---

## 8. Common Mistakes to Avoid

1. **Changing the order of the matrices:** Confusing associativity (changing parentheses $(AB)C = A(BC)$) with commutativity (swapping matrix positions $ABC \neq CBA$). In associativity, the left-to-right order of the matrix letters ($A, B, C$) never changes!
2. **Assuming all paths cost the same work:** The dimension of the intermediate matrix affects the number of scalar multiplications ($2 \times 2$ vs $3 \times 2$).

---

## 9. How I Would Explain This in Class

> "Matrix multiplication is associative, meaning that grouping matrices differently as $(AB)C$ or $A(BC)$ yields the exact same final matrix with rows $(10, 3)$ and $(2, -3)$. However, the order of calculation affects computational efficiency: computing $(AB)C$ takes 20 scalar multiplications, whereas $A(BC)$ takes 24. While the mathematical answer is identical regardless of parentheses, choosing the right path saves computational work."
