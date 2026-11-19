# Problem 06: Product Rule and Trigonometry

## 1. The Original Problem

For

$$
f(x)=x\sin x+\cos x
$$

compute the derivative and simplify the result. Then compute $f'(0)$ and interpret the direction of the tangent line at that point.

---

## 2. What Are We Trying to Find?

1. The derivative $f'(x)$ of $f(x) = x\sin x + \cos x$, applying the sum rule, product rule, and trigonometric differentiation rules.
2. The simplified form of $f'(x)$ after canceling like terms.
3. The exact value $f'(0)$.
4. A clear geometric interpretation of the direction of the tangent line to the graph of $f$ at $x = 0$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Sum rule:** Differentiate $x\sin x$ and $\cos x$ separately, then add the results.
- **Product rule for $x\sin x$:** Because $x$ and $\sin x$ are both non-constant functions of $x$, we must apply

$$
(u \cdot v)' = u'v + uv'.
$$

- **Basic trigonometric derivatives in radians:**

$$
\frac{d}{dx}(\sin x) = \cos x, \qquad \frac{d}{dx}(\cos x) = -\sin x.
$$

- **Geometric meaning of zero derivative:** When $f'(a) = 0$, the slope of the tangent line at $(a, f(a))$ is $0$, meaning the tangent line is **horizontal**, parallel to the $x$-axis.

---

## 4. Step-by-Step Solution

### Step 1: Differentiate Each Term

Break $f(x) = x\sin x + \cos x$ into two pieces:

1. **First term, $x\sin x$:** Apply the product rule with $u(x) = x$ and $v(x) = \sin x$, so $u'(x) = 1$ and $v'(x) = \cos x$:

$$
\frac{d}{dx}(x\sin x) = (1)\sin x + x\cos x = \sin x + x\cos x.
$$

2. **Second term, $\cos x$:**

$$
\frac{d}{dx}(\cos x) = -\sin x.
$$

### Step 2: Combine and Simplify

Add the derivatives of both terms:

$$
f'(x) = (\sin x + x\cos x) + (-\sin x) = \sin x + x\cos x - \sin x.
$$

The $+\sin x$ and $-\sin x$ cancel completely, leaving a remarkably clean derivative:

$$
f'(x) = x\cos x.
$$

### Step 3: Compute $f'(0)$

Substitute $x = 0$ into $f'(x) = x\cos x$:

$$
f'(0) = 0 \cdot \cos(0) = 0 \cdot 1 = 0.
$$

Let us also find the point on the graph at $x = 0$:

$$
f(0) = 0 \cdot \sin(0) + \cos(0) = 0 + 1 = 1.
$$

So the point of tangency is $(0, 1)$.

### Step 4: Interpret the Direction of the Tangent Line at $x = 0$

Because $f'(0) = 0$, the tangent line to the curve $y = x\sin x + \cos x$ at the point $(0, 1)$ has **slope $0$**.

- **Direction:** The tangent line is **horizontal** — completely flat and parallel to the $x$-axis, neither rising nor falling at $x = 0$.
- **Equation of the tangent line:** Passing through $(0, 1)$ with slope $0$, its equation is simply $y = 1$.
- **Local shape around $x = 0$:** For small $x$ near $0$, $\cos x > 0$. Therefore:
  - For small $x < 0$, $f'(x) = x\cos x < 0$, so $f$ is decreasing as $x$ approaches $0$ from the left.
  - For small $x > 0$, $f'(x) = x\cos x > 0$, so $f$ is increasing as $x$ moves right from $0$.

  Hence the graph levels off at $(0, 1)$ at a **local minimum**, touching the horizontal tangent line $y = 1$ from above.

---

## 5. Final Answer & Conclusion

- **Simplified derivative:**

$$
f'(x) = x\cos x.
$$

- **Value at $x = 0$:** $f'(0) = 0$.
- **Direction of the tangent line:** At the point $(0, 1)$, the tangent line has slope $0$, so it is **horizontal**, parallel to the $x$-axis, with equation $y = 1$.

---

## 6. Quick Verification

1. **Symmetry check for $f'(0) = 0$:** Check whether $f$ is an even function:

$$
f(-x) = (-x)\sin(-x) + \cos(-x) = (-x)(-\sin x) + \cos x = x\sin x + \cos x = f(x).
$$

   Since $f$ is even and differentiable at $x = 0$, its graph is mirror-symmetric across the $y$-axis. A smooth curve that is symmetric across $x = 0$ **must** have a horizontal tangent at $x = 0$, confirming $f'(0) = 0$! Likewise, the derivative of an even function must be an odd function, and indeed $f'(-x) = (-x)\cos(-x) = -x\cos x = -f'(x)$.

2. **Numerical difference-quotient checks at $x = 0$ and $x = 1$:**
   - At $x = 0$ with $h = 0.001$: $f(0) = 1$ and $f(0.001) = 0.001\sin(0.001) + \cos(0.001) \approx 1.0000005$, so

$$
\frac{f(0.001) - f(0)}{0.001} \approx 0.000500 \approx 0 = f'(0).
$$

   - At $x = 1$ with $h = 0.001$: exact value $f'(1) = 1 \cdot \cos(1) \approx 0.540302$. Meanwhile $f(1) \approx 1.381773$ and $f(1.001) \approx 1.382313$, giving

$$
\frac{f(1.001) - f(1)}{0.001} \approx 0.540151 \approx 0.540302.
$$

---

## 7. Common Mistakes to Avoid

- **Forgetting the minus sign in $\frac{d}{dx}(\cos x) = -\sin x$:** Writing $+\sin x$ instead of $-\sin x$ turns the cancellation into $2\sin x + x\cos x$, missing the simplification completely.
- **Not using the product rule on $x\sin x$:** Differentiating each factor separately to get $1 \cdot \cos x = \cos x$ drops the $\sin x$ term and produces $\cos x - \sin x$, which falsely gives $f'(0) = 1$.
- **Confusing "zero slope" with "no tangent line":** Having $f'(0) = 0$ does **not** mean the tangent line fails to exist; it means the tangent line exists and is perfectly horizontal.
- **Evaluating $\cos(0)$ as $0$:** Remember that $\sin(0) = 0$ while $\cos(0) = 1$. Here $f'(0) = 0$ happens because of the leading factor $x = 0$, not because of $\cos(0)$.

---

## 8. How I Would Explain This in Class

> "This problem is a miniature magic trick built from two basic rules. When you apply the product rule to $x\sin x$, out pops $\sin x + x\cos x$. That extra $+\sin x$ looks messy for a split second — until the derivative of $+\cos x$ arrives as $-\sin x$ and wipes it clean off the board, leaving just $x\cos x$! At $x = 0$, the derivative equals $0$, which geometrically means that if you ski along the curve $y = x\sin x + \cos x$, your skis are completely flat and level at the exact moment you cross the $y$-axis at height $1$."
