# Problem 03: Vector Normalization

## 1. The Original Problem

For $v = (3, 4)$ find a unit vector $e$ with the same direction and orientation. Check that $\|e\| = 1$, reconstruct $v$ in the form $v = \|v\|e$, and explain what changes during normalization and what remains unchanged.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the magnitude (length) $\|v\|$ of vector $v = (3, 4)$.
2. Construct the normalized unit vector $e$ pointing in the exact same direction and orientation as $v$.
3. Prove that the constructed vector is indeed a unit vector by computing its norm and verifying $\|e\| = 1$.
4. Reconstruct the original vector using the polar-like decomposition $v = \|v\| e$.
5. Explain conceptually what geometric property changes and what remains invariant during normalization.

---

## 3. Before Calculating: What Idea Do We Need?

- **Vector Length in $\mathbb{R}^2$:**
  For $v = (x, y)$, its length is given by:

$$
\|v\| = \sqrt{x^2 + y^2}
$$

- **Vector Normalization Formula:**
  Multiplying a non-zero vector $v$ by the reciprocal of its length scales its magnitude to $1$ while preserving its direction:

$$
e = \frac{v}{\|v\|} = \frac{1}{\|v\|} v
$$

- **Separation of Magnitude and Direction:**
  Every non-zero vector can be factored uniquely into a scalar magnitude and a directional unit vector:

$$
v = \|v\| e = (\text{magnitude}) \times (\text{direction})
$$

- **Geometric Invariance:**
  The direction angle $\theta$ in polar coordinates satisfies $\tan \theta = y / x$. When scaling by a positive factor $c > 0$, the ratio $(cy)/(cx) = y/x$ remains identical, so $\theta$ is unchanged.

---

## 4. Step-by-Step Solution

### Step 1: Compute the Length of $v$

Calculate the Euclidean norm of $v = (3, 4)$:

$$
\|v\| = \sqrt{3^2 + 4^2} = \sqrt{9 + 16} = \sqrt{25} = 5
$$

The vector has a length of $5$ units.

### Step 2: Construct the Unit Vector $e$

Divide vector $v$ by its length $\|v\| = 5$:

$$
e = \frac{v}{\|v\|} = \frac{1}{5} (3, 4) = \left( \frac{3}{5}, \frac{4}{5} \right) = (0.6, 0.8)
$$

Since the scaling factor $1/5$ is strictly positive, $e$ shares the exact same line of action (direction) and arrow pointing sense (orientation) as $v$.

---

### Step 3: Check That $\|e\| = 1$

Compute the Euclidean norm of $e = \left(\frac{3}{5}, \frac{4}{5}\right)$:

$$
\|e\| = \sqrt{\left(\frac{3}{5}\right)^2 + \left(\frac{4}{5}\right)^2} = \sqrt{\frac{9}{25} + \frac{16}{25}} = \sqrt{\frac{25}{25}} = \sqrt{1} = 1
$$

The vector $e$ is verified to be a unit vector.

---

### Step 4: Reconstruct $v$ in the Form $v = \|v\| e$

Multiply the unit vector $e$ by the scalar length $\|v\| = 5$:

$$
\|v\| e = 5 \cdot \left( \frac{3}{5}, \frac{4}{5} \right) = \left( 5 \cdot \frac{3}{5}, 5 \cdot \frac{4}{5} \right) = (3, 4) = v
$$

The original vector $v$ is perfectly reconstructed.

---

### Step 5: What Changes and What Remains Unchanged?

1. **What changes:**
   - **Magnitude (Length):** The length shrinks from $5$ down to $1$.
   - **Individual Coordinates:** The components change from $(3, 4)$ to $(0.6, 0.8)$ because each coordinate is divided by $5$.

2. **What remains unchanged:**
   - **Direction (Line of Action):** The vector lies along the exact same ray originating from the origin. The slope of the line remains $m = 4/3 \approx 1.333$.
   - **Orientation (Sense):** The vector continues to point into the first quadrant with angle $\theta = \arctan(4/3) \approx 53.13^\circ$ relative to the positive $x$-axis. It is not reversed because $1/\|v\| > 0$.
   - **Relative Proportions:** The ratio between the vertical and horizontal components is preserved: $\frac{4/5}{3/5} = \frac{4}{3}$.

---

## 5. Final Answer & Conclusion

- **Unit Vector:**

$$
e = \left( \frac{3}{5}, \frac{4}{5} \right) = (0.6, 0.8)
$$

- **Length Verification:** $\|e\| = 1$.
- **Reconstruction:** $v = 5 \cdot \left(\frac{3}{5}, \frac{4}{5}\right) = (3, 4)$.
- **Conceptual Summary:** Normalization strips away the vector's size (reducing it to $1$) while isolating and preserving its pure directional pointer.

---

## 6. Quick Verification

Check the angle using dot product between $v$ and $e$:

$$
v \cdot e = (3)\left(\frac{3}{5}\right) + (4)\left(\frac{4}{5}\right) = \frac{9 + 16}{5} = \frac{25}{5} = 5
$$

Recall the geometric dot product formula:

$$
v \cdot e = \|v\| \|e\| \cos \theta = 5 \cdot 1 \cdot \cos \theta = 5 \cos \theta
$$

Equating the two:

$$
5 \cos \theta = 5 \implies \cos \theta = 1 \implies \theta = 0^\circ
$$

An angle of $0^\circ$ confirms that $e$ points in the exact same direction and orientation as $v$.

---

## 7. Common Mistakes to Avoid

1. **Dividing by the Square of the Length:**
   Accidentally computing $v / \|v\|^2 = (3/25, 4/25)$. The resulting vector would have length $1/5$, not $1$.
2. **Forgetting to Distribute to Both Coordinates:**
   Dividing only the first coordinate by $5$, writing $(3/5, 4)$.
3. **Confusing Orientation with Direction:**
   Assuming $-e = (-3/5, -4/5)$ has the same direction and orientation. While $-e$ shares the same line of action (direction), its orientation is flipped by $180^\circ$.

---

## 8. How I Would Explain This in Class

> "Imagine you have an arrow pointing toward a treasure chest 5 miles away: normalization simply shrinks that arrow so it is exactly 1 mile long, but without tilting it by even a fraction of a degree. You are keeping the pure direction of the compass needle while resetting its ruler measurement to 1, which lets you write any vector as 'magnitude times direction'."

