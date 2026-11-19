# Problem 05: Relative Position of Two Lines

## 1. The Original Problem

Analyze the position of

$$
L_1: (x, y, z) = (1, 1, 0) + t(1, 2, 1),
$$

$$
L_2: (x, y, z) = (2, 0, 1) + s(0, 1, -1).
$$

If they intersect, give the intersection point. If not, determine whether they are parallel or skew. Justify the classification.

---

## 2. What Are We Trying to Find?

We need to:
1. Extract the direction vectors $v_1$ and $v_2$ of lines $L_1$ and $L_2$.
2. Test whether the direction vectors are collinear (parallel lines).
3. If not parallel, test whether there exist parameters $t$ and $s$ that produce a common intersection point.
4. Classify the relative position of the two lines into one of the three possibilities in $\mathbb{R}^3$: intersecting, parallel, or skew.
5. Provide a complete mathematical justification for the final classification.

---

## 3. Before Calculating: What Idea Do We Need?

- **Classification of Two Lines in 3D Space:**
  Two lines $L_1: P_1 + t v_1$ and $L_2: P_2 + s v_2$ in $\mathbb{R}^3$ can have one of four relative configurations:
  1. **Coincident (identical):** $v_1 \parallel v_2$ and $P_1 \in L_2$.
  2. **Parallel (disjoint):** $v_1 \parallel v_2$ and $P_1 \notin L_2$.
  3. **Intersecting:** $v_1 \nparallel v_2$ and there exists a unique pair $(t, s)$ such that $P_1 + t v_1 = P_2 + s v_2$.
  4. **Skew (non-coplanar):** $v_1 \nparallel v_2$ and no intersection point exists (they pass each other at different depths without ever meeting).
- **Parallelism Test:**
  $v_1$ and $v_2$ are parallel if and only if $v_1 = k v_2$ for some non-zero scalar $k \in \mathbb{R}$.
- **Intersection Test:**
  Equating the $x, y,$ and $z$ coordinates gives a linear system of 3 equations in 2 unknowns $(t, s)$. If the system is inconsistent, the lines do not intersect.

---

## 4. Step-by-Step Solution

### Step 1: Check for Parallelism

Extract the direction vectors from the equations:
- Direction vector of $L_1$: $v_1 = (1, 2, 1)$
- Direction vector of $L_2$: $v_2 = (0, 1, -1)$

Check if $v_1$ is a scalar multiple of $v_2$:

$$
(1, 2, 1) = k (0, 1, -1) \implies \begin{cases} 1 = 0 \cdot k \\\\ 2 = 1 \cdot k \\\\ 1 = -1 \cdot k \end{cases}
$$

The first equation $1 = 0$ is impossible.
Therefore, $v_1$ and $v_2$ are **not parallel**.
The lines are neither parallel nor coincident; they must be either **intersecting** or **skew**.

---

### Step 2: Set Up the System for an Intersection Point

Equate the coordinate expressions of $L_1$ and $L_2$:

$$
\begin{cases}
1 + t = 2 + 0s \\\\
1 + 2t = 0 + s \\\\
0 + t = 1 - s
\end{cases}
\iff
\begin{cases}
t = 1 & \text{(Equation 1)} \\\\
2t - s = -1 & \text{(Equation 2)} \\\\
t + s = 1 & \text{(Equation 3)}
\end{cases}
$$

### Step 3: Solve the First Two Equations and Test the Third

1. **From Equation 1:**

$$
t = 1
$$

2. **Substitute $t = 1$ into Equation 3:**

$$
1 + s = 1 \implies s = 0
$$

3. **Now test the pair $(t, s) = (1, 0)$ in Equation 2:**

$$
2(1) - 0 = 2
$$

However, Equation 2 requires:

$$
2t - s = -1
$$

Evaluating the left-hand side gives $2$, but the right-hand side is $-1$:

$$
2 \neq -1 \quad (\text{Contradiction})
$$

Equivalently, check the $y$-coordinates at $t = 1$ and $s = 0$:
- On line $L_1$: $y = 1 + 2(1) = 3$
- On line $L_2$: $y = 0 + 1(0) = 0$
- Since $3 \neq 0$, the lines never occupy the same $y$-position when their $x$ and $z$ coordinates match.

The system of equations is **inconsistent**; no pair $(t, s)$ satisfies all three coordinate equations simultaneously.

---

### Step 4: Justify the Classification

- The direction vectors $v_1 = (1, 2, 1)$ and $v_2 = (0, 1, -1)$ are linearly independent (not parallel).
- The lines share no common intersection point ($L_1 \cap L_2 = \emptyset$).
- In three-dimensional space, any two non-parallel lines that do not intersect are, by definition, **skew lines**.

---

## 5. Final Answer & Conclusion

- **Relative Position:** The lines $L_1$ and $L_2$ are **skew** (non-parallel and non-intersecting).
- **Intersection Point:** **None** (the solution set is empty: $\emptyset$).
- **Justification:**
  1. Direction vectors $v_1 = (1, 2, 1)$ and $v_2 = (0, 1, -1)$ are not scalar multiples of each other, ruling out parallelism.
  2. The system of coordinate equations is inconsistent ($2 \neq -1$), proving there is no point of intersection.
  3. Non-parallel, non-intersecting lines in $\mathbb{R}^3$ are skew.

---

## 6. Quick Verification

Verify non-coplanarity using the scalar triple product.
Let $P_1 = (1, 1, 0) \in L_1$ and $P_2 = (2, 0, 1) \in L_2$.
The displacement vector between the two base points is:

$$
\overrightarrow{P_1 P_2} = P_2 - P_1 = (2 - 1, 0 - 1, 1 - 0) = (1, -1, 1)
$$

Two lines in $\mathbb{R}^3$ lie in the same plane if and only if $[\overrightarrow{P_1 P_2}, v_1, v_2] = 0$.
Compute the determinant:

$$
\det \begin{pmatrix} 1 & -1 & 1 \\\\ 1 & 2 & 1 \\\\ 0 & 1 & -1 \end{pmatrix}
$$

Subtract Row 1 from Row 2:

$$
\det \begin{pmatrix} 1 & -1 & 1 \\\\ 0 & 3 & 0 \\\\ 0 & 1 & -1 \end{pmatrix} = 1 \cdot [ 3(-1) - 0(1) ] = -3 \neq 0
$$

Because the scalar triple product is $-3 \neq 0$, the volume of the parallelepiped spanned by the directions and the connecting vector is non-zero. The lines do not lie in the same plane, proving with absolute certainty that they are **skew**.

---

## 7. Common Mistakes to Avoid

1. **Using the Same Parameter for Both Lines:**
   Writing $t$ for both $L_1$ and $L_2$. Lines are traversed independently; intersecting lines cross when $L_1(t) = L_2(s)$, which generally happens at different parameter values ($t \neq s$).
2. **Stopping After Solving Two Equations:**
   Solving equations 1 and 3 to get $t = 1, s = 0$, and erroneously declaring that an intersection point exists without checking equation 2! In 3D geometry, two equations determine $t$ and $s$, and the third equation acts as the consistency test.
3. **Confusing Skew with Parallel:**
   Assuming that "no intersection" automatically means parallel. In 3D space, lines can avoid each other by running in different directions at different depths (skew).

---

## 8. How I Would Explain This in Class

> "In a flat 2D notebook, two lines that don't cross must be parallel. But in 3D space, imagine an airplane flying east at 10,000 feet while another airplane flies north at 20,000 feet: their flight paths aren't parallel, yet they will never collide because they fly at different altitudes. These are skew lines. In our algebra, the first two equations match up their ground coordinates, but the third equation reveals they are at different heights ($y = 3$ versus $y = 0$)."

