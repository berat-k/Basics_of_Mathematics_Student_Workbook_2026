# Problem 10: Paraboloids

## 1. The Original Problem

Compare

$$
z = x^2 + y^2
$$

and

$$
z = x^2 - y^2.
$$

For each surface, describe the cross-sections $x = 0$, $y = 0$, and $z = c$, then make a qualitative sketch.

---

## 2. What Are We Trying to Find?

We need to:
1. Analyze the first surface $S_1: z = x^2 + y^2$ (elliptic/circular paraboloid) by determining its principal vertical cross-sections ($x = 0$ and $y = 0$) and its horizontal cross-sections ($z = c$).
2. Analyze the second surface $S_2: z = x^2 - y^2$ (hyperbolic paraboloid / saddle surface) through its principal vertical cross-sections ($x = 0$ and $y = 0$) and horizontal cross-sections ($z = c$).
3. Compare the contrasting geometric behavior of both surfaces.
4. Provide qualitative sketch descriptions illustrating their 3D shapes.

---

## 3. Before Calculating: What Idea Do We Need?

- **Understanding 3D Surfaces Through 2D Traces:**
  A three-dimensional surface $z = f(x, y)$ can be fully understood by analyzing its planar intersections (traces) with the coordinate planes and with horizontal planes $z = c$:
  - Setting $x = 0$ reveals the profile in the $yz$-plane.
  - Setting $y = 0$ reveals the profile in the $xz$-plane.
  - Setting $z = c$ reveals the contour lines (level curves) in horizontal planes.
- **The Elliptic Paraboloid ($z = x^2 + y^2$):**
  Both quadratic terms have the same positive sign. The vertical traces are upward-opening parabolas, while the horizontal traces are concentric circles. The surface forms an upward-opening cup (bowl).
- **The Hyperbolic Paraboloid ($z = x^2 - y^2$):**
  The quadratic terms have opposite signs ($+x^2$ and $-y^2$). One vertical trace opens upwards while the other opens downwards. The horizontal traces are hyperbolas. The surface forms a saddle (mountain pass).

---

## 4. Step-by-Step Solution

### Part 1: Analysis of Surface 1 ($z = x^2 + y^2$)

#### 1. Vertical Cross-Section $x = 0$ ($yz$-plane):
Substitute $x = 0$:

$$
z = 0^2 + y^2 \implies z = y^2
$$

- **Description:** A standard upward-opening **parabola** lying in the $yz$-plane, with vertex at the origin $(0, 0, 0)$ and vertical axis of symmetry along the positive $z$-axis.

#### 2. Vertical Cross-Section $y = 0$ ($xz$-plane):
Substitute $y = 0$:

$$
z = x^2 + 0^2 \implies z = x^2
$$

- **Description:** An identical upward-opening **parabola** lying in the $xz$-plane, with vertex at $(0, 0, 0)$ and vertical axis of symmetry along the positive $z$-axis.

#### 3. Horizontal Cross-Sections $z = c$:
Substitute $z = c$:

$$
x^2 + y^2 = c
$$

- **If $c > 0$:** This is a **circle** of radius $R = \sqrt{c}$ centered at $(0, 0, c)$. As $c$ increases, the circles widen monotonically.
- **If $c = 0$:** $x^2 + y^2 = 0 \implies (x, y) = (0, 0)$. The cross-section is the single **vertex point** $(0, 0, 0)$.
- **If $c < 0$:** $x^2 + y^2 = c < 0$. Because the sum of real squares cannot be negative, there are **no real points** (the surface sits entirely above the $xy$-plane, $z \ge 0$).

#### 4. Qualitative Geometric Shape:
An **elliptic (circular) paraboloid**: a smooth, symmetric, upward-opening bowl whose bottom rests at the origin and whose circular cross-sections expand upwards to infinity.

---

### Part 2: Analysis of Surface 2 ($z = x^2 - y^2$)

#### 1. Vertical Cross-Section $x = 0$ ($yz$-plane):
Substitute $x = 0$:

$$
z = 0^2 - y^2 \implies z = -y^2
$$

- **Description:** A **downward-opening parabola** in the $yz$-plane with vertex at the origin $(0, 0, 0)$. As $|y|$ increases, $z$ plunges downwards toward $-\infty$.

#### 2. Vertical Cross-Section $y = 0$ ($xz$-plane):
Substitute $y = 0$:

$$
z = x^2 - 0^2 \implies z = x^2
$$

- **Description:** An **upward-opening parabola** in the $xz$-plane with vertex at the origin $(0, 0, 0)$. As $|x|$ increases, $z$ climbs upwards toward $+\infty$.

#### 3. Horizontal Cross-Sections $z = c$:
Substitute $z = c$:

$$
x^2 - y^2 = c
$$

- **If $c > 0$:** A **hyperbola** opening along the $x$-axis with real vertices at $(\pm \sqrt{c}, 0, c)$ and asymptotes $y = \pm x$.
- **If $c = 0$:** $x^2 - y^2 = 0 \iff (x - y)(x + y) = 0$. This is a **pair of intersecting lines** $y = x$ and $y = -x$ in the $xy$-plane, crossing at the origin.
- **If $c < 0$:** Multiply by $-1$: $y^2 - x^2 = -c > 0$. This is a **hyperbola** opening along the $y$-axis with real vertices at $(0, \pm \sqrt{-c}, c)$ and the same asymptotes $y = \pm x$.

#### 4. Qualitative Geometric Shape:
A **hyperbolic paraboloid**: a classic **saddle surface** (like a horse saddle or a Pringles potato chip). The origin $(0, 0, 0)$ is a saddle point (minimax point): moving along the $x$-direction curves upwards like a bowl, while moving along the perpendicular $y$-direction curves downwards like a hill.

---

## 5. Final Answer & Conclusion

| Feature | Surface 1: $z = x^2 + y^2$ | Surface 2: $z = x^2 - y^2$ |
| :--- | :--- | :--- |
| **Section $x = 0$** | Parabola opening upwards ($z = y^2$) | Parabola opening downwards ($z = -y^2$) |
| **Section $y = 0$** | Parabola opening upwards ($z = x^2$) | Parabola opening upwards ($z = x^2$) |
| **Section $z = c > 0$** | Circle ($x^2 + y^2 = c$, radius $\sqrt{c}$) | Hyperbola opening along $x$ ($x^2 - y^2 = c$) |
| **Section $z = 0$** | Single vertex point $(0, 0, 0)$ | Pair of intersecting lines ($y = \pm x$) |
| **Section $z = c < 0$** | Empty set ($\emptyset$, no real points) | Hyperbola opening along $y$ ($y^2 - x^2 = -c$) |
| **Surface Name** | **Elliptic (Circular) Paraboloid** | **Hyperbolic Paraboloid** |
| **Shape** | Upward-facing bowl | Saddle / Mountain pass |

---

## 6. Quick Verification

1. **Verify Extrema at the Origin:**
   - On $z = x^2 + y^2$: Since $x^2 \ge 0$ and $y^2 \ge 0$, $z(0, 0) = 0$ is the absolute global **minimum**.
   - On $z = x^2 - y^2$: For $y = 0$, $z(x, 0) = x^2 \ge 0$ (origin is a minimum along $x$). For $x = 0$, $z(0, y) = -y^2 \le 0$ (origin is a maximum along $y$). A point that is simultaneously a minimum along one direction and a maximum along another is the textbook definition of a **saddle point**.

2. **Verify Level Curves Consistency:**
   At $z = 4$:
   - On Surface 1: $x^2 + y^2 = 4$ is a circle of radius $2$.
   - On Surface 2: $x^2 - y^2 = 4$ is a hyperbola with vertices at $(\pm 2, 0, 4)$.
   Both formulas hold with complete mathematical fidelity.

---

## 7. Common Mistakes to Avoid

1. **Assuming $z = c < 0$ Produces Curves on the Elliptic Paraboloid:**
   Forgetting that $x^2 + y^2 \ge 0$ means the surface exists strictly in the upper half-space $z \ge 0$.
2. **Missing the Line Pair at $z = 0$ on the Saddle:**
   Assuming $z = 0$ gives a single point on the saddle. $x^2 - y^2 = 0$ factors into $(x - y)(x + y) = 0$, producing two intersecting lines on the surface.
3. **Confusing Which Way the Hyperbolas Open:**
   For $z = c > 0$, the hyperbolas open in the $x$-direction; for $z = c < 0$, they rotate by $90^\circ$ and open in the $y$-direction.

---

## 8. How I Would Explain This in Class

> "Both surfaces are built out of parabolas, but their signs make all the difference in the world. In $z = x^2 + y^2$, both parabolas curve upwards, welding together into a soup bowl that catches water. In $z = x^2 - y^2$, the $x$-parabola curves upwards while the $y$-parabola curves downwards, forming a horse saddle. If you sit at the origin, your legs hang down along the falling $y$-parabolas while the front and back of the saddle rise up along the $x$-parabola."

