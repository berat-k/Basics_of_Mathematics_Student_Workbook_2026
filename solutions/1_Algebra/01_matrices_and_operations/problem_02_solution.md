# Exercise 2: Addition and Scalar Multiplication

## 1. Problem Statement

Given the matrices:
$$A = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix}, \qquad B = \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix}$$

1. Compute $A + B$.
2. Compute $A - B$.
3. Compute $3A - 2B$.
4. Explain why matrix addition is possible only for matrices of the same size.

---

## 2. Theoretical Background and Concepts

* **Matrix Dimensions:** A matrix with $m$ rows and $n$ columns has size $m \times n$. Both matrices $A$ and $B$ are square matrices of size $2 \times 2$.
* **Matrix Addition and Subtraction:** For two matrices $A = (a_{ij})$ and $B = (b_{ij})$ of the same size $m \times n$, addition and subtraction are performed entry-by-entry:
  $$(A + B)_{ij} = a_{ij} + b_{ij}, \qquad (A - B)_{ij} = a_{ij} - b_{ij}$$
* **Scalar Multiplication:** For any real scalar $c \in \mathbb{R}$ and matrix $A = (a_{ij})$, the scalar multiple $cA$ is obtained by multiplying every element of $A$ by $c$:
  $$(cA)_{ij} = c \cdot a_{ij}$$
* **Dimension Compatibility:** Matrix addition and subtraction are component-wise operations requiring an exact one-to-one correspondence between the entries $(i, j)$ of both matrices.

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computing $A + B$

We add the corresponding entries of $A$ and $B$:

$$A + B = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} + \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix} = \begin{pmatrix} 1 + 4 & 2 + (-2) \\ -1 + 0 & 3 + 5 \end{pmatrix}$$

* Entry $(1, 1)$: $1 + 4 = 5$
* Entry $(1, 2)$: $2 + (-2) = 0$
* Entry $(2, 1)$: $-1 + 0 = -1$
* Entry $(2, 2)$: $3 + 5 = 8$

$$\mathbf{A + B = \begin{pmatrix} 5 & 0 \\ -1 & 8 \end{pmatrix}}$$

---

### 3.2. Computing $A - B$

We subtract the corresponding entries of $B$ from $A$:

$$A - B = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} - \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix} = \begin{pmatrix} 1 - 4 & 2 - (-2) \\ -1 - 0 & 3 - 5 \end{pmatrix}$$

* Entry $(1, 1)$: $1 - 4 = -3$
* Entry $(1, 2)$: $2 - (-2) = 2 + 2 = 4$
* Entry $(2, 1)$: $-1 - 0 = -1$
* Entry $(2, 2)$: $3 - 5 = -2$

$$\mathbf{A - B = \begin{pmatrix} -3 & 4 \\ -1 & -2 \end{pmatrix}}$$

---

### 3.3. Computing $3A - 2B$

**Step 1: Compute $3A$ (scalar multiplication of $A$ by $3$):**

$$3A = 3 \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} = \begin{pmatrix} 3 \cdot 1 & 3 \cdot 2 \\ 3 \cdot (-1) & 3 \cdot 3 \end{pmatrix} = \begin{pmatrix} 3 & 6 \\ -3 & 9 \end{pmatrix}$$

**Step 2: Compute $2B$ (scalar multiplication of $B$ by $2$):**

$$2B = 2 \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix} = \begin{pmatrix} 2 \cdot 4 & 2 \cdot (-2) \\ 2 \cdot 0 & 2 \cdot 5 \end{pmatrix} = \begin{pmatrix} 8 & -4 \\ 0 & 10 \end{pmatrix}$$

**Step 3: Subtract $2B$ from $3A$:**

$$3A - 2B = \begin{pmatrix} 3 & 6 \\ -3 & 9 \end{pmatrix} - \begin{pmatrix} 8 & -4 \\ 0 & 10 \end{pmatrix} = \begin{pmatrix} 3 - 8 & 6 - (-4) \\ -3 - 0 & 9 - 10 \end{pmatrix}$$

* Entry $(1, 1)$: $3 - 8 = -5$
* Entry $(1, 2)$: $6 - (-4) = 6 + 4 = 10$
* Entry $(2, 1)$: $-3 - 0 = -3$
* Entry $(2, 2)$: $9 - 10 = -1$

$$\mathbf{3A - 2B = \begin{pmatrix} -5 & 10 \\ -3 & -1 \end{pmatrix}}$$

---

### 3.4. Why Matrix Addition Requires Identical Dimensions

Matrix addition is defined algebraically by adding corresponding entries:
$$(A + B)_{ij} = a_{ij} + b_{ij}$$
For this operation to be meaningful:
1. Every position $(i, j)$ in matrix $A$ must correspond to an identical position $(i, j)$ in matrix $B$.
2. If the two matrices have different numbers of rows or columns ($m_A \neq m_B$ or $n_A \neq n_B$), there will be entries in one matrix that have no corresponding counterpart in the other matrix to pair with.

Because there is no natural or well-defined value to pair with missing entries, matrix addition (and subtraction) is strictly defined **only for matrices of the exact same size ($m \times n$)**.

---

## 4. Verification and Consistency Checks

1. **Verification of $A + B$:**
   $$\begin{pmatrix} 5 & 0 \\ -1 & 8 \end{pmatrix} - B = \begin{pmatrix} 5 - 4 & 0 - (-2) \\ -1 - 0 & 8 - 5 \end{pmatrix} = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} = A \quad \checkmark$$

2. **Verification of $A - B$:**
   $$\begin{pmatrix} -3 & 4 \\ -1 & -2 \end{pmatrix} + B = \begin{pmatrix} -3 + 4 & 4 + (-2) \\ -1 + 0 & -2 + 5 \end{pmatrix} = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} = A \quad \checkmark$$

3. **Verification of $3A - 2B$:**
   $$\begin{pmatrix} -5 & 10 \\ -3 & -1 \end{pmatrix} + 2B = \begin{pmatrix} -5 + 8 & 10 + (-4) \\ -3 + 0 & -1 + 10 \end{pmatrix} = \begin{pmatrix} 3 & 6 \\ -3 & 9 \end{pmatrix} = 3A \quad \checkmark$$

4. **Consistency via Linear Combination:**
   $$(A + B) + 2(A - B) - B = 3A - 2B$$
   $$\begin{pmatrix} 5 & 0 \\ -1 & 8 \end{pmatrix} + \begin{pmatrix} -6 & 8 \\ -2 & -4 \end{pmatrix} - \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix} = \begin{pmatrix} -5 & 10 \\ -3 & -1 \end{pmatrix} \quad \checkmark$$