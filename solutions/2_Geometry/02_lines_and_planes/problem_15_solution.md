# Problem 15: Complete Classification of a Line Relative to a Plane

## 1. The Original Problem

Let

$$
L: p + tv, \qquad \Pi: n \cdot x = d.
$$

State the conditions distinguishing the three cases: one intersection point, parallel with no common points, and the line contained in the plane. Then illustrate each case with your own simple numerical example.

---

## 2. What Are We Trying to Find?

We need to:
1. Derive the general algebraic master equation governing the intersection of a line $L: p + tv$ and a plane $\Pi: n \cdot x = d$ in $\mathbb{R}^3$.
2. Formulate the precise mathematical conditions (in terms of dot products $n \cdot v$ and $n \cdot p$, and the constant $d$) that distinguish the three exhaustive geometric cases:
   - Exactly one intersection point.
   - Strictly parallel with no common points ($L \cap \Pi = \emptyset$).
   - The line is contained entirely within the plane ($L \subset \Pi$).
3. Provide a clear, simple numerical example for each of the three cases.
4. Solve each numerical example completely to illustrate the theory in action.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Master Linear Equation in $t$:**
  Substitute the parametric expression of the line $x(t) = p + tv$ into the plane equation $n \cdot x = d$:

$$
n \cdot (p + tv) = d
$$

  Apply the linearity of the dot product:

$$
(n \cdot v) t + (n \cdot p) = d \iff (n \cdot v) t = d - n \cdot p
$$

  This is a scalar linear equation of the fundamental form $A t = B$, where:
  - Coefficient: $A = n \cdot v$
  - Constant: $B = d - n \cdot p$
- **Algebraic Classification of $A t = B$:**
  1. If $A \neq 0$: Exactly one unique solution $t = B/A$.
  2. If $A = 0$ and $B \neq 0$: No solution ($0 \cdot t = B \neq 0$, contradiction).
  3. If $A = 0$ and $B = 0$: Infinitely many solutions ($0 \cdot t = 0$, identity holding for all $t \in \mathbb{R}$).

---

## 4. Step-by-Step Solution

### Step 1: Formal Statement of General Conditions

Let a line be $L: x = p + tv$ (with $v \neq \mathbf{0}$) and a plane be $\Pi: n \cdot x = d$ (with $n \neq \mathbf{0}$).
The relative position is completely determined by the following criteria:

| Case | Geometric Description | Necessary & Sufficient Condition | Algebraic Meaning in $(n \cdot v)t = d - n \cdot p$ |
| :--- | :--- | :--- | :--- |
| **Case 1** | **Exactly one intersection point** | $n \cdot v \neq 0$ | Unique solution: $t = \frac{d - n \cdot p}{n \cdot v}$ |
| **Case 2** | **Strictly parallel (disjoint, $L \cap \Pi = \emptyset$)** | $n \cdot v = 0$ and $n \cdot p \neq d$ | Contradiction: $0 \cdot t = \text{non-zero}$ |
| **Case 3** | **Line contained in plane ($L \subset \Pi$)** | $n \cdot v = 0$ and $n \cdot p = d$ | Identity: $0 \cdot t = 0$ for all $t \in \mathbb{R}$ |

---

### Step 2: Numerical Example for Case 1 (One Intersection Point)

#### Construction:
Choose plane $\Pi: z = 5$ (so $n = (0, 0, 1)$ and $d = 5$) and line $L: p + tv$ with $p = (1, 2, 0)$ and $v = (0, 0, 1)$:

$$
L: (x, y, z) = (1, 2, 0) + t(0, 0, 1) \iff \begin{cases} x = 1 \\\\ y = 2 \\\\ z = t \end{cases}
$$

#### Condition Check:
- $n \cdot v = (0)(0) + (0)(0) + (1)(1) = 1 \neq 0$.
- Because $n \cdot v = 1 \neq 0$, Case 1 applies.

#### Solution:
Substitute into the plane equation $z = 5$:

$$
t = 5
$$

Compute the intersection point:

$$
I = (1, 2, 5)
$$

The line intersects the plane at the single point $(1, 2, 5)$.

---

### Step 3: Numerical Example for Case 2 (Parallel with No Common Points)

#### Construction:
Use the same plane $\Pi: z = 5$ ($n = (0, 0, 1), d = 5$), but choose a line running parallel to the $x$-axis at height $z = 1$:

$$
L: (x, y, z) = (0, 0, 1) + t(1, 0, 0) \iff \begin{cases} x = t \\\\ y = 0 \\\\ z = 1 \end{cases}
$$

Here, $p = (0, 0, 1)$ and $v = (1, 0, 0)$.

#### Condition Check:
1. $n \cdot v = (0)(1) + (0)(0) + (1)(0) = 0$. (Line direction is parallel to plane)
2. $n \cdot p = (0)(0) + (0)(0) + (1)(1) = 1$.
3. Compare with $d = 5$:

$$
n \cdot p = 1 \neq 5 = d
$$

#### Algebraic Equation:

$$
(n \cdot v)t = d - n \cdot p \implies 0 \cdot t = 5 - 1 \implies 0 = 4 \quad (\text{Contradiction})
$$

No value of $t$ can satisfy $0 = 4$. The line floats $4$ units below the plane and never meets it.
Line $L$ is strictly parallel to $\Pi$.

---

### Step 4: Numerical Example for Case 3 (Line Contained in the Plane)

#### Construction:
Use the same plane $\Pi: z = 5$ ($n = (0, 0, 1), d = 5$), but choose a line that runs parallel to the $x$-axis lying right on the plane at height $z = 5$:

$$
L: (x, y, z) = (0, 0, 5) + t(1, 0, 0) \iff \begin{cases} x = t \\\\ y = 0 \\\\ z = 5 \end{cases}
$$

Here, $p = (0, 0, 5)$ and $v = (1, 0, 0)$.

#### Condition Check:
1. $n \cdot v = (0)(1) + (0)(0) + (1)(0) = 0$. (Line direction is parallel to plane)
2. $n \cdot p = (0)(0) + (0)(0) + (1)(5) = 5$.
3. Compare with $d = 5$:

$$
n \cdot p = 5 = d
$$

#### Algebraic Equation:

$$
(n \cdot v)t = d - n \cdot p \implies 0 \cdot t = 5 - 5 \implies 0 = 0 \quad (\text{Identity})
$$

The equation $0 = 0$ is true for every real number $t \in \mathbb{R}$.
Every point $(t, 0, 5)$ on the line has $z = 5$, and therefore satisfies the plane equation $z = 5$.
Line $L$ lies entirely within plane $\Pi$ ($L \subset \Pi$).

---

## 5. Final Answer & Conclusion

- **Classification Master Table:**

| Case | Condition | Geometric Result |
| :--- | :--- | :--- |
| **Case 1** | $n \cdot v \neq 0$ | Exactly one point of intersection: $I = p + \left(\frac{d - n \cdot p}{n \cdot v}\right) v$ |
| **Case 2** | $n \cdot v = 0$ and $n \cdot p \neq d$ | Strictly parallel, disjoint ($L \cap \Pi = \emptyset$) |
| **Case 3** | $n \cdot v = 0$ and $n \cdot p = d$ | Line contained in the plane ($L \subset \Pi$) |

- **Numerical Examples:**
  - Case 1: Line $(1, 2, t)$ and plane $z = 5 \implies$ intersection at $(1, 2, 5)$.
  - Case 2: Line $(t, 0, 1)$ and plane $z = 5 \implies 0 = 4$ contradiction, strictly parallel.
  - Case 3: Line $(t, 0, 5)$ and plane $z = 5 \implies 0 = 0$ identity, line lies in the plane.

---

## 6. Quick Verification

Verify that the three cases are mathematically exhaustive and mutually exclusive:
1. For any pair of non-zero vectors $n, v$, the scalar $n \cdot v$ is either non-zero or zero. If non-zero, Case 1 holds uniquely.
2. If $n \cdot v = 0$, the scalar $n \cdot p$ is either unequal to $d$ (Case 2 holds uniquely) or equal to $d$ (Case 3 holds uniquely).

Because these three logical branches cover all real numbers without overlap, no fourth geometric case can exist in Euclidean 3D space.

---

## 7. Common Mistakes to Avoid

1. **Assuming $n \cdot v = 0$ Always Means "Disjoint":**
   Forgetting that a line can lie completely inside the plane. Checking $n \cdot p = d$ is essential to separate Case 2 from Case 3.
2. **Confusing Plane Normal with Line Normal:**
   $n$ is the normal to the plane. $n \cdot v \neq 0$ means the line is *not* parallel to the plane, so it must pierce it.
3. **Overcomplicating the Numerical Examples:**
   Choosing complicated $3 \times 3$ numbers with fractions for illustrative examples. Selecting coordinate planes like $z = 5$ and coordinate axes highlights the underlying algebraic structure with crystal clarity.

---

## 8. How I Would Explain This in Class

> "When you plug a parametric line into a plane equation, you are always solving one simple grade-school equation: $A t = B$. If $A = n \cdot v$ is non-zero, you can divide by it to find the exact second the arrow punctures the wall. If $A = 0$, the arrow is flying parallel to the wall: if it is flying 4 feet away ($B \neq 0$), it never hits; but if it is already flush against the wall ($B = 0$), it stays in contact with the wall for its entire journey."

