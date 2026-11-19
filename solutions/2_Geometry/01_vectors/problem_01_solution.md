# Problem 01: Vector Operations and Their Meaning

## 1. The Original Problem

For $u = (2, -1, 3)$ and $v = (-1, 4, 2)$ compute

$$
u + v, \qquad u - v, \qquad 3u - 2v.
$$

Then verify that $(u + v) - v = u$, and explain geometrically what adding two vectors means.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the componentwise vector sum $u + v$.
2. Compute the componentwise vector difference $u - v$.
3. Compute the linear combination $3u - 2v$.
4. Verify algebraically that subtracting $v$ from the sum vector $(u + v)$ recovers the original vector $u$.
5. Provide a clear geometric interpretation of vector addition using displacement and the head-to-tail / parallelogram rules.

---

## 3. Before Calculating: What Idea Do We Need?

- **Componentwise Operations in $\mathbb{R}^3$:**
  For any vectors $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$ and scalars $c, d \in \mathbb{R}$:
  - Addition: $u + v = (u_1 + v_1, u_2 + v_2, u_3 + v_3)$
  - Subtraction: $u - v = (u_1 - v_1, u_2 - v_2, u_3 - v_3)$
  - Scalar Multiplication: $c u = (c u_1, c u_2, c u_3)$
- **Inverse Operations:**
  Vector addition forms an abelian group under addition; the operation of subtracting $v$ is the addition of the additive inverse $-v$. Thus, $(u + v) - v = u + (v - v) = u + \mathbf{0} = u$.
- **Geometric Meaning of Addition:**
  A vector represents a translation (displacement) in space. Adding vector $v$ to vector $u$ corresponds to applying displacement $u$ first, and then, starting from the tip of $u$, applying displacement $v$. The resultant vector $u + v$ connects the initial starting point to the final endpoint (the **head-to-tail rule**). Equivalently, it forms the main diagonal of the parallelogram determined by $u$ and $v$.

---

## 4. Step-by-Step Solution

### Step 1: Compute $u + v$

Add the corresponding coordinates of $u = (2, -1, 3)$ and $v = (-1, 4, 2)$:

$$
u + v = (2 + (-1), -1 + 4, 3 + 2) = (1, 3, 5)
$$

### Step 2: Compute $u - v$

Subtract each coordinate of $v$ from the corresponding coordinate of $u$:

$$
u - v = (2 - (-1), -1 - 4, 3 - 2) = (2 + 1, -5, 1) = (3, -5, 1)
$$

### Step 3: Compute $3u - 2v$

1. Scale $u$ by $3$:

$$
3u = 3(2, -1, 3) = (6, -3, 9)
$$

2. Scale $v$ by $2$:

$$
2v = 2(-1, 4, 2) = (-2, 8, 4)
$$

3. Subtract $2v$ from $3u$:

$$
3u - 2v = (6 - (-2), -3 - 8, 9 - 4) = (6 + 2, -11, 5) = (8, -11, 5)
$$

### Step 4: Verify that $(u + v) - v = u$

Take the calculated sum $u + v = (1, 3, 5)$ and subtract $v = (-1, 4, 2)$:

$$
(u + v) - v = (1 - (-1), 3 - 4, 5 - 2) = (1 + 1, -1, 3) = (2, -1, 3)
$$

This matches $u = (2, -1, 3)$ component by component:

$$
(2, -1, 3) = u
$$

The identity is verified.

---

### Step 5: Geometric Interpretation of Vector Addition

Geometrically, a vector represents a directed displacement from an initial position to a final position:
- If an object begins at an arbitrary point $P_0$ in space and undergoes displacement $u$, it arrives at point $P_1 = P_0 + u$.
- If the object subsequently undergoes displacement $v$ starting from $P_1$, its new position is $P_2 = P_1 + v = P_0 + u + v$.
- The net displacement directly from $P_0$ to $P_2$ is represented by the single vector $u + v$.
- In the **head-to-tail (triangle) rule**, placing the tail of $v$ at the head of $u$ makes $u + v$ the directed segment from the tail of $u$ to the head of $v$.
- In the **parallelogram rule**, placing both $u$ and $v$ with a common tail makes $u + v$ the diagonal of the parallelogram spanning between them.

---

## 5. Final Answer & Conclusion

- **Calculated Vectors:**

$$
u + v = (1, 3, 5)
$$

$$
u - v = (3, -5, 1)
$$

$$
3u - 2v = (8, -11, 5)
$$

- **Verification:** $(u + v) - v = (1, 3, 5) - (-1, 4, 2) = (2, -1, 3) = u$.
- **Geometric Conclusion:** Adding two vectors corresponds to chaining successive spatial displacements together (head-to-tail), yielding the net cumulative translation from start to finish.

---

## 6. Quick Verification

Verify $3u - 2v$ algebraically by rearranging:

$$
(3u - 2v) + 2v = (8, -11, 5) + 2(-1, 4, 2) = (8 - 2, -11 + 8, 5 + 4) = (6, -3, 9) = 3(2, -1, 3) = 3u
$$

Since $(3u - 2v) + 2v = 3u$, the linear combination is confirmed.

---

## 7. Common Mistakes to Avoid

1. **Sign Errors with Negative Coordinates:**
   When subtracting negative coordinates, forgetting that $2 - (-1) = 2 + 1 = 3$, or computing $6 - (-2)$ as $4$ instead of $8$.
2. **Mixing Up Vector Order in Subtraction:**
   Computing $v - u$ instead of $u - v$. Note that $v - u = -(u - v) = (-3, 5, -1)$.
3. **Confusing Points with Displacements:**
   Treating vectors purely as fixed static points rather than directed translations that can be chained together anywhere in space.

---

## 8. How I Would Explain This in Class

> "Think of vector addition as taking consecutive walking steps: if vector $u$ takes you 2 steps east, 1 step south, and 3 steps up, and vector $v$ then takes you 1 step west, 4 steps north, and 2 steps up, your total journey is the sum $(1, 3, 5)$. If you then take the exact reverse of step $v$, you must inevitably end up back at the end of step $u$, which explains why $(u + v) - v = u$ both mathematically and physically."

