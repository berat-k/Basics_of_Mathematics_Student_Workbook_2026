# Problem 09: Ellipsoid and Its Cross-Sections

## 1. The Original Problem

Consider

$$
\frac{x^2}{9} + \frac{y^2}{4} + \frac{z^2}{16} = 1.
$$

Give the semiaxis lengths, describe the cross-section $z = 0$, and explain how the cross-sections $z = c$ change for $|c| < 4$.

---

## 2. What Are We Trying to Find?

We need to:
1. Extract the three semiaxis lengths ($a, b, c_z$) of the ellipsoid from its canonical equation.
2. Characterize the central equatorial cross-section formed by the coordinate plane $z = 0$.
3. Analyze the horizontal family of planar cross-sections produced by slicing the surface with planes $z = c$ for all values $|c| < 4$.
4. Describe how the size and shape of these 2D cross-sectional curves evolve as the height parameter $c$ varies between the two poles.

---

## 3. Before Calculating: What Idea Do We Need?

- **Canonical Equation of an Ellipsoid:**

$$
\frac{x^2}{a^2} + \frac{y^2}{b^2} + \frac{z^2}{c_z^2} = 1
$$

  where $a, b, c_z > 0$ are the lengths of the principal semiaxes along the $x$-, $y$-, and $z$-axes respectively.
- **Planar Cross-Section Analysis (Slicing):**
  To determine the shape of a surface intersected by a plane $z = c$, treat $z$ as a fixed constant $c$ and analyze the resulting 2D equation in the remaining variables $x$ and $y$:

$$
\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1 - \frac{c^2}{c_z^2}
$$

- **Scaling of Cross-Sectional Curves:**
  If $1 - \frac{c^2}{c_z^2} > 0$ (which occurs when $|c| < c_z$), dividing by this positive factor yields a family of similar 2D ellipses whose dimensions scale continuously with height $c$.

---

## 4. Step-by-Step Solution

### Step 1: Identify the Semiaxis Lengths

Write the denominators of $\frac{x^2}{9} + \frac{y^2}{4} + \frac{z^2}{16} = 1$ as squares:

$$
\frac{x^2}{3^2} + \frac{y^2}{2^2} + \frac{z^2}{4^2} = 1
$$

Comparing with the canonical form:
- Semiaxis along the $x$-axis: $a = \sqrt{9} = 3$
- Semiaxis along the $y$-axis: $b = \sqrt{4} = 2$
- Semiaxis along the $z$-axis: $c_z = \sqrt{16} = 4$

The surface extends from $-3$ to $3$ in $x$, from $-2$ to $2$ in $y$, and from $-4$ to $4$ in $z$.
The longest axis is along $z$, making this an ellipsoid elongated vertically.

---

### Step 2: Describe the Cross-Section $z = 0$

Substitute $z = 0$ into the surface equation:

$$
\frac{x^2}{9} + \frac{y^2}{4} + \frac{0^2}{16} = 1 \iff \frac{x^2}{9} + \frac{y^2}{4} = 1
$$

- **Shape:** This is a 2D **ellipse** lying in the $xy$-coordinate plane (the equator of the ellipsoid).
- **Center:** Origin $(0, 0, 0)$.
- **Semiaxes:** Horizontal semiaxis $a = 3$ along $x$, vertical semiaxis $b = 2$ along $y$.
- **Vertices:** $(\pm 3, 0, 0)$ and $(0, \pm 2, 0)$.
This equatorial slice is the largest horizontal cross-section of the entire ellipsoid.

---

### Step 3: Analyze the Cross-Sections $z = c$ for $|c| < 4$

Substitute $z = c$ into the equation:

$$
\frac{x^2}{9} + \frac{y^2}{4} + \frac{c^2}{16} = 1
$$

Subtract $\frac{c^2}{16}$ from both sides:

$$
\frac{x^2}{9} + \frac{y^2}{4} = 1 - \frac{c^2}{16}
$$

Let $k(c) = 1 - \frac{c^2}{16}$.
Since $|c| < 4$, we have $c^2 < 16$, which guarantees $k(c) > 0$.
Now divide both sides by $k(c)$:

$$
\frac{x^2}{9\left(1 - \frac{c^2}{16}\right)} + \frac{y^2}{4\left(1 - \frac{c^2}{16}\right)} = 1
$$

Express the new denominators as squares of the height-dependent semiaxes $a(c)$ and $b(c)$:

$$
a(c) = 3 \sqrt{1 - \frac{c^2}{16}}, \qquad b(c) = 2 \sqrt{1 - \frac{c^2}{16}}
$$

---

### Step 4: Describe How the Cross-Sections Change with $c$

1. **Geometry of the Slices:**
   For every height $c$ strictly between $-4$ and $4$, the cross-section is an **ellipse** parallel to the $xy$-plane, centered at $(0, 0, c)$.
2. **Preservation of Shape (Aspect Ratio):**
   The ratio of the semiaxes is completely invariant with respect to $c$:

$$
\frac{a(c)}{b(c)} = \frac{3 \sqrt{1 - c^2/16}}{2 \sqrt{1 - c^2/16}} = \frac{3}{2} = 1.5
$$

   All horizontal cross-sections are geometrically **similar ellipses**, sharing the exact same $3:2$ aspect ratio.
3. **Monotonic Shrinking Toward the Poles:**
   - At $c = 0$ (equator), the factor $\sqrt{1 - c^2/16} = 1$ is maximized, giving the largest ellipse with semiaxes $a = 3$ and $b = 2$.
   - As $|c|$ increases away from $0$ toward $4$ (moving toward the north or south poles), the factor $\sqrt{1 - c^2/16}$ decreases strictly monotonically. The cross-sectional ellipses shrink smoothly in area.
   - At $|c| = 4$ ($z = 4$ or $z = -4$), the factor becomes $\sqrt{1 - 1} = 0$. The ellipse collapses down to a single point: the north pole $(0, 0, 4)$ or the south pole $(0, 0, -4)$.
   - For $|c| > 4$, $1 - c^2/16 < 0$, meaning no real points exist (the plane misses the ellipsoid completely).

---

## 5. Final Answer & Conclusion

- **Semiaxis Lengths:**

$$
a = 3 \quad (\text{along } x), \qquad b = 2 \quad (\text{along } y), \qquad c_z = 4 \quad (\text{along } z)
$$

- **Cross-Section $z = 0$:**
  An ellipse in the $xy$-plane given by $\frac{x^2}{9} + \frac{y^2}{4} = 1$, with semiaxes $3$ and $2$.
- **Evolution of Cross-Sections $z = c$ for $|c| < 4$:**
  Each slice is a similar ellipse centered at $(0, 0, c)$ with constant aspect ratio $3:2$. The semiaxes are $a(c) = 3\sqrt{1 - c^2/16}$ and $b(c) = 2\sqrt{1 - c^2/16}$. The ellipses are largest at the equator $c = 0$, shrink continuously as $|c|$ increases, and collapse to single pole points at $c = \pm 4$.

---

## 6. Quick Verification

Calculate a specific slice, for example at $z = 2$:
- $|c| = 2 < 4$.
- Scaling factor: $1 - \frac{2^2}{16} = 1 - \frac{4}{16} = 1 - \frac{1}{4} = \frac{3}{4}$.
- Equation of slice: $\frac{x^2}{9(3/4)} + \frac{y^2}{4(3/4)} = 1 \iff \frac{x^2}{27/4} + \frac{y^2}{3} = 1$.
- Semiaxes: $a(2) = \sqrt{27/4} = \frac{3\sqrt{3}}{2} \approx 2.598 < 3$; $b(2) = \sqrt{3} \approx 1.732 < 2$.
- Ratio: $\frac{a(2)}{b(2)} = \frac{3\sqrt{3}/2}{\sqrt{3}} = \frac{3}{2}$.
The aspect ratio is exactly $3/2$ and the dimensions are strictly smaller than at $z = 0$, confirming the theoretical model.

---

## 7. Common Mistakes to Avoid

1. **Confusing Semiaxis with Full Axis:**
   Reporting $6, 4, 8$ instead of $a = 3, b = 2, c_z = 4$. The parameters $a, b, c_z$ are *semiaxes* (half-lengths from the center).
2. **Forgetting to Normalize the Right-Hand Side:**
   Writing the cross-section as $\frac{x^2}{9} + \frac{y^2}{4} = 1 - c^2/16$ and claiming the semiaxes are $3$ and $2$. To read true semiaxes, the right-hand side must be normalized to $1$, which scales the denominators by $(1 - c^2/16)$.
3. **Claiming Slices Beyond $|c| = 4$ Exist:**
   Assuming the ellipsoid continues indefinitely like a cylinder. Because all three terms are positive squares, the surface is completely bounded within $|z| \le 4$.

---

## 8. How I Would Explain This in Class

> "Imagine slicing an American football horizontally like a loaf of bread: the very middle slice at the equator $z = 0$ is the largest oval. As you move your knife upwards towards the tip at $z = 4$ or downwards towards $z = -4$, every slice remains an oval with the exact same 3-to-2 shape, but the slices get progressively smaller until your knife hits the very tip and the oval collapses into a single point."

