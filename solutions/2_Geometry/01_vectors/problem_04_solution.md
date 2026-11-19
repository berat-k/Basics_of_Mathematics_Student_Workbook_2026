# Problem 04: Dot Product and Perpendicularity

## 1. The Original Problem

For $u = (1, 2, -1)$ and $v = (2, -1, 3)$ compute $u \cdot v$ and determine whether the vectors are perpendicular. Then find $a$ so that $w = (2, -1, a)$ is perpendicular to $u$, and check the result.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the algebraic dot product $u \cdot v$.
2. Use the dot product value to determine whether $u$ and $v$ are perpendicular (orthogonal).
3. Set up the orthogonality condition between $u$ and the parametric vector $w = (2, -1, a)$.
4. Solve the resulting linear equation for the unknown parameter $a$.
5. Check the result by evaluating $w \cdot u$ with the calculated value of $a$.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Dot Product Formula:**
  For vectors $x = (x_1, x_2, x_3)$ and $y = (y_1, y_2, y_3)$ in $\mathbb{R}^3$, the dot product is:

$$
x \cdot y = x_1 y_1 + x_2 y_2 + x_3 y_3
$$

- **Orthogonality Criterion:**
  Geometrically, the dot product is related to the enclosed angle $\theta$ by:

$$
x \cdot y = \|x\| \|y\| \cos \theta
$$

  For two non-zero vectors, $\cos \theta = 0$ if and only if $\theta = 90^\circ = \pi/2 \text{ rad}$.
  Therefore:

$$
x \perp y \iff x \cdot y = 0
$$

  - If $x \cdot y = 0$, the vectors are perpendicular.
  - If $x \cdot y \neq 0$, the vectors are not perpendicular (acute if positive, obtuse if negative).

---

## 4. Step-by-Step Solution

### Step 1: Compute $u \cdot v$

Multiply corresponding components of $u = (1, 2, -1)$ and $v = (2, -1, 3)$ and add them:

$$
u \cdot v = (1)(2) + (2)(-1) + (-1)(3)
$$

Compute each product:

$$
(1)(2) = 2, \quad (2)(-1) = -2, \quad (-1)(3) = -3
$$

Sum the terms:

$$
u \cdot v = 2 - 2 - 3 = -3
$$

### Step 2: Determine Whether $u$ and $v$ Are Perpendicular

Compare the dot product value to zero:

$$
u \cdot v = -3 \neq 0
$$

Because the dot product is non-zero, the vectors $u$ and $v$ are **not perpendicular**.
Since $u \cdot v = -3 < 0$, $\cos \theta < 0$, which indicates that the angle between $u$ and $v$ is obtuse ($90^\circ < \theta < 180^\circ$).

---

### Step 3: Find $a$ Such That $w \perp u$

We are given $w = (2, -1, a)$. For $w$ to be perpendicular to $u = (1, 2, -1)$, their dot product must equal zero:

$$
w \cdot u = 0
$$

Express $w \cdot u$ in terms of coordinates:

$$
(2)(1) + (-1)(2) + (a)(-1) = 0
$$

Simplify each term:

$$
2 - 2 - a = 0
$$

Combine like terms:

$$
0 - a = 0 \implies -a = 0 \implies a = 0
$$

Thus, the parameter must be $a = 0$.

---

### Step 4: Check the Result

Substitute $a = 0$ into $w$ to get $w = (2, -1, 0)$. Now compute $w \cdot u$:

$$
w \cdot u = (2)(1) + (-1)(2) + (0)(-1) = 2 - 2 + 0 = 0
$$

Because $w \cdot u = 0$, the vector $w = (2, -1, 0)$ is verified to be perpendicular to $u$.

---

## 5. Final Answer & Conclusion

- **Dot Product:**

$$
u \cdot v = -3
$$

- **Perpendicularity:** $u$ and $v$ are **not perpendicular** (they form an obtuse angle).
- **Parameter Value:**

$$
a = 0
$$

- **Perpendicular Vector:**

$$
w = (2, -1, 0)
$$

- **Conclusion:** The dot product serves both as a diagnostic detector of orthogonality and as an algebraic equation builder to constrain unknown parameters.

---

## 6. Quick Verification

Calculate the actual angle between $u$ and $v$:
- $\|u\| = \sqrt{1^2 + 2^2 + (-1)^2} = \sqrt{1 + 4 + 1} = \sqrt{6}$
- $\|v\| = \sqrt{2^2 + (-1)^2 + 3^2} = \sqrt{4 + 1 + 9} = \sqrt{14}$
- $\cos \theta = \frac{u \cdot v}{\|u\| \|v\|} = \frac{-3}{\sqrt{6}\sqrt{14}} = \frac{-3}{\sqrt{84}} \approx \frac{-3}{9.165} \approx -0.3273$
- $\theta = \arccos(-0.3273) \approx 109.1^\circ$

Because $109.1^\circ \neq 90^\circ$, $u$ and $v$ are not perpendicular, confirming our algebraic deduction.

---

## 7. Common Mistakes to Avoid

1. **Multiplying Componentwise Without Summing:**
   Writing $u \cdot v = (2, -2, -3)$ as a vector. The dot product (scalar product) of two vectors is always a single scalar number, never a vector.
2. **Minus Sign Errors with Negative Components:**
   Computing $(a)(-1)$ as $a - 1$ instead of $-a$, or treating $(-1)(3)$ as $+3$.
3. **Assuming Orthogonality Implies $a$ Must Be Non-Zero:**
   Fearing that $a = 0$ is a "trivial" or invalid answer. A coordinate entry of $0$ simply means the vector lies parallel to a coordinate plane (here, the $xy$-plane).

---

## 8. How I Would Explain This in Class

> "The dot product is our mathematical right-angle detector: if two arrows meet at exactly 90 degrees, their shadow onto each other is zero, meaning their dot product collapses to 0. Since $u \cdot v = -3$, they don't form a right angle—in fact, the negative sign tells us they lean away from each other at an obtuse angle. To make a new vector $w$ perpendicular to $u$, we simply set up the equation $w \cdot u = 0$, which immediately forces the mystery dial $a$ to be 0."

