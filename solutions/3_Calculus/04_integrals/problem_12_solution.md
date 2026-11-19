# Problem 12: Symmetry, Sign, and Absolute Value

## 1. The Original Problem

Compare

$$
\int_{-2}^{2}x\,dx
$$

and

$$
\int_{-2}^{2}|x|\,dx.
$$

Before calculating, predict the results from symmetry and a sketch, then carry out the calculation and explain the difference.

---

## 2. What Are We Trying to Find?

1. Visual sketches of $f(x) = x$ and $g(x) = |x|$ on the symmetric interval $[-2, 2]$.
2. Predictions of both definite integrals **before** calculating, using odd/even symmetry and geometric reasoning.
3. Exact algebraic computations of the definite integral of $x$ and the definite integral of $|x|$ over $[-2, 2]$.
4. A clear conceptual explanation of why the two integrals differ.

---

## 3. Before Calculating: What Idea Do We Need?

- **Symmetric interval $[-a, a]$:** Both integrals are evaluated over $[-2, 2]$, which is symmetric about the origin $x = 0$.
- **Odd function symmetry:** A function $f$ is **odd** if $f(-x) = -f(x)$ for all $x$. For any continuous odd function on $[-a, a]$, the signed areas on $[-a, 0]$ and $[0, a]$ have equal magnitude and opposite signs, so they cancel completely:

$$
\int_{-a}^{a} f(x)\,dx = 0.
$$

- **Even function symmetry:** A function $g$ is **even** if $g(-x) = g(x)$ for all $x$. For any continuous even function on $[-a, a]$, the graph is symmetric across the $y$-axis, so the integral over $[-a, a]$ is twice the integral over $[0, a]$:

$$
\int_{-a}^{a} g(x)\,dx = 2\int_{0}^{a} g(x)\,dx.
$$

- **Piecewise definition of absolute value:** To integrate $|x|$ directly using antiderivatives, we remove the absolute value bars by splitting at $x = 0$:

$$
|x| = \begin{cases} -x, & x < 0, \\ x, & x \ge 0. \end{cases}
$$

---

## 4. Step-by-Step Solution

### Step 1: Sketch Both Graphs and Predict the Results from Symmetry

**Graph 1: $f(x) = x$ on $[-2, 2]$**

Notice that $f(-x) = -x = -f(x)$, so $f(x) = x$ is an **odd** function.

```text
      y
      ^
    2 +                     * (2, 2)
      |                   / |
      |                 /###|  Signed area = +2
    1 +               /#####|  (base = 2, height = 2)
      |             /#######|
   ---+-----------+---------+-----> x
     -2           0         2
      |#######  / |
   -1 +#####  /   |  Signed area = -2
      |###  /     |  (base = 2, height = 2)
   -2 + * /       |
  (-2,-2)         |
```

- **Prediction for $\int_{-2}^{2} x\,dx$:** The triangle on $[-2, 0]$ lies below the $x$-axis with area $\frac{1}{2} \cdot 2 \cdot 2 = 2$, contributing $-2$. The congruent triangle on $[0, 2]$ lies above the $x$-axis, contributing $+2$. By odd symmetry, they cancel completely, so we predict

$$
\int_{-2}^{2} x\,dx = -2 + 2 = 0.
$$

**Graph 2: $g(x) = |x|$ on $[-2, 2]$**

Notice that $g(-x) = |-x| = |x| = g(x)$, so $g(x) = |x|$ is an **even** function, and $g(x) \ge 0$ everywhere.

```text
      y
      ^
    2 + *                   * (2, 2)
(-2,2)| |\                / |
      | |##\            /###|  Two identical triangles
    1 + |####\        /#####|  above the x-axis:
      | |######\    /#######|  each has base = 2, height = 2
      | |########\/#########|  and area = 2
   ---+-----------+---------+-----> x
     -2           0         2
```

- **Prediction for $\int_{-2}^{2} |x|\,dx$:** Both congruent right triangles now lie **above** the $x$-axis, each with base $2$, height $2$, and area $\frac{1}{2} \cdot 2 \cdot 2 = 2$. By even symmetry, the two areas reinforce each other rather than canceling, so we predict

$$
\int_{-2}^{2} |x|\,dx = 2 + 2 = 4.
$$

### Step 2: Compute $\int_{-2}^{2} x\,dx$ Algebraically

Using the antiderivative $F(x) = \frac{1}{2}x^2$:

$$
\int_{-2}^{2} x\,dx = \left[\frac{1}{2}x^2\right]_{-2}^{2} = \frac{1}{2}(2)^2 - \frac{1}{2}(-2)^2 = 2 - 2 = 0.
$$

This matches our symmetry prediction of $0$ exactly.

### Step 3: Compute $\int_{-2}^{2} |x|\,dx$ Algebraically

Because $|x|$ changes algebraic formula at $x = 0$, we split the integral at $x = 0$ using additivity:

$$
\begin{aligned}
\int_{-2}^{2} |x|\,dx &= \int_{-2}^{0} (-x)\,dx + \int_{0}^{2} x\,dx \\
&= \left[-\frac{1}{2}x^2\right]_{-2}^{0} + \left[\frac{1}{2}x^2\right]_{0}^{2} \\
&= \left(0 - \left(-\frac{1}{2}(-2)^2\right)\right) + \left(\frac{1}{2}(2)^2 - 0\right) \\
&= (0 - (-2)) + (2 - 0) \\
&= 2 + 2 = 4.
\end{aligned}
$$

Equivalently, using the even-function shortcut directly:

$$
\int_{-2}^{2} |x|\,dx = 2\int_{0}^{2} x\,dx = 2\left[\frac{1}{2}x^2\right]_{0}^{2} = 2(2 - 0) = 4.
$$

This also matches our symmetry prediction of $4$ exactly.

### Step 4: Explain the Difference

| Property | Integral of $x$ on $[-2, 2]$ | Integral of $\lvert x \rvert$ on $[-2, 2]$ |
| --- | --- | --- |
| Symmetry of integrand | Odd, $f(-x) = -f(x)$ | Even, $g(-x) = g(x)$ |
| Sign on $[-2, 0)$ | Negative | Positive |
| Sign on $(0, 2]$ | Positive | Positive |
| Effect of left and right halves | Cancellation: $-2 + 2$ | Addition: $2 + 2$ |
| Value of integral | $0$ | $4$ |
| Geometric meaning | Net signed area | Total unsigned geometric area |

Taking the absolute value of $x$ reflects the negative part of the graph on $[-2, 0]$ upward across the $x$-axis. As a result, the integral of $x$ over $[-2, 2]$ measures the **net signed area**, where opposite halves cancel to $0$, whereas the integral of $|x|$ over $[-2, 2]$ measures the **total geometric area** enclosed between $y = x$ and the $x$-axis on $[-2, 2]$, doubling one triangle to give $4$.

---

## 5. Final Answer & Conclusion

- Predicted and exact values:

$$
\int_{-2}^{2} x\,dx = 0, \qquad \int_{-2}^{2} |x|\,dx = 4.
$$

- **Explanation:** On the symmetric interval $[-2, 2]$, the odd function $x$ produces equal and opposite signed areas that cancel to $0$. Applying the absolute value turns the integrand into the non-negative even function $|x|$, flipping the negative contribution on $[-2, 0]$ into a positive one so that the two halves add together to give the total geometric area $4$.

---

## 6. Quick Verification

1. **Direct triangle-area verification:** Each triangle on $[-2, 0]$ and $[0, 2]$ has base $2$ and height $2$, so each has geometric area $\frac{1}{2} \cdot 2 \cdot 2 = 2$.
   - Net signed area for $y = x$: $-2 + 2 = 0$.
   - Total unsigned area for $y = |x|$: $2 + 2 = 4$.
2. **Inequality check between integrals:** For any continuous function $f$ on $[a, b]$ with $a \le b$, the triangle inequality for integrals states that

$$
\left|\int_{a}^{b} f(x)\,dx\right| \le \int_{a}^{b} |f(x)|\,dx.
$$

Here $|0| = 0 \le 4$, which holds strictly because $f(x) = x$ changes sign on $[-2, 2]$.

---

## 7. Common Mistakes to Avoid

- **Trying to pull absolute value bars outside the integral:** Writing $\int_{-2}^{2} |x|\,dx = \left|\int_{-2}^{2} x\,dx\right| = |0| = 0$. In general, $\int |f(x)|\,dx \ne \left|\int f(x)\,dx\right|$ whenever $f$ changes sign!
- **Ignoring the absolute value and using $\frac{1}{2}x^2$ across $[-2, 2]$:** Treating $|x|$ as if it were $x$ gives $0$ instead of $4$. Always split an absolute value integral at the points where the inside expression equals $0$.
- **Making a sign error on the negative piece:** Computing $\left[-\frac{1}{2}x^2\right]_{-2}^{0}$ as $0 - \frac{1}{2}(4) = -2$ instead of $0 - \left(-\frac{1}{2}(4)\right) = +2$. Remember that on $[-2, 0]$ we are integrating the positive function $-x$, so the result must be positive!
- **Applying odd/even symmetry shortcuts on non-symmetric intervals:** Odd symmetry gives $0$ on $[-2, 2]$, but NOT on $[-1, 2]$ as seen in Problem 9. Always verify that the limits are $-a$ and $+a$ first.

---

## 8. How I Would Explain This in Class

> "Picture walking $2$ kilometers west and then $2$ kilometers east. Your net displacement — that is the integral of $x$ from $-2$ to $2$ — is $0$, because you ended up right back where you started. Your odometer — that is the integral of $|x|$ from $-2$ to $2$ — doesn't care about minus signs; it adds every step as positive distance and reads $4$. Absolute value inside the integral flips the negative half up into the positive half, turning cancellation into doubling."
