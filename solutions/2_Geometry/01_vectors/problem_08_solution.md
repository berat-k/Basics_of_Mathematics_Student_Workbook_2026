# Problem 08: Linear Combination and Checking the Result

## 1. The Original Problem

Check whether $w = (5, 1)$ can be written as

$$
w = au + bv,
$$

where $u = (1, 1)$ and $v = (2, -1)$. If so, find $a, b$, reconstruct $w$ from them, and explain the geometric meaning of the existence of such coefficients.

---

## 2. What Are We Trying to Find?

We need to:
1. Determine whether vector $w$ can be expressed as a linear combination of vectors $u$ and $v$.
2. Formulate the vector equation as a $2 \times 2$ linear system in the scalar unknowns $a$ and $b$.
3. Solve for $a$ and $b$ and verify that a unique solution exists.
4. Reconstruct $w$ using the computed values of $a$ and $b$ to verify the result.
5. Explain the geometric meaning of representing $w$ in the non-orthogonal basis formed by $u$ and $v$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Linear Combination in $\mathbb{R}^2$:**
  The vector equation $w = au + bv$ translates to:

$$
\begin{pmatrix} 5 \\\\ 1 \end{pmatrix} = a \begin{pmatrix} 1 \\\\ 1 \end{pmatrix} + b \begin{pmatrix} 2 \\\\ -1 \end{pmatrix} \iff \begin{pmatrix} 1 & 2 \\\\ 1 & -1 \end{pmatrix} \begin{pmatrix} a \\\\ b \end{pmatrix} = \begin{pmatrix} 5 \\\\ 1 \end{pmatrix}
$$

- **Basis of the Plane:**
  Two non-zero vectors in $\mathbb{R}^2$ form a basis of $\mathbb{R}^2$ if and only if they are not collinear ($\det \neq 0$).
  Here:

$$
\det \begin{pmatrix} 1 & 2 \\\\ 1 & -1 \end{pmatrix} = 1(-1) - 2(1) = -3 \neq 0
$$

  Because the determinant is non-zero, $u$ and $v$ form a basis for $\mathbb{R}^2$. Every vector in $\mathbb{R}^2$, including $w$, can be written **uniquely** as a linear combination of $u$ and $v$.
- **Geometric Interpretation:**
  The scalars $a$ and $b$ serve as coordinates along the non-orthogonal coordinate axes defined by the directions of $u$ and $v$.

---

## 4. Step-by-Step Solution

### Step 1: Set Up the Linear System

Expand the vector equation $au + bv = w$ into coordinate equations:

$$
a(1, 1) + b(2, -1) = (5, 1)
$$

This gives the system of two equations:

$$
\begin{cases}
a + 2b = 5 \\\\
a - b = 1
\end{cases}
$$

### Step 2: Solve the System for $a$ and $b$

1. **Subtract the second equation from the first equation:**

$$
(a + 2b) - (a - b) = 5 - 1
$$

Simplify:

$$
3b = 4 \implies b = \frac{4}{3}
$$

2. **Substitute $b = \frac{4}{3}$ into the second equation:**

$$
a - \frac{4}{3} = 1 \implies a = 1 + \frac{4}{3} = \frac{7}{3}
$$

The coefficients are $a = \frac{7}{3}$ and $b = \frac{4}{3}$.

---

### Step 3: Reconstruct $w$ from $a$ and $b$

Evaluate the linear combination $au + bv$:

$$
a u + b v = \frac{7}{3} (1, 1) + \frac{4}{3} (2, -1)
$$

Multiply the scalars into the vectors:

$$
\left( \frac{7}{3}, \frac{7}{3} \right) + \left( \frac{8}{3}, -\frac{4}{3} \right)
$$

Add componentwise:

$$
\left( \frac{7 + 8}{3}, \frac{7 - 4}{3} \right) = \left( \frac{15}{3}, \frac{3}{3} \right) = (5, 1) = w
$$

The reconstruction matches vector $w = (5, 1)$ exactly.

---

### Step 4: Geometric Meaning of the Existence of $a$ and $b$

1. **Spanning the Entire 2D Plane:**
   Vectors $u = (1, 1)$ and $v = (2, -1)$ point in two distinct directions (their slopes are $1$ and $-0.5$). Since they are not parallel, any movement in $\mathbb{R}^2$ can be broken down into steps along the $u$-direction and steps along the $v$-direction.
2. **Alternative Coordinate System (Basis):**
   The existence and uniqueness of the coefficients $a = 7/3$ and $b = 4/3$ mean that $\{u, v\}$ forms an alternative, oblique (non-perpendicular) coordinate grid for the plane.
3. **Parallelogram Navigation:**
   To reach the point $(5, 1)$ starting from the origin $(0, 0)$, one can travel $7/3$ lengths along vector $u$, and from that point travel $4/3$ lengths along vector $v$. Vector $w$ forms the diagonal of the parallelogram whose sides are $(7/3)u$ and $(4/3)v$.

---

## 5. Final Answer & Conclusion

- **Can $w$ be written as a linear combination?** **Yes**, uniquely.
- **Coefficients:**

$$
a = \frac{7}{3}, \qquad b = \frac{4}{3}
$$

- **Vector Form:**

$$
w = \frac{7}{3} u + \frac{4}{3} v
$$

- **Geometric Meaning:** Because $u$ and $v$ are non-parallel vectors in $\mathbb{R}^2$, they form a basis. The pair $(7/3, 4/3)$ represents the coordinates of $w$ on this oblique coordinate grid.

---

## 6. Quick Verification

Substitute $a = 7/3$ and $b = 4/3$ into both original scalar equations:
1. $a + 2b = \frac{7}{3} + 2\left(\frac{4}{3}\right) = \frac{7 + 8}{3} = \frac{15}{3} = 5$ (Matches 5)
2. $a - b = \frac{7}{3} - \frac{4}{3} = \frac{3}{3} = 1$ (Matches 1)
Both equations are verified.

---

## 7. Common Mistakes to Avoid

1. **Sign Errors with Negative Coordinates:**
   Writing $a - (-b)$ or forgetting the minus sign in $b(2, -1)$, which yields $+b$ instead of $-b$ in the second equation.
2. **Arithmetic Errors in Adding Fractions:**
   Miscalculating $1 + 4/3$ as $5/3$ instead of $7/3$.
3. **Omitting the Geometric Discussion:**
   Finding $a$ and $b$ purely through algebra without explaining that $u$ and $v$ span the plane as an oblique basis.

---

## 8. How I Would Explain This in Class

> "Think of standard $x$ and $y$ coordinates as city streets arranged in a neat perpendicular grid. Here, vectors $u$ and $v$ represent two slanted streets heading in different directions. Because the two slanted streets don't run parallel, you can reach any address in the city simply by walking $7/3$ blocks along street $u$, and then turning to walk $4/3$ blocks along street $v$."

