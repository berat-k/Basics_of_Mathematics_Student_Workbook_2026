# Problem 03: Ellipse

## 1. The Original Problem

For

$$
\frac{x^2}{25} + \frac{y^2}{9} = 1,
$$

find the semiaxis lengths, the intercepts with the coordinate axes, and make a sketch. Explain along which axis the ellipse is more stretched and how this is visible in the equation.

---

## 2. What Are We Trying to Find?

We need to:
1. Extract the semimajor and semiminor axis lengths ($a$ and $b$) from the canonical equation.
2. Determine all four intercepts with the coordinate axes.
3. Provide a clear structural sketch layout of the ellipse.
4. Explain along which coordinate axis the ellipse is more stretched, and show where and why this is directly visible in the equation.

---

## 3. Before Calculating: What Idea Do We Need?

- **Canonical Form of an Origin-Centered Ellipse:**

$$
\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1
$$

  where:
  - $a > 0$ is the horizontal semiaxis length along the $x$-axis.
  - $b > 0$ is the vertical semiaxis length along the $y$-axis.
- **Axis Intercepts:**
  - $x$-intercepts: Setting $y = 0 \implies \frac{x^2}{a^2} = 1 \implies x = \pm a$. The vertices on the $x$-axis are $(\pm a, 0)$.
  - $y$-intercepts: Setting $x = 0 \implies \frac{y^2}{b^2} = 1 \implies y = \pm b$. The vertices on the $y$-axis are $(0, \pm b)$.
- **Stretching Criterion:**
  Each variable's denominator represents the square of its maximum reach away from the center. The variable with the **larger denominator** corresponds to the axis along which the ellipse is more stretched.

---

## 4. Step-by-Step Solution

### Step 1: Identify Semiaxis Lengths

Compare the given equation with the standard canonical form:

$$
\frac{x^2}{25} + \frac{y^2}{9} = 1 \iff \frac{x^2}{5^2} + \frac{y^2}{3^2} = 1
$$

- Horizontal semiaxis length:

$$
a = \sqrt{25} = 5
$$

- Vertical semiaxis length:

$$
b = \sqrt{9} = 3
$$

The semimajor axis has length $a = 5$, and the semiminor axis has length $b = 3$.

---

### Step 2: Compute Intercepts with Coordinate Axes

1. **Intercepts with the $x$-axis (set $y = 0$):**

$$
\frac{x^2}{25} + \frac{0^2}{9} = 1 \implies \frac{x^2}{25} = 1 \implies x^2 = 25 \implies x = \pm 5
$$

The $x$-intercepts (major vertices) are:

$$
A_1(-5, 0) \quad \text{and} \quad A_2(5, 0)
$$

2. **Intercepts with the $y$-axis (set $x = 0$):**

$$
\frac{0^2}{25} + \frac{y^2}{9} = 1 \implies \frac{y^2}{9} = 1 \implies y^2 = 9 \implies y = \pm 3
$$

The $y$-intercepts (minor vertices) are:

$$
B_1(0, -3) \quad \text{and} \quad B_2(0, 3)
$$

---

### Step 3: Explain the Stretching Direction and Equation Visibility

1. **Along Which Axis Is It More Stretched?**
   The ellipse is more stretched along the **$x$-axis** (horizontal axis).
   - Total width along $x$: $2a = 2(5) = 10$ units.
   - Total height along $y$: $2b = 2(3) = 6$ units.
   Since $10 > 6$, the curve stretches significantly further along the horizontal direction.

2. **How This Is Visible in the Equation:**
   In the equation $\frac{x^2}{25} + \frac{y^2}{9} = 1$, the denominator beneath $x^2$ is $25$, while the denominator beneath $y^2$ is $9$.
   Because $25 > 9$:
   - For a point on the curve where $y = 0$, $x^2$ can reach all the way up to $25$ ($x = \pm 5$).
   - But for a point where $x = 0$, $y^2$ can only reach up to $9$ ($y = \pm 3$).
   A larger denominator under a variable means that variable must travel further away from zero to contribute its share toward the sum of $1$. Thus, the larger denominator $25$ under $x^2$ immediately announces that the ellipse is elongated along the $x$-axis.

---

### Step 4: Qualitative Sketch Layout

- Center at the origin $(0, 0)$.
- The curve is bounded inside the rectangular box $[-5, 5] \times [-3, 3]$.
- Symmetric across both the $x$-axis, the $y$-axis, and the origin.
- Smoothly tangent to the vertical boundary lines $x = \pm 5$ at $(5, 0)$ and $(-5, 0)$.
- Smoothly tangent to the horizontal boundary lines $y = \pm 3$ at $(0, 3)$ and $(0, -3)$.

---

## 5. Final Answer & Conclusion

- **Semiaxis Lengths:**

$$
a = 5 \quad (\text{horizontal}), \qquad b = 3 \quad (\text{vertical})
$$

- **Intercepts:**
  - $x$-axis: $(-5, 0)$ and $(5, 0)$
  - $y$-axis: $(0, -3)$ and $(0, 3)$
- **Stretching Explanation:**
  The ellipse is stretched along the $x$-axis because the denominator beneath $x^2$ ($25 = 5^2$) is strictly greater than the denominator beneath $y^2$ ($9 = 3^2$), allowing $x$ to reach $\pm 5$ while confining $y$ to $\pm 3$.

---

## 6. Quick Verification

Verify an intermediate point on the ellipse.
Let $x = 4$:

$$
\frac{4^2}{25} + \frac{y^2}{9} = 1 \implies \frac{16}{25} + \frac{y^2}{9} = 1 \implies \frac{y^2}{9} = 1 - \frac{16}{25} = \frac{9}{25}
$$

Multiply by $9$:

$$
y^2 = \frac{81}{25} \implies y = \pm \frac{9}{5} = \pm 1.8
$$

Check in the equation:

$$
\frac{4^2}{25} + \frac{(\pm 1.8)^2}{9} = \frac{16}{25} + \frac{3.24}{9} = 0.64 + 0.36 = 1.00
$$

The sum is identically $1$, confirming that $(4, 1.8)$ lies squarely on the ellipse.

---

## 7. Common Mistakes to Avoid

1. **Taking Denominators as Semiaxis Lengths Directly:**
   Reporting $a = 25$ and $b = 9$. The denominators represent the *squares* of the semiaxes: $a^2 = 25 \implies a = 5$ and $b^2 = 9 \implies b = 3$.
2. **Confusing Semiaxis with Full Axis:**
   Reporting the semiaxes as $10$ and $6$. Semiaxis is the half-length from center to vertex ($a = 5, b = 3$); the full axis length is $2a = 10, 2b = 6$.
3. **Inverting the Stretch Logic:**
   Assuming a larger denominator means a compressed axis. In fraction addition, dividing by a larger number means $x$ must be larger to produce the same numerical fraction value.

---

## 8. How I Would Explain This in Class

> "An ellipse is simply a circle that has been pulled like taffy in one direction. In the equation $\frac{x^2}{25} + \frac{y^2}{9} = 1$, the denominators are ruler measurements for each coordinate: the 25 under $x^2$ tells you that $x$ can stretch out to $\sqrt{25} = 5$, while the 9 under $y^2$ only lets $y$ reach $\sqrt{9} = 3$. Because 25 is bigger than 9, the taffy was pulled horizontally, giving an oval that is 10 units wide but only 6 units tall."

