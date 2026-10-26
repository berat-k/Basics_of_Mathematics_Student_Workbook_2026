# Problem 11: When Do Matrices Commute?

## 1. The Original Problem

Given
$$A=\begin{pmatrix}1&1\\0&1\end{pmatrix},\qquad B=\begin{pmatrix}a&b\\c&d\end{pmatrix}.$$
Find the conditions on $a,b,c,d$ under which $AB=BA$. Describe the general form of all such matrices $B$.

---

## 2. What Are We Trying to Find?

Although matrix multiplication is generally noncommutative, some specific pairs of matrices do commute. We want to find all conditions on the parameters $a, b, c, d$ that make $AB = BA$, and characterize the geometric and algebraic form of all matrices $B$ that commute with $A$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Equality of Matrices:**
  Two matrices are equal ($AB = BA$) if and only if each of their four corresponding entries are equal. This sets up a linear system of equations in the unknowns $a, b, c, d$.
- **Commutant (Centralizer):**
  The set of matrices that commute with a given matrix $A$ is called the *centralizer* of $A$. Any matrix of the form $c_0 I + c_1 A$ automatically commutes with $A$ because $A$ commutes with itself and with the identity matrix $I$. We will see if there are any other matrices or if all commuting matrices come from this family.

---

## 4. Step-by-Step Solution

### Step 1: Compute $AB$
Multiply $A$ by $B$:
$$AB = \begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}a&b\\c&d\end{pmatrix} = \begin{pmatrix}1\cdot a + 1\cdot c & 1\cdot b + 1\cdot d \\ 0\cdot a + 1\cdot c & 0\cdot b + 1\cdot d\end{pmatrix} = \begin{pmatrix}a+c & b+d \\ c & d\end{pmatrix}.$$

### Step 2: Compute $BA$
Multiply $B$ by $A$:
$$BA = \begin{pmatrix}a&b\\c&d\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix} = \begin{pmatrix}a\cdot 1 + b\cdot 0 & a\cdot 1 + b\cdot 1 \\ c\cdot 1 + d\cdot 0 & c\cdot 1 + d\cdot 1\end{pmatrix} = \begin{pmatrix}a & a+b \\ c & c+d\end{pmatrix}.$$

### Step 3: Set $AB = BA$ and Equate Entries
For the two matrices to be equal, each corresponding entry must match:
1. **Entry (1, 1):**
   $$a + c = a \implies c = 0.$$
2. **Entry (2, 1):**
   $$c = c \implies 0 = 0 \quad (\text{holds automatically when } c = 0).$$
3. **Entry (2, 2):**
   $$d = c + d \implies c = 0 \quad (\text{consistent with Entry (1, 1)}).$$
4. **Entry (1, 2):**
   $$b + d = a + b \implies d = a.$$

### Step 4: Interpret the Free Parameters
- $c$ must be $0$.
- $d$ must equal $a$.
- There are no restrictions on $a$ and $b$; they can be any real numbers ($a, b \in \mathbb{R}$).

---

## 5. Final Answer & Conclusion

- **Conditions on the entries:**
  $$c = 0 \quad \text{and} \quad d = a$$
  with $a$ and $b$ being completely arbitrary real numbers.
- **General form of matrix $B$:**
  $$B = \begin{pmatrix}a & b \\ 0 & a\end{pmatrix}.$$
- **Structural meaning:**
  All commuting matrices are upper triangular with equal diagonal entries. We can write $B$ as:
  $$B = a \begin{pmatrix}1&0\\0&1\end{pmatrix} + b \begin{pmatrix}0&1\\0&0\end{pmatrix} = a I + b(A - I) = (a - b)I + bA.$$
  Thus, every matrix that commutes with $A$ is an affine combination (a polynomial) of $A$ and the identity matrix $I$.

---

## 6. Quick Verification

Substitute $B = \begin{pmatrix}a & b \\ 0 & a\end{pmatrix}$ back into both products:
$$AB = \begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}a&b\\0&a\end{pmatrix} = \begin{pmatrix}a & a+b \\ 0 & a\end{pmatrix},$$
$$BA = \begin{pmatrix}a&b\\0&a\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix} = \begin{pmatrix}a & a+b \\ 0 & a\end{pmatrix}.$$
Since $AB - BA = \begin{pmatrix}0&0\\0&0\end{pmatrix}$, $AB = BA$ holds for all $a, b \in \mathbb{R}$.

---

## 7. Common Mistakes to Avoid

1. **Assuming $B$ must be a scalar multiple of $A$:** While $B = kA$ works, it is not the *only* solution; $b$ can vary independently of $a$.
2. **Forgetting that $b$ is free:** Because $b$ cancels out in $b + d = a + b \implies d = a$, students sometimes mistakenly think $b$ must be $0$. In reality, $b$ is completely unconstrained.

---

## 8. How I Would Explain This in Class

> "To find when $A$ and $B$ commute, we calculate both $AB$ and $BA$ in terms of $a, b, c, d$ and set their entries equal. The equations immediately force $c = 0$ and $d = a$, while $b$ and $a$ remain free parameters. This means all matrices that commute with $A$ have the form $\begin{pmatrix}a & b \\ 0 & a\end{pmatrix}$, which represents any linear combination of the identity matrix $I$ and the matrix $A$."
