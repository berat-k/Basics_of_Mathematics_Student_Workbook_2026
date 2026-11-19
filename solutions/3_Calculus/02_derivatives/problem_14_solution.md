# Problem 14: Continuity and Differentiability of a Piecewise Function

## 1. The Original Problem

Investigate the behavior at $x = 0$ of

$$
f(x) = \begin{cases}
x^2, & x \ge 0, \\
ax, & x < 0.
\end{cases}
$$

For which values of $a$ is the function continuous? For which values do the one-sided derivatives exist and agree? For which value of $a$ is the function differentiable? Explain why continuity alone is not sufficient.

---

## 2. What Are We Trying to Find?

1. All real values of the parameter $a$ for which $f$ is continuous at $x = 0$, and hence on all of $\mathbb{R}$.
2. All values of $a$ for which the left-hand and right-hand derivatives at $x = 0$ exist, and all values of $a$ for which those two one-sided derivatives agree.
3. The exact value of $a$ for which $f$ is differentiable at $x = 0$, together with the resulting value $f'(0)$.
4. A clear geometric and analytic explanation of why continuity at $x = 0$ does not automatically guarantee differentiability at $x = 0$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Definition of continuity at $x = 0$:** A function $f$ is continuous at $x = 0$ if and only if $f(0)$ is defined, both one-sided limits exist and are equal, and their common value equals $f(0)$:

$$
\lim_{x \to 0^-} f(x) = \lim_{x \to 0^+} f(x) = f(0).
$$

- **Definition of one-sided derivatives at $x = 0$:** For a piecewise function whose formula changes at $x = 0$, we must compute the one-sided derivatives directly from the difference quotient:

$$
f'_{-}(0) = \lim_{h \to 0^-} \frac{f(0 + h) - f(0)}{h}, \qquad f'_{+}(0) = \lim_{h \to 0^+} \frac{f(0 + h) - f(0)}{h}.
$$

- **Existence of the two-sided derivative:** The derivative $f'(0) = \lim_{h \to 0} \frac{f(h) - f(0)}{h}$ exists if and only if both one-sided derivatives exist as finite numbers and are equal:

$$
f'_{-}(0) = f'_{+}(0).
$$

- **Differentiability vs. continuity:** Differentiability implies continuity, because if the difference quotient has a finite limit then $f(h) - f(0) \to 0$. However, the converse is false: a continuous curve can still have a sharp corner where the incoming and outgoing slopes disagree.

---

## 4. Step-by-Step Solution

### Step 1: Investigate Continuity at $x = 0$

Check the three quantities required by the definition of continuity at $x = 0$:

1. **Function value at $x = 0$:** Since $0 \ge 0$, we use the top branch $x^2$:

$$
f(0) = 0^2 = 0.
$$

2. **Right-hand limit as $x \to 0^+$:** For $x > 0$, we have $f(x) = x^2$, so

$$
\lim_{x \to 0^+} f(x) = \lim_{x \to 0^+} x^2 = 0.
$$

3. **Left-hand limit as $x \to 0^-$:** For $x < 0$, we have $f(x) = ax$, so

$$
\lim_{x \to 0^-} f(x) = \lim_{x \to 0^-} (ax) = a \cdot 0 = 0.
$$

Comparing all three values:

$$
\lim_{x \to 0^-} f(x) = 0 = \lim_{x \to 0^+} f(x) = f(0)
$$

holds regardless of the value of $a$. Moreover, on $(-\infty, 0)$ the function is linear and on $(0, \infty)$ it is quadratic, so it is automatically continuous at every $x \ne 0$.

**Conclusion on continuity:** The function $f$ is continuous at $x = 0$, and on all of $\mathbb{R}$, for **every real number $a \in \mathbb{R}$**.

### Step 2: Compute the One-Sided Derivatives at $x = 0$

Use the limit definition of the one-sided derivatives at $x = 0$, recalling that $f(0) = 0$.

**Right-hand derivative:** When $h > 0$, we have $0 + h = h > 0$, so $f(h) = h^2$. Therefore:

$$
f'_{+}(0) = \lim_{h \to 0^+} \frac{f(h) - f(0)}{h} = \lim_{h \to 0^+} \frac{h^2 - 0}{h} = \lim_{h \to 0^+} h = 0.
$$

**Left-hand derivative:** When $h < 0$, we have $0 + h = h < 0$, so $f(h) = ah$. Therefore:

$$
f'_{-}(0) = \lim_{h \to 0^-} \frac{f(h) - f(0)}{h} = \lim_{h \to 0^-} \frac{ah - 0}{h} = \lim_{h \to 0^-} a = a.
$$

Now answer both parts of the question about one-sided derivatives:
- **Existence of one-sided derivatives:** Both $f'_{-}(0) = a \text{ and } f'_{+}(0) = 0$ are finite real numbers for **every $a \in \mathbb{R}$**, so both one-sided derivatives exist for all $a \in \mathbb{R}$.
- **Agreement of one-sided derivatives:** The two one-sided derivatives agree if and only if

$$
f'_{-}(0) = f'_{+}(0) \iff a = 0.
$$

### Step 3: Determine Differentiability at $x = 0$

The two-sided derivative

$$
f'(0) = \lim_{h \to 0} \frac{f(h) - f(0)}{h}
$$

exists if and only if the left-hand and right-hand limits of the difference quotient exist and are equal. By Step 2, this occurs **if and only if $a = 0$**.

When $a = 0$, the piecewise function becomes

$$
f(x) = \begin{cases}
x^2, & x \ge 0, \\
0, & x < 0,
\end{cases}
$$

and its derivative at $x = 0$ exists and equals $f'(0) = 0$.

We summarize the behavior at $x = 0$ across all values of $a$:

| Parameter $a$ | Continuous at $x = 0$? | Left-hand derivative | Right-hand derivative | Differentiable at $x = 0$? | Geometry at $(0, 0)$ |
| :--- | :---: | :---: | :---: | :---: | :--- |
| $a \ne 0$ | Yes | $a$ | $0$ | No | Sharp corner where line of slope $a$ meets flat parabola |
| $a = 0$ | Yes | $0$ | $0$ | Yes, $f'(0) = 0$ | Smooth horizontal join with unique tangent line $y = 0$ |

### Step 4: Explain Why Continuity Alone Is Not Sufficient

This example illustrates sharply why continuity is *necessary* for differentiability, yet far from *sufficient*:

1. **Geometric reason — meeting smoothly vs. meeting at a corner:** Continuity at $x = 0$ only demands that the left and right branches *connect* at the point $(0, 0)$ without a break or jump. Since both $ax$ and $x^2$ equal $0$ at $x = 0$, the two branches always connect for every $a \in \mathbb{R}$. Differentiability demands something much stricter: the two branches must arrive at $(0, 0)$ with the *same direction*, so that zooming in on $(0, 0)$ makes the graph look like a single straight line. When $a \ne 0$, the left branch enters with slope $a \ne 0$ while the right branch leaves with slope $0$, forming a sharp corner that never flattens into a single line no matter how closely we zoom in.
2. **Analytic reason — values vs. rates of change:** Continuity only requires $f(h) - f(0) \to 0$ as $h \to 0$. Differentiability requires the *rate* $\frac{f(h) - f(0)}{h}$ to settle to a single limit from both sides. Here the difference quotient is

$$
\frac{f(h) - f(0)}{h} = \begin{cases}
h, & h > 0, \\
a, & h < 0,
\end{cases}
$$

which approaches $a$ from the left and $0$ from the right. Unless $a = 0$, the difference quotient itself has a jump discontinuity at $h = 0$, so the two-sided limit fails to exist.

Compare the shapes at the origin for $a = 1$ (continuous but not differentiable) and $a = 0$ (continuous and differentiable):

```text
    a = 1 (corner at origin)                 a = 0 (smooth join at origin)
           y                                        y
           ^       /  y = x^2                       ^       /  y = x^2
           |      /                                 |      /
           |    _/                                  |    _/
    -------+---*--------+--> x       y = 0  ========*---+--------+--> x
          /    0                                    0
         /  y = x  (slope 1 vs slope 0)         (slope 0 meets slope 0)
```

---

## 5. Final Answer & Conclusion

- **Continuous at $x = 0$:** For **all $a \in \mathbb{R}$**.
- **Both one-sided derivatives exist at $x = 0$:** For **all $a \in \mathbb{R}$**, with left-hand derivative $a$ and right-hand derivative $0$.
- **One-sided derivatives agree at $x = 0$:** Only for **$a = 0$**.
- **Differentiable at $x = 0$:** Only for **$a = 0$**, with $f'(0) = 0$.
- **Why continuity is not sufficient:** Continuity ensures only that the graph has no break at $(0, 0)$, whereas differentiability requires the slopes from both sides to match so that there is no corner and a single tangent line exists.

---

## 6. Quick Verification

1. **Concrete numerical test for $a = 2$ (non-differentiable case):** Check the difference quotient $\frac{f(h) - f(0)}{h}$ for small $h$ on both sides of $0$:
  - For $h = 0.001$: $\frac{(0.001)^2 - 0}{0.001} = 0.001 \to 0$.
  - For $h = -0.001$: $\frac{2(-0.001) - 0}{-0.001} = 2 \to 2$.

Meanwhile, $f(0.001) = 10^{-6}$ and $f(-0.001) = -0.002$ are both close to $f(0) = 0$. Thus $f$ is continuous at $0$, yet the secant slopes from the left stay locked at $2$ while the secant slopes from the right shrink to $0$, proving non-differentiability.

2. **Concrete numerical test for $a = 0$ (differentiable case):** Check the difference quotient $\frac{f(h) - f(0)}{h}$ on both sides of $0$:
  - For $h = 0.001$: $\frac{(0.001)^2 - 0}{0.001} = 0.001 \to 0$.
  - For $h = -0.001$: $\frac{0 - 0}{-0.001} = 0 \to 0$.

Now both sides approach the same limit $0$, confirming $f'(0) = 0$.

3. **Check using the derivative away from $0$:** For $x > 0$, $f'(x) = 2x \to 0$ as $x \to 0^+$. For $x < 0$, $f'(x) = a \to a$ as $x \to 0^-$. For the derivative function $f'(x)$ to match across $x = 0$, we must have $a = 0$, matching our limit-definition result.

---

## 7. Common Mistakes to Avoid

- **Assuming continuity implies differentiability:** A student might verify $\lim_{x \to 0^-} f(x) = \lim_{x \to 0^+} f(x) = f(0)$ for all $a$ and mistakenly conclude $f$ is differentiable for all $a$. Continuity only eliminates jumps and holes; it does not eliminate corners.
- **Forgetting to check continuity before differentiating branches:** Even though this problem happens to be continuous for every $a$, in general piecewise problems, matching the branch derivatives alone is *not* enough—two branches can have the same slope while jumping vertically! Always verify continuity first, then check the one-sided derivatives from the definition.
- **Computing one-sided derivatives by blindly plugging $x = 0$ into $f'(x) = 2x$ and $f'(x) = a$ without justification:** While the branch derivatives here happen to give the right limits $0$ and $a$, the *definition* of one-sided derivatives uses the difference quotient $\frac{f(h) - f(0)}{h}$, which works reliably even for functions whose derivative oscillates or is discontinuous.
- **Confusing "the one-sided derivatives exist" with "the one-sided derivatives agree":** For $a = 5$, both one-sided derivatives *exist*, since one equals $5$ and the other equals $0$, yet they do not *agree*, so the two-sided derivative $f'(0)$ does not exist.

---

## 8. How I Would Explain This in Class

> "Picture laying down two pieces of train track that meet at the origin: to the right of zero you have the curved parabola $y = x^2$, which leaves the origin heading dead flat with slope $0$; to the left of zero you have a straight ramp $y = ax$ with slope $a$. No matter what slope $a$ you pick, both pieces hit the origin $(0, 0)$—so the tracks are always connected, meaning the function is continuous for every $a$. Now ask: can a train ride smoothly across the origin without a violent jolt? Only if the incoming ramp matches the outgoing flat track, which forces $a = 0$. Connected tracks give you continuity; smoothly aligned tracks with matching slopes give you differentiability."
