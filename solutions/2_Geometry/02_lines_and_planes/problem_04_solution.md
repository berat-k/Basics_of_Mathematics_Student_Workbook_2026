# Problem 04: Plane Through Three Points

## 1. The Original Problem

Find the equation of the plane through

$$
A = (1, 0, 0), \quad B = (0, 1, 0), \quad C = (0, 0, 1).
$$

First construct two vectors lying in the plane, and then use the cross product. Check the resulting equation on all three points.

---

## 2. What Are We Trying to Find?

We need to:
1. Construct two displacement vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ connecting the three given non-collinear points in $\mathbb{R}^3$.
2. Compute the cross product $n = \overrightarrow{AB} \times \overrightarrow{AC}$ to determine a normal vector to the plane.
3. Formulate the general Cartesian equation of the plane $ax + by + cz = d$.
4. Check the resulting equation by substituting all three points $A, B,$ and $C$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Plane Determined by Three Non-Collinear Points:**
  Three points that do not lie on a single line uniquely define a 2D plane in $\mathbb{R}^3$.
- **Finding the Normal Vector via Cross Product:**
  If $u = \overrightarrow{AB}$ and $v = \overrightarrow{AC}$ are two non-parallel vectors lying in the plane, their cross product is perpendicular to both vectors, and therefore perpendicular to the entire plane:

$$
n = u \times v = \overrightarrow{AB} \times \overrightarrow{AC}
$$

- **Intercept Form of a Plane:**
  Notice that $A(1, 0, 0)$, $B(0, 1, 0)$, and $C(0, 0, 1)$ are the standard unit basis intercepts on the $x$-, $y$-, and $z$-axes. The equation of a plane with intercepts $(a, 0, 0)$, $(0, b, 0)$, and $(0, 0, c)$ is $\frac{x}{a} + \frac{y}{b} + \frac{z}{c} = 1$, which suggests immediately that the equation will be $x + y + z = 1$.

---

## 4. Step-by-Step Solution

### Step 1: Construct Two Vectors Lying in the Plane

Subtract point $A(1, 0, 0)$ from $B(0, 1, 0)$ and $C(0, 0, 1)$:

1. **Vector $u = \overrightarrow{AB}$:**

$$
u = B - A = (0 - 1, 1 - 0, 0 - 0) = (-1, 1, 0)
$$

2. **Vector $v = \overrightarrow{AC}$:**

$$
v = C - A = (0 - 1, 0 - 0, 1 - 0) = (-1, 0, 1)
$$

Both vectors $u$ and $v$ lie entirely in the desired plane.

---

### Step 2: Compute the Normal Vector via Cross Product

Set up the formal cross product determinant $n = u \times v$:

$$
n = \det \begin{pmatrix} i & j & k \\\\ -1 & 1 & 0 \\\\ -1 & 0 & 1 \end{pmatrix}
$$

Expand along the first row:

$$
n = i \det \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} - j \det \begin{pmatrix} -1 & 0 \\\\ -1 & 1 \end{pmatrix} + k \det \begin{pmatrix} -1 & 1 \\\\ -1 & 0 \end{pmatrix}
$$

Evaluate each component:
- $i$-component: $(1)(1) - (0)(0) = 1 - 0 = 1$
- $j$-component: $- [ (-1)(1) - (0)(-1) ] = - [ -1 - 0 ] = - (-1) = 1$
- $k$-component: $(-1)(0) - (1)(-1) = 0 - (-1) = 1$

Therefore, the normal vector is:

$$
n = (1, 1, 1)
$$

---

### Step 3: Derive the Plane Equation

Using the normal vector $n = (1, 1, 1)$ and base point $A(1, 0, 0)$:

$$
n \cdot (X - A) = 0 \iff 1(x - 1) + 1(y - 0) + 1(z - 0) = 0
$$

Expand:

$$
x - 1 + y + z = 0
$$

Rearrange to standard form:

$$
x + y + z = 1 \quad (\text{or } x + y + z - 1 = 0)
$$

---

### Step 4: Check All Three Points

Substitute each given point into $x + y + z = 1$:

1. **Point $A(1, 0, 0)$:**

$$
1 + 0 + 0 = 1
$$

Matches $1 = 1$. (Correct)

2. **Point $B(0, 1, 0)$:**

$$
0 + 1 + 0 = 1
$$

Matches $1 = 1$. (Correct)

3. **Point $C(0, 0, 1)$:**

$$
0 + 0 + 1 = 1
$$

Matches $1 = 1$. (Correct)

All three points satisfy the equation.

---

## 5. Final Answer & Conclusion

- **In-Plane Vectors:**

$$
\overrightarrow{AB} = (-1, 1, 0), \qquad \overrightarrow{AC} = (-1, 0, 1)
$$

- **Normal Vector:**

$$
n = (1, 1, 1)
$$

- **Equation of the Plane:**

$$
x + y + z = 1 \quad (\text{or } x + y + z - 1 = 0)
$$

- **Verification:** All three points $A(1, 0, 0)$, $B(0, 1, 0)$, and $C(0, 0, 1)$ satisfy the equation identically.

---

## 6. Quick Verification

Verify orthogonality directly via dot products:
- $n \cdot \overrightarrow{AB} = (1)(-1) + (1)(1) + (1)(0) = -1 + 1 + 0 = 0$.
- $n \cdot \overrightarrow{AC} = (1)(-1) + (1)(0) + (1)(1) = -1 + 0 + 1 = 0$.
- Also check third side $\overrightarrow{BC} = C - B = (0, -1, 1)$:
  $n \cdot \overrightarrow{BC} = (1)(0) + (1)(-1) + (1)(1) = 0 - 1 + 1 = 0$.

Because $n = (1, 1, 1)$ is perpendicular to all three side vectors of the triangle $\Delta ABC$, it is unconditionally the true normal vector of the plane.

---

## 7. Common Mistakes to Avoid

1. **Minus Sign Errors in the $j$-Component:**
   Computing the minor determinant $(-1)(1) - (0)(-1) = -1$ and forgetting the minus sign attached to the $j$ unit vector, resulting in $-1$ instead of $+1$.
2. **Using Non-Existent Cross Products in 2D:**
   The cross product method is unique to $\mathbb{R}^3$. Here it works because the points are in three dimensions.
3. **Checking Only One Point:**
   Checking only point $A$ and neglecting $B$ and $C$. If the cross product had an arithmetic error, $A$ might still satisfy the equation if $d$ was computed from $A$, but $B$ and $C$ would fail.

---

## 8. How I Would Explain This in Class

> "Points $A, B,$ and $C$ mark the spots where a tilted triangle cuts through the three coordinate axes at distance 1 from the origin. To find the equation of the flat sheet containing that triangle, we trace two arrows across the surface, $\overrightarrow{AB}$ and $\overrightarrow{AC}$, and take their cross product. The result is the arrow $(1, 1, 1)$ pointing diagonally into the first octant, giving the beautifully symmetrical equation $x + y + z = 1$."
