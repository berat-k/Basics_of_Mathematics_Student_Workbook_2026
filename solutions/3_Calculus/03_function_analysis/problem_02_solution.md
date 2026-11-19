# Problem 02: A Parabola from the Perspective of the Derivative

## 1. The Original Problem

For $f(x) = x^2 - 4x + 1$, find the minimum using the derivative. Compare the result with the vertex form and explain why both approaches lead to the same point.

---

## 2. What Are We Trying to Find?

1. The minimum point and minimum value of $f(x) = x^2 - 4x + 1$ using differentiation and monotonicity analysis.
2. The vertex form of $f(x)$ by completing the square, and the resulting minimum point and minimum value.
3. A direct comparison of the two results.
4. Both an algebraic and a geometric explanation of why the calculus method and the vertex-form method always produce the exact same point for a parabola.

---

## 3. Before Calculating: What Idea Do We Need?

- **Calculus approach:** For a differentiable function on $\mathbb{R}$, any local extremum occurs at a critical point where $f'(x) = 0$. If $f'(x) < 0$ to the left of $c$ and $f'(x) > 0$ to the right of $c$, then $f$ strictly decreases up to $c$ and strictly increases afterward, making $f(c)$ the unique global minimum on $\mathbb{R}$.
- **Algebraic approach via completing the square:** Writing a quadratic $f(x) = ax^2 + bx + c$ with $a > 0$ in vertex form $f(x) = a(x - p)^2 + q$ isolates the nonnegative term $a(x - p)^2 \ge 0$, which attains its smallest value $0$ uniquely when $x = p$.
- **Geometric meaning of the derivative:** The value $f'(x)$ is the slope of the tangent line to the parabola at $x$. At the lowest point of an upward-opening parabola, the tangent line must be horizontal, meaning its slope is $0$.

---

## 4. Step-by-Step Solution

### Step 1: Finding the Minimum Using the Derivative

The function $f(x) = x^2 - 4x + 1$ is a polynomial, so its domain is $\mathbb{R}$ and it is differentiable everywhere. Computing its first derivative gives

$$
f'(x) = 2x - 4 = 2(x - 2).
$$

Setting $f'(x) = 0$ locates the unique critical number:

$$
2(x - 2) = 0 \iff x = 2.
$$

Now we examine the sign of $f'(x)$ on the two intervals separated by $x = 2$:

- For $x \in (-\infty, 2)$, we have $x - 2 < 0$, so $f'(x) < 0$. Thus $f$ is strictly decreasing on $(-\infty, 2]$.
- For $x \in (2, \infty)$, we have $x - 2 > 0$, so $f'(x) > 0$. Thus $f$ is strictly increasing on $[2, \infty)$.

| Interval / Point | $(-\infty, 2)$ | $x = 2$ | $(2, \infty)$ |
| :--- | :---: | :---: | :---: |
| Sign of $f'(x)$ | $-$ | $0$ | $+$ |
| Behavior of $f(x)$ | Strictly decreasing | Global min: $-3$ | Strictly increasing |

Because $f$ decreases everywhere to the left of $x = 2$ and increases everywhere to the right of $x = 2$, it attains a **global minimum** at $x = 2$. The minimum value is

$$
f(2) = 2^2 - 4(2) + 1 = 4 - 8 + 1 = -3.
$$

Thus, the derivative method identifies the minimum point as $(2, -3)$ and the minimum value as $-3$.

### Step 2: Finding the Minimum Using the Vertex Form

To write $f(x) = x^2 - 4x + 1$ in vertex form $f(x) = a(x - p)^2 + q$, we complete the square by adding and subtracting $\left(\frac{-4}{2}\right)^2 = 4$:

$$
f(x) = x^2 - 4x + 4 - 4 + 1 = (x - 2)^2 - 3.
$$

Since the square of any real number is nonnegative,

$$
(x - 2)^2 \ge 0 \quad \text{for all } x \in \mathbb{R},
$$

with equality if and only if $x - 2 = 0$, that is, $x = 2$. Subtracting $3$ from both sides yields

$$
f(x) = (x - 2)^2 - 3 \ge -3 \quad \text{for all } x \in \mathbb{R},
$$

with $f(2) = -3$. Therefore, the vertex form immediately shows that the parabola opens upward with vertex and global minimum at $(2, -3)$.

### Step 3: Comparison of the Two Results

Both methods produce the exact same location $x = 2$, the exact same minimum value $y = -3$, and the exact same point $(2, -3)$ on the graph.

### Step 4: Why Both Approaches Lead to the Same Point

There are two complementary ways to see why this agreement is guaranteed for every upward-opening parabola $f(x) = ax^2 + bx + c$ with $a > 0$:

1. **Algebraic connection:** Rewrite any quadratic in vertex form as

$$
f(x) = a(x - p)^2 + q.
$$

Differentiating this form directly gives

$$
f'(x) = 2a(x - p).
$$

Because $a \ne 0$, the equation $f'(x) = 0$ is literally equivalent to $x - p = 0$, or $x = p$. Equivalently, differentiating the standard form $f(x) = ax^2 + bx + c$ gives

$$
f'(x) = 2ax + b = 0 \iff x = -\frac{b}{2a},
$$

which is the familiar algebraic formula for the $x$-coordinate of the vertex. In this problem, $-\frac{-4}{2 \cdot 1} = 2$.

2. **Geometric connection:** The vertex $(p, q)$ of an upward-opening parabola is the unique turning point where the graph changes from descending to ascending. Geometrically, the tangent line at this lowest point must be horizontal, which means its slope is $0$, so $f'(p) = 0$. Meanwhile, the vertex form $f(x) = (x - 2)^2 - 3$ expresses the vertical distance of every point on the parabola above that horizontal tangent line $y = -3$: the quantity $(x - 2)^2$ is strictly positive everywhere except at the point of tangency $x = 2$. Both tools are therefore detecting the same geometric feature from different angles: the vertex form measures height above the lowest level, while the derivative measures where the slope levels off to zero.

---

## 5. Final Answer & Conclusion

- **Derivative method:** $f'(x) = 2x - 4 = 0$ at $x = 2$, with $f'(x) < 0$ for $x < 2$ and $f'(x) > 0$ for $x > 2$. The global minimum is $f(2) = -3$, attained at $(2, -3)$.
- **Vertex form method:** $f(x) = (x - 2)^2 - 3 \ge -3$, giving the exact same vertex and global minimum at $(2, -3)$.
- **Why they match:** Differentiating the vertex form $a(x - p)^2 + q$ gives $2a(x - p)$, whose unique root is $x = p$. Geometrically, both methods identify the unique point on the parabola where the graph turns from falling to rising and where the tangent line is horizontal.

---

## 6. Quick Verification

1. **Second Derivative Test:** $f''(x) = 2 > 0$ for every $x \in \mathbb{R}$, confirming that the graph is strictly convex everywhere and that the critical point $x = 2$ is indeed a minimum.
2. **Symmetry check around $x = 2$:** Testing symmetric points $x = 1$ and $x = 3$ gives

$$
f(1) = 1 - 4 + 1 = -2, \qquad f(3) = 9 - 12 + 1 = -2,
$$

and testing $x = 0$ and $x = 4$ gives $f(0) = 1 = f(4)$. Both pairs lie strictly above $f(2) = -3$ and confirm the axis of symmetry $x = 2$.

---

## 7. Common Mistakes to Avoid

- **Stopping after solving $f'(x) = 0$:** Finding $x = 2$ only identifies a critical point; you must check the sign change of $f'(x)$ or compute $f''(2) > 0$ to prove it is a minimum rather than a maximum or a saddle point.
- **Sign error when reading the vertex from $(x - 2)^2 - 3$:** Students sometimes misread the vertex as $(-2, -3)$. The expression $(x - 2)^2$ vanishes at $x = +2$, not $x = -2$.
- **Forgetting to subtract the added square when completing the square:** Writing $x^2 - 4x + 1 = (x - 2)^2 + 1$ adds $4$ without compensating for it, which shifts the minimum up by $4$ units.
- **Concluding only a local minimum without justifying globality:** Because $f$ decreases on all of $(-\infty, 2]$ and increases on all of $[2, \infty)$, the minimum at $x = 2$ is global, not merely local.

---

## 8. How I Would Explain This in Class

> "Before calculus, completing the square was our special trick for finding the bottom of a parabola. Calculus does not replace that trick—it explains what is happening geometrically and generalizes it to curves that have no vertex form. When you write $f(x) = (x - 2)^2 - 3$, you are seeing that the parabola sits on top of the flat floor $y = -3$ and touches it only at $x = 2$. When you set $f'(x) = 0$, you are asking where the curve becomes momentarily flat so it can rest on that floor. Same point, two languages!"
