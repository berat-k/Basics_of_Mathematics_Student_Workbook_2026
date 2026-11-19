# Problem 14: Closest Point on a Line

## 1. The Original Problem

Given a point $P = (4, 1)$ and a line through the origin with direction $v = (1, 2)$. Using projection, find the closest point on the line, the distance from $P$ to the line, and verify that the appropriate vector is perpendicular to the direction of the line.

---

## 2. What Are We Trying to Find?

We need to:
1. Identify the line $\mathcal{L}$ through the origin parameterized by direction vector $v = (1, 2)$.
2. Use vector projection to find the point $Q$ on $\mathcal{L}$ that is closest to point $P(4, 1)$.
3. Compute the geometric distance $d(P, \mathcal{L}) = \|\overrightarrow{QP}\|$.
4. Algebraically verify that the displacement vector $\overrightarrow{QP}$ (or $\overrightarrow{PQ}$) is strictly perpendicular to the direction vector $v$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Line Through the Origin:**
  A line $\mathcal{L}$ passing through the origin $O(0, 0)$ with direction vector $v$ consists of all points whose position vectors are scalar multiples of $v$:

$$
\mathcal{L} = \{ t v \mid t \in \mathbb{R} \}
$$

- **Orthogonal Projection as Minimum Distance:**
  By Euclidean geometry, the shortest distance from an external point $P$ to a line $\mathcal{L}$ is measured along the unique line segment that drops perpendicularly onto $\mathcal{L}$.
  The foot of this perpendicular is the orthogonal projection of the position vector $u = \overrightarrow{OP} = P$ onto the direction vector $v$:

$$
Q = \text{proj}_v(u) = \left( \frac{u \cdot v}{v \cdot v} \right) v
$$

- **Perpendicular Distance Vector:**
  The vector connecting the closest point $Q$ back to $P$ is:

$$
\overrightarrow{QP} = u - \text{proj}_v(u)
$$

  The distance from $P$ to the line is the length of this perpendicular vector: $d = \|\overrightarrow{QP}\|$.
  Orthogonality guarantees:

$$
\overrightarrow{QP} \cdot v = 0
$$

---

## 4. Step-by-Step Solution

### Step 1: Identify Vectors and Compute Dot Products

Let $u = \overrightarrow{OP} = (4, 1)$ and $v = (1, 2)$:

1. **Compute $u \cdot v$:**

$$
u \cdot v = (4)(1) + (1)(2) = 4 + 2 = 6
$$

2. **Compute $v \cdot v = \|v\|^2$:**

$$
v \cdot v = 1^2 + 2^2 = 1 + 4 = 5
$$

### Step 2: Find the Closest Point $Q$ on the Line

Compute the projection vector $\text{proj}_v(u)$:

$$
\text{proj}_v(u) = \left( \frac{u \cdot v}{v \cdot v} \right) v = \frac{6}{5} (1, 2) = \left( \frac{6}{5}, \frac{12}{5} \right) = (1.2, 2.4)
$$

Because the line passes through the origin $O(0, 0)$, the position vector of the closest point $Q$ is identically $\text{proj}_v(u)$:

$$
Q = \left( \frac{6}{5}, \frac{12}{5} \right) = (1.2, 2.4)
$$

---

### Step 3: Compute the Distance from $P$ to the Line

The vector connecting the closest point $Q$ to $P$ is:

$$
\overrightarrow{QP} = P - Q = (4, 1) - \left( \frac{6}{5}, \frac{12}{5} \right)
$$

Express $P$ with common denominator $5$:

$$
(4, 1) = \left( \frac{20}{5}, \frac{5}{5} \right)
$$

Subtract the coordinates:

$$
\overrightarrow{QP} = \left( \frac{20 - 6}{5}, \frac{5 - 12}{5} \right) = \left( \frac{14}{5}, -\frac{7}{5} \right) = (2.8, -1.4)
$$

Now calculate the Euclidean norm of $\overrightarrow{QP}$:

$$
\|\overrightarrow{QP}\| = \sqrt{\left(\frac{14}{5}\right)^2 + \left(-\frac{7}{5}\right)^2} = \sqrt{\frac{196 + 49}{25}} = \sqrt{\frac{245}{25}}
$$

Factor out the perfect square:

$$
\sqrt{\frac{49 \times 5}{25}} = \frac{7\sqrt{5}}{5} = \frac{7}{\sqrt{5}} \approx 3.1305
$$

The distance from $P$ to the line is $\frac{7\sqrt{5}}{5} \approx 3.13$.

---

### Step 4: Verify Perpendicularity to Direction Vector $v$

Take the scalar dot product between $\overrightarrow{QP} = \left(\frac{14}{5}, -\frac{7}{5}\right)$ and $v = (1, 2)$:

$$
\overrightarrow{QP} \cdot v = \left(\frac{14}{5}\right)(1) + \left(-\frac{7}{5}\right)(2) = \frac{14}{5} - \frac{14}{5} = 0
$$

Because $\overrightarrow{QP} \cdot v = 0$, the vector connecting the line to point $P$ is verified to be strictly perpendicular to the direction of the line:

$$
\overrightarrow{QP} \perp v
$$

---

## 5. Final Answer & Conclusion

- **Closest Point on the Line:**

$$
Q = \left( \frac{6}{5}, \frac{12}{5} \right) = (1.2, 2.4)
$$

- **Distance from $P$ to the Line:**

$$
d(P, \mathcal{L}) = \frac{7\sqrt{5}}{5} = \frac{7}{\sqrt{5}} \approx 3.1305
$$

- **Verification:** $\overrightarrow{QP} \cdot v = \frac{14}{5}(1) - \frac{7}{5}(2) = 0$.
- **Conclusion:** Orthogonal projection automatically identifies the point of closest approach because the shortest path from a point to a straight line is always the perpendicular drop.

---

## 6. Quick Verification

Verify using calculus / minimization of squared distance:
Any point on the line is $X(t) = (t, 2t)$. The squared distance from $P(4, 1)$ to $X(t)$ is:

$$
f(t) = (t - 4)^2 + (2t - 1)^2 = (t^2 - 8t + 16) + (4t^2 - 4t + 1) = 5t^2 - 12t + 17
$$

To minimize, take the derivative and set to zero:

$$
f'(t) = 10t - 12 = 0 \implies t = \frac{12}{10} = \frac{6}{5}
$$

Substitute $t = 6/5$ back into $X(t)$:

$$
X\left(\frac{6}{5}\right) = \left(\frac{6}{5}, 2 \cdot \frac{6}{5}\right) = \left(\frac{6}{5}, \frac{12}{5}\right) = Q
$$

The minimum value of $f(t)$ is:

$$
f\left(\frac{6}{5}\right) = 5\left(\frac{36}{25}\right) - 12\left(\frac{6}{5}\right) + 17 = \frac{36}{5} - \frac{72}{5} + \frac{85}{5} = \frac{49}{5}
$$

The distance is $d = \sqrt{49/5} = \frac{7}{\sqrt{5}} = \frac{7\sqrt{5}}{5}$.
The calculus minimization gives the exact same closest point and distance.

---

## 7. Common Mistakes to Avoid

1. **Dividing by $\|u\|^2$ Instead of $\|v\|^2$:**
   Using $\frac{u \cdot v}{u \cdot u}$ instead of dividing by the direction vector's squared length $v \cdot v$.
2. **Missing the Square Root for Distance:**
   Reporting $49/5 = 9.8$ as the distance. $9.8$ is the *squared* distance; the actual distance is $\sqrt{49/5} \approx 3.13$.
3. **Leaving Fractions Unchecked:**
   Computing $5 - 12$ as $+7$ instead of $-7$, resulting in the wrong sign for the vertical component.

---

## 8. How I Would Explain This in Class

> "If you are standing out at coordinate $(4, 1)$ in a field and want to reach a straight paved road that runs along direction $(1, 2)$ through the origin, what is the quickest way? You don't walk to the origin; you walk directly perpendicular to the road. The vector projection finds the exact spot on the asphalt where your perpendicular path lands—at $(1.2, 2.4)$—and measuring the length of that perpendicular path gives your exact walking distance of $\frac{7}{\sqrt{5}}$ units."

