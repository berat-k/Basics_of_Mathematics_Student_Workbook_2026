# Problem 03: A Box Made from Cardboard

## 1. The Original Problem

From a $30\text{ cm} \times 40\text{ cm}$ sheet, squares of side length $x$ are cut from the corners and the edges are folded up to form an open box.

Write the volume as a function of $x$, determine the physically meaningful domain, and find the value of $x$ for which the volume is greatest.

---

## 2. What Are We Trying to Find?

1. The volume function $V(x)$ of the open-top rectangular box in terms of the side length $x$ of the cut-out corner squares, measured in centimeters.
2. The physically meaningful domain of $x$ for which a genuine three-dimensional box can be formed.
3. The exact value $x^*$ inside that domain that maximizes $V(x)$, along with its decimal approximation, a rigorous justification that it yields the global maximum, and the corresponding optimal box dimensions and maximum volume.

---

## 3. Before Calculating: What Idea Do We Need?

- **Geometry of folding up the flaps:** Cutting a square of side $x$ from each of the four corners removes $x$ from *both* ends of the width and *both* ends of the length. Therefore:
  - the base width becomes $30 - 2x$,
  - the base length becomes $40 - 2x$,
  - the height of the folded box becomes $x$.
- **Volume of a rectangular box:** $V = \text{height} \times \text{width} \times \text{length}$.
- **Physical domain:** Every dimension of the box must be strictly positive, so we enforce $x > 0$, $30 - 2x > 0$, and $40 - 2x > 0$ simultaneously. The tightest upper bound comes from the shorter side of the sheet.
- **Finding and verifying the global maximum:** Since $V(x)$ is a cubic polynomial, its derivative $V'(x)$ is a quadratic polynomial with two real roots. We must check which root lies inside the physical domain, discard any root outside it, and confirm the maximum via both the first-derivative sign chart and the second-derivative test.

---

## 4. Step-by-Step Solution

### Step 1: Build the volume model $V(x)$

Visualize the $30\text{ cm} \times 40\text{ cm}$ sheet with a square of side $x$ removed from each corner:

```text
|<-------------- 40 cm -------------->|
+------+-----------------------+------+   ---
|  x   |                       |  x   |    ^
+------+ - - - - - - - - - - - +------+    |
|      |                       |      |    |
|      |   Base:               |      |  30 cm
|      |   (40 - 2x) by        |      |    |
|      |   (30 - 2x)           |      |    |
+------+ - - - - - - - - - - - +------+    |
|  x   |                       |  x   |    v
+------+-----------------------+------+   ---
|<--x->|<------ 40 - 2x ------>|<--x->|
```

When the four flaps are folded upward along the dashed lines:
- the **height** of the box is $h = x\text{ cm}$,
- the **width** of the base is $w = 30 - 2x\text{ cm}$,
- the **length** of the base is $\ell = 40 - 2x\text{ cm}$.

Multiplying the three dimensions gives the volume $V(x)$ in $\text{cm}^3$:

$$
V(x) = x(30 - 2x)(40 - 2x).
$$

Expanding the product prepares it for differentiation:

$$
\begin{aligned}
V(x) &= x\left(1200 - 60x - 80x + 4x^2\right) \\
     &= x\left(4x^2 - 140x + 1200\right) \\
     &= 4x^3 - 140x^2 + 1200x.
\end{aligned}
$$

### Step 2: Determine the physically meaningful domain

For an open box with positive volume, all three dimensions must be strictly positive:

$$
x > 0, \qquad 30 - 2x > 0, \qquad 40 - 2x > 0.
$$

Solving each inequality yields:

$$
x > 0, \qquad x < 15, \qquad x < 20.
$$

To satisfy all three inequalities simultaneously, $x$ must obey the strictest upper bound $x < 15$. Thus the physically meaningful domain is:

$$
D = (0, 15), \qquad \text{meaning } 0 < x < 15\text{ cm}.
$$

If we include the degenerate flat cases where no box rises up or the shorter side vanishes completely, we can also view $V(x)$ as a continuous function on the closed interval $[0, 15]$ with boundary values $V(0) = 0$ and $V(15) = 0$.

### Step 3: Differentiate and find the critical points

Differentiate $V(x) = 4x^3 - 140x^2 + 1200x$ with respect to $x$:

$$
V'(x) = 12x^2 - 280x + 1200.
$$

Factor out the common factor $4$:

$$
V'(x) = 4\left(3x^2 - 70x + 300\right).
$$

Set $V'(x) = 0$:

$$
3x^2 - 70x + 300 = 0.
$$

Compute the discriminant $\Delta = b^2 - 4ac$ with $a = 3$, $b = -70$, and $c = 300$:

$$
\Delta = (-70)^2 - 4(3)(300) = 4900 - 3600 = 1300 = 100 \cdot 13.
$$

Therefore $\sqrt{\Delta} = 10\sqrt{13}$, and the quadratic formula gives two roots:

$$
x = \frac{70 \pm 10\sqrt{13}}{6} = \frac{35 \pm 5\sqrt{13}}{3}.
$$

We denote these two roots by:

$$
x_1 = \frac{35 - 5\sqrt{13}}{3}, \qquad x_2 = \frac{35 + 5\sqrt{13}}{3}.
$$

### Step 4: Check which critical point lies in the domain $(0, 15)$

Even without a calculator, we know $9 < 13 < 16$, so $3 < \sqrt{13} < 4$ and hence $15 < 5\sqrt{13} < 20$. Consequently:
- For $x_1$: $35 - 20 < 35 - 5\sqrt{13} < 35 - 15$, which gives $15 < 35 - 5\sqrt{13} < 20$, so $5 < x_1 < \frac{20}{3} \approx 6.67$. Thus $x_1 \in (0, 15)$ is physically valid!
- For $x_2$: $35 + 5\sqrt{13} > 35 + 15 = 50$, so $x_2 > \frac{50}{3} \approx 16.67 > 15$. Thus $x_2 \notin (0, 15)$ and must be rejected because cutting squares larger than $15\text{ cm}$ from a $30\text{ cm}$ side is physically impossible.

Using $\sqrt{13} \approx 3.60555128$, the numerical approximations are:

$$
x_1 \approx 5.6574\text{ cm}, \qquad x_2 \approx 17.6759\text{ cm}.
$$

So the unique critical point inside the domain $(0, 15)$ is:

$$
x^* = \frac{35 - 5\sqrt{13}}{3} \approx 5.66\text{ cm}.
$$

### Step 5: Verify that $x^*$ gives the global maximum

**Method A: First-derivative sign analysis on $(0, 15)$.**

The quadratic $V'(x) = 12(x - x_1)(x - x_2)$ opens upward, so it is positive outside the interval $(x_1, x_2)$ and negative between $x_1$ and $x_2$. Restricting to our domain $(0, 15)$, where $0 < x_1 < 15 < x_2$:

| Interval or point | Sign of $x - x_1$ | Sign of $x - x_2$ | Sign of $V'(x)$ | Behavior of $V(x)$ |
| :--- | :---: | :---: | :---: | :--- |
| $0 < x < x_1$ | $-$ | $-$ | $+$ | Strictly increasing |
| $x = x_1$ | $0$ | $-$ | $0$ | Global maximum on $(0, 15)$ |
| $x_1 < x < 15$ | $+$ | $-$ | $-$ | Strictly decreasing |

Since $V(x)$ increases strictly on $(0, x_1)$ and decreases strictly on $(x_1, 15)$, the point $x^* = x_1$ yields the unique **global maximum** on $(0, 15)$ and also on $[0, 15]$.

**Method B: Second-derivative test.**

Differentiating $V'(x) = 12x^2 - 280x + 1200$ gives:

$$
V''(x) = 24x - 280.
$$

Evaluating $V''$ at $x^* = \frac{35 - 5\sqrt{13}}{3}$:

$$
V''(x^*) = 24 \cdot \frac{35 - 5\sqrt{13}}{3} - 280 = 8\left(35 - 5\sqrt{13}\right) - 280 = 280 - 40\sqrt{13} - 280 = -40\sqrt{13}.
$$

Since $V''(x^*) = -40\sqrt{13} \approx -144.22 < 0$, the graph of $V(x)$ is concave down at $x^*$, confirming a strict maximum.

### Step 6: Compute the optimal dimensions and maximum volume

At $x^* = \frac{35 - 5\sqrt{13}}{3} \approx 5.6574\text{ cm}$, the remaining box dimensions are:

$$
30 - 2x^* = 30 - \frac{70 - 10\sqrt{13}}{3} = \frac{20 + 10\sqrt{13}}{3} = \frac{10\left(2 + \sqrt{13}\right)}{3} \approx 18.6852\text{ cm},
$$

$$
40 - 2x^* = 40 - \frac{70 - 10\sqrt{13}}{3} = \frac{50 + 10\sqrt{13}}{3} = \frac{10\left(5 + \sqrt{13}\right)}{3} \approx 28.6852\text{ cm}.
$$

Multiplying the three exact dimensions gives the exact maximum volume:

$$
\begin{aligned}
V(x^*) &= \frac{5\left(7 - \sqrt{13}\right)}{3} \cdot \frac{10\left(2 + \sqrt{13}\right)}{3} \cdot \frac{10\left(5 + \sqrt{13}\right)}{3} \\
       &= \frac{500}{27}\left(7 - \sqrt{13}\right)\left(10 + 7\sqrt{13} + 13\right) \\
       &= \frac{500}{27}\left(7 - \sqrt{13}\right)\left(23 + 7\sqrt{13}\right) \\
       &= \frac{500}{27}\left(161 + 49\sqrt{13} - 23\sqrt{13} - 91\right) \\
       &= \frac{500}{27}\left(70 + 26\sqrt{13}\right) \\
       &= \frac{1000\left(35 + 13\sqrt{13}\right)}{27}\text{ cm}^3.
\end{aligned}
$$

Evaluating numerically:

$$
V(x^*) \approx \frac{1000\left(35 + 13 \times 3.60555128\right)}{27} \approx 3032.30\text{ cm}^3 \approx 3.032\text{ L}.
$$

---

## 5. Final Answer & Conclusion

- **Volume function:**

$$
V(x) = x(30 - 2x)(40 - 2x) = 4x^3 - 140x^2 + 1200x.
$$

- **Physically meaningful domain:** $x \in (0, 15)$, meaning $0 < x < 15\text{ cm}$.
- **Optimal corner cut:**

$$
x^* = \frac{35 - 5\sqrt{13}}{3}\text{ cm} \approx 5.66\text{ cm}.
$$

- **Optimal box dimensions and maximum volume:** height $\approx 5.66\text{ cm}$, base $\approx 18.69\text{ cm} \times 28.69\text{ cm}$, and maximum volume

$$
V(x^*) = \frac{1000\left(35 + 13\sqrt{13}\right)}{27}\text{ cm}^3 \approx 3032.30\text{ cm}^3.
$$

---

## 6. Quick Verification

1. **Numerical table around $x^* \approx 5.6574\text{ cm}$:**

| $x$ in $\text{cm}$ | $30 - 2x$ in $\text{cm}$ | $40 - 2x$ in $\text{cm}$ | $V(x)$ in $\text{cm}^3$ |
| :---: | :---: | :---: | :---: |
| $5.00$ | $20.00$ | $30.00$ | $3000.0000$ |
| $5.50$ | $19.00$ | $29.00$ | $3030.5000$ |
| $5.60$ | $18.80$ | $28.80$ | $3032.0640$ |
| $5.65$ | $18.70$ | $28.70$ | $3032.2985$ |
| $x^* \approx 5.6574$ | $\approx 18.6852$ | $\approx 28.6852$ | $\approx 3032.3025$ |
| $5.66$ | $18.68$ | $28.68$ | $3032.3020$ |
| $5.70$ | $18.60$ | $28.60$ | $3032.1720$ |
| $6.00$ | $18.00$ | $28.00$ | $3024.0000$ |

The volume rises steadily up to $x^* \approx 5.6574\text{ cm}$ and falls strictly afterward, matching our calculus result.

2. **Direct substitution into $V'(x) = 0$:**
   Using $x^* = \frac{35 - 5\sqrt{13}}{3}$, we compute:

$$
(x^*)^2 = \frac{1225 - 350\sqrt{13} + 325}{9} = \frac{1550 - 350\sqrt{13}}{9}.
$$

   Substituting into $3(x^*)^2 - 70x^* + 300$:

$$
\frac{1550 - 350\sqrt{13}}{3} - \frac{2450 - 350\sqrt{13}}{3} + \frac{900}{3} = \frac{1550 - 2450 + 900}{3} = 0.
$$

3. **Check boundary behavior:** At $x = 0$, $V(0) = 0$; at $x = 15$, $V(15) = 15 \cdot 0 \cdot 10 = 0$; and at $x^*$, $V(x^*) \approx 3032.30 > 0$.

---

## 7. Common Mistakes to Avoid

- **Writing $(30 - x)(40 - x)$ instead of $(30 - 2x)(40 - 2x)$:** Squares are cut from *all four* corners, so each edge loses $x$ on the left and $x$ on the right, a total reduction of $2x$.
- **Forgetting to discard the second root $x_2 \approx 17.68\text{ cm}$:** Algebraically, $x_2$ is a genuine local minimum of the cubic $4x^3 - 140x^2 + 1200x$, where $V(x_2) < 0$ because $30 - 2x_2 < 0$. Geometrically it is meaningless because you cannot cut two $17.68\text{ cm}$ squares out of a $30\text{ cm}$ side!
- **Using the longer side to determine the domain:** Requiring only $40 - 2x > 0$ gives $x < 20$, which mistakenly allows values between $15$ and $20$ where the shorter side $30 - 2x$ is negative.
- **Rounding too early in intermediate steps:** Keeping the exact radical $x^* = \frac{35 - 5\sqrt{13}}{3}$ until the final evaluation avoids cumulative rounding errors in $V''(x^*)$ and $V(x^*)$.

---

## 8. How I Would Explain This in Class

> "Picture cutting those four little squares out of a poster board. If your cut $x$ is tiny, you get a huge base but paper-thin walls, so the box holds almost nothing. If your cut $x$ gets close to 15 centimeters, the walls are tall, but the shorter side of the base shrinks down to a narrow ribbon, so again the box holds almost nothing. Somewhere in between, the tug-of-war between height and base area reaches its sweet spot. Writing the volume as a cubic and setting its derivative to zero pinpoints that exact balance at $x^* = \frac{35 - 5\sqrt{13}}{3}$ centimeters, a little over 5.65 centimeters, while the physical domain immediately warns us to throw away the phantom algebraic root near 17.68 centimeters."
