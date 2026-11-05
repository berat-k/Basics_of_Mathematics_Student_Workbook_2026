# Problem 04: Gauss–Jordan

## 1. The Original Problem

Find $A^{-1}$ using the Gauss–Jordan method for

$$
A = \begin{pmatrix} 1 & 2 \\\\ 3 & 5 \end{pmatrix}
$$

Show the augmented matrix $[A \mid I]$ after successive operations and explain why obtaining $I$ on the left gives the inverse on the right.

---

## 2. What Are We Trying to Find?

We need to:
1. Set up the augmented block matrix $[A \mid I_2]$.
2. Perform a clear sequence of elementary row operations to reduce the left block from $A$ to the identity matrix $I_2$.
3. Display the state of the augmented matrix after each operation.
4. Extract the resulting inverse matrix $A^{-1}$ from the right block.
5. Provide a rigorous theoretical explanation for why the Gauss–Jordan process guarantees that the right block becomes $A^{-1}$.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Gauss–Jordan Setup:**
  We place the target matrix $A$ alongside the identity matrix $I$ in an augmented matrix:

$$
[A \mid I]
$$

- **Why Row Operations Invert Matrices (Elementary Matrices):**
  Every elementary row operation corresponds to multiplying on the left by an invertible elementary matrix $E_k$.
  If a sequence of $k$ row operations transforms $A$ into the identity matrix $I$:

$$
E_k \cdots E_2 E_1 A = I
$$

  then by definition, the product of these elementary matrices is the inverse of $A$:

$$
(E_k \cdots E_2 E_1) = A^{-1}
$$

  Because the exact same row operations are simultaneously applied to the right block $I$:

$$
E_k \cdots E_2 E_1 [A \mid I] = [E_k \cdots E_1 A \mid E_k \cdots E_1 I] = [I \mid A^{-1}]
$$

  Therefore, the moment $I$ appears on the left, $A^{-1}$ automatically appears on the right!

---

## 4. Step-by-Step Solution

### Step 1: Set Up the Augmented Matrix

Place $A$ on the left and the $2 \times 2$ identity matrix $I_2$ on the right:

$$
[A \mid I] = \left(\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\\\ 3 & 5 & 0 & 1 \end{array}\right)
$$

### Step 2: Eliminate Entry Under the First Pivot ($a_{21} = 3$)

Using Row 1 as our pivot, eliminate the $3$ in Row 2 by the operation:

$$
R_2 \leftarrow R_2 - 3R_1
$$

Calculate the new entries for Row 2:
- Left block: $(3 - 3(1), \, 5 - 3(2)) = (0, \, 5 - 6) = (0, -1)$
- Right block: $(0 - 3(1), \, 1 - 3(0)) = (-3, 1)$

The augmented matrix becomes:

$$
\left(\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\\\ 0 & -1 & -3 & 1 \end{array}\right)
$$

### Step 3: Normalize the Second Pivot to $+1$

Multiply Row 2 by $-1$:

$$
R_2 \leftarrow -R_2
$$

The augmented matrix becomes:

$$
\left(\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\\\ 0 & 1 & 3 & -1 \end{array}\right)
$$

### Step 4: Eliminate Entry Above the Second Pivot ($a_{12} = 2$)

Using Row 2 as the pivot, eliminate the $2$ in Row 1 by the operation:

$$
R_1 \leftarrow R_1 - 2R_2
$$

Calculate the new entries for Row 1:
- Left block: $(1 - 2(0), \, 2 - 2(1)) = (1, 0)$
- Right block: $(1 - 2(3), \, 0 - 2(-1)) = (1 - 6, \, 0 + 2) = (-5, 2)$

The augmented matrix is now in reduced row echelon form:

$$
\left(\begin{array}{cc|cc} 1 & 0 & -5 & 2 \\\\ 0 & 1 & 3 & -1 \end{array}\right)
$$

The left side is now the identity matrix $I_2$. Consequently, the right side is the inverse matrix $A^{-1}$:

$$
A^{-1} = \begin{pmatrix} -5 & 2 \\\\ 3 & -1 \end{pmatrix}
$$

---

## 5. Final Answer & Conclusion

- **The Inverse Matrix:**

$$
A^{-1} = \begin{pmatrix} -5 & 2 \\\\ 3 & -1 \end{pmatrix}
$$

- **Theoretical Explanation:**
  The row operations applied were:
  1. $E_1$: $R_2 \leftarrow R_2 - 3R_1$
  2. $E_2$: $R_2 \leftarrow -R_2$
  3. $E_3$: $R_1 \leftarrow R_1 - 2R_2$

  Since $E_3 E_2 E_1 A = I$, the product $E = E_3 E_2 E_1$ satisfies $E A = I$, which means $E = A^{-1}$. Simultaneously applying $E$ to the identity matrix yields $E I = A^{-1}$, proving that the right side must be $A^{-1}$.

---

## 6. Quick Verification

Multiply $A$ by $A^{-1}$:

$$
A A^{-1} = \begin{pmatrix} 1 & 2 \\\\ 3 & 5 \end{pmatrix} \begin{pmatrix} -5 & 2 \\\\ 3 & -1 \end{pmatrix}
$$

Evaluate entries:
- **Row 1, Column 1:** $1(-5) + 2(3) = -5 + 6 = 1$
- **Row 1, Column 2:** $1(2) + 2(-1) = 2 - 2 = 0$
- **Row 2, Column 1:** $3(-5) + 5(3) = -15 + 15 = 0$
- **Row 2, Column 2:** $3(2) + 5(-1) = 6 - 5 = 1$

$$
A A^{-1} = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} = I
$$

Also verify via the $2 \times 2$ formula: $\det A = 5 - 6 = -1$:

$$
A^{-1} = \frac{1}{-1} \begin{pmatrix} 5 & -2 \\\\ -3 & 1 \end{pmatrix} = \begin{pmatrix} -5 & 2 \\\\ 3 & -1 \end{pmatrix}
$$

Both methods match identically.

---

## 7. Common Mistakes to Avoid

1. **Applying Operations Only to the Left Side:**
   Modifying the $A$ block and forgetting to apply the exact same arithmetic to the $I$ block on the right.
2. **Sign Slips on Pivot Normalization:**
   When scaling $R_2$ by $-1$, forgetting to flip the signs on the right-hand entries: $-3$ becomes $+3$, and $+1$ becomes $-1$.

---

## 8. How I Would Explain This in Class

> "The Gauss–Jordan method works by setting up $[A \mid I]$ and applying row operations until $A$ becomes $I$. Because every row operation is mathematically equivalent to multiplying on the left by an elementary matrix, the sequence of operations that turns $A$ into $I$ is literally the inverse matrix $A^{-1}$. By applying those identical operations to $I$ on the right side, we record the accumulation of those operations, leaving the inverse matrix with rows $(-5, 2)$ and $(3, -1)$ cleanly on the right."