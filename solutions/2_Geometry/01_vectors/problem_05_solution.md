# Problem 05: Angle Between Vectors

## 1. The Original Problem

Given $u = (1, 1, 0)$ and $v = (1, 0, 1)$:

1. Use the sign of $u \cdot v$ to predict the type of angle.
2. Compute the angle.
3. Compare the result with the prediction.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the algebraic dot product $u \cdot v$ and use its sign to qualitatively classify the angle $\theta$ (acute, right, or obtuse) before calculating it.
2. Calculate the exact magnitudes $\|u\|$ and $\|v\|$.
3. Compute the cosine of the angle $\cos \theta = \frac{u \cdot v}{\|u\| \|v\|}$ and determine the exact angle $\theta$ in radians and degrees.
4. Compare the exact numerical angle with the initial qualitative prediction to verify consistency.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Geometric Dot Product Formula:**
  For any two non-zero vectors $u$ and $v$ enclosing an angle $\theta \in [0, \pi]$:

$$
u \cdot v = \|u\| \|v\| \cos \theta \iff \cos \theta = \frac{u \cdot v}{\|u\| \|v\|}
$$

- **Qualitative Angle Prediction by Sign:**
  Because vector norms $\|u\| > 0$ and $\|v\| > 0$ are strictly positive:
  - If $u \cdot v > 0 \implies \cos \theta > 0 \implies 0 \le \theta < \frac{\pi}{2}$ (**acute angle**).
  - If $u \cdot v = 0 \implies \cos \theta = 0 \implies \theta = \frac{\pi}{2}$ (**right angle**).
  - If $u \cdot v < 0 \implies \cos \theta < 0 \implies \frac{\pi}{2} < \theta \le \pi$ (**obtuse angle**).
- **Standard Special Angles:**
  If $\cos \theta = 1/2$, the corresponding reference angle in the first quadrant is $\theta = \pi/3 = 60^\circ$.

---

## 4. Step-by-Step Solution

### Step 1: Predict the Type of Angle from the Sign of $u \cdot v$

Compute the dot product of $u = (1, 1, 0)$ and $v = (1, 0, 1)$:

$$
u \cdot v = (1)(1) + (1)(0) + (0)(1) = 1 + 0 + 0 = 1
$$

Analyze the sign:

$$
u \cdot v = 1 > 0
$$

Because the dot product is strictly positive, the cosine of the angle must be positive:

$$
\cos \theta = \frac{u \cdot v}{\|u\| \|v\|} > 0
$$

On the interval $[0, \pi]$, $\cos \theta > 0$ implies:

$$
0^\circ \le \theta < 90^\circ \quad \left(0 \le \theta < \frac{\pi}{2}\right)
$$

**Prediction:** The angle between $u$ and $v$ is strictly **acute**.

---

### Step 2: Compute the Exact Angle

1. **Calculate the length of $u$:**

$$
\|u\| = \sqrt{1^2 + 1^2 + 0^2} = \sqrt{1 + 1 + 0} = \sqrt{2}
$$

2. **Calculate the length of $v$:**

$$
\|v\| = \sqrt{1^2 + 0^2 + 1^2} = \sqrt{1 + 0 + 1} = \sqrt{2}
$$

3. **Compute $\cos \theta$:**

$$
\cos \theta = \frac{u \cdot v}{\|u\| \|v\|} = \frac{1}{\sqrt{2} \cdot \sqrt{2}} = \frac{1}{2}
$$

4. **Determine the angle $\theta$:**
   Since $\cos \theta = 1/2$ and $\theta \in [0, \pi]$:

$$
\theta = \arccos\left(\frac{1}{2}\right) = \frac{\pi}{3} \text{ radians} = 60^\circ
$$

---

### Step 3: Compare the Result with the Prediction

- The prediction based on $u \cdot v = 1 > 0$ was that $\theta$ must be an **acute angle** ($0^\circ < \theta < 90^\circ$).
- The exact computed value is $\theta = 60^\circ$ ($\pi/3$).
- Because $0^\circ < 60^\circ < 90^\circ$, the exact result perfectly aligns with and validates the qualitative prediction.

---

## 5. Final Answer & Conclusion

- **Prediction:** The angle is **acute** because $u \cdot v = 1 > 0$.
- **Exact Angle:**

$$
\theta = \frac{\pi}{3} \text{ rad} = 60^\circ
$$

- **Comparison:** The exact value of $60^\circ$ is strictly between $0^\circ$ and $90^\circ$, completely confirming the initial sign analysis.

---

## 6. Quick Verification

Consider the equilateral triangle geometry:
- Vector $u = (1, 1, 0)$ is the diagonal of the face in the $xy$-plane of a unit cube.
- Vector $v = (1, 0, 1)$ is the diagonal of the adjacent face in the $xz$-plane of the same unit cube.
- Vector connecting their tips is $w = v - u = (1-1, 0-1, 1-0) = (0, -1, 1)$.
- Its length is $\|w\| = \sqrt{0^2 + (-1)^2 + 1^2} = \sqrt{2}$.

All three side lengths are equal:

$$
\|u\| = \sqrt{2}, \quad \|v\| = \sqrt{2}, \quad \|w\| = \sqrt{2}
$$

A triangle with three equal sides is an **equilateral triangle**, whose interior angles are all exactly $60^\circ$. This geometric proof confirms $\theta = 60^\circ$ without using trigonometry.

---

## 7. Common Mistakes to Avoid

1. **Forgetting to Normalize by Magnitudes:**
   Assuming $u \cdot v$ itself equals $\cos \theta$. The dot product only equals $\cos \theta$ when both vectors are unit vectors ($\|u\| = \|v\| = 1$). Here, each has length $\sqrt{2}$, so $\cos \theta = 1 / (\sqrt{2} \cdot \sqrt{2}) = 1/2$.
2. **Confusing Radians and Degrees:**
   Stating $\theta = \pi/6$ instead of $\pi/3$. Remember that $\cos(\pi/3) = 1/2$ while $\cos(\pi/6) = \sqrt{3}/2$.
3. **Skipping the Qualitative Sign Check:**
   Jumping straight to numerical calculation without checking the sign. Establishing the qualitative type of angle catches arithmetic errors before they propagate.

---

## 8. How I Would Explain This in Class

> "Before reaching for a calculator, always look at the sign of the dot product: positive means the arrows lean toward each other (acute), zero means a perfect right angle, and negative means they splay outward (obtuse). Here, $u \cdot v = +1$ immediately tells us the angle is acute. When we divide by their lengths $\sqrt{2} \times \sqrt{2} = 2$, we get $\cos \theta = 1/2$, which points directly to exactly 60 degrees—the angle between two face diagonals of a cube."

