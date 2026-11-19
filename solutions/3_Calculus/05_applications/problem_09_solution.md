# Problem 09: Minimizing the Material Used for a Can

## 1. The Original Problem

A closed cylinder has fixed volume $V$.

1. Write the volume constraint.
2. Eliminate one of the variables.
3. Express the surface area as a function of the radius $r$.
4. Find the relation between the height $h$ and the radius $r$ for which the material usage is minimal.

Interpret the obtained relation geometrically.

---

## 2. What Are We Trying to Find?

1. **Volume constraint:** Formulate the algebraic equation linking the fixed volume $V$ to the cylinder's base radius $r$ and height $h$.
2. **Variable elimination:** Solve the constraint for $h$ in terms of $r$ and $V$.
3. **Single-variable objective function:** Express the total surface area $S$ of the closed cylinder solely as a function $S(r)$, together with its physically meaningful domain.
4. **Optimal relation and verification:** Use differential calculus to minimize $S(r)$, justify that the critical point gives a global minimum, and determine the exact ratio between $h$ and $r$.
5. **Geometric interpretation:** Explain what the optimal relation between $h$ and $r$ means visually for the shape of the can.

---

## 3. Before Calculating: What Idea Do We Need?

- **Geometry of a closed right circular cylinder:** Let $r > 0$ be the radius of the circular base and $h > 0$ be the height of the cylinder. Its volume is $V = \pi r^2 h$. Because the can is *closed*, it consists of two circular ends, each of area $\pi r^2$, plus a curved lateral wall that unrolls into a rectangle of width $2\pi r$ and height $h$. Thus the total surface area is $S = 2\pi r^2 + 2\pi r h$.
- **Constrained optimization by substitution:** Surface area initially depends on two variables, $r$ and $h$, subject to the fixed-volume constraint $V = \pi r^2 h$. Solving the constraint for $h$ reduces $S$ to a function of a single variable $r$ on the open domain $(0, \infty)$.
- **First- and second-derivative tests for a global minimum:** At an interior minimum on $(0, \infty)$, we must have $S'(r) = 0$. If $S''(r) > 0$ everywhere on $(0, \infty)$, then $S$ is strictly convex, so any critical point is guaranteed to be the **unique global minimum**.
- **Boundary behavior intuition:** Making $r$ extremely tiny forces $h$ to be enormous, while making $r$ huge makes the two circular lids huge; in both extremes $S(r) \to \infty$, so a balanced intermediate radius must minimize material usage.

---

## 4. Step-by-Step Solution

### Step 1: Write the Volume Constraint

Let $r > 0$ be the radius of the circular base and $h > 0$ be the height of the cylinder, with fixed volume $V > 0$. The volume of a right circular cylinder is the base area multiplied by the height:

$$
V = \pi r^2 h.
$$

### Step 2: Eliminate One Variable

Since $r > 0$, we can divide both sides of the volume constraint by $\pi r^2$ to express the height $h$ in terms of $r$:

$$
h = \frac{V}{\pi r^2}.
$$

Notice that for every positive radius $r \in (0, \infty)$, this formula produces a unique positive height $h > 0$.

### Step 3: Express the Surface Area as a Function of $r$

A closed cylinder has a bottom disk of area $\pi r^2$, a top disk of area $\pi r^2$, and a lateral surface of area $2\pi r h$. Hence the total surface area is

$$
S = 2\pi r^2 + 2\pi r h.
$$

Substituting $h = \frac{V}{\pi r^2}$ eliminates $h$ and yields the single-variable objective function:

$$
S(r) = 2\pi r^2 + 2\pi r \left(\frac{V}{\pi r^2}\right) = 2\pi r^2 + \frac{2V}{r}, \qquad r \in (0, \infty).
$$

The domain is $r \in (0, \infty)$ because both $r$ and $h = \frac{V}{\pi r^2}$ must be strictly positive. Notice that at both ends of the domain the surface area blows up:

$$
\lim_{r \to 0^+} S(r) = \infty, \qquad \lim_{r \to \infty} S(r) = \infty.
$$

### Step 4: Differentiate and Find the Critical Point

Rewrite $S(r) = 2\pi r^2 + 2V r^{-1}$ and differentiate with respect to $r$, treating $V$ as a positive constant:

$$
S'(r) = 4\pi r - 2V r^{-2} = 4\pi r - \frac{2V}{r^2}.
$$

To find the critical points on $(0, \infty)$, set $S'(r) = 0$:

$$
4\pi r - \frac{2V}{r^2} = 0 \implies 4\pi r = \frac{2V}{r^2} \implies 4\pi r^3 = 2V \implies r^3 = \frac{V}{2\pi}.
$$

Taking the real cube root gives the unique critical radius:

$$
r^* = \left(\frac{V}{2\pi}\right)^{1/3}.
$$

### Step 5: Verify That $r^*$ Gives the Global Minimum

Compute the second derivative of $S(r)$:

$$
S''(r) = 4\pi + 4V r^{-3} = 4\pi + \frac{4V}{r^3}.
$$

Since $V > 0$ and $r > 0$, every term is strictly positive, so $S''(r) > 0$ for **all** $r \in (0, \infty)$. In particular, at the critical point where $V = 2\pi (r^*)^3$, we have

$$
S''(r^*) = 4\pi + \frac{4 \cdot 2\pi (r^*)^3}{(r^*)^3} = 12\pi > 0.
$$

We can also inspect the sign of $S'(r) = \frac{4\pi r^3 - 2V}{r^2}$:

| Interval | Sign of $S'(r)$ | Behavior of $S(r)$ |
| :--- | :---: | :--- |
| $0 < r < r^*$ | $-$ | Strictly decreasing |
| $r = r^*$ | $0$ | Unique global minimum |
| $r > r^*$ | $+$ | Strictly increasing |

Because $S(r)$ is strictly decreasing on $(0, r^*)$ and strictly increasing on $(r^*, \infty)$ and strictly convex on $(0, \infty)$, the radius $r^*$ indeed achieves the **unique global minimum** surface area.

### Step 6: Find the Relation Between $h$ and $r$ and Interpret It Geometrically

At the optimal radius $r^*$, we have $2V = 4\pi (r^*)^3$, so $V = 2\pi (r^*)^3$. Substituting this into the formula for the optimal height $h^*$ gives

$$
h^* = \frac{V}{\pi (r^*)^2} = \frac{2\pi (r^*)^3}{\pi (r^*)^2} = 2r^*.
$$

Equivalently, substituting the volume constraint $V = \pi (r^*)^2 h^*$ directly into $4\pi (r^*)^3 = 2V$ immediately yields

$$
4\pi (r^*)^3 = 2\pi (r^*)^2 h^* \implies h^* = 2r^*.
$$

**Geometric interpretation:** Since the diameter of the circular base is $d = 2r$, the optimality condition $h = 2r$ says that **the height of the can must equal its diameter**, i.e., $h = d$. If you view the optimal can from the side, or slice it vertically through its central axis, its silhouette is a **square** of side length $d = 2r$.

```text
          d = 2r
     +--------------+
     |              |
     |   Optimal    |  h = 2r = d
     |     Can      |
     |  (square     |
     |  side view)  |
     +--------------+
```

Furthermore, at the optimum $h = 2r$, the two circular lids have combined area $2\pi r^2$, while the lateral wall has area $2\pi r (2r) = 4\pi r^2$. Thus the lateral wall uses exactly twice as much material as the top and bottom lids combined, meaning one-third of the total material goes into the two ends and two-thirds goes into the curved side.

---

## 5. Final Answer & Conclusion

1. **Volume constraint:** $V = \pi r^2 h$.
2. **Eliminated variable:** $h = \frac{V}{\pi r^2}$ for $r > 0$.
3. **Surface area function:** $S(r) = 2\pi r^2 + \frac{2V}{r}$ on the domain $(0, \infty)$.
4. **Optimal relation:** Material usage is minimized when $r^* = \left(\frac{V}{2\pi}\right)^{1/3}$ and $h = 2r$.
5. **Geometric interpretation:** The optimal closed cylindrical can has its height equal to its base diameter, giving a **square** vertical cross-section.

---

## 6. Quick Verification

**Check 1 — Independent proof via the AM-GM inequality:** For any $r > 0$, split the second term of $S(r)$ into two equal parts and apply the Arithmetic Mean-Geometric Mean inequality to three positive numbers:

$$
S(r) = 2\pi r^2 + \frac{V}{r} + \frac{V}{r} \ge 3\left(2\pi r^2 \cdot \frac{V}{r} \cdot \frac{V}{r}\right)^{1/3} = 3\left(2\pi V^2\right)^{1/3}.
$$

Equality holds if and only if all three summands are equal, which means

$$
2\pi r^2 = \frac{V}{r} \iff V = 2\pi r^3 \iff \pi r^2 h = 2\pi r^3 \iff h = 2r.
$$

This confirms both the optimal proportion $h = 2r$ and the global nature of the minimum without using calculus at all.

**Check 2 — Numerical test for a $1\text{ L}$ can with $V = 1000\text{ cm}^3$:** Here $r^* = \left(\frac{1000}{2\pi}\right)^{1/3} \approx 5.4193\text{ cm}$ and $h^* = 2r^* \approx 10.8385\text{ cm}$. Comparing nearby radii shows that $S(r)$ is strictly larger on both sides of $r^*$:

| Radius $r$ in cm | Height $h = \frac{1000}{\pi r^2}$ in cm | Ratio $h/r$ | Surface Area $S(r)$ in $\text{cm}^2$ |
| :---: | :---: | :---: | :---: |
| $4.0000$ | $19.8944$ | $4.9736$ | $600.5310$ |
| $5.0000$ | $12.7324$ | $2.5465$ | $557.0796$ |
| **$5.4193$** | **$10.8385$** | **$2.0000$** | **$553.5810$** |
| $6.0000$ | $8.8419$ | $1.4737$ | $559.5280$ |
| $7.0000$ | $6.4961$ | $0.9280$ | $593.5904$ |

The AM-GM lower bound is $3\left(2\pi \cdot 1000^2\right)^{1/3} \approx 553.5810\text{ cm}^2$, matching $S(r^*)$ to all four decimal places.

---

## 7. Common Mistakes to Avoid

- **Using the open-top surface area formula $\pi r^2 + 2\pi r h$:** The problem specifies a *closed* cylinder, which has both a bottom and a top lid, giving $2\pi r^2 + 2\pi r h$. An open-top can has a different optimum, namely $h = r$.
- **Treating $V$ as a variable when differentiating:** Because the volume is *fixed*, $V$ is a constant with respect to $r$, so $\frac{d}{dr}\left(\frac{2V}{r}\right) = -\frac{2V}{r^2}$ with no $V'$ term.
- **Forgetting to verify that the critical point is a minimum:** Solving $S'(r) = 0$ only identifies a stationary point. Checking $S''(r) > 0$ on $(0, \infty)$, or checking the sign change of $S'(r)$ from negative to positive, is essential to prove that it is the global minimum.
- **Confusing radius with diameter in the geometric interpretation:** The equation $h = 2r$ does *not* mean height equals radius; it means height equals *diameter*, because $d = 2r$.

---

## 8. How I Would Explain This in Class

> "If you try to build a 1-liter can that is super tall and skinny like a drinking straw, you waste a ton of metal on the long curved wall. If you flatten it into a wide tuna-can pancake, you waste a ton of metal on two giant circular lids. Calculus finds the exact sweet spot where the two competing costs balance out: the height equals the diameter, so the can looks like a perfect square when viewed from the side. Real soda cans are slightly taller and narrower than $h = 2r$ only because aluminum lids have to be thicker than the side walls and people need to grip them comfortably—when all surfaces cost the same per square centimeter, the square-profile can always wins."
