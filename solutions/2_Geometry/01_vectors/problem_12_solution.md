# Problem 12: A Normal Vector to a Plane

## 1. The Original Problem

Given $A = (1, 0, 2)$, $B = (2, 1, 0)$, and $C = (0, 3, 1)$. Construct two vectors lying in the plane, find a vector perpendicular to both, and check the perpendicularity using dot products.

---

## 2. What Are We Trying to Find?

We need to:
1. Construct two non-parallel displacement vectors lying entirely within the plane containing points $A, B,$ and $C$.
2. Calculate a normal vector $n$ that is simultaneously perpendicular to both spanning vectors using the vector cross product.
3. Check the perpendicularity of $n$ to each spanning vector using scalar dot products ($n \cdot u = 0$ and $n \cdot v = 0$).
4. Explain how this normal vector characterizes the geometric orientation of the plane in 3D space.

---

## 3. Before Calculating: What Idea Do We Need?

- **Spanning Vectors in a Plane:**
  Three non-collinear points $A, B, C$ uniquely determine a plane in $\mathbb{R}^3$. Two displacement vectors sharing an initial point:

$$
u = \overrightarrow{AB} = B - A, \qquad v = \overrightarrow{AC} = C - A
$$

  lie completely within that plane and span its directions.
- **Normal Vector via Cross Product:**
  The cross product of any two non-parallel vectors in a plane produces a vector $n = u \times v$ perpendicular to both vectors.
- **The Plane Orthogonality Theorem:**
  If a vector $n$ is perpendicular to two linearly independent vectors in a plane, it is perpendicular to **every** vector lying in that plane, making it a true **normal vector** to the plane.

---

## 4. Step-by-Step Solution

### Step 1: Construct Two Vectors Lying in the Plane

Using point $A(1, 0, 2)$ as the base vertex:

1. **Vector $\overrightarrow{AB}$:**

$$
u = \overrightarrow{AB} = B - A = (2 - 1, 1 - 0, 0 - 2) = (1, 1, -2)
$$

2. **Vector $\overrightarrow{AC}$:**

$$
v = \overrightarrow{AC} = C - A = (0 - 1, 3 - 0, 1 - 2) = (-1, 3, -1)
$$

Both vectors $u$ and $v$ lie entirely in the plane determined by $A, B,$ and $C$.

---

### Step 2: Compute a Vector Perpendicular to Both ($n = u \times v$)

Compute the cross product $n = u \times v$:

$$
n = \det \begin{pmatrix} i & j & k \\\\ 1 & 1 & -2 \\\\ -1 & 3 & -1 \end{pmatrix}
$$

Expand along the first row:

$$
n = i \det \begin{pmatrix} 1 & -2 \\\\ 3 & -1 \end{pmatrix} - j \det \begin{pmatrix} 1 & -2 \\\\ -1 & -1 \end{pmatrix} + k \det \begin{pmatrix} 1 & 1 \\\\ -1 & 3 \end{pmatrix}
$$

Evaluate each component:
- $i$-component: $(1)(-1) - (-2)(3) = -1 - (-6) = -1 + 6 = 5$
- $j$-component: $- [ (1)(-1) - (-2)(-1) ] = - [ -1 - 2 ] = - (-3) = 3$
- $k$-component: $(1)(3) - (1)(-1) = 3 - (-1) = 3 + 1 = 4$

Thus, a perpendicular vector is:

$$
n = (5, 3, 4)
$$

---

### Step 3: Check Perpendicularity Using Dot Products

1. **Check perpendicularity to $u = (1, 1, -2)$:**

$$
n \cdot u = (5)(1) + (3)(1) + (4)(-2) = 5 + 3 - 8 = 0
$$

Since $n \cdot u = 0$, $n$ is perpendicular to $u$.

2. **Check perpendicularity to $v = (-1, 3, -1)$:**

$$
n \cdot v = (5)(-1) + (3)(3) + (4)(-1) = -5 + 9 - 4 = 0
$$

Since $n \cdot v = 0$, $n$ is perpendicular to $v$.

Both dot products are zero, confirming that $n = (5, 3, 4)$ is perpendicular to both spanning vectors.

---

### Step 4: Geometric Meaning of the Normal Vector

Because $n = (5, 3, 4)$ is perpendicular to two non-parallel vectors in the plane, it stands at a right angle to every possible line lying within the plane.
- The orientation of the plane is uniquely determined by this normal vector.
- The Cartesian equation of the plane can be written directly using $n = (a, b, c) = (5, 3, 4)$ and passing through $A(1, 0, 2)$:

$$
5(x - 1) + 3(y - 0) + 4(z - 2) = 0 \iff 5x + 3y + 4z = 13
$$

---

## 5. Final Answer & Conclusion

- **Two Vectors in the Plane:**

$$
\overrightarrow{AB} = (1, 1, -2), \qquad \overrightarrow{AC} = (-1, 3, -1)
$$

- **Normal Vector:**

$$
n = (5, 3, 4)
$$

(Any non-zero scalar multiple $k(5, 3, 4)$ with $k \neq 0$ is also a valid normal vector.)
- **Verification:** $n \cdot \overrightarrow{AB} = 0$ and $n \cdot \overrightarrow{AC} = 0$.
- **Conclusion:** The cross product provides a direct algebraic bridge from three points to the normal vector governing the orientation of their plane.

---

## 6. Quick Verification

Check the third vector in the plane, $\overrightarrow{BC} = C - B$:

$$
\overrightarrow{BC} = (0 - 2, 3 - 1, 1 - 0) = (-2, 2, 1)
$$

Compute its dot product with $n$:

$$
n \cdot \overrightarrow{BC} = (5)(-2) + (3)(2) + (4)(1) = -10 + 6 + 4 = 0
$$

Notice that $n \cdot \overrightarrow{BC} = 0$ automatically!
Also verify that all three points satisfy the plane equation $5x + 3y + 4z = 13$:
- $A(1, 0, 2): 5(1) + 3(0) + 4(2) = 5 + 8 = 13$
- $B(2, 1, 0): 5(2) + 3(1) + 4(0) = 10 + 3 = 13$
- $C(0, 3, 1): 5(0) + 3(3) + 4(1) = 9 + 4 = 13$
All three points lie squarely on the plane.

---

## 7. Common Mistakes to Avoid

1. **Double Negative Errors in Determinants:**
   In the $i$-component, $-1 - (-6) = +5$. A frequent error is computing it as $-7$.
2. **Forgetting the Negative Sign on the $j$-Component:**
   Computing the $j$-cofactor without the leading negative sign, yielding $-3$ instead of $+3$.
3. **Checking Only One Vector:**
   Checking $n \cdot u = 0$ and assuming $n \cdot v = 0$ must automatically hold. An algebraic error could easily produce a vector perpendicular to one vector but not the other.

---

## 8. How I Would Explain This in Class

> "If you balance a flat piece of cardboard on three fingertips $A, B,$ and $C$, two vectors connecting those fingertips trace out directions along the flat surface. Taking their cross product erects a rigid flagpole $(5, 3, 4)$ standing straight up from the cardboard. Because the flagpole is perpendicular to two different directions across the cardboard, it is guaranteed to stand at a perfect 90-degree angle to the entire flat surface."

