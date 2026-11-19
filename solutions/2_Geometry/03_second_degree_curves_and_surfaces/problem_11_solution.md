# Problem 11: Two Similar Surfaces

## 1. The Original Problem

Compare

$$
x^2 + y^2 - z^2 = 1
$$

and

$$
x^2 + y^2 - z^2 = -1.
$$

For several values $z = c$, check whether the cross-section exists and what its radius is. Based on this, describe qualitatively the difference between the surfaces and make sketches.

---

## 2. What Are We Trying to Find?

We need to:
1. Examine the horizontal cross-sections $z = c$ for both surfaces:
   - Surface 1: $S_1: x^2 + y^2 - z^2 = 1$
   - Surface 2: $S_2: x^2 + y^2 - z^2 = -1$
2. For specific test values of $c$ (e.g., $c = 0$, $c = \pm 0.5$, $c = \pm 1$, $c = \pm 2$, $c = \pm 3$), determine whether real cross-sections exist and compute their circular radii $R(c)$.
3. Compare the geometric behavior of both surfaces based on these cross-sections:
   - Identify which surface is connected into a single body and which consists of two disconnected components.
   - Name the surfaces (**hyperboloid of one sheet** vs. **hyperboloid of two sheets**).
4. Provide qualitative sketches and visual descriptions of both shapes.

---

## 3. Before Calculating: What Idea Do We Need?

- **Analyzing Surfaces via Horizontal Slices ($z = c$):**
  By fixing the vertical height $z = c$, we intersect the 3D surface with the horizontal plane $z = c$. The resulting 2D curve in the $(x, y)$-plane has the equation:
  - For $S_1$: $x^2 + y^2 = 1 + c^2$.
  - For $S_2$: $x^2 + y^2 = c^2 - 1$.
- **Condition for Real Solutions:**
  Since $x^2 + y^2 \ge 0$ for all real coordinates $(x, y)$:
  - If the right-hand side is strictly positive ($> 0$), the slice is a non-degenerate circle with radius $R = \sqrt{\text{RHS}}$.
  - If the right-hand side is zero ($= 0$), the slice is a single degenerate point $(0, 0, c)$ (radius $R = 0$).
  - If the right-hand side is strictly negative ($< 0$), no real points satisfy the equation; the cross-section is the empty set ($\emptyset$).
- **One Sheet vs. Two Sheets:**
  - In $S_1$, $1 + c^2 \ge 1 > 0$ for **all** $c \in \mathbb{R}$. Slices exist at every height without any interruption, producing an unbroken, hourglass-shaped tube: a **hyperboloid of one sheet**.
  - In $S_2$, $c^2 - 1 \ge 0$ requires $|c| \ge 1$. For $|c| < 1$, there is an empty gap where the surface does not exist. The surface splits into two separate cups: a **hyperboloid of two sheets**.

---

## 4. Step-by-Step Solution

### Part 1: Horizontal Cross-Sections of Surface 1 ($x^2 + y^2 - z^2 = 1$)

Rewrite the equation to express the horizontal cross-section at height $z = c$:

$$
x^2 + y^2 = 1 + c^2
$$

Because $c^2 \ge 0$ for all real numbers $c$, we have:

$$
1 + c^2 \ge 1 > 0 \quad \text{for all } c \in \mathbb{R}.
$$

Therefore, a real cross-section exists at every height $z = c$, and it is always a circle centered at $(0, 0, c)$ with radius:

$$
R_1(c) = \sqrt{1 + c^2}
$$

Let us evaluate $R_1(c)$ for several representative values of $c$:

1. **At $c = 0$ (the waist / $xy$-plane):**
   $$
   x^2 + y^2 = 1 + 0^2 = 1 \implies R_1(0) = \sqrt{1} = 1
   $$
   The slice is a circle of radius $1$. This is the **narrowest point (waist)** of the entire surface.

2. **At $c = \pm 0.5$:**
   $$
   x^2 + y^2 = 1 + (0.5)^2 = 1 + 0.25 = 1.25 \implies R_1(\pm 0.5) = \sqrt{1.25} \approx 1.118
   $$
   The cross-section is a circle with radius slightly larger than $1$.

3. **At $c = \pm 1$:**
   $$
   x^2 + y^2 = 1 + (\pm 1)^2 = 2 \implies R_1(\pm 1) = \sqrt{2} \approx 1.414
   $$

4. **At $c = \pm 2$:**
   $$
   x^2 + y^2 = 1 + (\pm 2)^2 = 5 \implies R_1(\pm 2) = \sqrt{5} \approx 2.236
   $$

5. **At $c = \pm 3$:**
   $$
   x^2 + y^2 = 1 + (\pm 3)^2 = 10 \implies R_1(\pm 3) = \sqrt{10} \approx 3.162
   $$

As $|c| \to \infty$, the radius $R_1(c) \approx |c|$ grows without bound. The surface is smooth, connected, and has no gaps. It is known as a **hyperboloid of one sheet** (or one-sheeted hyperboloid).

---

### Part 2: Horizontal Cross-Sections of Surface 2 ($x^2 + y^2 - z^2 = -1$)

Rewrite the equation to isolate the horizontal cross-section at height $z = c$:

$$
x^2 + y^2 = c^2 - 1
$$

Since $x^2 + y^2 \ge 0$, a real solution exists if and only if:

$$
c^2 - 1 \ge 0 \iff c^2 \ge 1 \iff |c| \ge 1.
$$

Let us evaluate this for the same values of $c$:

1. **At $c = 0$ ($xy$-plane):**
   $$
   x^2 + y^2 = 0^2 - 1 = -1 < 0
   $$
   The sum of two squares cannot equal $-1$ in real numbers. **The cross-section does not exist (empty set $\emptyset$).**

2. **At $c = \pm 0.5$:**
   $$
   x^2 + y^2 = (0.5)^2 - 1 = 0.25 - 1 = -0.75 < 0
   $$
   **The cross-section does not exist (empty set $\emptyset$).**

3. **At $c = \pm 1$ (the vertices):**
   $$
   x^2 + y^2 = (\pm 1)^2 - 1 = 0 \implies x = 0, \quad y = 0
   $$
   The cross-sections are single points: $(0, 0, 1)$ on the upper sheet, and $(0, 0, -1)$ on the lower sheet. The radius is $R_2(\pm 1) = 0$.

4. **At $c = \pm 2$:**
   $$
   x^2 + y^2 = (\pm 2)^2 - 1 = 4 - 1 = 3 \implies R_2(\pm 2) = \sqrt{3} \approx 1.732
   $$
   The cross-sections are circles of radius $\sqrt{3}$.

5. **At $c = \pm 3$:**
   $$
   x^2 + y^2 = (\pm 3)^2 - 1 = 9 - 1 = 8 \implies R_2(\pm 3) = \sqrt{8} = 2\sqrt{2} \approx 2.828
   $$
   The cross-sections are circles of radius $2\sqrt{2}$.

For any height $-1 < c < 1$, no points of the surface exist. The surface is divided into two separate, non-connecting sheets:
- An upper sheet opening upward for $z \ge 1$, with vertex at $(0, 0, 1)$.
- A lower sheet opening downward for $z \le -1$, with vertex at $(0, 0, -1)$.

This surface is known as a **hyperboloid of two sheets** (or two-sheeted hyperboloid).

---

### Part 3: Qualitative Sketches and Visual Representation

#### Sketch of Surface 1: $x^2 + y^2 - z^2 = 1$ (One Sheet)
```
         z
         ^
       \   /          <- circular slice at z = 3  (R = sqrt(10))
        \ /           <- circular slice at z = 1  (R = sqrt(2))
        | |           <- waist circle at z = 0    (R = 1)
        / \           <- circular slice at z = -1 (R = sqrt(2))
       /   \          <- circular slice at z = -3 (R = sqrt(10))
         |
    -----+-----> x / y
```
- A single unbroken cooling-tower / hourglass shape.
- Connected across the plane $z = 0$, where the radius attains its minimum value $R = 1$.

#### Sketch of Surface 2: $x^2 + y^2 - z^2 = -1$ (Two Sheets)
```
         z
         ^
       \   /          <- upper circular slice at z = 3 (R = sqrt(8))
        \ /           <- upper circular slice at z = 2 (R = sqrt(3))
         *            <- upper apex / vertex at (0, 0, 1) (R = 0)
         |
      [ GAP ]         <- NO POINTS for -1 < z < 1
         |
         *            <- lower apex / vertex at (0, 0, -1) (R = 0)
        / \           <- lower circular slice at z = -2 (R = sqrt(3))
       /   \          <- lower circular slice at z = -3 (R = sqrt(8))
    -----+-----> x / y
```
- Two separate symmetrical bowls pointing away from each other.
- Separated by an empty horizontal gap of height $\Delta z = 2$ centered at the origin.

---

## 5. Final Answer & Conclusion

### Summary Comparison Table:

| Height $z = c$ | Surface 1: $x^2 + y^2 - z^2 = 1$ ($R_1 = \sqrt{1 + c^2}$) | Surface 2: $x^2 + y^2 - z^2 = -1$ ($R_2 = \sqrt{c^2 - 1}$) |
| :--- | :--- | :--- |
| **$c = 0$** | Exists, Circle of radius $R = 1$ (waist) | **Does not exist** ($\emptyset$) |
| **$c = \pm 0.5$** | Exists, Circle of radius $R = \sqrt{1.25} \approx 1.118$ | **Does not exist** ($\emptyset$) |
| **$c = \pm 1$** | Exists, Circle of radius $R = \sqrt{2} \approx 1.414$ | Exists, **Single points** $(0, 0, \pm 1)$ ($R = 0$) |
| **$c = \pm 2$** | Exists, Circle of radius $R = \sqrt{5} \approx 2.236$ | Exists, Circle of radius $R = \sqrt{3} \approx 1.732$ |
| **$c = \pm 3$** | Exists, Circle of radius $R = \sqrt{10} \approx 3.162$ | Exists, Circle of radius $R = \sqrt{8} \approx 2.828$ |

### Qualitative Differences:
1. **Connectivity:** $S_1$ is a single connected surface (**Hyperboloid of One Sheet**). $S_2$ consists of two disconnected components (**Hyperboloid of Two Sheets**).
2. **Existence around the Equator:** $S_1$ intersects the plane $z = 0$ in the circle $x^2 + y^2 = 1$. $S_2$ has an empty gap for $-1 < z < 1$ with no real points.
3. **Vertices / Extrema along $z$:** $S_1$ has no vertices along the $z$-axis (the $z$-axis does not intersect the surface). $S_2$ intersects the $z$-axis at two vertices: $(0, 0, 1)$ and $(0, 0, -1)$.

---

## 6. Quick Verification

1. **Intersection with Coordinate Axes:**
   - On $S_1$: Setting $x = y = 0$ yields $-z^2 = 1 \implies z^2 = -1$ (no real solutions). Hence, the $z$-axis never intersects $S_1$. Setting $y = z = 0$ yields $x^2 = 1 \implies x = \pm 1$ (intersects the $x$-axis at $(\pm 1, 0, 0)$).
   - On $S_2$: Setting $x = y = 0$ yields $-z^2 = -1 \implies z^2 = 1 \implies z = \pm 1$ (intersects the $z$-axis at $(0, 0, \pm 1)$). Setting $y = z = 0$ yields $x^2 = -1$ (no real solutions; does not intersect $x$-axis or $y$-axis).
   This confirms that $S_1$ encircles the $z$-axis like a sleeve, while $S_2$ consists of two caps pierced by the $z$-axis.

2. **Asymptotic Cone:**
   Both surfaces share the same asymptotic cone:
   $$
   x^2 + y^2 - z^2 = 0 \implies x^2 + y^2 = z^2.
   $$
   For large $|c|$, both $R_1(c) = \sqrt{c^2 + 1}$ and $R_2(c) = \sqrt{c^2 - 1}$ approach the cone's radius $R_{\text{cone}}(c) = |c|$:
   $$
   \lim_{|c| \to \infty} (\sqrt{c^2 + 1} - |c|) = 0, \quad \lim_{|c| \to \infty} (|c| - \sqrt{c^2 - 1}) = 0.
   $$
   This verifies that both surfaces asymptotically approach the same circular cone from opposite sides.

---

## 7. Common Mistakes to Avoid

1. **Confusing One-Sheeted and Two-Sheeted Hyperboloids from the Right-Hand Sign:**
   Remember that $+1$ on the right ($x^2 + y^2 - z^2 = +1$) leaves the waist circle $x^2 + y^2 = 1$ when $z = 0$, giving **one continuous sheet**. A $-1$ ($x^2 + y^2 - z^2 = -1$) forces $z^2 = x^2 + y^2 + 1 \ge 1$, forbidding $z$ from entering the range $(-1, 1)$, which tears the surface into **two sheets**.
2. **Assuming $R(c) = c^2 - 1$ Instead of $\sqrt{c^2 - 1}$:**
   The radius is the square root of the right-hand side, not the right-hand side itself.
3. **Overlooking the Single Points at $|c| = 1$:**
   At $c = \pm 1$, the cross-section is not empty; it is a single point $(0, 0, \pm 1)$, which serves as the apex (vertex) of each sheet.

---

## 8. How I Would Explain This in Class

> "Look at the equations $x^2 + y^2 - z^2 = 1$ and $x^2 + y^2 - z^2 = -1$. They differ by just one sign, but that minus sign splits the universe! If you rewrite them as $x^2 + y^2 = 1 + z^2$ and $x^2 + y^2 = z^2 - 1$, slice both with a horizontal knife at height $z = c$. For the first equation, $1 + z^2$ is always at least $1$, so every slice is a circle—at $z = 0$, you get a circle of radius $1$. That's the waist of a cooling tower: a single unbroken surface, the hyperboloid of one sheet. For the second equation, $z^2 - 1$ can be negative. If you slice between $z = -1$ and $z = 1$, the knife hits empty space! The surface only begins at $z = 1$ (growing upward) and at $z = -1$ (growing downward). That gap splits the surface into two separate bowls: the hyperboloid of two sheets."
