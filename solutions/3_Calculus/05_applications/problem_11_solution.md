# Problem 11: Volume of a Solid of Revolution

## 1. The Original Problem

The region under the graph

$$
y = \sqrt{x}, \qquad x \in [0, 4],
$$

is rotated about the $x$-axis.

1. Construct the integral describing the volume using the disk method.
2. Compute the volume.
3. Explain where the factor $\pi y^2$ in the integral comes from.

---

## 2. What Are We Trying to Find?

1. **Disk-method integral setup:** Translate the geometric rotation of the region under $y = \sqrt{x}$ on $[0, 4]$ about the $x$-axis into a definite integral for the volume $V$.
2. **Exact volume evaluation:** Compute the definite integral to find the exact and approximate volume of the resulting solid of revolution.
3. **Geometric origin of $\pi y^2$:** Explain carefully, starting from cross-sectional slices and Riemann sums, why the integrand contains the factor $\pi y^2$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Volume by slicing (Cavalieri's principle):** If a three-dimensional solid extends from $x = a$ to $x = b$ and its cross-sectional area perpendicular to the $x$-axis at position $x$ is a continuous function $A(x)$, then the volume of the solid is $V = \int_a^b A(x)\,dx$.
- **Disk method for rotation about the $x$-axis:** When a region lying between a nonnegative curve $y = f(x) \ge 0$ and the $x$-axis on $[a, b]$ is rotated $360^\circ$ around the $x$-axis, every cross-section perpendicular to the $x$-axis is a solid circular disk of radius $r = y = f(x)$.
- **Area of a circle:** A circular disk of radius $r$ has area $A = \pi r^2$. Substituting $r = y$ yields the cross-sectional area $A(x) = \pi y^2$.
- **Fundamental Theorem of Calculus:** Once $A(x) = \pi\left(\sqrt{x}\right)^2 = \pi x$ is simplified, we integrate directly using the power rule.

---

## 4. Step-by-Step Solution

### Step 1: Visualize the Region and Construct the Disk-Method Integral

On the interval $x \in [0, 4]$, the function $y = \sqrt{x}$ is continuous and nonnegative, starting at $(0, 0)$ and rising to $(4, 2)$. Rotating the region between $y = \sqrt{x}$ and the $x$-axis around the $x$-axis sweeps out a **paraboloid of revolution** lying along the $x$-axis from $x = 0$ to $x = 4$, with a circular base of radius $2$ at $x = 4$:

```text
      y
      2 |                  .***|   y = sqrt(x)
        |           .******    |
      1 |     .****   | r=y    |
        |  .**        |        |
      0 +--*----------+--------+---> x
        0  **         |        4
     -1 |     '****   |        |
        |           '******    |
     -2 |                  '***|   y = -sqrt(x)
                    <dx>
                 thin circular disk
```

At any point $x \in [0, 4]$, a slice perpendicular to the $x$-axis is a circular disk of radius $r(x) = y = \sqrt{x}$. Therefore, the cross-sectional area is

$$
A(x) = \pi y^2 = \pi \left(\sqrt{x}\right)^2 = \pi x.
$$

Integrating the cross-sectional area from $x = 0$ to $x = 4$ gives the disk-method volume integral:

$$
V = \int_0^4 \pi y^2\,dx = \int_0^4 \pi \left(\sqrt{x}\right)^2 dx = \pi \int_0^4 x\,dx.
$$

### Step 2: Compute the Volume

Factor out the constant $\pi$ and apply the Fundamental Theorem of Calculus:

$$
V = \pi \int_0^4 x\,dx = \pi \left[\frac{x^2}{2}\right]_0^4 = \pi \left(\frac{4^2}{2} - \frac{0^2}{2}\right) = \pi \left(\frac{16}{2} - 0\right) = 8\pi.
$$

Numerically,

$$
V = 8\pi \approx 25.1327\text{ cubic units}.
$$

### Step 3: Explain Where the Factor $\pi y^2$ Comes From

The factor $\pi y^2$ is not an arbitrary rule to memorize; it comes directly from elementary geometry and the definition of the definite integral:

**1. Radius of rotation:** Each point $(x, y)$ on the curve $y = \sqrt{x}$ lies at a perpendicular distance $y \ge 0$ from the axis of rotation, which is the $x$-axis. When that vertical line segment from $(x, 0)$ to $(x, y)$ is rotated a full turn around the $x$-axis, it sweeps out a **circular disk** centered at $(x, 0)$ with radius $r = y$.

**2. Cross-sectional area:** The area of a circle of radius $r$ is $\pi r^2$. Because the radius at position $x$ is $r = y$, the area of the circular cross-section at $x$ is

$$
A(x) = \pi r^2 = \pi y^2.
$$

**3. Volume of a thin slice and passing to the limit:** Partition the interval $[0, 4]$ into $n$ narrow subintervals of width $\Delta x = \frac{4}{n}$. On the $i$-th subinterval around a sample point with height $y_i = \sqrt{x_i}$, the curve is nearly constant. Rotating this narrow vertical rectangle produces a thin right circular cylinder, or **disk**, whose radius is this sample height and whose thickness is $\Delta x$. Its volume is

$$
\Delta V_i = \text{base area} \times \text{thickness} = \pi y_i^2\,\Delta x.
$$

Summing the volumes of all $n$ thin disks gives a Riemann sum approximation to the total volume:

$$
V \approx \sum_{i=1}^n \pi y_i^2\,\Delta x.
$$

Taking the limit as $n \to \infty$ so that $\Delta x \to 0$ turns the sum into the definite integral:

$$
V = \lim_{n \to \infty} \sum_{i=1}^n \pi y_i^2\,\Delta x = \int_0^4 \pi y^2\,dx.
$$

Hence $\pi y^2$ is precisely the **area of the circular cross-section** at coordinate $x$, and $\pi y^2\,dx$ represents the infinitesimal volume of a disk of radius $y$ and thickness $dx$.

---

## 5. Final Answer & Conclusion

1. **Disk-method volume integral:** $V = \int_0^4 \pi y^2\,dx = \pi \int_0^4 x\,dx$.
2. **Volume of the solid:** Exact volume $V = 8\pi \approx 25.1327\text{ cubic units}$.
3. **Origin of $\pi y^2$:** Rotating a vertical segment of height $y$ around the $x$-axis creates a circular disk of radius $y$, whose area is $\pi y^2$. Multiplying by the infinitesimal slice thickness $dx$ gives the disk volume element $\pi y^2\,dx$, and integrating sums all slices from $x = 0$ to $x = 4$.

---

## 6. Quick Verification

**Check 1 — Geometric bounds via an inscribed cone and circumscribing cylinder:** Both shapes have height $H = 4$ along the $x$-axis and base radius $R = 2$ at $x = 4$:

- **Circumscribing cylinder** formed by rotating $y = 2$: $V_{\text{cyl}} = \pi R^2 H = \pi (2^2)(4) = 16\pi$.
- **Inscribed cone** formed by rotating the straight line $y = \frac{1}{2}x$: $V_{\text{cone}} = \frac{1}{3}\pi R^2 H = \frac{16}{3}\pi \approx 5.333\pi$.

Because $\frac{1}{2}x \le \sqrt{x} \le 2$ for every $x \in [0, 4]$ with strict inequality on $(0, 4)$, the solid's volume must satisfy $\frac{16}{3}\pi < V < 16\pi$. Indeed, $V = 8\pi$ lies strictly between $5.333\pi$ and $16\pi$, and equals **exactly half** the volume of the circumscribing cylinder, confirming Archimedes' classical theorem on paraboloids.

**Check 2 — Independent calculation via the cylindrical shell method:** Rewrite $y = \sqrt{x}$ as $x = y^2$ for $y \in [0, 2]$. A horizontal strip at height $y$ of thickness $dy$ spans from $x = y^2$ to $x = 4$, giving shell length $4 - y^2$ and radius $y$ around the $x$-axis. Integrating shell volumes $2\pi y (4 - y^2)\,dy$ yields

$$
V = \int_0^2 2\pi y\left(4 - y^2\right) dy = 2\pi \int_0^2 \left(4y - y^3\right) dy = 2\pi \left[2y^2 - \frac{y^4}{4}\right]_0^2 = 2\pi(8 - 4) = 8\pi.
$$

Both independent methods give the exact same volume $8\pi$.

---

## 7. Common Mistakes to Avoid

- **Forgetting to square $y$:** Writing $\int_0^4 \pi \sqrt{x}\,dx$ computes $\pi$ times the 2D area under the curve, not the 3D volume of revolution. The area of a disk is $\pi r^2$, so you must square $y = \sqrt{x}$ to get $\pi x$.
- **Forgetting the factor $\pi$:** Computing $\int_0^4 x\,dx = 8$ gives the integral of $r^2$, omitting the factor $\pi$ from the area of a circle.
- **Squaring the entire integral instead of the integrand:** Note that $\pi \int_0^4 y^2\,dx \ne \pi\left(\int_0^4 y\,dx\right)^2$. You must square $y$ *before* integrating, because you are summing areas of individual disks $\pi y^2\,dx$.
- **Using the wrong integration limits:** Because the disks are stacked along the $x$-axis with thickness $dx$, the limits must be $x$-values from $0$ to $4$, not the $y$-values from $0$ to $2$.

---

## 8. How I Would Explain This in Class

> "Imagine slicing a loaf of bread—or here, a solid cone-like bullet—into paper-thin round coins perpendicular to the $x$-axis. At any spot $x$, the coin's radius is simply the height $y = \sqrt{x}$ of the graph above the axis. What is the volume of one thin coin? Its flat face is a circle of area $\pi y^2$, and its thickness is $dx$, so its volume is $\pi y^2\,dx$. For $y = \sqrt{x}$, squaring the square root gives a wonderful gift: the circle's area is simply $\pi x$, growing linearly from $0$ at the tip to $4\pi$ at the base. Adding up all the coins from $x = 0$ to $x = 4$ gives an exact volume of $8\pi$, which is neatly half the volume of the cylinder that wraps around it."
