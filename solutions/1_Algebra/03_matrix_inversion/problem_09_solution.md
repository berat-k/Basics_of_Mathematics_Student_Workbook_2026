# Problem 09: Matrix Equation

## 1. The Original Problem

Given

$$
A = \begin{pmatrix} 1 & 2 \\\\ 0 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 3 & 1 \\\\ 2 & 4 \end{pmatrix}
$$

Solve the equation $AX = B$ for $X$. Before calculating, decide on which side of the equation $A^{-1}$ must be used. Then check the result by computing $AX$.

---

## 2. What Are We Trying to Find?

We need to:
1. Determine algebraically on which side of the equation $AX = B$ the inverse matrix $A^{-1}$ must be multiplied to isolate matrix $X$.
2. Compute the inverse matrix $A^{-1}$.
3. Calculate the solution matrix $X$ via matrix multiplication.
4. Verify the result by multiplying $A$ by the calculated matrix $X$ and confirming that it yields matrix $B$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Non-Commutativity and Side-Sensitivity in Matrix Equations:**
  In scalar algebra, if $a x = b$, dividing both sides by $a$ gives $x = b/a = a^{-1} b = b a^{-1}$ because scalar numbers commute.
  In matrix algebra, $M N \neq NM$ in general!
  To solve the equation:

$$
AX = B
$$

  $A$ is attached to the **left** of $X$. To eliminate $A$, we must multiply both sides on the **left** by $A^{-1}$:

$$
A^{-1}(AX) = A^{-1}B \implies (A^{-1}A)X = A^{-1}B \implies IX = A^{-1}B \implies X = A^{-1}B
$$

- **Why Right Multiplication Fails:**
  If we mistakenly multiplied on the right by $A^{-1}$:

$$
(AX)A^{-1} = B A^{-1}
$$

  Because $X$ and $A^{-1}$ do not commute ($X A^{-1} \neq A^{-1} X$), the term $(AX)A^{-1}$ cannot simplify to $X$. $A$ remains trapped! Thus, multiplying on the left is the only valid path.

---

## 4. Step-by-Step Solution

### Step 1: Decision on Multiplication Side

As established above, matrix $A$ acts on the left of $X$. Therefore, we must multiply both sides on the **left** by $A^{-1}$:

$$
X = A^{-1}B
$$

### Step 2: Compute $A^{-1}$

Given:

$$
A = \begin{pmatrix} 1 & 2 \\\\ 0 & 1 \end{pmatrix}
$$

1. Calculate the determinant:

$$
\det A = (1)(1) - (2)(0) = 1
$$

   Since $\det A = 1 \neq 0$, the inverse exists.
2. Form the inverse using the $2 \times 2$ formula:

$$
A^{-1} = \frac{1}{1} \begin{pmatrix} 1 & -2 \\\\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & -2 \\\\ 0 & 1 \end{pmatrix}
$$

Notice that $A$ is an upper unitriangular shear matrix; its inverse is simply obtained by negating the shear entry $2 \to -2$.

### Step 3: Compute $X = A^{-1}B$

Multiply $A^{-1}$ ($2 \times 2$) by $B$ ($2 \times 2$):

$$
X = \begin{pmatrix} 1 & -2 \\\\ 0 & 1 \end{pmatrix} \begin{pmatrix} 3 & 1 \\\\ 2 & 4 \end{pmatrix}
$$

Compute the row-by-column entries:
- **Row 1, Column 1:** $(1)(3) + (-2)(2) = 3 - 4 = -1$
- **Row 1, Column 2:** $(1)(1) + (-2)(4) = 1 - 8 = -7$
- **Row 2, Column 1:** $(0)(3) + (1)(2) = 0 + 2 = 2$
- **Row 2, Column 2:** $(0)(1) + (1)(4) = 0 + 4 = 4$

Putting the entries together:

$$
X = \begin{pmatrix} -1 & -7 \\\\ 2 & 4 \end{pmatrix}
$$

---

## 5. Final Answer & Conclusion

- **Side Decision:** We must multiply on the **left** by $A^{-1}$ to yield $X = A^{-1}B$.
- **The Solution Matrix:**

$$
X = \begin{pmatrix} -1 & -7 \\\\ 2 & 4 \end{pmatrix}
$$

- **Conclusion:** The matrix equation $AX = B$ is uniquely solved by isolating $X$ through left-multiplication by $A^{-1}$.

---

## 6. Quick Verification

Check by directly computing $AX$:

$$
AX = \begin{pmatrix} 1 & 2 \\\\ 0 & 1 \end{pmatrix} \begin{pmatrix} -1 & -7 \\\\ 2 & 4 \end{pmatrix}
$$

Evaluate the entries:
- **Row 1, Column 1:** $(1)(-1) + (2)(2) = -1 + 4 = 3$
- **Row 1, Column 2:** $(1)(-7) + (2)(4) = -7 + 8 = 1$
- **Row 2, Column 1:** $(0)(-1) + (1)(2) = 0 + 2 = 2$
- **Row 2, Column 2:** $(0)(-7) + (1)(4) = 0 + 4 = 4$

Combine into matrix form:

$$
AX = \begin{pmatrix} 3 & 1 \\\\ 2 & 4 \end{pmatrix} = B
$$

The product exactly matches matrix $B$, proving our solution $X$ is completely correct.

---

## 7. Common Mistakes to Avoid

1. **Multiplying on the Right:**
   Computing $B A^{-1}$ instead of $A^{-1} B$. Let us see what $B A^{-1}$ would give:

$$
B A^{-1} = \begin{pmatrix} 3 & 1 \\\\ 2 & 4 \end{pmatrix} \begin{pmatrix} 1 & -2 \\\\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 3 & -5 \\\\ 2 & 0 \end{pmatrix}
$$

   Notice that $B A^{-1} \neq X$. Computing $B A^{-1}$ solves $XA = B$, not $AX = B$!
2. **Treating Matrix Division like Scalar Division:**
   Writing $X = \frac{B}{A}$. Matrix division does not exist because order matters. Always write explicit left-multiplication $A^{-1}B$ or right-multiplication $B A^{-1}$.

---

## 8. How I Would Explain This in Class

> "Because matrix multiplication does not commute, we cannot simply 'divide by $A$'. In $AX = B$, matrix $A$ sits on the left of $X$, so to eliminate it, we must multiply both sides on the left by $A^{-1}$, giving $X = A^{-1}B$. Computing $A^{-1}$ with rows $(1, -2)$ and $(0, 1)$ and multiplying it by $B$ gives the solution $X$ with rows $(-1, -7)$ and $(2, 4)$. When we plug this back in and multiply $AX$, we recover $B$ exactly, confirming our solution."