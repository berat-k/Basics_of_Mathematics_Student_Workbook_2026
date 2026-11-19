# Problem 11: Plane Containing a Line and a Point

## 1. The Original Problem

Find the equation of the plane containing

$$
(x, y, z) = (1, 0, 2) + t(1, 1, -1)
$$

and the point $P = (0, 2, 1)$. Check that both the entire line and the point lie in the plane you obtain.

---

## 2. What Are We Trying to Find?

We need to:
1. Extract a base point $A$ and a direction vector $v$ from the given line $L$.
2. Verify that point $P(0, 2, 1)$ does not already lie on line $L$ (confirming they determine a unique plane).
3. Construct a second direction vector $u = \overrightarrow{AP}$ lying in the plane.
4. Compute a normal vector $n = v \times u$ using the cross product.
5. Derive the Cartesian equation of the plane.
6. Verify that point $P$ and every point of line $L$ satisfy the derived plane equation.

---

## 3. Before Calculating: What Idea Do We Need?

- **Plane Determined by a Line and an External Point:**
  A line $L: A + t v$ and an external point $P \notin L$ span a unique plane in $\mathbb{R}^3$.
- **Two Linearly Independent Direction Vectors:**
  Any plane requires two independent direction vectors to define its tilt:
  - Vector 1: The direction vector of the line, $v = (1, 1, -1)$.
  - Vector 2: The displacement vector connecting the line's base point $A$ to the external point $P$, $u = \overrightarrow{AP} = P - A$.
- **Normal Vector via Cross Product:**
  The normal vector to the plane must be perpendicular to both in-plane directions:

$$
n = v \times u
$$

- **Verification for an Entire Line:**
  To prove that an *entire line* lies in a plane, we substitute its parametric form $(x(t), y(t), z(t))$ into the plane equation. If the parameter $t$ cancels out identically and leaves a true numerical identity ($d = d$), every point on the line belongs to the plane.

---

## 4. Step-by-Step Solution

### Step 1: Extract Base Point and In-Plane Vectors

From the line $(x, y, z) = (1, 0, 2) + t(1, 1, -1)$:
- Base point of the line: $A = (1, 0, 2)$
- Direction vector of the line: $v = (1, 1, -1)$
- Given point: $P = (0, 2, 1)$

Check whether $P \in L$:
- $1 + t = 0 \implies t = -1$.
- Check $y$: $0 + (-1) = -1 \neq 2$.
Since $P$ does not lie on $L$, the line and point define a unique plane.

Now construct the second in-plane vector $u = \overrightarrow{AP}$:

$$
u = P - A = (0 - 1, 2 - 0, 1 - 2) = (-1, 2, -1)
$$

---

### Step 2: Compute the Normal Vector via Cross Product

Compute $n = v \times u$:

$$
n = \det \begin{pmatrix} i & j & k \\\\ 1 & 1 & -1 \\\\ -1 & 2 & -1 \end{pmatrix}
$$

Expand along the first row:

$$
n = i \det \begin{pmatrix} 1 & -1 \\\\ 2 & -1 \end{pmatrix} - j \det \begin{pmatrix} 1 & -1 \\\\ -1 & -1 \end{pmatrix} + k \det \begin{pmatrix} 1 & 1 \\\\ -1 & 2 \end{pmatrix}
$$

Evaluate each $2 \times 2$ determinant:
- $i$-component: $(1)(-1) - (-1)(2) = -1 - (-2) = -1 + 2 = 1$
- $j$-component: $- [ (1)(-1) - (-1)(-1) ] = - [ -1 - 1 ] = - (-2) = 2$
- $k$-component: $(1)(2) - (1)(-1) = 2 - (-1) = 2 + 1 = 3$

Therefore, the normal vector is:

$$
n = (1, 2, 3)
$$

---

### Step 3: Derive the Plane Equation

Using normal vector $n = (1, 2, 3)$ and base point $A(1, 0, 2)$:

$$
1(x - 1) + 2(y - 0) + 3(z - 2) = 0
$$

Expand the terms:

$$
x - 1 + 2y + 3z - 6 = 0
$$

Combine the constants:

$$
x + 2y + 3z - 7 = 0 \iff x + 2y + 3z = 7
$$

The equation of the plane is $x + 2y + 3z = 7$.

---

### Step 4: Check That the Entire Line Lies in the Plane

Substitute the parametric coordinates of the line:

$$
x = 1 + t, \quad y = t, \quad z = 2 - t
$$

into the plane equation $x + 2y + 3z = 7$:

$$
(1 + t) + 2(t) + 3(2 - t) = 7
$$

Expand and group terms:

$$
1 + t + 2t + 6 - 3t = 7
$$

$$
(t + 2t - 3t) + (1 + 6) = 7
$$

$$
0t + 7 = 7 \iff 7 = 7
$$

The equation simplifies to $7 = 7$, which holds identically for **all** real numbers $t \in \mathbb{R}$.
Therefore, every point of the line lies in the plane.

---

### Step 5: Check That Point $P(0, 2, 1)$ Lies in the Plane

Substitute $x = 0, y = 2, z = 1$ into $x + 2y + 3z = 7$:

$$
0 + 2(2) + 3(1) = 0 + 4 + 3 = 7
$$

Matches $7 = 7$.
The point $P(0, 2, 1)$ lies in the plane.

---

## 5. Final Answer & Conclusion

- **Equation of the Plane:**

$$
x + 2y + 3z = 7 \quad (\text{or } x + 2y + 3z - 7 = 0)
$$

- **Normal Vector:**

$$
n = (1, 2, 3)
$$

- **Verification:**
  - Entire line: Substituting $(1 + t, t, 2 - t)$ yields $7 = 7$ for all $t$.
  - Point $P(0, 2, 1)$: $0 + 2(2) + 3(1) = 7$.
  Both requirements are completely satisfied.

---

## 6. Quick Verification

Verify orthogonality of the normal vector to both generating vectors:
- $n \cdot v = (1, 2, 3) \cdot (1, 1, -1) = 1(1) + 2(1) + 3(-1) = 1 + 2 - 3 = 0$.
- $n \cdot u = (1, 2, 3) \cdot (-1, 2, -1) = 1(-1) + 2(2) + 3(-1) = -1 + 4 - 3 = 0$.

Because $n$ is perpendicular to both the direction of the line and the displacement to point $P$, the derived plane must contain both objects.

---

## 7. Common Mistakes to Avoid

1. **Attempting to Take Cross Product with a Point:**
   Trying to compute $v \times P$. Cross products must be taken between **displacement vectors**, never between a direction vector and the raw coordinates of a point. Always construct $u = P - A$.
2. **Checking Only a Single Point on the Line:**
   Checking $A(1, 0, 2)$ and assuming the whole line lies in the plane. If the normal vector was chosen incorrectly, point $A$ might satisfy the equation while the line tilts away from the plane.
3. **Double Negative Slips in Cross Product:**
   In the $j$-component, calculating $-(1(-1) - (-1)(-1)) = -(-1 - 1) = +2$. Forgetting the outer minus sign produces $-2$.

---

## 8. How I Would Explain This in Class

> "Think of the line as an iron rod suspended in space and point $P$ as an external peg. You want to lay a sheet of glass flat across both the rod and the peg. The rod gives you your first direction vector $(1, 1, -1)$, and connecting a point on the rod to the peg gives your second direction vector $(-1, 2, -1)$. Crossing those two vectors erects the normal arrow $(1, 2, 3)$, locking the glass into the exact equation $x + 2y + 3z = 7$."

