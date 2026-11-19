# Problem 12: Recognizing a Surface from Cross-Sections

## 1. The Original Problem

A certain surface has the following properties:
- the cross-section $z = 0$ is a point,
- for $z > 0$, the cross-sections $z = \text{const}$ are circles with increasing radius,
- vertical cross-sections through the $Oz$ axis are parabolas.

Propose a simple equation for such a surface and justify your choice.

---

## 2. What Are We Trying to Find?

We need to:
1. Reverse-engineer a 3D surface equation from its geometric cross-sectional properties.
2. Formulate a simple algebraic equation $F(x, y, z) = 0$ (or explicit form $z = f(x, y)$) satisfying all three given conditions:
   - Slice at $z = 0$ degenerates to a single isolated point.
   - Slices at horizontal levels $z = c > 0$ are concentric circles whose radii grow strictly monotonically with $c$.
   - Any planar vertical slice passing through the vertical $z$-axis ($Oz$) yields a parabola.
3. Provide a rigorous mathematical justification proving that the proposed equation satisfies every requirement.
4. Identify and name the resulting quadric surface (**elliptic / circular paraboloid**).

---

## 3. Before Calculating: What Idea Do We Need?

- **Rotational Symmetry Around $Oz$:**
  Since the horizontal cross-sections at $z > 0$ are circles centered on the $z$-axis, the surface must have rotational symmetry about the $z$-axis ($Oz$).
  Any surface of revolution around the $z$-axis can be written as:
  $$
  z = g(r) \quad \text{or} \quad r^2 = h(z)
  $$
  where $r = \sqrt{x^2 + y^2}$ is the radial distance from the $z$-axis.
- **Vertical Cross-Sections as Parabolas:**
  A vertical plane passing through $Oz$ has the general equation $y = mx$ (or $x = 0$). In such a plane, the radial coordinate is $r = \sqrt{x^2 + y^2}$.
  The requirement that the curve in any such vertical plane is a parabola with its vertex at the origin means the vertical profile must satisfy:
  $$
  z = a r^2 = a (x^2 + y^2) \quad \text{with } a > 0.
  $$
- **Checking All Three Properties:**
  1. At $z = 0$: $a(x^2 + y^2) = 0 \implies (x, y) = (0, 0)$, a single point.
  2. At $z = c > 0$: $x^2 + y^2 = c/a$, a circle of radius $R(c) = \sqrt{c/a}$, which strictly increases with $c$.
  3. Vertical slices through $Oz$: in radial coordinates, $z = a r^2$, a standard parabola.

---

## 4. Step-by-Step Solution

### Step 1: Proposing the Simplest Equation

Choosing the simplest positive scaling factor $a = 1$, we propose the equation:

$$
z = x^2 + y^2
$$

(or in implicit form, $x^2 + y^2 - z = 0$).

More generally, any equation of the form:

$$
z = a (x^2 + y^2) \quad \text{with } a > 0
$$

satisfies the given requirements. We will analyze and justify the canonical form $z = x^2 + y^2$.

---

### Step 2: Verification of Property 1 (Cross-Section at $z = 0$)

Substitute $z = 0$ into the proposed equation:

$$
x^2 + y^2 = 0
$$

Since $x$ and $y$ are real numbers, $x^2 \ge 0$ and $y^2 \ge 0$. The sum of two non-negative numbers equals zero if and only if each term is zero:

$$
x^2 = 0 \implies x = 0, \quad \text{and} \quad y^2 = 0 \implies y = 0.
$$

Thus, the cross-section $z = 0$ consists of the single point:

$$
(x, y, z) = (0, 0, 0)
$$

This completely satisfies Property 1.

---

### Step 3: Verification of Property 2 (Cross-Sections for $z > 0$)

Let $c$ be a strictly positive constant ($c > 0$). Intersect the surface with the horizontal plane $z = c$:

$$
x^2 + y^2 = c
$$

In the horizontal plane $z = c$, this is the standard equation of a circle centered at $(0, 0, c)$ with radius:

$$
R(c) = \sqrt{c}
$$

To verify that the radius increases with $z$:
- For $c_1 < c_2$, we have $\sqrt{c_1} < \sqrt{c_2}$, so $R(c_1) < R(c_2)$.
- The derivative with respect to $c$ is:
  $$
  \frac{dR}{dc} = \frac{1}{2\sqrt{c}} > 0 \quad \text{for all } c > 0.
  $$
As $c$ increases, the radius $R(c)$ increases strictly monotonically. This completely satisfies Property 2.

---

### Step 4: Verification of Property 3 (Vertical Cross-Sections Through $Oz$)

Any vertical plane passing through the $z$-axis ($Oz$) can be parameterized by its angle $\theta$ with the positive $x$-axis. Its equation is either:
- $y = (\tan\theta) x$ (for $\theta \ne \pi/2$), or
- $x = 0$ (the $yz$-plane, corresponding to $\theta = \pi/2$).

Let us analyze both:

1. **For $x = 0$ ($yz$-plane):**
   Substitute $x = 0$ into $z = x^2 + y^2$:
   $$
   z = 0^2 + y^2 \implies z = y^2
   $$
   This is an upward-opening **parabola** in the plane $x = 0$, with vertex at $(0, 0, 0)$ and vertical axis along $Oz$.

2. **For $y = 0$ ($xz$-plane):**
   Substitute $y = 0$ into $z = x^2 + y^2$:
   $$
   z = x^2 + 0^2 \implies z = x^2
   $$
   This is an identical upward-opening **parabola** in the plane $y = 0$.

3. **For an arbitrary vertical plane $y = mx$ passing through $Oz$:**
   Substitute $y = mx$ into $z = x^2 + y^2$:
   $$
   z = x^2 + (mx)^2 = (1 + m^2) x^2
   $$
   Within this plane, let $u$ be the horizontal coordinate measured along the line of intersection with the $xy$-plane: $u = \pm \sqrt{x^2 + y^2} = \pm \sqrt{1 + m^2}\, x$.
   Then:
   $$
   z = u^2
   $$
   This is a standard upward-opening **parabola** with vertex at the origin $(0, 0, 0)$ and vertical axis along $Oz$.

Because this holds for every vertical plane containing the $z$-axis, Property 3 is fully satisfied.

---

### Step 5: Identification and Qualitative Description of the Surface

- **Mathematical Name:** **Circular Paraboloid** (or **Elliptic Paraboloid of Revolution**).
- **Geometric Structure:**
  - The surface is generated by revolving the 2D parabola $z = x^2$ in the $xz$-plane around the vertical $z$-axis ($Oz$).
  - Its lowest point (global vertex / minimum) is at $(0, 0, 0)$.
  - For $z < 0$, no real points exist because $x^2 + y^2 \ge 0 > z$.
  - It opens continuously upward, forming a smooth, rotationally symmetric bowl.

---

## 5. Final Answer & Conclusion

### Proposed Equation:

$$
z = x^2 + y^2
$$

(or more generally, $z = a(x^2 + y^2)$ with any constant $a > 0$).

### Justification Summary:
1. **At $z = 0$:** $x^2 + y^2 = 0 \implies (x, y) = (0, 0)$, yielding the single point $(0, 0, 0)$.
2. **For $z = c > 0$:** $x^2 + y^2 = c$, yielding circles centered at $(0, 0, c)$ with radius $R = \sqrt{c}$, which strictly increases as $c$ increases.
3. **Vertical planes through $Oz$:** In any vertical plane at distance $r$ from $Oz$, the relation is $z = r^2$, which defines an upward-opening parabola with vertex at $(0, 0, 0)$.

### Surface Classification:
The surface is a **circular paraboloid** (elliptic paraboloid of revolution).

---

## 6. Quick Verification

1. **Why not a cone ($z = \sqrt{x^2 + y^2}$ or $z^2 = x^2 + y^2$)?**
   - For a cone $z = \sqrt{x^2 + y^2}$, vertical sections through $Oz$ give $z = |r|$, which are straight lines (a V-shape), **not** parabolas.
2. **Why not a sphere ($x^2 + y^2 + z^2 = R^2$)?**
   - Vertical slices of a sphere are circles, not parabolas.
   - Slices $z = c$ do not have an increasing radius for all $z > 0$; the radius shrinks as $z$ approaches $R$.
3. **Checking Monotonicity of Radius:**
   - At $z = 1$: circle of radius $R = 1$.
   - At $z = 4$: circle of radius $R = 2$.
   - At $z = 9$: circle of radius $R = 3$.
   Since $1 < 2 < 3$, the radius strictly increases with height, confirming our derivation.

---

## 7. Common Mistakes to Avoid

1. **Proposing a Cone Instead of a Paraboloid:**
   A cone ($z^2 = x^2 + y^2$) also has circular horizontal slices and vertex at the origin, but its vertical cross-sections through the axis are **lines**, not **parabolas**.
2. **Choosing Negative Sign ($z = -(x^2 + y^2)$):**
   If $z = -(x^2 + y^2)$, then for $z > 0$ we would have $x^2 + y^2 = -z < 0$, meaning cross-sections for $z > 0$ would be empty. The coefficient must be positive ($a > 0$).
3. **Proposing Unequal Coefficients ($z = 2x^2 + y^2$):**
   If the coefficients of $x^2$ and $y^2$ are unequal, the horizontal cross-sections are **ellipses**, not **circles**.

---

## 8. How I Would Explain This in Class

> "This problem asks us to play detective: we are given the clues (the slices), and we must find the equation.
> First clue: at every height $z > 0$, the slice is a circle centered on the $z$-axis. That means the equation must depend only on the radial distance $r = \sqrt{x^2 + y^2}$. So our surface must look like $z = g(r)$.
> Second clue: if we slice vertically through the $z$-axis, we get a parabola. A parabola with its vertex at the origin has the form $z = a r^2$.
> Third clue: at $z = 0$ we get just a single point $(0, 0, 0)$, and as $z$ goes up, the circles expand. That means $a$ must be positive!
> Setting $a = 1$, we get $z = r^2 = x^2 + y^2$. That is the classic circular paraboloid—the exact shape of a satellite dish or a parabolic mirror!"

