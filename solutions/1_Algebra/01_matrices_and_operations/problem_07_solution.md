# Problem 07: Identity Matrix, Zero Matrix, and Powers

## 1. The Original Problem

For
$$A=\begin{pmatrix}2&1\\0&2\end{pmatrix}$$
compute
$$AI,\qquad IA,\qquad A+0,\qquad A^2,\qquad A^3.$$
Explain the roles of the matrices $I$ and $0$, and describe the pattern you observe in successive powers of $A$.

---

## 2. What Are We Trying to Find?

We want to observe how special matrices—the identity matrix $I$ and zero matrix $0$—interact with $A$, compute the first few integer powers $A^2$ and $A^3$, and discover the general algebraic pattern governing $A^n$.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Neutral Elements:**
  - The **identity matrix $I$** is the neutral element for matrix multiplication: $AI = IA = A$ (analogous to $x \cdot 1 = 1 \cdot x = x$ for real numbers).
  - The **zero matrix $0$** is the neutral element for matrix addition: $A + 0 = A$ (analogous to $x + 0 = x$).
- **Powers via Decomposition:**
  Notice that $A$ can be split into a scalar multiple of identity and a simple shift matrix:
  $$A = 2I + N, \quad \text{where } N = \begin{pmatrix}0&1\\0&0\end{pmatrix}.$$
  Since $N^2 = \begin{pmatrix}0&0\\0&0\end{pmatrix} = 0$, $N$ is **nilpotent**, which will make the powers follow a very clear arithmetic-geometric pattern.

---

## 4. Step-by-Step Solution

Here, $I$ and $0$ are the $2 \times 2$ matrices:
$$I = \begin{pmatrix}1&0\\0&1\end{pmatrix},\qquad 0 = \begin{pmatrix}0&0\\0&0\end{pmatrix}.$$

### Step 1: Compute $AI$ and $IA$
- For $AI$:
  $$AI = \begin{pmatrix}2&1\\0&2\end{pmatrix}\begin{pmatrix}1&0\\0&1\end{pmatrix} = \begin{pmatrix}2(1)+1(0) & 2(0)+1(1) \\ 0(1)+2(0) & 0(0)+2(1)\end{pmatrix} = \begin{pmatrix}2&1\\0&2\end{pmatrix} = A.$$
- For $IA$:
  $$IA = \begin{pmatrix}1&0\\0&1\end{pmatrix}\begin{pmatrix}2&1\\0&2\end{pmatrix} = \begin{pmatrix}1(2)+0(0) & 1(1)+0(2) \\ 0(2)+1(0) & 0(1)+1(2)\end{pmatrix} = \begin{pmatrix}2&1\\0&2\end{pmatrix} = A.$$
Both confirm that multiplying by $I$ leaves $A$ unchanged.

### Step 2: Compute $A + 0$
Add corresponding entries:
$$A+0 = \begin{pmatrix}2+0 & 1+0 \\ 0+0 & 2+0\end{pmatrix} = \begin{pmatrix}2&1\\0&2\end{pmatrix} = A.$$
Adding the zero matrix leaves $A$ unchanged.

### Step 3: Compute $A^2$
Multiply $A$ by itself:
$$A^2 = \begin{pmatrix}2&1\\0&2\end{pmatrix}\begin{pmatrix}2&1\\0&2\end{pmatrix} = \begin{pmatrix}2(2)+1(0) & 2(1)+1(2) \\ 0(2)+2(0) & 0(1)+2(2)\end{pmatrix} = \begin{pmatrix}4 & 4 \\ 0 & 4\end{pmatrix}.$$

### Step 4: Compute $A^3$
Multiply $A^2$ by $A$:
$$A^3 = A^2 \cdot A = \begin{pmatrix}4&4\\0&4\end{pmatrix}\begin{pmatrix}2&1\\0&2\end{pmatrix} = \begin{pmatrix}4(2)+4(0) & 4(1)+4(2) \\ 0(2)+4(0) & 0(1)+4(2)\end{pmatrix} = \begin{pmatrix}8 & 4+8 \\ 0 & 8\end{pmatrix} = \begin{pmatrix}8 & 12 \\ 0 & 8\end{pmatrix}.$$

---

## 5. Final Answer & Conclusion

- $AI = IA = \begin{pmatrix}2&1\\0&2\end{pmatrix} = A$
- $A + 0 = \begin{pmatrix}2&1\\0&2\end{pmatrix} = A$
- $A^2 = \begin{pmatrix}4&4\\0&4\end{pmatrix}$
- $A^3 = \begin{pmatrix}8&12\\0&8\end{pmatrix}$
- **Roles of $I$ and $0$:**
  - $I$ acts as the multiplicative identity: it preserves any matrix under multiplication from either left or right.
  - $0$ acts as the additive identity: it preserves any matrix under addition.
- **Pattern in Powers ($A^n$):**
  Comparing the powers:
  - $A^1 = \begin{pmatrix}2^1 & 1 \cdot 2^0 \\ 0 & 2^1\end{pmatrix} = \begin{pmatrix}2&1\\0&2\end{pmatrix}$
  - $A^2 = \begin{pmatrix}2^2 & 2 \cdot 2^1 \\ 0 & 2^2\end{pmatrix} = \begin{pmatrix}4&4\\0&4\end{pmatrix}$
  - $A^3 = \begin{pmatrix}2^3 & 3 \cdot 2^2 \\ 0 & 2^3\end{pmatrix} = \begin{pmatrix}8&12\\0&8\end{pmatrix}$
  In general, for any integer $n \ge 1$:
  $$A^n = \begin{pmatrix}2^n & n 2^{n-1} \\ 0 & 2^n\end{pmatrix}.$$

---

## 6. Quick Verification

Using the binomial expansion since $2I$ and $N = \begin{pmatrix}0&1\\0&0\end{pmatrix}$ commute and $N^2 = 0$:
$$A^n = (2I + N)^n = (2I)^n + \binom{n}{1}(2I)^{n-1}N + 0 = 2^n I + n 2^{n-1} N = \begin{pmatrix}2^n & n 2^{n-1} \\ 0 & 2^n\end{pmatrix}.$$
For $n = 3$:
$$\begin{pmatrix}2^3 & 3 \cdot 2^2 \\ 0 & 2^3\end{pmatrix} = \begin{pmatrix}8 & 12 \\ 0 & 8\end{pmatrix}.$$
This matches our computed $A^3$ exactly.

---

## 7. Common Mistakes to Avoid

1. **Squaring entries directly:** Computing $A^2$ as $\begin{pmatrix}2^2 & 1^2 \\ 0^2 & 2^2\end{pmatrix} = \begin{pmatrix}4&1\\0&4\end{pmatrix}$. This is completely wrong; matrix multiplication is not entrywise exponentiation.
2. **Confusing identity matrix with all-ones matrix:** $I$ has ones only along the main diagonal and zeros elsewhere; it is not a matrix full of ones.

---

## 8. How I Would Explain This in Class

> "The identity matrix $I$ and zero matrix $0$ act just like the numbers $1$ and $0$ in standard arithmetic: $AI = IA = A$ and $A + 0 = A$. When calculating powers of $A$, we find $A^2 = \begin{pmatrix}4&4\\0&4\end{pmatrix}$ and $A^3 = \begin{pmatrix}8&12\\0&8\end{pmatrix}$. The diagonal entries double at each step as $2^n$, while the top-right entry grows as $n 2^{n-1}$ because the matrix is a sum of $2I$ and a nilpotent matrix that vanishes when squared."
