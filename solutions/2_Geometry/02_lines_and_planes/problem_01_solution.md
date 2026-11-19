# Problem 01: Line Through Two Points

## 1. The Original Problem

Find the equation of the line through $A = (1, 2)$ and $B = (4, -1)$ in parametric and general form. Identify a direction vector and an example of a normal vector. Check that both points satisfy the equation you obtain.

---

## 2. What Are We Trying to Find?

We need to:
1. Construct a direction vector $v$ for the line passing through points $A(1, 2)$ and $B(4, -1)$ in $\mathbb{R}^2$.
2. Write the parametric vector equation and scalar parametric equations of the line.
3. Identify a normal vector $n$ perpendicular to the direction vector.
4. Derive the general (standard Cartesian) equation of the line: $ax + by + c = 0$.
5. Verify that both given points $A$ and $B$ satisfy both the parametric and general equations.

---

## 3. Before Calculating: What Idea Do We Need?

- **Direction Vector:**
  The displacement vector connecting two distinct points $A$ and $B$ provides the direction of the line:

$$
v = \overrightarrow{AB} = B - A = (x_B - x_A, y_B - y_A)
$$

- **Parametric Form:**
  Using point $A$ as an anchor point and $t \in \mathbb{R}$ as a parameter:

$$
(x, y) = A + t v \iff \begin{cases} x = x_A + t v_x, \\\\ y = y_A + t v_y \end{cases}
$$

- **Normal Vector in 2D:**
  In the 2D plane $\mathbb{R}^2$, a vector $n = (a, b)$ is perpendicular to $v = (v_x, v_y)$ if their dot product vanishes:

$$
n \cdot v = a v_x + b v_y = 0
$$

  A standard perpendicular vector to $(v_x, v_y)$ is given by $(-v_y, v_x)$ or $(v_y, -v_x)$.
- **General Form ($ax + by + c = 0$):**
  The coefficients $a$ and $b$ of the general form correspond directly to the components of the normal vector $n = (a, b)$. The constant $c$ is determined by substituting any point on the line:

$$
c = -(a x_A + b y_A)
$$

---

## 4. Step-by-Step Solution

### Step 1: Find a Direction Vector $v$

Subtract point $A(1, 2)$ from point $B(4, -1)$:

$$
v = B - A = (4 - 1, -1 - 2) = (3, -3)
$$

We can use $v = (3, -3)$, or simplify by dividing by $3$ to get the simpler collinear direction vector:

$$
v = (1, -1)
$$

Both vectors describe the exact same line of slope $m = -1/1 = -1$.

---

### Step 2: Write the Parametric Form

Using anchor point $A(1, 2)$ and direction vector $v = (1, -1)$:

1. **Vector Parametric Form:**

$$
(x, y) = (1, 2) + t(1, -1), \quad t \in \mathbb{R}
$$

2. **Scalar Parametric Form:**

$$
\begin{cases}
x = 1 + t, \\\\
y = 2 - t,
\end{cases}
\quad t \in \mathbb{R}
$$

---

### Step 3: Find a Normal Vector $n$

We need a non-zero vector $n = (a, b)$ such that $n \cdot v = 0$:

$$
a(1) + b(-1) = 0 \implies a - b = 0 \implies a = b
$$

Choosing $a = 1$ gives $b = 1$. Thus, an example of a normal vector is:

$$
n = (1, 1)
$$

Check orthogonality: $n \cdot v = (1)(1) + (1)(-1) = 1 - 1 = 0$.

---

### Step 4: Derive the General Form

Using normal vector $n = (1, 1)$, the general form is:

$$
1x + 1y + c = 0 \iff x + y + c = 0
$$

Substitute point $A(1, 2)$ to determine $c$:

$$
1 + 2 + c = 0 \implies 3 + c = 0 \implies c = -3
$$

Thus, the general form equation of the line is:

$$
x + y - 3 = 0 \iff x + y = 3
$$

---

### Step 5: Check Both Points

1. **Check Point $A(1, 2)$:**
   - In general form: $1 + 2 - 3 = 3 - 3 = 0$. (Satisfied)
   - In parametric form: For $t = 0$, $x = 1 + 0 = 1$ and $y = 2 - 0 = 2$, yielding $A(1, 2)$. (Satisfied)

2. **Check Point $B(4, -1)$:**
   - In general form: $4 + (-1) - 3 = 4 - 4 = 0$. (Satisfied)
   - In parametric form: Setting $x = 4 \implies 1 + t = 4 \implies t = 3$. Then $y = 2 - 3 = -1$, yielding $B(4, -1)$. (Satisfied)

Both points lie on the line in both representations.

---

## 5. Final Answer & Conclusion

- **Direction Vector:**

$$
v = (1, -1) \quad (\text{or } (3, -3))
$$

- **Normal Vector:**

$$
n = (1, 1)
$$

- **Parametric Form:**

$$
\begin{cases}
x = 1 + t, \\\\
y = 2 - t,
\end{cases}
\quad t \in \mathbb{R}
$$

- **General Form:**

$$
x + y - 3 = 0 \quad (\text{or } x + y = 3)
$$

- **Verification:** Both points $A(1, 2)$ and $B(4, -1)$ satisfy $x + y = 3$ and correspond to $t = 0$ and $t = 3$ respectively.

---

## 6. Quick Verification

Eliminate the parameter $t$ from the scalar parametric equations:
- From $x = 1 + t$, we get $t = x - 1$.
- Substitute $t = x - 1$ into $y = 2 - t$:

$$
y = 2 - (x - 1) = 2 - x + 1 = 3 - x \implies x + y = 3
$$

The elimination of $t$ directly recovers the general Cartesian equation $x + y - 3 = 0$, proving that both descriptions are mathematically equivalent.

---

## 7. Common Mistakes to Avoid

1. **Sign Errors When Finding the Normal Vector:**
   Taking $n = (1, -1)$ instead of $(1, 1)$. Notice that $(1, -1) \cdot (1, -1) = 2 \neq 0$. Always verify $n \cdot v = 0$.
2. **Forgetting to Determine the Constant $c$:**
   Writing $x + y = 0$. The normal vector provides the coefficients $a$ and $b$, but the constant $c$ must be calculated by substituting an actual point on the line.
3. **Checking Only Point $A$:**
   Checking only the anchor point used in the construction. Testing point $B$ ensures the direction vector was computed correctly.

---

## 8. How I Would Explain This in Class

> "A straight line can be thought of in two complementary ways: either you start at point $A$ and walk along direction vector $(1, -1)$ with a dial $t$ in your hand (the parametric view), or you declare that every step must stay perpendicular to the normal vector $(1, 1)$ with a constant sum $x + y = 3$ (the general view). Both viewpoints describe the exact same straight path connecting $A$ and $B$."

