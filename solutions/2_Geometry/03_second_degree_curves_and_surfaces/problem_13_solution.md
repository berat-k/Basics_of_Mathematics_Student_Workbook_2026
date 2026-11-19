# Problem 13: Intersection of a Sphere and a Plane

## 1. The Original Problem

Given the sphere

$$
x^2 + y^2 + z^2 = 25
$$

and the plane $z = 3$, find the equation of the intersection curve and its radius. Then describe what happens for $z = c$ depending on $c$.

---

## 2. What Are We Trying to Find?

We need to:
1. Determine the intersection curve of the sphere $x^2 + y^2 + z^2 = 25$ with the horizontal plane $z = 3$:
   - Write its 2D and 3D equations.
   - Find the geometric shape, the center, and the exact radius of this curve.
2. Generalize the intersection for any horizontal plane $z = c$:
   - Solve $x^2 + y^2 + c^2 = 25 \implies x^2 + y^2 = 25 - c^2$.
   - Classify all possible geometric outcomes depending on the parameter $c \in \mathbb{R}$:
     - When is the intersection a non-degenerate circle?
     - When is it a single point (tangent plane)?
     - When is it empty ($\emptyset$, plane misses the sphere)?
3. Explain the geometry using the 3D Pythagorean theorem (distance from center to cutting plane).

---

## 3. Before Calculating: What Idea Do We Need?

- **The Geometry of Slicing a Sphere:**
  A sphere centered at the origin with radius $R_{\text{sphere}} = 5$ has equation $x^2 + y^2 + z^2 = 5^2$.
  Any plane at a perpendicular distance $d = |c|$ from the center intersects the sphere if and only if $d \le R_{\text{sphere}}$.
- **The Right-Triangle Relation:**
  Consider the center of the sphere $O(0, 0, 0)$, the center of the cross-section $C(0, 0, c)$, and any point $P(x, y, c)$ on the intersection curve:
  - The vector $\vec{OC}$ has length $|c|$ (the vertical distance).
  - The vector $\vec{CP}$ has length $r$ (the cross-sectional radius).
  - The vector $\vec{OP}$ has length $R = 5$ (the sphere radius).
  Because $\vec{OC} \perp \vec{CP}$, by the Pythagorean theorem:
  $$
  r^2 + c^2 = R^2 \implies r^2 + c^2 = 25 \implies r = \sqrt{25 - c^2}.
  $$
- **Algebraic Interpretation:**
  Substituting $z = c$ directly into $x^2 + y^2 + z^2 = 25$ yields:
  $$
  x^2 + y^2 = 25 - c^2.
  $$
  The nature of the solution set depends entirely on the sign of $25 - c^2$:
  - $25 - c^2 > 0 \iff |c| < 5$: a circle of radius $r(c) = \sqrt{25 - c^2}$.
  - $25 - c^2 = 0 \iff |c| = 5$: a single point (radius $0$).
  - $25 - c^2 < 0 \iff |c| > 5$: no real points ($\emptyset$).

---

## 4. Step-by-Step Solution

### Part 1: Intersection with the Specific Plane $z = 3$

#### Step 1: Substitute $z = 3$ into the Sphere Equation
The sphere is given by:

$$
x^2 + y^2 + z^2 = 25
$$

Setting $z = 3$:

$$
x^2 + y^2 + 3^2 = 25 \implies x^2 + y^2 + 9 = 25 \implies x^2 + y^2 = 16
$$

#### Step 2: Describe the Curve and Its Features
- In the plane $z = 3$, the equation $x^2 + y^2 = 16 = 4^2$ represents a **circle**.
- **Center of the circle:**
  The center lies on the $z$-axis at $x = 0, y = 0, z = 3$, which is the point:
  $$
  C(0, 0, 3)
  $$
- **Radius of the circle:**
  $$
  r = \sqrt{16} = 4
  $$
- **Full 3D specification of the curve:**
  In 3D space, a curve is defined as the intersection of two surfaces:
  $$
  \begin{cases}
  x^2 + y^2 = 16 \\\\
  z = 3
  \end{cases}
  $$
  Or in parametric form with parameter $\theta \in [0, 2\pi)$:
  $$
  \begin{cases}
  x = 4 \cos\theta \\\\
  y = 4 \sin\theta \\\\
  z = 3
  \end{cases}
  $$

---

### Part 2: General Case: Intersection with $z = c$

Substitute an arbitrary real constant $z = c$ into the sphere equation:

$$
x^2 + y^2 + c^2 = 25 \implies x^2 + y^2 = 25 - c^2
$$

Since $x^2 + y^2 \ge 0$ for all real coordinates $(x, y)$, the geometric nature of the intersection depends on the sign of the quantity $25 - c^2$:

$$
25 - c^2 = (5 - c)(5 + c)
$$

We examine the three mutually exclusive cases:

#### Case 1: $|c| < 5$ (Strictly Inside the Sphere, $-5 < c < 5$)
Here $c^2 < 25$, so $25 - c^2 > 0$.
- The intersection is a non-degenerate **circle** lying in the horizontal plane $z = c$.
- **Center:** $C(0, 0, c)$ on the vertical axis.
- **Radius:**
  $$
  r(c) = \sqrt{25 - c^2}
  $$
- **Notable values:**
  - At the equator ($c = 0$): $r(0) = \sqrt{25} = 5$ (the great circle / maximum possible cross-section).
  - At $c = \pm 3$: $r(\pm 3) = \sqrt{25 - 9} = \sqrt{16} = 4$.
  - At $c = \pm 4$: $r(\pm 4) = \sqrt{25 - 16} = \sqrt{9} = 3$.
  - As $|c| \to 5$, the radius shrinks smoothly toward $0$.

#### Case 2: $|c| = 5$ (Tangent Planes at the Poles, $c = 5$ or $c = -5$)
Here $c^2 = 25$, so $25 - c^2 = 0$.
The equation becomes:

$$
x^2 + y^2 = 0 \implies x = 0 \quad \text{and} \quad y = 0.
$$

- For $c = 5$: The intersection is the single point $(0, 0, 5)$ (the North Pole of the sphere).
- For $c = -5$: The intersection is the single point $(0, 0, -5)$ (the South Pole of the sphere).
- Geometrically, the planes $z = 5$ and $z = -5$ are **tangent planes** to the sphere. The intersection has radius $r = 0$.

#### Case 3: $|c| > 5$ (Outside the Sphere, $c > 5$ or $c < -5$)
Here $c^2 > 25$, so $25 - c^2 < 0$.
The equation becomes:

$$
x^2 + y^2 = \text{negative number} < 0
$$

Since the sum of two real squares $x^2 + y^2 \ge 0$ cannot be negative, there are no real solutions.
- The intersection is the **empty set** ($\emptyset$).
- Geometrically, the plane lies entirely outside the sphere and does not meet it.

---

## 5. Final Answer & Conclusion

### 1. Intersection with the Plane $z = 3$:
- **Equation of the curve:** $x^2 + y^2 = 16$ in the plane $z = 3$ (or system $\{x^2 + y^2 = 16,\ z = 3\}$).
- **Geometric Nature:** A circle centered at $(0, 0, 3)$ with radius $r = 4$.

### 2. General Classification for $z = c$:

| Condition on $c$ | Sign of $25 - c^2$ | Geometric Result | Center | Radius $r(c)$ |
| :--- | :--- | :--- | :--- | :--- |
| **$-5 < c < 5$ ($|c| < 5$)** | Positive ($> 0$) | **Circle** | $(0, 0, c)$ | $\sqrt{25 - c^2}$ |
| **$c = 5$** | Zero ($= 0$) | **Single Point** (North Pole) | $(0, 0, 5)$ | $0$ (tangent plane) |
| **$c = -5$** | Zero ($= 0$) | **Single Point** (South Pole) | $(0, 0, -5)$ | $0$ (tangent plane) |
| **$c > 5$ or $c < -5$ ($|c| > 5$)** | Negative ($< 0$) | **Empty Set** ($\emptyset$) | None | Does not exist |

---

## 6. Quick Verification

1. **Pythagorean 3-4-5 Triangle:**
   At $z = 3$, the vertical distance from the origin is $d = 3$. The sphere's radius is $R = 5$.
   By the classic 3-4-5 right triangle:
   $$
   d^2 + r^2 = R^2 \implies 3^2 + 4^2 = 9 + 16 = 25 = 5^2.
   $$
   This immediately confirms $r = 4$.

2. **Equatorial Extreme:**
   At $c = 0$, $r(0) = \sqrt{25 - 0} = 5 = R_{\text{sphere}}$.
   A plane passing through the center of a sphere cuts it into a great circle of radius equal to that of the sphere.

3. **Check Boundary Values:**
   At $c = 4.99$, $r = \sqrt{25 - 24.9001} = \sqrt{0.0999} \approx 0.316 > 0$.
   At $c = 5.01$, $25 - (5.01)^2 = 25 - 25.1001 = -0.1001 < 0$ (no real radius).
   The sharp transition at $|c| = 5$ is perfectly validated.

---

## 7. Common Mistakes to Avoid

1. **Forgetting to Specify the Plane ($z = 3$):**
   Writing merely $x^2 + y^2 = 16$ in 3D space defines a circular **cylinder**, not a circle. A circle in 3D is a 1D curve requiring two conditions: $x^2 + y^2 = 16$ **and** $z = 3$.
2. **Confusing Circle Radius with Sphere Radius:**
   Assuming the slice has the same radius as the sphere ($R = 5$). Slices away from the equator have strictly smaller radii: $r = \sqrt{R^2 - d^2}$.
3. **Omitting the Tangency Case $|c| = 5$:**
   Classifying only $|c| < 5$ and $|c| > 5$ misses the critical boundary where the plane touches the sphere tangentially at an isolated point.

---

## 8. How I Would Explain This in Class

> "Imagine slicing an orange of radius $5\text{ cm}$ with a horizontal knife. If you slice it right through the center ($z = 0$), you get the biggest possible circle, with radius $5\text{ cm}$.
> If you raise the knife to height $z = 3\text{ cm}$, you are cutting through the upper hemisphere. How big is the cut? Picture a right triangle from the center of the orange to the knife's height (distance $3$), out along the cut surface (radius $r$), and back down to the center (hypotenuse $5$). By the classic $3\text{-}4\text{-}5$ triangle, $3^2 + 4^2 = 5^2$, so the cut circle has radius $4\text{ cm}$!
> If you raise the knife all the way to $z = 5\text{ cm}$, it just grazes the top of the peel at a single point (the North Pole). If you go higher than $5\text{ cm}$, the knife swings through empty air—the intersection is empty!"

