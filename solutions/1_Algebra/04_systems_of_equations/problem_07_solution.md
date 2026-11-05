# Problem 07: Choosing a Method Deliberately

## 1. The Original Problem

Do not solve all of the following systems completely. For each situation, choose the method that best uses its structure and justify your choice:

1. One system with a triangular coefficient matrix:

$$
\begin{cases}
2x - y = 3, \\\\
4y = 8;
\end{cases}
$$

2. Three systems $Ax = b_i$ with the same invertible matrix $A$, when $A^{-1}$ is already known;
3. One $3 \times 3$ system for which the inverse matrix is not given and the goal is only to find one solution vector.

For case 1, carry out the chosen method completely. For cases 2 and 3, describe the plan and indicate which part of the computation would be reusable or unnecessary. Do not judge a method by its name alone — refer to the number of right-hand sides and the structure of the matrix.

---

## 2. What Are We Trying to Find?

We need to:
1. Analyze the mathematical structure of each of the three computational scenarios.
2. Select the most efficient and natural method for each scenario, justifying the choice based on computational cost, matrix structure, and number of right-hand sides.
3. Solve Case 1 completely using direct back-substitution.
4. For Case 2, describe the solution workflow, identifying the reusable component ($A^{-1}$) and why re-elimination is wasteful.
5. For Case 3, describe the solution workflow, explaining why computing the full matrix inverse $A^{-1}$ is completely unnecessary.

---

## 3. Before Calculating: What Idea Do We Need?

- **Structural Efficiency Over Formula Memorization:**
  In computational linear algebra, algorithms should exploit special structure (e.g., triangular matrices, multiple right-hand sides) to minimize operations:
  - **Triangular matrices** require zero forward elimination steps; they are ready for immediate substitution ($O(n^2)$ operations).
  - When $A^{-1}$ is **already precomputed**, solving $Ax = b$ takes only one matrix-vector multiplication: $x = A^{-1} b$ ($O(n^2)$ operations per right-hand side).
  - When solving **a single system from scratch**, Gaussian elimination on the augmented matrix $[A \mid b]$ takes approximately $\frac{2}{3}n^3$ operations, whereas computing $A^{-1}$ first takes $\approx 2n^3$ operations plus $n^2$ for the product — three times more work!

---

## 4. Step-by-Step Solution

### Scenario 1: Triangular Coefficient Matrix

#### Method Choice and Justification:
The system is:

$$
\begin{cases}
2x - y = 3, \\\\
4y = 8
\end{cases}
$$

The coefficient matrix is:

$$
A = \begin{pmatrix} 2 & -1 \\\\ 0 & 4 \end{pmatrix}
$$

Because all entries below the main diagonal are already zero ($a_{21} = 0$), the matrix is **upper triangular** (already in row echelon form).
- **Best Method:** **Direct Back-Substitution**.
- **Justification:** No elimination steps or matrix manipulations are needed. We can read and solve the variables directly from bottom to top.

#### Complete Calculation for Case 1:

1. **Solve for $y$ from Equation 2:**

$$
4y = 8 \implies y = \frac{8}{4} = 2
$$

2. **Substitute $y = 2$ into Equation 1 and solve for $x$:**

$$
2x - 2 = 3 \implies 2x = 5 \implies x = \frac{5}{2} = 2.5
$$

3. **Solution Vector:**

$$
\begin{pmatrix} x \\\\ y \end{pmatrix} = \begin{pmatrix} 5/2 \\\\ 2 \end{pmatrix}
$$

---

### Scenario 2: Multiple Systems with the Same Invertible Matrix and Known $A^{-1}$

#### Method Choice and Justification:
We are given three systems:

$$
Ax = b_1, \quad Ax = b_2, \quad Ax = b_3
$$

where $A$ is invertible and $A^{-1}$ is already known.
- **Best Method:** **Direct Matrix-Vector Multiplication**:

$$
x_1 = A^{-1} b_1, \quad x_2 = A^{-1} b_2, \quad x_3 = A^{-1} b_3
$$

- **Justification:** Because $A^{-1}$ is precomputed, obtaining each solution requires only a single matrix-by-vector multiplication ($n^2$ operations per system).
- **Reusable Part:** The known matrix $A^{-1}$ is reused directly across all three calculations without recomputation.
- **Unnecessary Work:** Running Gaussian elimination three separate times on $[A \mid b_1]$, $[A \mid b_2]$, and $[A \mid b_3]$ would needlessly repeat the identical row operations on $A$ three times, completely discarding the valuable pre-existing knowledge of $A^{-1}$.

---

### Scenario 3: Single $3 \times 3$ System with Unknown Inverse

#### Method Choice and Justification:
We have a single system $Ax = b$ of size $3 \times 3$, where $A^{-1}$ is unknown, and we only need the solution vector $x$.
- **Best Method:** **Gaussian Elimination on the Augmented Matrix $[A \mid b]$** followed by back-substitution.
- **Justification:** Gaussian elimination solves the system directly by reducing $[A \mid b]$ to row echelon form.
- **Unnecessary Work:** Computing the full matrix inverse $A^{-1}$ (which requires finding all 9 entries by reducing $[A \mid I_3]$) is completely unnecessary. Inverting a $3 \times 3$ matrix requires solving three systems of equations simultaneously (one for each standard basis vector), which takes roughly 3 times as much effort as solving the single system $[A \mid b]$.
- **Reusable Part:** Since there is only one right-hand side $b$, there are no future computations that would ever reuse $A^{-1}$.

---

## 5. Final Answer & Conclusion

- **Case 1 Solution:**
  - Method: Direct Back-Substitution.
  - Result: $x = \frac{5}{2} = 2.5$, $y = 2$.
- **Case 2 Strategy:**
  - Method: Compute $x_i = A^{-1} b_i$ via matrix-vector multiplication.
  - Reusable: The precomputed matrix $A^{-1}$ is applied to all three vectors.
  - Unnecessary: Repeating Gaussian elimination on $A$ three times.
- **Case 3 Strategy:**
  - Method: Gaussian elimination on $[A \mid b]$ with back-substitution.
  - Justification: Solves the single target vector in approximately one-third of the operations required to invert $A$.
  - Unnecessary: Calculating the 9 individual entries of $A^{-1}$.

---

## 6. Quick Verification

Verify the complete solution of Case 1:
- Equation 1: $2x - y = 2(2.5) - 2 = 5 - 2 = 3$. Matches 3. Correct.
- Equation 2: $4y = 4(2) = 8$. Matches 8. Correct.

Verify operation counts conceptually:
- In Case 2: Multiplying a $3 \times 3$ matrix by a $3 \times 1$ vector requires 9 multiplications and 6 additions per vector. Doing this 3 times takes 27 multiplications. In contrast, inverting and solving takes far more arithmetic steps.
- In Case 3: Elimination on a $3 \times 4$ augmented matrix requires only 8 row additions/multiplications plus 3 back-substitutions. Inverting a $3 \times 3$ matrix requires at least 21 operations. Gaussian elimination is clearly optimal.

---

## 7. Common Mistakes to Avoid

1. **Applying $A^{-1}$ as a Universal Reflex:**
   Many students memorize the formula $x = A^{-1} b$ and attempt to compute $A^{-1}$ for every linear system. In practice, finding $A^{-1}$ is computationally expensive and numerically less stable than Gaussian elimination.
2. **Ignoring Triangular Form:**
   Starting row elimination on a matrix that is already triangular, which wastes time and risks introducing arithmetic errors.
3. **Failing to Exploit Known Results:**
   In Case 2, running elimination on $[A \mid b_i]$ from scratch despite already having $A^{-1}$ in hand.

---

## 8. How I Would Explain This in Class

> "Math is not just about getting the right answer; it is about choosing the smartest tool for the specific job. If a system is already triangular, do not do any elimination—just read off the answers backwards! If you already own $A^{-1}$, do not re-solve the equations—just multiply by each right-hand side. And if you only have one system to solve once, never bother finding the entire inverse matrix when Gaussian elimination gets you straight to the finish line in a third of the steps."
