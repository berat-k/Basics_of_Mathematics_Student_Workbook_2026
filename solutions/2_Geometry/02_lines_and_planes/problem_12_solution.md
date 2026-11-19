# Problem 12: Intersection Line of Two Planes

## 1. The Original Problem

Find a parametric equation of the line that is the intersection of

$$
x + y + z = 3, \qquad x - y + z = 1.
$$

Find its direction vector in two ways: from the system of equations and from the cross product of the normal vectors. Compare the results.

---

## 2. What Are We Trying to Find?

We need to:
1. Find the complete parametric vector equation of the intersection line $L = \Pi_1 \cap \Pi_2$.
2. Compute the direction vector of the line using **Method 1: Solving the linear system of equations algebraically**.
3. Compute the direction vector of the line using **Method 2: Taking the cross product of the two plane normal vectors** ($n_1 \times n_2$).
4. Compare both direction vectors and explain their geometric equivalence.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Intersection Line of Two Planes:**
  Two non-parallel planes in $\mathbb{R}^3$ intersect along a single one-dimensional straight line.
- **Method 1 (Algebraic Elimination):**
  Treat the two plane equations as an underdetermined linear system (2 equations, 3 unknowns). With $\text{rank} = 2 < 3$, there is $3 - 2 = 1$ free variable. Setting the free variable as parameter $t$ expresses all coordinates in standard parametric line form $X(t) = P_0 + t v$.
- **Method 2 (Geometric Cross Product of Normals):**
  The line of intersection lies simultaneously inside both planes. Therefore, its direction vector $v$ must be perpendicular to the normal of the first plane ($v \perp n_1$) and perpendicular to the normal of the second plane ($v \perp n_2$).
  Any vector perpendicular to two vectors is parallel to their cross product:

$$
v \parallel n_1 \times n_2
$$

---

## 4. Step-by-Step Solution

### Step 1: Method 1 — Direction Vector and Line from the System of Equations

We are given the system:

$$
\begin{cases}
x + y + z = 3 & (\text{Equation 1}) \\\\
x - y + z = 1 & (\text{Equation 2})
\end{cases}
$$

1. **Eliminate $x$ and $z$ by subtracting Equation 2 from Equation 1:**

$$
(x + y + z) - (x - y + z) = 3 - 1
$$

$$
2y = 2 \implies y = 1
$$

Notice that $y$ is fixed at $1$ along the entire intersection line.

2. **Substitute $y = 1$ into Equation 1:**

$$
x + 1 + z = 3 \implies x + z = 2 \implies x = 2 - z
$$

3. **Parameterize with free variable $z$:**
   Let $z = t$, where $t \in \mathbb{R}$. Then:

$$
\begin{cases}
x = 2 - t, \\\\
y = 1, \\\\
z = t
\end{cases}
\quad t \in \mathbb{R}
$$

In vector parametric form:

$$
(x, y, z) = (2, 1, 0) + t(-1, 0, 1), \quad t \in \mathbb{R}
$$

- Base point on the line: $P_0 = (2, 1, 0)$
- **Direction vector from Method 1:**

$$
v_1 = (-1, 0, 1)
$$

---

### Step 2: Method 2 — Direction Vector from Cross Product of Normals

Extract the normal vectors from the two plane equations:
- For $\Pi_1: x + y + z = 3 \implies n_1 = (1, 1, 1)$
- For $\Pi_2: x - y + z = 1 \implies n_2 = (1, -1, 1)$

Compute the cross product $n_1 \times n_2$:

$$
v_2 = n_1 \times n_2 = \det \begin{pmatrix} i & j & k \\\\ 1 & 1 & 1 \\\\ 1 & -1 & 1 \end{pmatrix}
$$

Expand along the first row:

$$
v_2 = i \det \begin{pmatrix} 1 & 1 \\\\ -1 & 1 \end{pmatrix} - j \det \begin{pmatrix} 1 & 1 \\\\ 1 & 1 \end{pmatrix} + k \det \begin{pmatrix} 1 & 1 \\\\ 1 & -1 \end{pmatrix}
$$

Evaluate each component:
- $i$-component: $(1)(1) - (1)(-1) = 1 - (-1) = 1 + 1 = 2$
- $j$-component: $- [ (1)(1) - (1)(1) ] = - (1 - 1) = 0$
- $k$-component: $(1)(-1) - (1)(1) = -1 - 1 = -2$

Therefore, the cross product is:

$$
v_2 = (2, 0, -2)
$$

Dividing by $2$ to obtain the simplest integer vector:

$$
v_2' = (1, 0, -1)
$$

---

### Step 3: Compare the Results

Compare the direction vector obtained from algebraic elimination with the direction vector obtained from the cross product:

$$
v_1 = (-1, 0, 1), \qquad v_2 = (2, 0, -2)
$$

Notice that:

$$
v_2 = -2 v_1 \iff v_1 = -\frac{1}{2} v_2
$$

- The two direction vectors are **strictly collinear** (scalar multiples of each other).
- They point along the exact same line in 3D space, differing only by a scale factor of $-2$ (a reversal of parameter direction and a doubling of traversal speed).
- Both methods yield the exact same geometric line of intersection.

---

## 5. Final Answer & Conclusion

- **Parametric Equation of the Line:**

$$
(x, y, z) = (2, 1, 0) + t(-1, 0, 1), \quad t \in \mathbb{R}
$$

(or equivalently, $(x, y, z) = (2, 1, 0) + s(1, 0, -1)$ with $s = -t$).
- **Direction Vector from System:** $v_1 = (-1, 0, 1)$.
- **Direction Vector from Cross Product:** $v_2 = n_1 \times n_2 = (2, 0, -2) = 2(1, 0, -1)$.
- **Comparison:** Both vectors are collinear ($v_2 = -2v_1$), confirming the complete equivalence of the algebraic and geometric methods.

---

## 6. Quick Verification

Verify that the parametric line satisfies both plane equations for all $t$:
1. Substitute into $\Pi_1: x + y + z = 3$:

$$
(2 - t) + 1 + t = 2 + 1 - t + t = 3
$$

Matches $3 = 3$ identically.

2. Substitute into $\Pi_2: x - y + z = 1$:

$$
(2 - t) - 1 + t = 2 - 1 - t + t = 1
$$

Matches $1 = 1$ identically.

Verify orthogonality of $v_1$ to both normals:
- $v_1 \cdot n_1 = (-1)(1) + (0)(1) + (1)(1) = -1 + 0 + 1 = 0$.
- $v_1 \cdot n_2 = (-1)(1) + (0)(-1) + (1)(1) = -1 + 0 + 1 = 0$.
Both checks confirm complete correctness.

---

## 7. Common Mistakes to Avoid

1. **Thinking the Two Vectors Must Be Identical:**
   Worrying because $(-1, 0, 1) \neq (2, 0, -2)$. A line's direction vector is unique only up to a non-zero scalar multiple ($k \neq 0$). Any non-zero scalar multiple is completely correct.
2. **Forgetting to Find a Base Point When Using the Cross Product:**
   Finding $n_1 \times n_2 = (2, 0, -2)$ gives the direction, but to write the line equation, one still needs a point on the line (which requires setting one variable to a constant and solving the remaining $2 \times 2$ system).
3. **Sign Slips in Cross Product:**
   In the $k$-component, calculating $-1 - 1 = 0$ instead of $-2$.

---

## 8. How I Would Explain This in Class

> "When two planes slice through each other like two sheets of paper, their seam is a straight line. You can find this seam in two different ways: algebraically, by letting one variable be a free slider $t$; or geometrically, by recognizing that the seam must run perpendicular to both normal flagpoles simultaneously. Taking the cross product of the two flagpoles gives $(2, 0, -2)$, which is simply our algebraic direction $(-1, 0, 1)$ multiplied by $-2$."

