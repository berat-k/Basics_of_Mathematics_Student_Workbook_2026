# Problem 06: Average Value of a Function

## 1. The Original Problem

Compute the average value of the function

$$
f(x) = x^2
$$

on the interval $[0, 3]$.

Find a point $c \in [0, 3]$ for which $f(c)$ is equal to this average value, and interpret the result geometrically.

---

## 2. What Are We Trying to Find?

1. The continuous average value $f_{\text{avg}}$ of $f(x) = x^2$ on the closed interval $[0, 3]$.
2. A point $c \in [0, 3]$ satisfying $f(c) = f_{\text{avg}}$, as guaranteed by the Mean Value Theorem for Integrals.
3. A clear geometric interpretation connecting the average value, the point $c$, the area under the parabola, and the area of a rectangle.

---

## 3. Before Calculating: What Idea Do We Need?

- **Average value of a function on $[a, b]$:** Just as the average of $n$ discrete numbers sums them and divides by $n$, the average value of an integrable function $f$ on $[a, b]$ sums its values continuously via the definite integral and divides by the length of the interval $b - a$:

$$
f_{\text{avg}} = \frac{1}{b - a} \int_a^b f(x)\,dx.
$$

- **Mean Value Theorem for Integrals:** If $f$ is continuous on $[a, b]$, then there exists at least one number $c \in [a, b]$ such that

$$
f(c) = f_{\text{avg}} = \frac{1}{b - a} \int_a^b f(x)\,dx, \qquad \text{equivalently } \int_a^b f(x)\,dx = f(c)(b - a).
$$

- **Geometric interpretation:** For a non-negative function $f(x) \ge 0$, multiplying the average value by the interval width gives the area $f_{\text{avg}}(b - a)$ of a rectangle with width $b - a$ and constant height equal to that average value. Equality with $\int_a^b f(x)\,dx$ means this rectangle has the exact same area as the curved region beneath the graph of $f$, and $x = c$ is where the curve crosses that horizontal average level.

---

## 4. Step-by-Step Solution

### Step 1: Compute the average value of $f(x) = x^2$ on $[0, 3]$

Apply the average value formula with $a = 0$, $b = 3$, and $f(x) = x^2$:

$$
f_{\text{avg}} = \frac{1}{3 - 0} \int_0^3 x^2\,dx = \frac{1}{3} \int_0^3 x^2\,dx.
$$

First evaluate the definite integral:

$$
\int_0^3 x^2\,dx = \left[\frac{x^3}{3}\right]_0^3 = \frac{3^3}{3} - \frac{0^3}{3} = \frac{27}{3} - 0 = 9.
$$

Now divide by the interval length $b - a = 3$:

$$
f_{\text{avg}} = \frac{1}{3} \cdot 9 = 3.
$$

Thus, the average value of $f(x) = x^2$ on $[0, 3]$ is $3$.

### Step 2: Find the point $c \in [0, 3]$ such that $f(c) = f_{\text{avg}}$

Since $f(x) = x^2$ is continuous on $[0, 3]$, the Mean Value Theorem for Integrals guarantees at least one $c \in [0, 3]$ satisfying $f(c) = 3$:

$$
c^2 = 3.
$$

Solving over $\mathbb{R}$ gives two solutions:

$$
c = \sqrt{3} \qquad \text{or} \qquad c = -\sqrt{3}.
$$

Because we require $c \in [0, 3]$ and $0 < \sqrt{3} \approx 1.7321 < 3$ whereas $-\sqrt{3} < 0$, we discard $-\sqrt{3}$ and obtain the unique point in $[0, 3]$:

$$
c = \sqrt{3} \approx 1.7321.
$$

### Step 3: Interpret the result geometrically

Geometrically, the result has three linked meanings:

1. **Equal-area rectangle:** The area under the parabola $y = x^2$ from $x = 0$ to $x = 3$ is $\int_0^3 x^2\,dx = 9$. The horizontal line $y = f_{\text{avg}} = 3$ forms a rectangle over $[0, 3]$ of width $3$ and height $3$, whose area is also $3 \times 3 = 9$.
2. **Exact leveling of excess and deficit:** The point $c = \sqrt{3}$ is the exact $x$-coordinate where the parabola $y = x^2$ crosses the horizontal line $y = 3$. If you imagine the region under $y = x^2$ as a pile of sand over $[0, 3]$ and flatten the sand into a uniform layer, the excess sand sitting *above* $y = 3$ on $[\sqrt{3}, 3]$ fills the empty space *below* $y = 3$ on $[0, \sqrt{3}]$ with nothing left over.
3. **Why $f_{\text{avg}} < 4.5$ and $c > 1.5$:** Because $f(x) = x^2$ is strictly convex — bending upward — it stays low over the left half of $[0, 3]$ and shoots up rapidly near $x = 3$. Consequently, its true average value $3$ is noticeably lower than the midpoint of its endpoint values, $\frac{f(0) + f(3)}{2} = \frac{0 + 9}{2} = 4.5$, and the curve does not reach height $3$ until $c = \sqrt{3} \approx 1.732$, slightly past the interval midpoint $1.5$.

```text
y
9 +                              * (3, 9)
  |                             *|
  |                           *  |  <-- excess above y = 3
6 +                         *    |      (area = 2*sqrt(3))
  |                       *      |
  |                    *         |
3 +------------------*-----------+  <-- average level y = 3
  |  empty gap     * |           |      (rectangle area = 3 x 3 = 9)
  | (area =     *    |           |
  | 2*sqrt(3)) *     |           |
0 +*-----------------+-----------+---> x
  0              c=sqrt(3)       3
                 (~1.732)
```

---

## 5. Final Answer & Conclusion

- **Average value on $[0, 3]$:**

$$
f_{\text{avg}} = 3.
$$

- **Point $c \in [0, 3]$ with $f(c) = f_{\text{avg}}$:**

$$
c = \sqrt{3} \approx 1.7321.
$$

- **Geometric interpretation:** The rectangle over $[0, 3]$ of constant height $f(c) = 3$ has area $3 \cdot 3 = 9$, equal to the area under $y = x^2$ on $[0, 3]$. The curve crosses this average level at $x = \sqrt{3}$, where the area above the line $y = 3$ on $[\sqrt{3}, 3]$ exactly balances the area below $y = 3$ on $[0, \sqrt{3}]$.

---

## 6. Quick Verification

1. **Exact area-balance check between deficit and excess:**
   Compute the area of the gap below $y = 3$ on $[0, \sqrt{3}]$:

$$
A_{\text{below}} = \int_0^{\sqrt{3}} \left(3 - x^2\right)\,dx = \left[3x - \frac{x^3}{3}\right]_0^{\sqrt{3}} = 3\sqrt{3} - \frac{3\sqrt{3}}{3} = 2\sqrt{3}.
$$

   Compute the area of the mound above $y = 3$ on $[\sqrt{3}, 3]$:

$$
A_{\text{above}} = \int_{\sqrt{3}}^3 \left(x^2 - 3\right)\,dx = \left[\frac{x^3}{3} - 3x\right]_{\sqrt{3}}^3 = (9 - 9) - \left(\sqrt{3} - 3\sqrt{3}\right) = 2\sqrt{3}.
$$

   Indeed $A_{\text{below}} = A_{\text{above}} = 2\sqrt{3} \approx 3.4641$, confirming perfect area balance!

2. **Sanity check via discrete sample averages:**
   Sampling $f(x) = x^2$ at $6$ midpoints $x = 0.25, 0.75, 1.25, 1.75, 2.25, 2.75$ gives function values $0.0625, 0.5625, 1.5625, 3.0625, 5.0625, 7.5625$. Their arithmetic mean is:

$$
\frac{0.0625 + 0.5625 + 1.5625 + 3.0625 + 5.0625 + 7.5625}{6} = \frac{17.875}{6} \approx 2.9792,
$$

   already very close to the exact continuous average $3$, and approaching $3$ as the number of sample points grows.

3. **Direct substitution check:** $f(\sqrt{3}) = (\sqrt{3})^2 = 3 = f_{\text{avg}}$, and $0 \le \sqrt{3} \le 3$.

---

## 7. Common Mistakes to Avoid

- **Averaging only the endpoints:** Computing $\frac{f(0) + f(3)}{2} = \frac{0 + 9}{2} = 4.5$ works only for *linear* functions. For curved functions like $f(x) = x^2$, endpoint averaging ignores the curvature and gives the wrong result.
- **Forgetting to divide by the interval length $b - a$:** Reporting the integral $\int_0^3 x^2\,dx = 9$ as the average value confuses total area with average height. Remember that $9$ is the *maximum* value of $f(x)$ on $[0, 3]$, so it cannot possibly be its average!
- **Confusing $c$ with the midpoint of the interval:** Evaluating $f(1.5) = 2.25$ does not give the average value, and $c$ is generally *not* the midpoint $\frac{a + b}{2}$ unless $f$ is linear or appropriately symmetric.
- **Keeping $c = -\sqrt{3}$:** Always check that $c$ belongs to the given interval $[0, 3]$.

---

## 8. How I Would Explain This in Class

> "Picture pouring water into a transparent tank shaped like the area under $y = x^2$ from $x = 0$ to $x = 3$, and then letting gravity flatten the top surface into a perfectly level horizontal line. That level water height is the average value, $y = 3$, because the amount of water never changes: total area stays 9, spread evenly across width 3. Notice why the water settles at height 3 instead of 4.5 — the parabola hugs the floor for a long stretch before climbing steeply near $x = 3$, so there is much less water on the left than a straight ramp would hold. And the exact spot where the original parabola pokes through the flat waterline is $c = \sqrt{3}$."
