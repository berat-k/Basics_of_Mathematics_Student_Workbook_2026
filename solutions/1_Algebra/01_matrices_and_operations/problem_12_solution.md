# Problem 12: Formula for a Matrix Power

## 1. The Original Problem

Let
$$

A=\begin{pmatrix}1&1\\0&1\end{pmatrix}.
$$

Compute $A^2$, $A^3$, and $A^4$, and use them to formulate a conjecture for $A^n$. Then do not stop after checking one more case: assume the formula is true for $n$, multiply by $A$, and explain why you obtain exactly the formula for $n+1$.

---

## 2. What Are We Trying to Find?

We want to calculate the small powers $A^2, A^3, A^4$ of a shear matrix $A$, spot the emerging pattern for the general power $A^n$, and prove this conjecture conclusively for all positive integers $n \ge 1$ using mathematical induction.

---

## 3. Before Calculating: What Idea Do We Need?

- **Mathematical Induction:**
  A two-step proof method for statements indexed by integers $n \in \{1, 2, 3, \dots\}$:
  1. *Base Case:* Verify the formula works for $n = 1$.
  2. *Inductive Step:* Prove that IF the formula is true for an arbitrary integer $k$, THEN it must also be true for $k + 1$ (by computing $A^{k+1} = A^k \cdot A$).
- **Geometric Shear Intuition:**
  The matrix $A = \begin{pmatrix}1&1\\0&1\end{pmatrix}$ represents a horizontal shear $(x, y) \mapsto (x + y, y)$. Applying the shear twice shifts $x$ by $2y$; applying it $n$ times should naturally shift $x$ by $ny$.

---

## 4. Step-by-Step Solution

### Step 1: Compute Small Powers
Given $A = \begin{pmatrix}1&1\\0&1\end{pmatrix}$:

1. **Compute $A^2$:**
$$

A^2 = A \cdot A = \begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix} = \begin{pmatrix}1(1)+1(0) & 1(1)+1(1) \\ 0(1)+1(0) & 0(1)+1(1)\end{pmatrix} = \begin{pmatrix}1&2\\0&1\end{pmatrix}.
$$

2. **Compute $A^3$:**
$$

A^3 = A^2 \cdot A = \begin{pmatrix}1&2\\0&1\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix} = \begin{pmatrix}1(1)+2(0) & 1(1)+2(1) \\ 0(1)+1(0) & 0(1)+1(1)\end{pmatrix} = \begin{pmatrix}1&3\\0&1\end{pmatrix}.
$$

3. **Compute $A^4$:**
$$

A^4 = A^3 \cdot A = \begin{pmatrix}1&3\\0&1\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix} = \begin{pmatrix}1(1)+3(0) & 1(1)+3(1) \\ 0(1)+1(0) & 0(1)+1(1)\end{pmatrix} = \begin{pmatrix}1&4\\0&1\end{pmatrix}.
$$

### Step 2: Formulate the General Conjecture
Looking at the sequence:
$$

A^1 = \begin{pmatrix}1&1\\0&1\end{pmatrix},\quad A^2 = \begin{pmatrix}1&2\\0&1\end{pmatrix},\quad A^3 = \begin{pmatrix}1&3\\0&1\end{pmatrix},\quad A^4 = \begin{pmatrix}1&4\\0&1\end{pmatrix},
$$

the diagonal entries stay $1$, the lower-left entry stays $0$, and the upper-right entry is precisely the exponent $n$.
We conjecture:
$$

A^n = \begin{pmatrix}1&n\\0&1\end{pmatrix} \quad \text{for all integers } n \ge 1.
$$

---

## 5. Formal Proof by Mathematical Induction

### Step 1: Base Step ($n = 1$)
For $n = 1$, the formula asserts:
$$

A^1 = \begin{pmatrix}1&1\\0&1\end{pmatrix}.
$$

This matches the given matrix $A$. The base step is verified.

### Step 2: Inductive Hypothesis
Assume the conjecture is true for some positive integer $k \ge 1$:
$$

A^k = \begin{pmatrix}1&k\\0&1\end{pmatrix}.
$$

### Step 3: Inductive Step ($n = k + 1$)
We must show that this implies the formula holds for $k + 1$, meaning:
$$

A^{k+1} = \begin{pmatrix}1&k+1\\0&1\end{pmatrix}.
$$

By definition of matrix powers:
$$

A^{k+1} = A^k \cdot A.
$$

Substituting our inductive hypothesis for $A^k$:
$$

A^{k+1} = \begin{pmatrix}1&k\\0&1\end{pmatrix} \begin{pmatrix}1&1\\0&1\end{pmatrix}.
$$

Now multiply the two matrices row-by-column:
- **Entry (1, 1):** $1(1) + k(0) = 1$
- **Entry (1, 2):** $1(1) + k(1) = 1 + k = k + 1$
- **Entry (2, 1):** $0(1) + 1(0) = 0$
- **Entry (2, 2):** $0(1) + 1(1) = 1$

Putting the entries together:
$$

A^{k+1} = \begin{pmatrix}1&k+1\\0&1\end{pmatrix}.
$$

The result has the exact same form with $k$ replaced by $k + 1$.

### Conclusion:
By the Principle of Mathematical Induction, the formula $A^n = \begin{pmatrix}1&n\\0&1\end{pmatrix}$ is proved for all positive integers $n \ge 1$. $\blacksquare$

---

## 6. Quick Verification

Alternative verification via binomial theorem:
Let $N = \begin{pmatrix}0&1\\0&0\end{pmatrix}$. Note that $A = I + N$ and $N^2 = 0$.
Since $I$ and $N$ commute, we can expand:
$$

A^n = (I + N)^n = I^n + \binom{n}{1} I^{n-1} N + \binom{n}{2} I^{n-2} N^2 + \dots = I + n N = \begin{pmatrix}1&n\\0&1\end{pmatrix}.
$$

This completely confirms our inductive proof.

---

## 7. Common Mistakes to Avoid

1. **Confusing induction with checking examples:** Computing $A^5$ and $A^6$ is not a proof. A proof requires the formal inductive step where $A^k$ is multiplied by $A$ to yield $A^{k+1}$.
2. **Raising every entry to the power $n$:** Writing $A^n = \begin{pmatrix}1^n & 1^n \\ 0^n & 1^n\end{pmatrix} = \begin{pmatrix}1&1\\0&1\end{pmatrix}$. Powers of matrices are products, not entrywise powers.

---

## 8. How I Would Explain This in Class

> "After multiplying $A$ by itself several times, we see that $A^2, A^3, A^4$ only change in their top-right entry, which equals $2, 3, 4$. To prove the conjecture $A^n = \begin{pmatrix}1&n\\0&1\end{pmatrix}$ for all $n$, we use mathematical induction: assuming it holds for $k$, multiplying by $A$ adds another 1 to the top-right entry ($k + 1$) while leaving the other entries unchanged, completing the proof."
