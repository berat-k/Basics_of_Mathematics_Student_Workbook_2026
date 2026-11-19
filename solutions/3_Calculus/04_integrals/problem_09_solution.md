# Problem 9: Definite Integral and Geometric Area

## 1. The Original Problem

Compute

$$
\int_{-1}^{2} x\,dx.
$$

Then separately compute the areas of the parts of the graph below and above the $x$-axis and explain the difference between the definite integral and geometric area.

---

## 2. What Are We Trying to Find?

1. The exact value of the definite integral $\int_{-1}^{2} x\,dx$.
2. A clear picture of where the graph of $f(x) = x$ lies below and above the $x$-axis on the interval $[-1, 2]$.
3. The separate geometric area of the region below the $x$-axis on $[-1, 0]$ and the region above the $x$-axis on $[0, 2]$, as well as their sum, which is the total geometric area.
4. A clear conceptual explanation of the difference between a definite integral and geometric area.

---

## 3. Before Calculating: What Idea Do We Need?

- **Fundamental Theorem of Calculus, Part 2:** If $F$ is any antiderivative of a continuous function $f$ on $[a, b]$, then

$$
\int_{a}^{b} f(x)\,dx = F(b) - F(a).
$$

- **Signed area interpretation:** A definite integral $\int_{a}^{b} f(x)\,dx$ measures **net signed area** between the graph of $f$ and the $x$-axis. Regions where $f(x) > 0$ contribute positively, while regions where $f(x) < 0$ contribute negatively.
- **Geometric area formula:** Geometric area is always non-negative. To compute the total geometric area between $y = f(x)$ and the $x$-axis on $[a, b]$, we integrate the absolute value $|f(x)|$:

$$
A_{\text{total}} = \int_{a}^{b} |f(x)|\,dx.
$$

In practice, we find the zeros of $f(x)$ inside $[a, b]$, split the interval there, integrate $f(x)$ where $f(x) \ge 0$, and integrate $-f(x)$ where $f(x) \le 0$.
- **Elementary geometry connection:** Because $f(x) = x$ is a straight line, the regions between the graph and the $x$-axis are right triangles whose areas can also be computed directly with $\frac{1}{2} \times \text{base} \times \text{height}$.

---

## 4. Step-by-Step Solution

### Step 1: Compute the Definite Integral Directly

For the integrand $f(x) = x$, the power rule gives the antiderivative

$$
F(x) = \frac{1}{2}x^2.
$$

Applying the Fundamental Theorem of Calculus on $[-1, 2]$:

$$
\int_{-1}^{2} x\,dx = \left[\frac{1}{2}x^2\right]_{-1}^{2} = \frac{1}{2}(2)^2 - \frac{1}{2}(-1)^2 = \frac{4}{2} - \frac{1}{2} = 2 - \frac{1}{2} = \frac{3}{2}.
$$

So the definite integral equals $\frac{3}{2}$, or $1.5$ in decimal form.

### Step 2: Locate the Sign Change and Sketch the Regions

To separate the graph into parts below and above the $x$-axis, set $f(x) = 0$:

$$
x = 0.
$$

Thus the graph crosses the $x$-axis at the origin:

- For $-1 \le x < 0$, we have $f(x) = x < 0$, so the graph lies **below** the $x$-axis.
- For $0 < x \le 2$, we have $f(x) = x > 0$, so the graph lies **above** the $x$-axis.

```text
      y
      ^
    2 +                  * (2, 2)
      |                / |
      |              /###|  Above x-axis:
    1 +            /#####|  right triangle
      |          /#######|  base = 2, height = 2
      |        /#########|  Area = 2
   ---+-------+----------+-----> x
     -1      0|          2
      |###  / |
   -1 + * /   |  Below x-axis:
  (-1,-1)     |  right triangle
              |  base = 1, height = 1
              |  Area = 1/2
```

### Step 3: Compute the Area Below the $x$-Axis

On the subinterval $[-1, 0]$, the function satisfies $x \le 0$, so $|x| = -x$.

First, notice what the definite integral over $[-1, 0]$ produces:

$$
\int_{-1}^{0} x\,dx = \left[\frac{1}{2}x^2\right]_{-1}^{0} = 0 - \frac{1}{2}(-1)^2 = -\frac{1}{2}.
$$

The negative sign reflects that the region lies below the $x$-axis. The **geometric area** below the $x$-axis is positive:

$$
A_{\text{below}} = \int_{-1}^{0} |x|\,dx = \int_{-1}^{0} (-x)\,dx = \left[-\frac{1}{2}x^2\right]_{-1}^{0} = 0 - \left(-\frac{1}{2}\right) = \frac{1}{2}.
$$

Geometrically, this is a right triangle with vertices $(-1, 0)$, $(0, 0)$, and $(-1, -1)$, which has base $1$ and height $1$, so

$$
A_{\text{below}} = \frac{1}{2} \cdot 1 \cdot 1 = \frac{1}{2}.
$$

### Step 4: Compute the Area Above the $x$-Axis

On the subinterval $[0, 2]$, the function satisfies $x \ge 0$, so $|x| = x$. The geometric area above the $x$-axis is

$$
A_{\text{above}} = \int_{0}^{2} x\,dx = \left[\frac{1}{2}x^2\right]_{0}^{2} = \frac{1}{2}(2)^2 - 0 = 2.
$$

Geometrically, this is a right triangle with vertices $(0, 0)$, $(2, 0)$, and $(2, 2)$, which has base $2$ and height $2$, so

$$
A_{\text{above}} = \frac{1}{2} \cdot 2 \cdot 2 = 2.
$$

### Step 5: Compare the Definite Integral and Geometric Area

| Quantity | Formula | Value |
| --- | --- | --- |
| Area below the $x$-axis on $[-1, 0]$ | $\int_{-1}^{0} (-x)\,dx$ | $\frac{1}{2} = 0.5$ |
| Area above the $x$-axis on $[0, 2]$ | $\int_{0}^{2} x\,dx$ | $2$ |
| Definite integral on $[-1, 2]$ | $A_{\text{above}} - A_{\text{below}}$ | $2 - \frac{1}{2} = \frac{3}{2} = 1.5$ |
| Total geometric area on $[-1, 2]$ | $A_{\text{above}} + A_{\text{below}}$ | $2 + \frac{1}{2} = \frac{5}{2} = 2.5$ |

**Why are they different?**

- A **definite integral** computes **signed accumulation**, meaning regions above the $x$-axis are added and regions below the $x$-axis are subtracted. Here, the region of area $\frac{1}{2}$ below the axis cancels out an equal amount of area from the region above the axis, leaving a net value of $2 - \frac{1}{2} = \frac{3}{2}$.
- **Geometric area** is strictly non-negative and ignores orientation above or below the axis. Both regions contribute positively, so the total area is $2 + \frac{1}{2} = \frac{5}{2}$.
- The definite integral equals geometric area **only** when $f(x) \ge 0$ across the entire interval of integration.

---

## 5. Final Answer & Conclusion

- Definite integral:

$$
\int_{-1}^{2} x\,dx = \frac{3}{2}.
$$

- Geometric area below the $x$-axis, on $[-1, 0]$:

$$
A_{\text{below}} = \frac{1}{2}.
$$

- Geometric area above the $x$-axis, on $[0, 2]$:

$$
A_{\text{above}} = 2.
$$

- Total geometric area enclosed with the $x$-axis on $[-1, 2]$:

$$
A_{\text{total}} = \int_{-1}^{2} |x|\,dx = \frac{1}{2} + 2 = \frac{5}{2}.
$$

- **Key difference:** The definite integral computes net signed area, where negative values cancel positive values, whereas geometric area computes total unsigned area:

$$
A_{\text{above}} - A_{\text{below}} = \frac{3}{2}, \qquad A_{\text{above}} + A_{\text{below}} = \frac{5}{2}.
$$

---

## 6. Quick Verification

1. **Additivity and triangle-area check:** Splitting the definite integral at $x = 0$ gives

$$
\int_{-1}^{2} x\,dx = \int_{-1}^{0} x\,dx + \int_{0}^{2} x\,dx = -\frac{1}{2} + 2 = \frac{3}{2}.
$$

Using the triangle areas directly, the net signed area is $+2 - \frac{1}{2} = \frac{3}{2}$, matching the Fundamental Theorem calculation.
2. **Symmetry cancellation check:** Split $[-1, 2]$ into $[-1, 1]$ and $[1, 2]$. Since $f(x) = x$ is an odd function, the signed area on $[-1, 1]$ cancels to $0$:

$$
\int_{-1}^{1} x\,dx = 0.
$$

What remains is the trapezoid on $[1, 2]$ with parallel vertical sides of heights $f(1) = 1$ and $f(2) = 2$ and width $1$. Its area is

$$
\frac{1 + 2}{2} \cdot 1 = \frac{3}{2},
$$

confirming $\int_{-1}^{2} x\,dx = \frac{3}{2}$ independently!

---

## 7. Common Mistakes to Avoid

- **Equating every definite integral with geometric area:** Students often report $\frac{3}{2}$ as the total area between $y = x$ and the $x$-axis on $[-1, 2]$, forgetting that the portion on $[-1, 0]$ is below the axis and was subtracted rather than added.
- **Sign error when squaring the lower limit:** Writing $\frac{1}{2}(2)^2 - \frac{1}{2}(-1)^2 = 2 - \left(-\frac{1}{2}\right) = \frac{5}{2}$ because of computing $(-1)^2$ as $-1$ instead of $+1$. Always square first: $(-1)^2 = +1$.
- **Reporting a negative geometric area:** Writing $A_{\text{below}} = -\frac{1}{2}$. Geometric area is always non-negative; the minus sign belongs to the signed integral on $[-1, 0]$, not to the area itself.
- **Forgetting to split at the zero of the integrand:** Trying to compute $\int_{-1}^{2} |x|\,dx$ with a single antiderivative without splitting at $x = 0$, where $|x|$ changes formula from $-x$ to $x$.

---

## 8. How I Would Explain This in Class

> "Think of a definite integral like your bank account balance over a few days, where money deposited is above the axis and money spent is below the axis. From $x = -1$ to $x = 0$, you spend half a dollar; from $x = 0$ to $x = 2$, you deposit two dollars. Your net change in balance — the definite integral — is $2 - 0.5 = 1.5$ dollars. But if someone asks for the total volume of cash that moved through your hands — the geometric area — you add both transactions as positive numbers and get $2 + 0.5 = 2.5$ dollars. Same graph, two completely different questions!"
