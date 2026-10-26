# Problem 13: A Recurrence Written in Matrix Form

## 1. The Original Problem

Let

$$
F = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix}
$$

Compute $F^2$, $F^3$, $F^4$, and $F^5$. Compare the numbers obtained with the sequence

$$
0, 1, 1, 2, 3, 5, 8, \ldots
$$

and describe the relationship you observe. Then compute

$$
F \begin{pmatrix} a \\ b \end{pmatrix}
$$

and explain how this multiplication performs one recurrence step: it creates the sum of two consecutive terms and keeps one of them for the next step.

---

## 2. What Are We Trying to Find?

We want to:
1. Compute the powers $F^2, F^3, F^4, F^5$.
2. Identify the connection between the entries in these matrix powers and the famous Fibonacci sequence ($0, 1, 1, 2, 3, 5, 8, \dots$).
3. Multiply $F$ by an arbitrary 2-vector $\begin{pmatrix} a \\ b \end{pmatrix}$ to explain the algebraic mechanism by which matrix multiplication executes a recurrence step.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Fibonacci Sequence ($f_n$):**
  Defined by the starting values $f_0 = 0, f_1 = 1$, and the recurrence relation:
  $$f_{n+1} = f_n + f_{n-1} \quad \text{for } n \ge 1.$$
  The first few terms are:
  $$f_0=0,\ f_1=1,\ f_2=1,\ f_3=2,\ f_4=3,\ f_5=5,\ f_6=8,\ f_7=13,\ \dots$$
- **Matrix State Machine for Recurrences:**
  A two-term linear recurrence can be packaged into a vector $\begin{pmatrix}\text{current}\\\text{previous}\end{pmatrix}$. Multiplying by a companion matrix creates the next term and shifts the state forward.

---

## 4. Step-by-Step Solution

### Step 1: Compute the Successive Powers of $F$
Given $F = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix}$:

1. **Compute $F^2$:**

$$
F^2 = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 1(1)+1(1) & 1(1)+1(0) \\ 1(1)+0(1) & 1(1)+0(0) \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}
$$

2. **Compute $F^3$:**

$$
F^3 = F^2 \cdot F = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 2(1)+1(1) & 2(1)+1(0) \\ 1(1)+1(1) & 1(1)+0(0) \end{pmatrix} = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix}
$$

3. **Compute $F^4$:**

$$
F^4 = F^3 \cdot F = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 3(1)+2(1) & 3(1)+2(0) \\ 2(1)+1(1) & 2(1)+0(0) \end{pmatrix} = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix}
$$

4. **Compute $F^5$:**

$$
F^5 = F^4 \cdot F = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 5(1)+3(1) & 5(1)+3(0) \\ 3(1)+2(1) & 3(1)+0(0) \end{pmatrix} = \begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix}
$$

### Step 2: Compare with the Fibonacci Sequence
Let us compare each matrix power with the Fibonacci numbers $f_0=0, f_1=1, f_2=1, f_3=2, f_4=3, f_5=5, f_6=8$:
- $F^1 = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} f_2 & f_1 \\ f_1 & f_0 \end{pmatrix}$
- $F^2 = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} = \begin{pmatrix} f_3 & f_2 \\ f_2 & f_1 \end{pmatrix}$
- $F^3 = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix} = \begin{pmatrix} f_4 & f_3 \\ f_3 & f_2 \end{pmatrix}$
- $F^4 = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix} = \begin{pmatrix} f_5 & f_4 \\ f_4 & f_3 \end{pmatrix}$
- $F^5 = \begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix} = \begin{pmatrix} f_6 & f_5 \\ f_5 & f_4 \end{pmatrix}$

**General Relationship Observed:**
For every positive integer $n \ge 1$:

$$
F^n = \begin{pmatrix} f_{n+1} & f_n \\ f_n & f_{n-1} \end{pmatrix}
$$

### Step 3: Compute $F \begin{pmatrix} a \\ b \end{pmatrix}$ and Explain the Mechanism
Multiply matrix $F$ by the vector $\begin{pmatrix} a \\ b \end{pmatrix}$:

$$
F \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} 1\cdot a + 1\cdot b \\ 1\cdot a + 0\cdot b \end{pmatrix} = \begin{pmatrix} a+b \\ a \end{pmatrix}
$$

**How This Performs One Recurrence Step:**
1. **Generating the new term:** The top row $(1, 1)$ adds the two consecutive values $a$ and $b$ to form $a + b$. This is precisely the rule that generates the next Fibonacci number: $f_{n+1} = f_n + f_{n-1}$.
2. **Preserving the state:** The bottom row $(1, 0)$ selects only $a$ (the former top term), discarding $b$. This stores $a$ as the "previous term" for the next iteration.
3. Therefore, multiplying by $F$ updates the state vector:

$$
\begin{pmatrix} f_n \\ f_{n-1} \end{pmatrix} \xrightarrow{\times F} \begin{pmatrix} f_{n+1} \\ f_n \end{pmatrix}
$$

4. Multiplying $n$ times by $F$ allows one to compute the $n$-th Fibonacci number in logarithmic time via matrix exponentiation ($F^n$).

---

## 5. Final Answer & Conclusion

- The powers are:

$$
F^2 = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}, \quad F^3 = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix}, \quad F^4 = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix}, \quad F^5 = \begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix}
$$

- Every entry of $F^n$ is a Fibonacci number: the entries are $\begin{pmatrix} f_{n+1} & f_n \\ f_n & f_{n-1} \end{pmatrix}$.
- The product $F\begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} a+b \\ a \end{pmatrix}$ models the recurrence step: the top coordinate generates the sum of the last two terms, and the bottom coordinate stores the previous term.

---

## 6. Quick Verification

Start with the base vector $\begin{pmatrix} f_1 \\ f_0 \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$ and multiply by $F^5$:

$$
F^5 \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 8(1)+5(0) \\ 5(1)+3(0) \end{pmatrix} = \begin{pmatrix} 8 \\ 5 \end{pmatrix} = \begin{pmatrix} f_6 \\ f_5 \end{pmatrix}
$$

Since $f_5 = 5$ and $f_6 = 8$, the formula is verified.
Additionally, using determinants:

$$
\det(F) = 1(0) - 1(1) = -1 \implies \det(F^n) = (\det F)^n = (-1)^n
$$

From our formula, $\det(F^n) = f_{n+1}f_{n-1} - f_n^2 = (-1)^n$, which is Cassini's famous identity.

---

## 7. Common Mistakes to Avoid

1. **Off-by-one indexing:** Forgetting that $f_0 = 0$, so $F^1$ contains $f_2, f_1, f_1, f_0$, not starting from $f_1$ at the top-left.
2. **Thinking matrix powers can only be solved term-by-term:** Matrix exponentiation $F^n$ can be computed via repeated squaring in $O(\log n)$ operations, which is much faster than the linear recurrence.

---

## 8. How I Would Explain This in Class

> "When we calculate powers of $F$, every single entry turns out to be a Fibonacci number: $F^n = \begin{pmatrix}f_{n+1} & f_n \\ f_n & f_{n-1}\end{pmatrix}$. This happens because multiplying $F$ by any vector $\begin{pmatrix}a\\b\end{pmatrix}$ produces $\begin{pmatrix}a+b\\a\end{pmatrix}$, which literally computes the next Fibonacci number in the top entry while saving $a$ in the bottom entry for the next step. Thus, matrix multiplication turns a recursive sequence into standard matrix algebra."
