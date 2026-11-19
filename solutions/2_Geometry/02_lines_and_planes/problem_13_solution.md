# Problem 13: Closest Point on a Plane

## 1. The Original Problem

Find the point on the plane $x + 2y + 2z = 4$ closest to $P = (3, 0, 0)$. Give the distance and check that the segment joining the two points is perpendicular to the plane.

---

## 2. What Are We Trying to Find?

We need to:
1. Construct the perpendicular line dropped from the external point $P(3, 0, 0)$ to the plane $\Pi: x + 2y + 2z = 4$.
2. Compute the exact coordinates of the closest point $Q$ on the plane (the orthogonal projection).
3. Compute the shortest distance $d(P, \Pi)$ between $P$ and the plane.
4. Verify that the displacement segment $\overrightarrow{PQ}$ (or $\overrightarrow{QP}$) is strictly perpendicular to the plane by checking that it is parallel to the normal vector $n$.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Geometry of Closest Approach:**
  In Euclidean 3D space, the shortest distance from an external point $P$ to a plane $\Pi$ occurs along the unique normal line dropped perpendicularly from $P$ to the plane.
  The closest point $Q$ is the intersection of this normal line with $\Pi$.
- **The Normal Line Equation:**
  With plane normal vector $n = (a, b, c) = (1, 2, 2)$, the normal line passing through $P(x_0, y_0, z_0)$ is:

$$
X(t) = P + t n
$$

- **Distance Formula Check:**
  The distance can be verified independently using the point-plane distance formula:

$$
d(P, \Pi) = \frac{|a x_0 + b y_0 + c z_0 - d|}{\sqrt{a^2 + b^2 + c^2}}
$$

- **Perpendicularity Check:**
  The segment connecting $P$ and $Q$ is perpendicular to the plane if and only if its displacement vector $\overrightarrow{PQ} = Q - P$ is a scalar multiple of the normal vector $n$:

$$
\overrightarrow{PQ} \parallel n \iff \overrightarrow{PQ} = k n
$$

---

## 4. Step-by-Step Solution

### Step 1: Set Up the Normal Line Through $P$

From the plane equation $x + 2y + 2z = 4$, the normal vector is:

$$
n = (1, 2, 2)
$$

The line passing through $P(3, 0, 0)$ in the normal direction $n$ is parameterized by:

$$
\begin{cases}
x = 3 + t, \\\\
y = 0 + 2t = 2t, \\\\
z = 0 + 2t = 2t
\end{cases}
$$

### Step 2: Intersect the Line with the Plane to Find $Q$

Substitute the parametric expressions for $x, y,$ and $z$ into $x + 2y + 2z = 4$:

$$
(3 + t) + 2(2t) + 2(2t) = 4
$$

Expand and combine like terms:

$$
3 + t + 4t + 4t = 4
$$

$$
9t + 3 = 4 \implies 9t = 4 - 3 = 1 \implies t = \frac{1}{9}
$$

Now substitute $t = \frac{1}{9}$ into the parametric line equations to obtain the coordinates of $Q$:
- $x$-coordinate:

$$
x = 3 + \frac{1}{9} = \frac{27 + 1}{9} = \frac{28}{9}
$$

- $y$-coordinate:

$$
y = 2\left(\frac{1}{9}\right) = \frac{2}{9}
$$

- $z$-coordinate:

$$
z = 2\left(\frac{1}{9}\right) = \frac{2}{9}
$$

Thus, the closest point on the plane is:

$$
Q = \left( \frac{28}{9}, \frac{2}{9}, \frac{2}{9} \right)
$$

Check that $Q$ lies on the plane:

$$
\frac{28}{9} + 2\left(\frac{2}{9}\right) + 2\left(\frac{2}{9}\right) = \frac{28 + 4 + 4}{9} = \frac{36}{9} = 4
$$

It satisfies the plane equation.

---

### Step 3: Compute the Distance

The distance is the Euclidean length of the displacement segment $\overrightarrow{PQ}$:

$$
\overrightarrow{PQ} = Q - P = \left( \frac{28}{9} - 3, \frac{2}{9} - 0, \frac{2}{9} - 0 \right) = \left( \frac{1}{9}, \frac{2}{9}, \frac{2}{9} \right)
$$

Compute the norm $\|\overrightarrow{PQ}\|$:

$$
d = \|\overrightarrow{PQ}\| = \sqrt{\left(\frac{1}{9}\right)^2 + \left(\frac{2}{9}\right)^2 + \left(\frac{2}{9}\right)^2} = \sqrt{\frac{1 + 4 + 4}{81}} = \sqrt{\frac{9}{81}} = \sqrt{\frac{1}{9}} = \frac{1}{3} \approx 0.333
$$

The shortest distance from $P$ to the plane is $\frac{1}{3}$.

---

### Step 4: Verify Perpendicularity of the Segment to the Plane

The displacement vector connecting $P$ to $Q$ is:

$$
\overrightarrow{PQ} = \left( \frac{1}{9}, \frac{2}{9}, \frac{2}{9} \right) = \frac{1}{9} (1, 2, 2) = \frac{1}{9} n
$$

Because $\overrightarrow{PQ}$ is an exact positive scalar multiple of the plane's normal vector $n = (1, 2, 2)$, the segment $[PQ]$ is aligned precisely with the normal direction.
Since the normal direction is perpendicular to the plane, the segment joining $P$ and $Q$ is **strictly perpendicular to the plane**:

$$
\overrightarrow{PQ} \perp \Pi
$$

---

## 5. Final Answer & Conclusion

- **Closest Point on the Plane:**

$$
Q = \left( \frac{28}{9}, \frac{2}{9}, \frac{2}{9} \right)
$$

- **Shortest Distance:**

$$
d = \frac{1}{3}
$$

- **Perpendicularity Verification:** $\overrightarrow{PQ} = \frac{1}{9}(1, 2, 2) = \frac{1}{9} n$, confirming that the segment $[PQ]$ meets the plane at a perfect right angle.

---

## 6. Quick Verification

Verify the distance using the standard point-to-plane distance formula:

$$
d(P, \Pi) = \frac{|a x_0 + b y_0 + c z_0 - d|}{\sqrt{a^2 + b^2 + c^2}}
$$

For $P(3, 0, 0)$ and plane $x + 2y + 2z - 4 = 0$:
- Numerator: $|1(3) + 2(0) + 2(0) - 4| = |3 - 4| = |-1| = 1$.
- Denominator: $\sqrt{1^2 + 2^2 + 2^2} = \sqrt{1 + 4 + 4} = \sqrt{9} = 3$.
- Distance: $d = \frac{1}{3}$.

The direct formula yields $d = 1/3$, confirming both the geometric projection and the distance value.

---

## 7. Common Mistakes to Avoid

1. **Arithmetic Errors in the Normal Length:**
   Computing $\sqrt{1^2 + 2^2 + 2^2} = \sqrt{1 + 4 + 4} = \sqrt{9} = 3$. A frequent slip is writing $\sqrt{5}$ by forgetting the third component.
2. **Fraction Addition Slips:**
   Computing $3 + 1/9$ as $4/9$ instead of $\frac{27 + 1}{9} = \frac{28}{9}$.
3. **Forgetting to Check That $Q$ Lies in the Plane:**
   Never leave the projection unchecked. Plugging $Q$ into $x + 2y + 2z = 4$ takes only seconds and catches any algebra errors.

---

## 8. How I Would Explain This in Class

> "If you drop a stone from point $P(3, 0, 0)$ straight down onto the slanted roof $x + 2y + 2z = 4$, gravity pulls it along the normal direction $(1, 2, 2)$. The stone travels along that perpendicular path for a tiny distance of $t = 1/9$, landing at point $(28/9, 2/9, 2/9)$. Because it took the strictly perpendicular plumb line to the roof, that landing spot is the closest possible point on the entire plane, and the journey was only $1/3$ of a unit long."

