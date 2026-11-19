# Problem 15: Comparing Directions Using the Cosine of the Angle

## 1. The Original Problem

Given

$$
a = (1, 2, 1), \qquad b = (2, 4, 2), \qquad c = (2, 0, 3).
$$

For each pair, compute

$$
\frac{u \cdot v}{\|u\| \|v\|}.
$$

Order the pairs by increasing angle between the vectors. Explain why for $a$ and $b$ the value is $1$ even though the vectors have different lengths.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the Euclidean norms $\|a\|$, $\|b\|$, and $\|c\|$.
2. Compute the cosine of the angle $\cos \theta = \frac{u \cdot v}{\|u\| \|v\|}$ for all three unordered pairs: $(a, b)$, $(a, c)$, and $(b, c)$.
3. Determine the enclosed angle $\theta$ (in degrees and radians) for each pair.
4. Order the three pairs in ascending order of their enclosed angles (from smallest angle to largest angle).
5. Explain why the pair $(a, b)$ yields $\cos \theta = 1$ despite the fact that vector $b$ is twice as long as vector $a$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Direction Cosine Formula:**
  For any two non-zero vectors $u$ and $v$, the cosine of the enclosed angle $\theta \in [0, \pi]$ is:

$$
\cos \theta = \frac{u \cdot v}{\|u\| \|v\|}
$$

- **Monotonicity of the Cosine Function:**
  On the interval $\theta \in [0, \pi]$:
  - The cosine function is strictly **decreasing**.
  - A **larger** cosine value corresponds to a **smaller** enclosed angle:

$$
\cos \theta_1 > \cos \theta_2 \iff \theta_1 < \theta_2
$$

  - The maximum possible cosine value is $\cos \theta = 1$, corresponding to $\theta = 0^\circ$ (collinear vectors with the same orientation).
- **Scale Invariance of Direction:**
  If $v = k u$ with positive scalar $k > 0$, the scalar factor $k$ cancels out of both numerator and denominator:

$$
\frac{u \cdot (ku)}{\|u\| \|ku\|} = \frac{k(u \cdot u)}{\|u\| (k \|u\|)} = \frac{k \|u\|^2}{k \|u\|^2} = 1
$$

  The angle between two vectors depends exclusively on their **directional orientation**, completely independent of their lengths.

---

## 4. Step-by-Step Solution

### Step 1: Compute Vector Norms

1. **Norm of $a = (1, 2, 1)$:**

$$
\|a\| = \sqrt{1^2 + 2^2 + 1^2} = \sqrt{1 + 4 + 1} = \sqrt{6}
$$

2. **Norm of $b = (2, 4, 2)$:**

$$
\|b\| = \sqrt{2^2 + 4^2 + 2^2} = \sqrt{4 + 16 + 4} = \sqrt{24} = 2\sqrt{6}
$$

3. **Norm of $c = (2, 0, 3)$:**

$$
\|c\| = \sqrt{2^2 + 0^2 + 3^2} = \sqrt{4 + 0 + 9} = \sqrt{13}
$$

---

### Step 2: Evaluate $\frac{u \cdot v}{\|u\| \|v\|}$ for Each Pair

#### Pair 1: $(a, b)$
- Dot product:

$$
a \cdot b = (1)(2) + (2)(4) + (1)(2) = 2 + 8 + 2 = 12
$$

- Product of norms:

$$
\|a\| \|b\| = \sqrt{6} \cdot 2\sqrt{6} = 2 \times 6 = 12
$$

- Cosine of the angle:

$$
\cos \theta_{ab} = \frac{12}{12} = 1
$$

- Enclosed angle:

$$
\theta_{ab} = \arccos(1) = 0 \text{ rad} = 0^\circ
$$

---

#### Pair 2: $(a, c)$
- Dot product:

$$
a \cdot c = (1)(2) + (2)(0) + (1)(3) = 2 + 0 + 3 = 5
$$

- Product of norms:

$$
\|a\| \|c\| = \sqrt{6} \cdot \sqrt{13} = \sqrt{78}
$$

- Cosine of the angle:

$$
\cos \theta_{ac} = \frac{5}{\sqrt{78}} \approx \frac{5}{8.83176} \approx 0.5661
$$

- Enclosed angle:

$$
\theta_{ac} = \arccos(0.5661) \approx 0.969 \text{ rad} \approx 55.52^\circ
$$

---

#### Pair 3: $(b, c)$
- Dot product:

$$
b \cdot c = (2)(2) + (4)(0) + (2)(3) = 4 + 0 + 6 = 10
$$

- Product of norms:

$$
\|b\| \|c\| = 2\sqrt{6} \cdot \sqrt{13} = 2\sqrt{78}
$$

- Cosine of the angle:

$$
\cos \theta_{bc} = \frac{10}{2\sqrt{78}} = \frac{5}{\sqrt{78}} \approx 0.5661
$$

- Enclosed angle:

$$
\theta_{bc} = \arccos(0.5661) \approx 0.969 \text{ rad} \approx 55.52^\circ
$$

---

### Step 3: Order Pairs by Increasing Angle

List the angles from smallest to largest:
1. **Pair $(a, b)$:** $\theta_{ab} = 0^\circ$ ($\cos \theta = 1$)
2. **Pair $(a, c)$ and Pair $(b, c)$:** $\theta_{ac} = \theta_{bc} \approx 55.52^\circ$ ($\cos \theta = \frac{5}{\sqrt{78}}$)

The ordered ranking by increasing angle is:

$$
(a, b) < (a, c) = (b, c)
$$

---

### Step 4: Explain Why $\cos \theta_{ab} = 1$ Despite Different Lengths

Observe that vector $b$ is an exact positive scalar multiple of vector $a$:

$$
b = (2, 4, 2) = 2(1, 2, 1) = 2a
$$

1. **Algebraic Explanation:**
   In the cosine quotient, substituting $b = 2a$:

$$
\cos \theta_{ab} = \frac{a \cdot (2a)}{\|a\| \|2a\|} = \frac{2(a \cdot a)}{\|a\| (2\|a\|)} = \frac{2 \|a\|^2}{2 \|a\|^2} = 1
$$

   The scalar scaling factor $k = 2$ appears in both the numerator and denominator, canceling out completely.

2. **Geometric Explanation:**
   The angle between two vectors measures the divergence between their **directions**, not their lengths. Because $b = 2a$ with $2 > 0$, vector $b$ points along the exact same ray from the origin as vector $a$. There is zero angular separation between them ($\theta = 0^\circ$).
   Even though $b$ is twice as long as $a$, they point towards the exact same spot on the horizon; therefore, the cosine of their enclosed angle is identically $1$.

---

## 5. Final Answer & Conclusion

- **Computed Values:**
  - Pair $(a, b)$: $\cos \theta = 1 \implies \theta = 0^\circ$
  - Pair $(a, c)$: $\cos \theta = \frac{5}{\sqrt{78}} \approx 0.5661 \implies \theta \approx 55.52^\circ$
  - Pair $(b, c)$: $\cos \theta = \frac{5}{\sqrt{78}} \approx 0.5661 \implies \theta \approx 55.52^\circ$
- **Pairs Ordered by Increasing Angle:**

$$
\text{Pair } (a, b) \quad \left(0^\circ\right) \quad < \quad \text{Pair } (a, c) = \text{Pair } (b, c) \quad \left(55.52^\circ\right)
$$

- **Explanation:** The value is $1$ because $b = 2a$ points in the exact same direction as $a$. The cosine formula normalizes by lengths, making the angle completely independent of vector magnitudes.

---

## 6. Quick Verification

Verify that $\theta_{ac} = \theta_{bc}$ directly using collinearity:
Since $b = 2a$, the ray spanned by $b$ is identical to the ray spanned by $a$.
Therefore, the angle formed by any third vector $c$ with $b$ must be geometrically identical to the angle formed by $c$ with $a$:

$$
\angle(b, c) = \angle(2a, c) = \angle(a, c)
$$

This geometric necessity confirms why $\theta_{ac} = \theta_{bc} = 55.52^\circ$ without relying on intermediate calculations.

---

## 7. Common Mistakes to Avoid

1. **Inverting the Monotonicity of Cosine:**
   Thinking that a larger cosine means a larger angle. In fact, $\cos \theta$ decreases as $\theta$ increases from $0^\circ$ to $180^\circ$. A cosine of $1$ corresponds to the smallest possible angle ($0^\circ$).
2. **Confusing Direction with Length:**
   Expecting vectors of different lengths to have an angle between them. Parallel arrows sharing the same line and pointing sense always have an angle of $0^\circ$.
3. **Approximating Radicals Prematurely:**
   Writing $\cos \theta \approx 0.57$ without keeping the exact radical fraction $\frac{5}{\sqrt{78}}$.

---

## 8. How I Would Explain This in Class

> "The dot product formula divides out the lengths of both vectors on purpose: it acts like an angle sensor that completely ignores how long the arrows are, caring only about where they point. Vector $b$ is just vector $a$ stretched to twice its length, so both arrows point in the exact same compass direction with zero angular divergence. That is why their cosine is 1, and why measuring the angle from vector $c$ to either $a$ or $b$ gives the exact same 55.5 degrees."

