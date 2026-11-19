# Problem 14: A Piecewise-Defined Function

## 1. The Original Problem

Let

$$
f(x)=\begin{cases}x+1,&-1\le x<1,\\2,&1\le x\le3.\end{cases}
$$

Sketch the graph, decide where to split the integral, compute

$$
\int_{-1}^{3}f(x)\,dx
$$

and verify the result geometrically.

---

## 2. What Are We Trying to Find?

1. An accurate sketch of the piecewise-defined function $f(x)$ on its entire domain $[-1, 3]$, including its behavior at the transition point $x = 1$.
2. The exact point where the definite integral must be split, together with the justification.
3. The exact value of $\int_{-1}^{3} f(x)\,dx$ computed via the Fundamental Theorem of Calculus on each piece.
4. An independent geometric verification of the result using elementary area formulas.

---

## 3. Before Calculating: What Idea Do We Need?

- **Additivity of the definite integral:** For any integrable function $f$ on $[a, b]$ and any split point $c \in [a, b]$,

$$
\int_{a}^{b} f(x)\,dx = \int_{a}^{c} f(x)\,dx + \int_{c}^{b} f(x)\,dx.
$$

- **Why piecewise functions require splitting:** The Fundamental Theorem of Calculus applies directly to a single algebraic formula on each subinterval where that formula holds. Whenever the defining formula of $f(x)$ changes at a breakpoint $c$, we split the integral at $c$.
- **Behavior at a single endpoint does not affect an integral:** On $[-1, 1)$, the formula is $x + 1$. Changing or defining the value at the single endpoint $x = 1$ does not alter the definite integral of $x + 1$ over $[-1, 1]$, because a single vertical line segment has zero area. Here, in fact, the two pieces meet continuously at $(1, 2)$ since $\lim_{x \to 1^-} (x + 1) = 2 = f(1)$.
- **Geometric area check:** Whenever $f(x) \ge 0$ on $[a, b]$, the definite integral equals the exact geometric area under the graph, which here splits cleanly into a triangle and a square, or combines into a single trapezoid.

---

## 4. Step-by-Step Solution

### Step 1: Analyze and Sketch the Graph of $f(x)$

Examine each piece of the definition on $[-1, 3]$:

- **First piece, for $-1 \le x < 1$:** $f(x) = x + 1$, a straight line with slope $1$.
  - At $x = -1$: $f(-1) = -1 + 1 = 0$, giving the point $(-1, 0)$.
  - At $x = 0$: $f(0) = 1$, giving the point $(0, 1)$.
  - As $x \to 1^-$: $f(x) \to 1 + 1 = 2$, approaching the point $(1, 2)$.
- **Second piece, for $1 \le x \le 3$:** $f(x) = 2$, a horizontal line segment at height $y = 2$.
  - At $x = 1$: $f(1) = 2$, so the second piece connects seamlessly to the first piece at $(1, 2)$ with a sharp corner.
  - At $x = 3$: $f(3) = 2$, giving the point $(3, 2)$.

Notice also that $f(x) \ge 0$ across the entire interval $[-1, 3]$.

```text
      y
      ^
    2 +              *---------------* (3, 2)
      |            / |###############|
      |          /###|###############|
    1 +        *#####|###############|
      |      /#######|###############|
      |    /#########|###############|
   ---+---*----------+---------------+-----> x
     -1   0          1               3
      |<-- Triangle ->|<-- Square -->|
      |   base = 2    |   width = 2  |
      |  height = 2   |  height = 2  |
```

### Step 2: Decide Where to Split the Integral

The formula defining $f(x)$ changes at $x = 1$:

- On $[-1, 1)$, we have $f(x) = x + 1$.
- On $[1, 3]$, we have $f(x) = 2$.

Therefore, we split the integral at **$x = 1$** using additivity of the definite integral:

$$
\int_{-1}^{3} f(x)\,dx = \int_{-1}^{1} (x + 1)\,dx + \int_{1}^{3} 2\,dx.
$$

### Step 3: Compute Each Sub-Integral and Sum Them

**First sub-integral, on $[-1, 1]$:**

An antiderivative of $x + 1$ is $\frac{x^2}{2} + x$. Evaluating from $-1$ to $1$:

$$
\begin{aligned}
\int_{-1}^{1} (x + 1)\,dx &= \left[\frac{x^2}{2} + x\right]_{-1}^{1} \\
&= \left(\frac{1^2}{2} + 1\right) - \left(\frac{(-1)^2}{2} + (-1)\right) \\
&= \left(\frac{1}{2} + 1\right) - \left(\frac{1}{2} - 1\right) \\
&= \frac{3}{2} - \left(-\frac{1}{2}\right) = \frac{4}{2} = 2.
\end{aligned}
$$

**Second sub-integral, on $[1, 3]$:**

An antiderivative of $2$ is $2x$. Evaluating from $1$ to $3$:

$$
\int_{1}^{3} 2\,dx = \Big[2x\Big]_{1}^{3} = 2(3) - 2(1) = 6 - 2 = 4.
$$

**Total definite integral:**

$$
\int_{-1}^{3} f(x)\,dx = 2 + 4 = 6.
$$

### Step 4: Verify the Result Geometrically

Since $f(x) \ge 0$ everywhere on $[-1, 3]$, the definite integral must equal the geometric area enclosed between the graph and the $x$-axis.

**Method A — Triangle plus square:**

- On $[-1, 1]$, the region is a right triangle with vertices $(-1, 0)$, $(1, 0)$, and $(1, 2)$. Its base is $1 - (-1) = 2$ and its height is $2$:

$$
A_{\text{triangle}} = \frac{1}{2} \cdot 2 \cdot 2 = 2.
$$

- On $[1, 3]$, the region is a square with vertices $(1, 0)$, $(3, 0)$, $(3, 2)$, and $(1, 2)$. Its width is $3 - 1 = 2$ and its height is $2$:

$$
A_{\text{square}} = 2 \cdot 2 = 4.
$$

- Summing the two pieces:

$$
A_{\text{total}} = 2 + 4 = 6.
$$

**Method B — Single trapezoid:**

Looking at the entire shaded region from $x = -1$ to $x = 3$ as one right trapezoid:

- Bottom horizontal base along $y = 0$: length $3 - (-1) = 4$.
- Top horizontal base along $y = 2$: length $3 - 1 = 2$.
- Height between the parallel bases: $2$.

The trapezoid area formula gives

$$
A_{\text{trapezoid}} = \frac{4 + 2}{2} \cdot 2 = 6.
$$

Both geometric computations match the calculus result of $6$ exactly.

---

## 5. Final Answer & Conclusion

- Split point: **$x = 1$**, where the piecewise formula switches from $x + 1$ to $2$.
- Piece-by-piece integrals:

$$
\int_{-1}^{1} (x + 1)\,dx = 2, \qquad \int_{1}^{3} 2\,dx = 4.
$$

- Final value:

$$
\int_{-1}^{3} f(x)\,dx = 6.
$$

- **Geometric confirmation:** The area under the graph consists of a triangle of area $2$ plus a square of area $4$, or equivalently a trapezoid of bases $4$ and $2$ and height $2$, confirming the exact total area $6$.

---

## 6. Quick Verification

1. **Odd/even symmetry shortcut on $[-1, 1]$:** On the symmetric interval $[-1, 1]$, split $\int_{-1}^{1} (x + 1)\,dx$ into

$$
\int_{-1}^{1} x\,dx + \int_{-1}^{1} 1\,dx = 0 + 1 \cdot (1 - (-1)) = 2,
$$

because $x$ is odd on $[-1, 1]$. Adding $\int_{1}^{3} 2\,dx = 2 \cdot (3 - 1) = 4$ gives $2 + 4 = 6$.
2. **Bounding check on $[-1, 3]$:** Since $0 \le f(x) \le 2$ on $[-1, 3]$ and the interval width is $3 - (-1) = 4$, the integral must satisfy

$$
0 \cdot 4 < \int_{-1}^{3} f(x)\,dx < 2 \cdot 4 \implies 0 < \int_{-1}^{3} f(x)\,dx < 8.
$$

Indeed, $6$ sits right inside $(0, 8)$, and specifically equals the full $4 \times 2 = 8$ bounding rectangle minus the missing upper-left triangle of base $2$ and height $2$ whose area is $2$, giving $8 - 2 = 6$.

---

## 7. Common Mistakes to Avoid

- **Integrating only one formula across the whole interval $[-1, 3]$:** Using $x + 1$ on $[-1, 3]$ gives $8$, while using $2$ on $[-1, 3]$ gives $8$ — both wrong because each formula only governs part of $[-1, 3]$.
- **Sign error when evaluating at the lower limit $x = -1$:** Writing $\left(\frac{1}{2} + 1\right) - \left(\frac{1}{2} - 1\right) = \frac{3}{2} - \frac{1}{2} = 1$ by dropping the double negative $-\left(-\frac{1}{2}\right) = +\frac{1}{2}$.
- **Worrying unnecessarily about the strict inequality $-1 \le x < 1$:** Thinking you cannot write $\int_{-1}^{1} (x + 1)\,dx$ because $x = 1$ is excluded from the first branch. Changing a function at a single point never changes the value of a definite integral.
- **Misreading the width of $[-1, 1]$ as $1$ instead of $2$:** The distance from $-1$ to $1$ is $1 - (-1) = 2$, not $1$. Sketching the graph prevents this slip immediately.

---

## 8. How I Would Explain This in Class

> "Think of a piecewise function like a hike with two different trail sections: from mile $-1$ to mile $1$ you climb a steady ramp up to height $2$, and from mile $1$ to mile $3$ you walk along a flat plateau at height $2$. You cannot describe both sections with one formula, so you simply split your integral at mile $1$, right where the rule changes. And whenever a graph is built out of straight lines, always sketch it — seeing a triangle of area $2$ glued onto a square of area $4$ makes the answer $6$ unmistakable!"
