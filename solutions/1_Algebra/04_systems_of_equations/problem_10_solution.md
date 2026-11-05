# Problem 10: A Polynomial Through Three Points

## 1. The Original Problem

Find a polynomial $p(x) = ax^2 + bx + c$ whose graph passes through $(0, 1)$, $(1, 3)$, and $(2, 9)$. Reduce the problem to a system of equations and check the result by substituting all three points.

---

## 2. What Are We Trying to Find?

We need to:
1. Substitute each of the three given coordinate pairs into the quadratic polynomial $p(x) = ax^2 + bx + c$ to generate three linear equations in the unknown coefficients $a, b,$ and $c$.
2. Write the resulting linear system in matrix form.
3. Solve the system systematically using Gaussian elimination (or systematic substitution).
4. State the explicit equation of the interpolating polynomial $p(x)$.
5. Rigorously check the polynomial by evaluating it at $x = 0, x = 1,$ and $x = 2$ to confirm it reproduces the required $y$-values.

---

## 3. Before Calculating: What Idea Do We Need?

- **Polynomial Interpolation as a Linear System:**
  Even though the polynomial $p(x) = ax^2 + bx + c$ is a nonlinear (quadratic) function of the variable $x$, it depends **linearly** on the unknown coefficients $a, b,$ and $c$.
  For each known data point $(x_k, y_k)$, the condition $p(x_k) = y_k$ produces a linear equation:

$$
a x_k^2 + b x_k + c = y_k
$$

- **The Vandermonde Matrix:**
  For $n$ distinct points $x_0, x_1, \dots, x_{n-1}$, the coefficient matrix of powers of $x_k$ is known as a Vandermonde matrix. Because all three $x$-coordinates ($0, 1, 2$) are distinct, the Vandermonde matrix is non-singular, guaranteeing that a unique polynomial of degree at most $2$ exists.

---

## 4. Step-by-Step Solution

### Step 1: Set Up the Equations from the Points

Substitute each given point $(x, y)$ into $p(x) = ax^2 + bx + c$:

1. **Point $(0, 1)$:**

$$
p(0) = a(0)^2 + b(0) + c = 1 \implies c = 1
$$

2. **Point $(1, 3)$:**

$$
p(1) = a(1)^2 + b(1) + c = 3 \implies a + b + c = 3
$$

3. **Point $(2, 9)$:**

$$
p(2) = a(2)^2 + b(2) + c = 9 \implies 4a + 2b + c = 9
$$

### Step 2: Form the Augmented Matrix

In terms of the unknown coefficient vector $(a, b, c)^T$, the augmented matrix is:

$$
\left[\begin{array}{ccc|c}
0 & 0 & 1 & 1 \\\\
1 & 1 & 1 & 3 \\\\
4 & 2 & 1 & 9
\end{array}\right]
$$

### Step 3: Solve the System

Rearrange rows so that the first column contains non-zero entries for elimination:

$$
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 3 \\\\
4 & 2 & 1 & 9 \\\\
0 & 0 & 1 & 1
\end{array}\right]
$$

1. **Eliminate entry $(2, 1)$ using $R_2 \leftarrow R_2 - 4R_1$:**
   - First column: $4 - 4(1) = 0$
   - Second column: $2 - 4(1) = -2$
   - Third column: $1 - 4(1) = -3$
   - Constant term: $9 - 4(3) = 9 - 12 = -3$

The matrix becomes:

$$
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 3 \\\\
0 & -2 & -3 & -3 \\\\
0 & 0 & 1 & 1
\end{array}\right]
$$

2. **Perform Back-Substitution:**
   - From Row 3:

$$
c = 1
$$

   - From Row 2:

$$
-2b - 3c = -3
$$

   Substitute $c = 1$:

$$
-2b - 3(1) = -3 \implies -2b - 3 = -3 \implies -2b = 0 \implies b = 0
$$

   - From Row 1:

$$
a + b + c = 3
$$

   Substitute $b = 0$ and $c = 1$:

$$
a + 0 + 1 = 3 \implies a = 2
$$

---

## 5. Final Answer & Conclusion

The coefficients are:

$$
a = 2, \quad b = 0, \quad c = 1
$$

The unique quadratic polynomial passing through the three points is:

$$
p(x) = 2x^2 + 1
$$

---

## 6. Quick Verification

Substitute the three points back into our calculated polynomial $p(x) = 2x^2 + 1$:

1. **For $x = 0$:**

$$
p(0) = 2(0)^2 + 1 = 0 + 1 = 1
$$

Matches the point $(0, 1)$. Correct.

2. **For $x = 1$:**

$$
p(1) = 2(1)^2 + 1 = 2(1) + 1 = 3
$$

Matches the point $(1, 3)$. Correct.

3. **For $x = 2$:**

$$
p(2) = 2(2)^2 + 1 = 2(4) + 1 = 8 + 1 = 9
$$

Matches the point $(2, 9)$. Correct.

All three points lie exactly on the graph of $p(x) = 2x^2 + 1$.

---

## 7. Common Mistakes to Avoid

1. **Confusing Variables with Unknowns:**
   Thinking of $x$ as the unknown in the system. The $x$-values ($0, 1, 2$) are known data constants; the unknowns to solve for are the polynomial coefficients $a, b,$ and $c$.
2. **Squaring the Coefficient Instead of the Coordinate:**
   Writing $(ax)^2$ instead of $a(x^2)$. For $x = 2$, $x^2 = 4$, so the term is $4a$.
3. **Dropping the Constant Term:**
   Assuming $b$ cannot be zero. Here, $b = 0$ simply means the parabola is symmetric with respect to the $y$-axis (its vertex is at $(0, 1)$).

---

## 8. How I Would Explain This in Class

> "Although a parabola bends curves through space, fitting a parabola to data points is a purely linear algebra problem. That is because the curve bends with respect to $x$, but the mystery coefficients $a, b,$ and $c$ enter each equation purely to the first power. Plugging in the three $(x, y)$ coordinates gives us three linear equations, immediately pinning down $c = 1$, $b = 0$, and $a = 2$."
