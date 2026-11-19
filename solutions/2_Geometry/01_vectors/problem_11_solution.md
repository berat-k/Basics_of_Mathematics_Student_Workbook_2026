# Problem 11: Decomposition into Parallel and Perpendicular Components

## 1. The Original Problem

Decompose $u = (3, 4)$ into components parallel and perpendicular to $v = (1, 2)$. Check

$$
u = u_{\parallel} + u_{\perp}, \qquad u_{\perp} \cdot v = 0.
$$

Explain why these are two independent checks of correctness.

---

## 2. What Are We Trying to Find?

We need to:
1. Decompose the vector $u = (3, 4)$ into:
   - A parallel component $u_{\parallel}$ directed along $v = (1, 2)$.
   - A perpendicular component $u_{\perp}$ orthogonal to $v$.
2. Check the additive reconstruction condition: $u_{\parallel} + u_{\perp} = u$.
3. Check the orthogonality condition: $u_{\perp} \cdot v = 0$.
4. Explain theoretically why these two verification tests are logically independent of each other (neither implies the other on its own).

---

## 3. Before Calculating: What Idea Do We Need?

- **Parallel Component (Orthogonal Projection):**
  The component of $u$ along $v$ is the vector projection:

$$
u_{\parallel} = \text{proj}_v(u) = \left( \frac{u \cdot v}{v \cdot v} \right) v
$$

- **Perpendicular Component (Orthogonal Complement):**
  The component of $u$ perpendicular to $v$ is obtained by subtracting the parallel component:

$$
u_{\perp} = u - u_{\parallel}
$$

- **Independence of Verification Tests:**
  A correct orthogonal decomposition requires two distinct geometric conditions:
  1. **Completeness (Span):** The two components must sum to the original vector ($u_{\parallel} + u_{\perp} = u$).
  2. **Orthogonality (Perpendicularity):** The perpendicular component must be genuinely orthogonal to the reference vector ($u_{\perp} \cdot v = 0$).

---

## 4. Step-by-Step Solution

### Step 1: Compute $u \cdot v$ and $v \cdot v$

For $u = (3, 4)$ and $v = (1, 2)$:

1. **Compute $u \cdot v$:**

$$
u \cdot v = (3)(1) + (4)(2) = 3 + 8 = 11
$$

2. **Compute $v \cdot v$:**

$$
v \cdot v = 1^2 + 2^2 = 1 + 4 = 5
$$

### Step 2: Compute the Parallel Component $u_{\parallel}$

Substitute the scalar products into the projection formula:

$$
u_{\parallel} = \left( \frac{u \cdot v}{v \cdot v} \right) v = \frac{11}{5} (1, 2) = \left( \frac{11}{5}, \frac{22}{5} \right) = (2.2, 4.4)
$$

### Step 3: Compute the Perpendicular Component $u_{\perp}$

Subtract $u_{\parallel}$ from $u = (3, 4)$:

$$
u_{\perp} = u - u_{\parallel} = (3, 4) - \left( \frac{11}{5}, \frac{22}{5} \right)
$$

Convert $u$ to fifths:

$$
(3, 4) = \left( \frac{15}{5}, \frac{20}{5} \right)
$$

Perform the subtraction:

$$
u_{\perp} = \left( \frac{15 - 11}{5}, \frac{20 - 22}{5} \right) = \left( \frac{4}{5}, -\frac{2}{5} \right) = (0.8, -0.4)
$$

---

### Step 4: Verify Both Conditions

1. **Check 1: Additive Reconstruction ($u = u_{\parallel} + u_{\perp}$):**

$$
u_{\parallel} + u_{\perp} = \left( \frac{11}{5}, \frac{22}{5} \right) + \left( \frac{4}{5}, -\frac{2}{5} \right) = \left( \frac{11 + 4}{5}, \frac{22 - 2}{5} \right) = \left( \frac{15}{5}, \frac{20}{5} \right) = (3, 4) = u
$$

Check 1 passes.

2. **Check 2: Orthogonality ($u_{\perp} \cdot v = 0$):**

$$
u_{\perp} \cdot v = \left( \frac{4}{5} \right)(1) + \left( -\frac{2}{5} \right)(2) = \frac{4}{5} - \frac{4}{5} = 0
$$

Check 2 passes.

---

### Step 5: Explain Why These Are Two Independent Checks

The two checks test two completely separate mathematical properties:

1. **Check 1 tests algebraic conservation (no loss of information):**
   It ensures that the two pieces combine back into the original vector $u$. However, satisfying Check 1 alone is trivial and does **not** guarantee perpendicularity. For example, the arbitrary split:

$$
w_1 = (2, 2) \quad \text{and} \quad w_2 = (1, 2)
$$

   satisfies $w_1 + w_2 = (3, 4) = u$, but $w_2 \cdot v = (1)(1) + (2)(2) = 5 \neq 0$ (not perpendicular at all).

2. **Check 2 tests geometric orientation (orthogonality to $v$):**
   It ensures that the component $u_{\perp}$ has zero projection onto $v$. However, satisfying Check 2 alone does **not** guarantee that the vectors sum to $u$. For example:

$$
z = (2, -1)
$$

   satisfies $z \cdot v = (2)(1) + (-1)(2) = 0$ (perpendicular to $v$), but $u_{\parallel} + z = (2.2, 4.4) + (2, -1) = (4.2, 3.4) \neq u$.

Because a candidate decomposition could satisfy Check 1 while completely failing Check 2, or satisfy Check 2 while failing Check 1, both checks are **logically independent and jointly necessary** to guarantee mathematical correctness.

---

## 5. Final Answer & Conclusion

- **Parallel Component:**

$$
u_{\parallel} = \left( \frac{11}{5}, \frac{22}{5} \right) = (2.2, 4.4)
$$

- **Perpendicular Component:**

$$
u_{\perp} = \left( \frac{4}{5}, -\frac{2}{5} \right) = (0.8, -0.4)
$$

- **Verification:** Both $u_{\parallel} + u_{\perp} = (3, 4) = u$ and $u_{\perp} \cdot v = 0$ are satisfied.
- **Independence Conclusion:** Check 1 validates additive completeness, while Check 2 validates geometric orthogonality; neither test implies the other.

---

## 6. Quick Verification

Verify that $u_{\parallel}$ is indeed a scalar multiple of $v$:

$$
u_{\parallel} = (2.2, 4.4) = 2.2(1, 2) = 2.2 v
$$

Since $2.2 = 11/5$, $u_{\parallel}$ is strictly collinear with $v$.
Verify norms via the Pythagorean theorem:
- $\|u\|^2 = 3^2 + 4^2 = 9 + 16 = 25$
- $\|u_{\parallel}\|^2 = \left(\frac{11}{5}\right)^2 + \left(\frac{22}{5}\right)^2 = \frac{121 + 484}{25} = \frac{605}{25} = 24.2$
- $\|u_{\perp}\|^2 = \left(\frac{4}{5}\right)^2 + \left(-\frac{2}{5}\right)^2 = \frac{16 + 4}{25} = \frac{20}{25} = 0.8$
- Sum of squares: $24.2 + 0.8 = 25 = \|u\|^2$.
The Pythagorean theorem holds with exact precision.

---

## 7. Common Mistakes to Avoid

1. **Arithmetic Slips with Fractions:**
   Converting $3$ to fifths as $12/5$ instead of $15/5$, or $4$ as $16/5$ instead of $20/5$.
2. **Assuming One Check Is Enough:**
   Checking only that $u_{\parallel} + u_{\perp} = u$ and skipping the dot product $u_{\perp} \cdot v = 0$.
3. **Sign Confusion in $u_{\perp}$:**
   Calculating $20 - 22 = +2$ instead of $-2$, resulting in an incorrect sign for the second coordinate.

---

## 8. How I Would Explain This in Class

> "Splitting a vector into parallel and perpendicular parts is like breaking down a diagonal force on a hill into the part pushing down the slope and the part pressing directly into the rock. Checking your answer requires two separate tests: first, do the two parts add back up to your original push? Second, does your perpendicular push form a true 90-degree angle with the slope? Checking one without the other is like checking that the pieces of a puzzle fit on the board without making sure they form the right picture."

