# Problem 03: Swapping Two Rows

## 1. The Original Problem

For

$$
A = \begin{pmatrix} 1 & 2 & 0 \\\\ 0 & 3 & 1 \\\\ 2 & 1 & 1 \end{pmatrix}
$$

compute $\det A$. Then form a matrix $B$ by swapping the first and second rows of $A$.

First predict $\det B$ using a determinant property, and then verify your prediction by calculation.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the determinant of matrix $A$.
2. Write down matrix $B$, which results from exchanging Row 1 and Row 2 of $A$: $R_1 \leftrightarrow R_2$.
3. State the theoretical determinant property governing row swaps and use it to predict $\det B$.
4. Directly compute $\det B$ from scratch to verify whether the prediction matches reality.

---

## 3. Before Calculating: What Idea Do We Need?

- **Row Swap (Alternating Property of Determinants):**
  Swapping any two rows (or any two columns) of a square matrix negates its determinant:

$$
\det(\text{matrix after one row swap}) = -\det(\text{original matrix})
$$

- **Geometric Reason:**
  The determinant represents the oriented volume (or oriented area) of the parallelepiped spanned by the row vectors. Swapping two vectors reverses the orientation (chirality) of the coordinate system—analogous to reflecting across a hyperplane—which changes the sign of the oriented volume from positive to negative (or vice versa).

---

## 4. Step-by-Step Solution

### Step 1: Compute $\det A$

We expand along **Row 1** of $A$ because entry $a_{13} = 0$:

$$
\det A = 1 \cdot \begin{vmatrix} 3 & 1 \\\\ 1 & 1 \end{vmatrix} - 2 \cdot \begin{vmatrix} 0 & 1 \\\\ 2 & 1 \end{vmatrix} + 0 \cdot \begin{vmatrix} 0 & 3 \\\\ 2 & 1 \end{vmatrix}
$$

Evaluate each $2 \times 2$ determinant:

$$
\begin{vmatrix} 3 & 1 \\\\ 1 & 1 \end{vmatrix} = (3)(1) - (1)(1) = 3 - 1 = 2
$$

$$
\begin{vmatrix} 0 & 1 \\\\ 2 & 1 \end{vmatrix} = (0)(1) - (1)(2) = 0 - 2 = -2
$$

Combine:

$$
\det A = 1(2) - 2(-2) + 0 = 2 - (-4) = 2 + 4 = 6
$$

### Step 2: Form Matrix $B$ and Predict $\det B$

Exchange Row 1 and Row 2 of $A$:

$$
B = \begin{pmatrix} 0 & 3 & 1 \\\\ 1 & 2 & 0 \\\\ 2 & 1 & 1 \end{pmatrix}
$$

**Prediction:**
Since $B$ is obtained from $A$ by exactly one row transposition ($R_1 \leftrightarrow R_2$), the alternating property dictates:

$$
\det B = -\det A = -6
$$

### Step 3: Directly Compute $\det B$ to Verify

We calculate $\det B$ directly by expanding along **Column 1** of $B$:

$$
\det B = 0 \cdot \begin{vmatrix} 2 & 0 \\\\ 1 & 1 \end{vmatrix} - 1 \cdot \begin{vmatrix} 3 & 1 \\\\ 1 & 1 \end{vmatrix} + 2 \cdot \begin{vmatrix} 3 & 1 \\\\ 2 & 0 \end{vmatrix}
$$

Evaluate the minors:

$$
\begin{vmatrix} 3 & 1 \\\\ 1 & 1 \end{vmatrix} = (3)(1) - (1)(1) = 2
$$

$$
\begin{vmatrix} 3 & 1 \\\\ 2 & 0 \end{vmatrix} = (3)(0) - (1)(2) = 0 - 2 = -2
$$

Combine:

$$
\det B = 0 - 1(2) + 2(-2) = -2 - 4 = -6
$$

The direct calculation yields $-6$, exactly matching our theoretical prediction.

---

## 5. Final Answer & Conclusion

- $\det A = 6$
- The swapped matrix is:

$$
B = \begin{pmatrix} 0 & 3 & 1 \\\\ 1 & 2 & 0 \\\\ 2 & 1 & 1 \end{pmatrix}
$$

- **Prediction:** $\det B = -\det A = -6$
- **Verification:** Direct calculation gives $\det B = -6$.
- **Conclusion:** The alternating sign property under row swapping is completely verified.

---

## 6. Quick Verification

Check $\det A$ using Sarrus' rule:
- Downward: $(1)(3)(1) + (2)(1)(2) + (0)(0)(1) = 3 + 4 + 0 = 7$
- Upward: $(2)(3)(0) + (1)(1)(1) + (1)(0)(2) = 0 + 1 + 0 = 1$
- Result: $\det A = 7 - 1 = 6$.
Since $\det B$ was computed via Column 1 cofactor expansion as $-6$, the relationship $\det B = -\det A$ is independently verified.

---

## 7. Common Mistakes to Avoid

1. **Forgetting the Sign Change:**
   Assuming row operations do not change the determinant. Adding a multiple of one row to another does not change the determinant, but swapping two rows **multiplies the determinant by $-1$**.
2. **Double Swaps:**
   If two separate row swaps are performed, the sign changes twice: $(-1)^2 = +1$, returning to the original sign.

---

## 8. How I Would Explain This in Class

> "When we expand $A$ along its first row, we get $\det A = 6$. The fundamental alternating property states that swapping any two rows reverses the orientation of the row vectors, introducing a minus sign. Therefore, swapping Rows 1 and 2 must give $\det B = -6$. When we compute $\det B$ directly by expanding its first column, we get $-1(2) + 2(-2) = -6$, confirming that every row swap strictly multiplies the determinant by $-1$."