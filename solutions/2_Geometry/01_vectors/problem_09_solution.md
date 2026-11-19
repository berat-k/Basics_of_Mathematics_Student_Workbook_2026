# Problem 09: Cross Product as a Perpendicular Direction

## 1. The Original Problem

For $u = (1, 2, 0)$ and $v = (0, 1, 3)$ compute $u \times v$. Use dot products to check perpendicularity to both vectors, compute $v \times u$, and compare the results.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the vector cross product $u \times v$ using standard component formulas or formal $3 \times 3$ determinant expansion.
2. Check that the resulting cross product vector is perpendicular to both original vectors $u$ and $v$ using dot products.
3. Compute the cross product in reverse order, $v \times u$.
4. Compare $u \times v$ with $v \times u$ and explain the algebraic property of anticommutativity and its geometric right-hand rule meaning.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Cross Product Definition:**
  For vectors $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$ in $\mathbb{R}^3$, the cross product is given by the formal determinant:

$$
u \times v = \det \begin{pmatrix} i & j & k \\\\ u_1 & u_2 & u_3 \\\\ v_1 & v_2 & v_3 \end{pmatrix} = (u_2 v_3 - u_3 v_2) i - (u_1 v_3 - u_3 v_1) j + (u_1 v_2 - u_2 v_1) k
$$

- **Mutual Perpendicularity:**
  The cross product $u \times v$ is constructed specifically to be orthogonal to both parent vectors:

$$
(u \times v) \cdot u = 0, \qquad (u \times v) \cdot v = 0
$$

- **Anticommutativity:**
  Unlike scalar multiplication or dot products, the cross product is **not commutative**; it is **anticommutative**:

$$
v \times u = -(u \times v)
$$

  Reversing the order swaps two rows in the determinant, multiplying the result by $-1$. Geometrically, by the right-hand rule, reversing the order flips the orientation of the thumb by $180^\circ$.

---

## 4. Step-by-Step Solution

### Step 1: Compute $u \times v$

Set up the formal determinant for $u = (1, 2, 0)$ and $v = (0, 1, 3)$:

$$
u \times v = \det \begin{pmatrix} i & j & k \\\\ 1 & 2 & 0 \\\\ 0 & 1 & 3 \end{pmatrix}
$$

Expand along the first row:

$$
u \times v = i \det \begin{pmatrix} 2 & 0 \\\\ 1 & 3 \end{pmatrix} - j \det \begin{pmatrix} 1 & 0 \\\\ 0 & 3 \end{pmatrix} + k \det \begin{pmatrix} 1 & 2 \\\\ 0 & 1 \end{pmatrix}
$$

Evaluate each $2 \times 2$ determinant:
- $i$-component: $(2)(3) - (0)(1) = 6 - 0 = 6$
- $j$-component: $- [ (1)(3) - (0)(0) ] = - (3 - 0) = -3$
- $k$-component: $(1)(1) - (2)(0) = 1 - 0 = 1$

Therefore:

$$
u \times v = (6, -3, 1)
$$

---

### Step 2: Check Perpendicularity Using Dot Products

1. **Check perpendicularity to $u = (1, 2, 0)$:**

$$
(u \times v) \cdot u = (6)(1) + (-3)(2) + (1)(0) = 6 - 6 + 0 = 0
$$

Since $(u \times v) \cdot u = 0$, $u \times v \perp u$.

2. **Check perpendicularity to $v = (0, 1, 3)$:**

$$
(u \times v) \cdot v = (6)(0) + (-3)(1) + (1)(3) = 0 - 3 + 3 = 0
$$

Since $(u \times v) \cdot v = 0$, $u \times v \perp v$.

The vector $(6, -3, 1)$ is verified to be perpendicular to both vectors.

---

### Step 3: Compute $v \times u$

Set up the formal determinant with the rows swapped:

$$
v \times u = \det \begin{pmatrix} i & j & k \\\\ 0 & 1 & 3 \\\\ 1 & 2 & 0 \end{pmatrix}
$$

Expand along the first row:

$$
v \times u = i \det \begin{pmatrix} 1 & 3 \\\\ 2 & 0 \end{pmatrix} - j \det \begin{pmatrix} 0 & 3 \\\\ 1 & 0 \end{pmatrix} + k \det \begin{pmatrix} 0 & 1 \\\\ 1 & 2 \end{pmatrix}
$$

Evaluate each $2 \times 2$ determinant:
- $i$-component: $(1)(0) - (3)(2) = 0 - 6 = -6$
- $j$-component: $- [ (0)(0) - (3)(1) ] = - (0 - 3) = +3$
- $k$-component: $(0)(2) - (1)(1) = 0 - 1 = -1$

Therefore:

$$
v \times u = (-6, 3, -1)
$$

---

### Step 4: Compare the Results

Comparing the two cross product vectors:

$$
u \times v = (6, -3, 1)
$$

$$
v \times u = (-6, 3, -1)
$$

Notice that:

$$
v \times u = -(6, -3, 1) = -(u \times v)
$$

- **Algebraic Meaning:** The cross product operation is **anticommutative**. Swapping the input vectors flips the sign of every component.
- **Geometric Meaning:** Both $u \times v$ and $v \times u$ lie along the exact same normal line perpendicular to the plane formed by $u$ and $v$, and they have the exact same length ($\sqrt{6^2 + (-3)^2 + 1^2} = \sqrt{46}$). However, according to the **right-hand rule**, curling fingers from $u$ to $v$ points the thumb in one direction, while curling from $v$ to $u$ points the thumb in the exact opposite direction.

---

## 5. Final Answer & Conclusion

- **Cross Product $u \times v$:**

$$
u \times v = (6, -3, 1)
$$

- **Perpendicularity Verification:**
  $(u \times v) \cdot u = 0$ and $(u \times v) \cdot v = 0$.
- **Reversed Cross Product $v \times u$:**

$$
v \times u = (-6, 3, -1)
$$

- **Comparison:** $v \times u = -(u \times v)$. The cross product is anticommutative; reversing the factor order preserves the line of action and length but reverses the pointing orientation by $180^\circ$.

---

## 6. Quick Verification

Calculate the magnitude of both vectors:

$$
\|u \times v\| = \sqrt{6^2 + (-3)^2 + 1^2} = \sqrt{36 + 9 + 1} = \sqrt{46}
$$

$$
\|v \times u\| = \sqrt{(-6)^2 + 3^2 + (-1)^2} = \sqrt{36 + 9 + 1} = \sqrt{46}
$$

Now calculate the area of the spanned parallelogram using $\|u\| \|v\| \sin \theta$:
- $\|u\| = \sqrt{1^2 + 2^2 + 0^2} = \sqrt{5}$
- $\|v\| = \sqrt{0^2 + 1^2 + 3^2} = \sqrt{10}$
- $u \cdot v = 1(0) + 2(1) + 0(3) = 2$
- By Lagrange's identity: $\|u \times v\|^2 = \|u\|^2 \|v\|^2 - (u \cdot v)^2 = (5)(10) - (2)^2 = 50 - 4 = 46$.
- Thus, $\|u \times v\| = \sqrt{46}$.
Everything matches with complete mathematical harmony.

---

## 7. Common Mistakes to Avoid

1. **Forgetting the Minus Sign on the $j$-Component:**
   In the determinant expansion, the second cofactor has a negative sign: $-j(u_1 v_3 - u_3 v_1)$. A common error is writing $+j(3) = +3$ instead of $-3$.
2. **Assuming $u \times v = v \times u$:**
   Assuming the operation is commutative like the dot product. Swapping inputs produces the negative vector.
3. **Confusing Cross Product with Dot Product:**
   The cross product is defined only in three dimensions (and 7D) and produces a **vector**, while the dot product produces a scalar number.

---

## 8. How I Would Explain This in Class

> "Imagine two sticks lying flat on a table. The cross product creates a flagpole sticking straight up out of the table, perfectly perpendicular to both sticks. But which way does the flagpole point—up into the sky, or down through the floor? The right-hand rule tells you: sweeping from $u$ to $v$ points your thumb straight up, but sweeping in reverse from $v$ to $u$ points your thumb down, which is why $v \times u = -(u \times v)$."

