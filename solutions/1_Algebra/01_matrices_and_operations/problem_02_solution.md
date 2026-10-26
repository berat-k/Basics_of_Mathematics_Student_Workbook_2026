

---

### **Given Matrices:**

$$A = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix}, \qquad B = \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix}$$

---

### **1. Compute $A + B$**

Matrix addition is performed entry by entry:

$$A + B = \begin{pmatrix} 1 + 4 & 2 + (-2) \\ -1 + 0 & 3 + 5 \end{pmatrix} = \begin{pmatrix} 5 & 0 \\ -1 & 8 \end{pmatrix}$$

---

### **2. Compute $A - B$**

Matrix subtraction is performed entry by entry:

$$A - B = \begin{pmatrix} 1 - 4 & 2 - (-2) \\ -1 - 0 & 3 - 5 \end{pmatrix} = \begin{pmatrix} -3 & 4 \\ -1 & -2 \end{pmatrix}$$

---

### **3. Compute $3A - 2B$**

First, compute the scalar multiplications:

$$3A = 3 \cdot \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} = \begin{pmatrix} 3 & 6 \\ -3 & 9 \end{pmatrix}$$

$$2B = 2 \cdot \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix} = \begin{pmatrix} 8 & -4 \\ 0 & 10 \end{pmatrix}$$

Now, subtract the two resulting matrices:

$$3A - 2B = \begin{pmatrix} 3 - 8 & 6 - (-4) \\ -3 - 0 & 9 - 10 \end{pmatrix} = \begin{pmatrix} -5 & 10 \\ -3 & -1 \end{pmatrix}$$

---

### **4. Why Matrix Addition Is Only Possible for Matrices of the Same Size**

Matrix addition is defined as an **entry-by-entry** operation:


$$(A + B)_{ij} = a_{ij} + b_{ij}$$

For the addition to be defined, each entry in matrix $A$ must correspond to an entry in matrix $B$ at the exact same row and column index $(i, j)$. If the matrices have different dimensions (different numbers of rows or columns), at least one entry will not have a matching partner to pair with, making the operation mathematically undefined.
