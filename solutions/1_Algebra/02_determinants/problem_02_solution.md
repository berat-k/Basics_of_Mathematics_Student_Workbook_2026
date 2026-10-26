# Problem 02: Determinant of a 3×3 Matrix

## 1. The Original Problem

For

$$
A = \begin{pmatrix} 1 & 2 & -1 \\\\ 0 & 3 & 4 \\\\ 2 & 1 & 5 \end{pmatrix}
$$

compute $\det A$ using Sarrus' rule. Then perform one simple check using a chosen property of the determinant.

---

## 2. What Are We Trying to Find?

We need to:
1. Calculate $\det A$ using Sarrus' rule by writing out the forward and backward diagonal products.
2. Verify the result using an alternative method or determinant property (specifically Laplace expansion along Column 1, which contains a zero).
3. Confirm that both independent calculation paths arrive at the exact same value.

---

## 3. Before Calculating: What Idea Do We Need?

- **Sarrus' Rule ($3 \times 3$ Only):**
  Write the $3 \times 3$ matrix and copy its first two columns to the right:

$$
\begin{matrix}
1 & 2 & -1 & 1 & 2 \\\\
0 & 3 & 4 & 0 & 3 \\\\
2 & 1 & 5 & 2 & 1
\end{matrix}
$$

  - Add the products of the three downward-right diagonals: $D_1 = (1)(3)(5)$, $D_2 = (2)(4)(2)$, $D_3 = (-1)(0)(1)$.
  - Subtract the products of the three upward-right diagonals: $U_1 = (2)(3)(-1)$, $U_2 = (1)(4)(1)$, $U_3 = (5)(0)(2)$.
  - Result: $\det A = (D_1 + D_2 + D_3) - (U_1 + U_2 + U_3)$.
  - *Caution:* Sarrus' rule is strictly valid for $3 \times 3$ matrices and cannot be generalized to $4 \times 4$ or higher dimensions.
- **Verification Property (Laplace Expansion):**
  We can expand along any row or column: $\det A = \sum_{j=1}^3 (-1)^{i+j} a_{ij} M_{ij}$. Choosing a row or column with zero entries minimizes arithmetic.

---

## 4. Step-by-Step Solution

### Step 1: Calculate Diagonal Products Using Sarrus' Rule

1. **Downward-Right Diagonals (Positive Terms):**
   - First diagonal: $1 \cdot 3 \cdot 5 = 15$
   - Second diagonal: $2 \cdot 4 \cdot 2 = 16$
   - Third diagonal: $(-1) \cdot 0 \cdot 1 = 0$
   - Sum of downward products:

$$
\Sigma_{\text{down}} = 15 + 16 + 0 = 31
$$

2. **Upward-Right Diagonals (Negative Terms):**
   - First diagonal: $2 \cdot 3 \cdot (-1) = -6$
   - Second diagonal: $1 \cdot 4 \cdot 1 = 4$
   - Third diagonal: $5 \cdot 0 \cdot 2 = 0$
   - Sum of upward products:

$$
\Sigma_{\text{up}} = (-6) + 4 + 0 = -2
$$

3. **Compute the Determinant:**

$$
\det A = \Sigma_{\text{down}} - \Sigma_{\text{up}} = 31 - (-2) = 31 + 2 = 33
$$

---

## 5. Final Answer & Conclusion

- The determinant of matrix $A$ computed via Sarrus' rule is:

$$
\det A = 33
$$

---

## 6. Quick Verification

To verify the result without repeating the entire Sarrus scheme, we perform a Laplace expansion along **Column 1**, which contains entry $a_{21} = 0$:

$$
\det A = a_{11} C_{11} + a_{21} C_{21} + a_{31} C_{31}
$$

$$
\det A = 1 \cdot \begin{vmatrix} 3 & 4 \\\\ 1 & 5 \end{vmatrix} - 0 \cdot \begin{vmatrix} 2 & -1 \\\\ 1 & 5 \end{vmatrix} + 2 \cdot \begin{vmatrix} 2 & -1 \\\\ 3 & 4 \end{vmatrix}
$$

Evaluate the two remaining $2 \times 2$ determinants:

$$
\begin{vmatrix} 3 & 4 \\\\ 1 & 5 \end{vmatrix} = (3)(5) - (4)(1) = 15 - 4 = 11
$$

$$
\begin{vmatrix} 2 & -1 \\\\ 3 & 4 \end{vmatrix} = (2)(4) - (-1)(3) = 8 - (-3) = 11
$$

Substitute these back:

$$
\det A = 1(11) - 0 + 2(11) = 11 + 22 = 33
$$

Both methods yield exactly $33$, confirming the calculation with complete certainty.

---

## 7. Common Mistakes to Avoid

1. **Applying Sarrus to $4 \times 4$ Matrices:**
   Sarrus' rule only produces the full $3! = 6$ permutations for $n = 3$. For $n = 4$, there are $4! = 24$ terms, while drawing diagonals only yields 8 terms.
2. **Sign Confusion on Upward Diagonals:**
   Remember that upward diagonals are *subtracted*. When the product itself is negative (like $2 \cdot 3 \cdot (-1) = -6$), subtracting it becomes $+6$: $-(-6) = +6$.

---

## 8. How I Would Explain This in Class

> "To evaluate a $3 \times 3$ determinant by Sarrus' rule, we repeat the first two columns and multiply along three downward diagonals, giving $15 + 16 + 0 = 31$, then subtract the three upward diagonals, which sum to $-2$. Subtracting gives $31 - (-2) = 33$. We can immediately check our answer by expanding down the first column where zero simplifies our work: $1(11) + 2(11) = 33$, verifying the result in seconds."