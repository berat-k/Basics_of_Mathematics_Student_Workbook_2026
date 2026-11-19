# Problem 14: Cone and Cylinder

## 1. The Original Problem

Compare

$$
x^2 + y^2 = z^2
$$

and

$$
x^2 + y^2 = 4.
$$

For each surface, describe the cross-sections $z = c$, $x = 0$, and $y = 0$, make a sketch, and explain why the radius of the cross-section depends on $z$ in the first case but is constant in the second.

---

## 2. What Are We Trying to Find?

We need to:
1. Analyze the first surface $S_1: x^2 + y^2 = z^2$ (circular cone) by finding its traces:
   - Horizontal cross-sections $z = c$.
   - Vertical cross-sections $x = 0$ ($yz$-plane) and $y = 0$ ($xz$-plane).
2. Analyze the second surface $S_2: x^2 + y^2 = 4$ (circular cylinder) by finding its traces:
   - Horizontal cross-sections $z = c$.
   - Vertical cross-sections $x = 0$ ($yz$-plane) and $y = 0$ ($xz$-plane).
3. Provide qualitative 3D sketches of both surfaces.
4. Explain clearly from algebraic and geometric viewpoints why the cross-sectional radius depends on the height $z$ in $S_1$ ($R(z) = |z|$), but remains strictly constant in $S_2$ ($R(z) = 2$).

---

## 3. Before Calculating: What Idea Do We Need?

- **Understanding Equations in $\mathbb{R}^3$ Missing a Variable:**
  When a spatial variable (such as $z$) is completely missing from an equation $F(x, y) = 0$, the constraint applies identically to every horizontal plane $z = c$. The 2D curve in the $xy$-plane is simply translated along the $z$-axis to form a **cylinder** whose generating lines (rulings) are parallel to the missing axis ($Oz$).
- **Homogeneous Quadratic Equations:**
  The equation $x^2 + y^2 - z^2 = 0$ is homogeneous of degree 2: if $(x, y, z)$ is on the surface, then for any scalar $k \in \mathbb{R}$, $(kx, ky, kz)$ also satisfies the equation:

$$
(kx)^2 + (ky)^2 - (kz)^2 = k^2(x^2 + y^2 - z^2) = 0.
$$

  Geometrically, this means the surface is formed by straight lines passing through the origin: it is a **cone** with vertex at $(0, 0, 0)$.
- **Radius as a Function of Height:**
  - In $S_1$, $x^2 + y^2 = z^2$ explicitly ties the sum of squares $x^2 + y^2$ to the square of height $z^2$. Slicing at $z = c$ yields $x^2 + y^2 = c^2$, so the radius is $R(c) = |c|$, which scales linearly with $|c|$.
  - In $S_2$, $x^2 + y^2 = 4$ sets the sum of squares to a fixed numerical constant $4$. Slicing at $z = c$ yields $x^2 + y^2 = 4$, so the radius is $R(c) = \sqrt{4} = 2$, completely independent of $c$.

---

## 4. Step-by-Step Solution

### Part 1: Detailed Analysis of Surface 1 ($S_1: x^2 + y^2 = z^2$)

#### 1. Horizontal Cross-Sections $z = c$:
Substitute $z = c$ into $x^2 + y^2 = z^2$:

$$
x^2 + y^2 = c^2
$$

- **For $c \ne 0$:**
  This is a **circle** in the horizontal plane $z = c$, centered at $(0, 0, c)$ with radius:

$$
R_1(c) = \sqrt{c^2} = |c|
$$

  The radius expands linearly as we move away from the $xy$-plane in either vertical direction:
  - At $z = 1$: circle of radius $1$.
  - At $z = 2$: circle of radius $2$.
  - At $z = -3$: circle of radius $3$.
- **For $c = 0$ ($xy$-plane):**

$$
x^2 + y^2 = 0 \implies x = 0, \quad y = 0
$$

  The cross-section collapses to the single point $(0, 0, 0)$, which is the **apex (vertex)** of the cone.

#### 2. Vertical Cross-Section $x = 0$ ($yz$-plane):
Substitute $x = 0$:

$$
0^2 + y^2 = z^2 \implies y^2 - z^2 = 0 \implies (y - z)(y + z) = 0
$$

This factors into two distinct linear equations:

$$
y = z \quad \text{or} \quad y = -z
$$

- **Description:** A **pair of intersecting lines** crossing at the origin $(0, 0, 0)$ with slopes $\pm 1$ ($45^\circ$ angles relative to the axes).

#### 3. Vertical Cross-Section $y = 0$ ($xz$-plane):
Substitute $y = 0$:

$$
x^2 + 0^2 = z^2 \implies x^2 - z^2 = 0 \implies (x - z)(x + z) = 0
$$

This factors into:

$$
x = z \quad \text{or} \quad x = -z
$$

- **Description:** An identical **pair of intersecting lines** crossing at the origin $(0, 0, 0)$ with slopes $\pm 1$.

#### Identification:
Surface 1 is a **circular double cone** (right circular cone) with vertex at $(0, 0, 0)$ and vertical axis along $Oz$. It consists of an upper nappe ($z \ge 0$) and a lower nappe ($z \le 0$) meeting tip-to-tip at the origin.

---

### Part 2: Detailed Analysis of Surface 2 ($S_2: x^2 + y^2 = 4$)

#### 1. Horizontal Cross-Sections $z = c$:
Substitute $z = c$ into $x^2 + y^2 = 4$:

$$
x^2 + y^2 = 4
$$

- **Description:** For **every** value of $c \in \mathbb{R}$, this is a **circle** in the horizontal plane $z = c$, centered at $(0, 0, c)$ with constant radius:

$$
R_2(c) = \sqrt{4} = 2
$$

  The cross-section is identical at all heights:
  - At $z = 0$: circle of radius $2$.
  - At $z = 5$: circle of radius $2$.
  - At $z = -10$: circle of radius $2$.

#### 2. Vertical Cross-Section $x = 0$ ($yz$-plane):
Substitute $x = 0$:

$$
0^2 + y^2 = 4 \implies y^2 = 4 \implies y = 2 \quad \text{or} \quad y = -2
$$

- **Description:** A **pair of parallel vertical lines** in the $yz$-plane, parallel to the $z$-axis:

$$
\text{Line 1: } (0, 2, z), \quad \text{Line 2: } (0, -2, z) \quad \text{for } z \in \mathbb{R}.
$$

#### 3. Vertical Cross-Section $y = 0$ ($xz$-plane):
Substitute $y = 0$:

$$
x^2 + 0^2 = 4 \implies x^2 = 4 \implies x = 2 \quad \text{or} \quad x = -2
$$

- **Description:** A **pair of parallel vertical lines** in the $xz$-plane, parallel to the $z$-axis:

$$
\text{Line 1: } (2, 0, z), \quad \text{Line 2: } (-2, 0, z) \quad \text{for } z \in \mathbb{R}.
$$

#### Identification:
Surface 2 is a **right circular cylinder** with vertical axis along $Oz$ and fixed radius $R = 2$. It extends infinitely in both vertical directions without widening or tapering.

---

### Part 3: Why Does the Radius Depend on $z$ in $S_1$ but is Constant in $S_2$?

1. **Algebraic Reason:**
   - In the cylinder equation $x^2 + y^2 = 4$, the coordinate $z$ does not appear anywhere. This means that whatever value $z$ takes, it imposes no restriction on $x$ and $y$, and conversely, $x$ and $y$ are constrained to satisfy $x^2 + y^2 = 4$ uniformly. Thus, the radius is constant: $R_2(z) = \sqrt{4} = 2$.
   - In the cone equation $x^2 + y^2 = z^2$, the coordinate $z$ is explicitly tied to the sum of squares. When $z$ varies, the value of $z^2$ changes, directly prescribing the radius: $R_1(z) = \sqrt{z^2} = |z|$. The radius is proportional to the distance from the $xy$-plane.

2. **Geometric / Symmetry Reason:**
   - The cylinder possesses **translational symmetry** along the $z$-axis: shifting the surface vertically by any displacement vector $\vec{v} = (0, 0, \Delta z)$ maps the surface onto itself. Therefore, its cross-section cannot vary with height.
   - The cone possesses **dilation (scale) symmetry** centered at the origin: scaling coordinates by a factor $k > 0$ maps the point $(x, y, z)$ to $(kx, ky, kz)$, which remains on the cone. This scale invariance dictates that the cross-sectional size must be directly proportional to the scale parameter, which is the height $|z|$.

---

### Part 4: Qualitative Sketches

#### Sketch of Surface 1: $x^2 + y^2 = z^2$ (Double Cone)
```
         z
         ^
       \   /          <- circular slice at z = c > 0 (radius R = c)
        \ /
         *            <- apex at origin (0, 0, 0) (radius R = 0)
        / \
       /   \          <- circular slice at z = -c < 0 (radius R = |c|)
         |
    -----+-----> x / y
```
- Vertical profile is formed by two intersecting straight lines $z = \pm r$ crossing at the origin.
- Cross-sections are circles expanding linearly away from the origin in both vertical directions.

#### Sketch of Surface 2: $x^2 + y^2 = 4$ (Cylinder)
```
         z
         ^
       |   |          <- circular slice at z = c (radius R = 2)
       |   |
       |   |          <- circular slice at z = 0 (radius R = 2)
       |   |
       |   |          <- circular slice at z = -c (radius R = 2)
         |
    -----+-----> x / y
```
- Vertical profile is formed by two parallel straight lines $r = \pm 2$.
- Cross-sections are identical circles of fixed radius $R = 2$ at every height $z$.

---

## 5. Final Answer & Conclusion

### Summary Comparison Table:

| Property | Surface 1: $x^2 + y^2 = z^2$ | Surface 2: $x^2 + y^2 = 4$ |
| :--- | :--- | :--- |
| **Section $z = c$ ($c \ne 0$)** | Circle of radius $R(c) = \|c\|$ | Circle of constant radius $R = 2$ |
| **Section $z = 0$** | Single point $(0, 0, 0)$ (apex) | Circle of radius $R = 2$ |
| **Section $x = 0$ ($yz$-plane)** | Two intersecting lines: $y = \pm z$ | Two parallel vertical lines: $y = \pm 2$ |
| **Section $y = 0$ ($xz$-plane)** | Two intersecting lines: $x = \pm z$ | Two parallel vertical lines: $x = \pm 2$ |
| **Dependency on $z$** | $R(z) = \|z\|$ (linear growth) | $R(z) = 2$ (constant, independent of $z$) |
| **Mathematical Name** | **Right Circular Cone** | **Right Circular Cylinder** |

---

## 6. Quick Verification

1. **Test Points on $S_1$:**
   - At $z = 0$, $(0, 0, 0)$ gives $0^2 + 0^2 = 0^2$ (true).
   - At $z = 5$, $(3, 4, 5)$ gives $3^2 + 4^2 = 9 + 16 = 25 = 5^2$ (true, radius is $5$).
   - At $z = -5$, $(3, 4, -5)$ gives $3^2 + 4^2 = 25 = (-5)^2$ (true, radius is $|-5| = 5$).
2. **Test Points on $S_2$:**
   - At $z = 0$, $(\sqrt{2}, \sqrt{2}, 0)$ gives $(\sqrt{2})^2 + (\sqrt{2})^2 = 2 + 2 = 4$ (true).
   - At $z = 100$, $(\sqrt{2}, \sqrt{2}, 100)$ gives $2 + 2 = 4$ (true).
   - The height $z$ has zero effect on whether a point lies on the cylinder.

---

## 7. Common Mistakes to Avoid

1. **Thinking the Cone is Just a Single Cone:**
   The equation $x^2 + y^2 = z^2$ produces both $z = \sqrt{x^2 + y^2}$ (upper cone) and $z = -\sqrt{x^2 + y^2}$ (lower cone). It is a **double cone**.
2. **Confusing Intersecting Lines with Parallel Lines:**
   In $S_1$, setting $x = 0$ gives $y^2 = z^2 \implies y = \pm z$ (lines meet at the origin). In $S_2$, setting $x = 0$ gives $y^2 = 4 \implies y = \pm 2$ (lines never meet; they are parallel).
3. **Assuming Missing $z$ Means $z = 0$:**
   In 3D analytical geometry, when $z$ does not appear in $x^2 + y^2 = 4$, it means $z$ can take **any** real value ($-\infty < z < \infty$), generating a 3D cylindrical surface, not just a 2D circle on the floor.

---

## 8. How I Would Explain This in Class

> "Imagine holding a circular hoop.
> In the equation $x^2 + y^2 = 4$, the variable $z$ is nowhere to be seen. That means no matter how high or low you lift the hoop along the $z$-axis, its radius must always be $2$. Stacking those identical circles from bottom to top creates a tin can or pipe—a cylinder!
> Now look at $x^2 + y^2 = z^2$. Here $z$ is on the other side of the equal sign. At height $z = 0$, the hoop shrinks to a single point. As you move up to $z = 1, 2, 3$, the radius expands to $1, 2, 3$. As you move down to $z = -1, -2, -3$, it expands again to $1, 2, 3$. That creates two party hats touching tip-to-tip at the origin—a double cone!"
