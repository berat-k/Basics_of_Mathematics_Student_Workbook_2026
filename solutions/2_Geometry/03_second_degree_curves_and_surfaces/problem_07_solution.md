# Problem 07: Classifying a Second-Degree Equation

## 1. The Original Problem

Determine the type of object described by:

1. $4x^2 + 9y^2 = 36$,
2. $x^2 - y^2 = 1$,
3. $x^2 - 4y = 0$,
4. $x^2 + y^2 + 1 = 0$.

In the last case, explain why there are no real points.

---

## 2. What Are We Trying to Find?

We need to:
1. Classify each of the four second-degree planar equations into its specific geometric category.
2. Put each equation into its standard canonical form.
3. Identify the key structural geometric parameters (center, vertex, semiaxes, or focal opening).
4. For the fourth equation ($x^2 + y^2 + 1 = 0$), provide a rigorous algebraic proof explaining why its solution set contains no real points in the Cartesian plane $\mathbb{R}^2$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Classification Criteria for Quadratic Curves in $\mathbb{R}^2$:**
  Consider $A x^2 + B y^2 + C x + D y + F = 0$ (with no cross-term $xy$):
  1. **Both $A$ and $B$ have the same sign ($A \cdot B > 0$):**
     - If coefficients are equal ($A = B$), it represents a **circle** (or single point, or empty set).
     - If coefficients are unequal ($A \neq B$), it represents an **ellipse** (or single point, or empty set).
  2. **$A$ and $B$ have opposite signs ($A \cdot B < 0$):**
     - Represents a **hyperbola** (or a pair of intersecting lines if the constant is $0$).
  3. **Exactly one quadratic coefficient is zero ($A \cdot B = 0$):**
     - Represents a **parabola** (or parallel lines, or empty set).
- **The Non-Negativity of Real Squares:**
  For any real number $u \in \mathbb{R}$, $u^2 \ge 0$. The sum of squares of real numbers can never be strictly negative.

---

## 4. Step-by-Step Solution

### Case 1: $4x^2 + 9y^2 = 36$

1. **Reduce to Canonical Form:**
   Divide the entire equation by $36$:

$$
\frac{4x^2}{36} + \frac{9y^2}{36} = \frac{36}{36} \implies \frac{x^2}{9} + \frac{y^2}{4} = 1 \iff \frac{x^2}{3^2} + \frac{y^2}{2^2} = 1
$$

2. **Classification and Features:**
   - Both variables are squared with positive, unequal coefficients ($9 \neq 4$), summing to $1$.
   - **Type:** **Ellipse** centered at the origin $(0, 0)$.
   - Horizontal semimajor axis: $a = 3$.
   - Vertical semiminor axis: $b = 2$.
   - Intercepts: $(\pm 3, 0)$ on the $x$-axis and $(0, \pm 2)$ on the $y$-axis.

---

### Case 2: $x^2 - y^2 = 1$

1. **Reduce to Canonical Form:**
   Write the denominators explicitly as $1^2$:

$$
\frac{x^2}{1^2} - \frac{y^2}{1^2} = 1
$$

2. **Classification and Features:**
   - Both variables are squared with opposite signs ($+x^2$ and $-y^2$), equaling $1$.
   - The coefficients are equal in magnitude ($a = b = 1$).
   - **Type:** **Equilateral (Rectangular) Hyperbola** opening horizontally.
   - Real vertices: $(\pm 1, 0)$ on the $x$-axis.
   - Semiaxes: $a = 1, b = 1$.
   - Asymptotes: $y = \pm \frac{b}{a} x = \pm x$. The asymptotes are perpendicular to each other ($m_1 \cdot m_2 = (1)(-1) = -1$).

---

### Case 3: $x^2 - 4y = 0$

1. **Reduce to Canonical Form:**
   Isolate the linear term:

$$
x^2 = 4y \iff y = \frac{1}{4} x^2
$$

2. **Classification and Features:**
   - Only variable $x$ is squared; variable $y$ appears only to the first power.
   - In standard form $x^2 = 2py$, $2p = 4 \implies p = 2$ (focal distance $f = p/2 = 1$).
   - **Type:** **Parabola** opening vertically upwards.
   - Vertex: $V = (0, 0)$.
   - Axis of symmetry: The vertical line $x = 0$ (the $y$-axis).
   - Focus: $(0, 1)$; Directrix line: $y = -1$.

---

### Case 4: $x^2 + y^2 + 1 = 0$

1. **Algebraic Manipulation:**
   Subtract $1$ from both sides:

$$
x^2 + y^2 = -1
$$

2. **Classification:**
   - **Type:** **Empty Set** ($\emptyset$) / **Imaginary (Virtual) Circle**.
   - No real geometric curve exists in the real coordinate plane $\mathbb{R}^2$.

3. **Rigorous Explanation of Why There Are No Real Points:**
   - By the fundamental axiom of real numbers, the square of any real number is non-negative:

$$
x \in \mathbb{R} \implies x^2 \ge 0
$$

$$
y \in \mathbb{R} \implies y^2 \ge 0
$$

   - Adding two non-negative real numbers always produces a non-negative real number:

$$
x^2 + y^2 \ge 0 \quad \text{for all } (x, y) \in \mathbb{R}^2
$$

   - Adding $1$ to both sides gives:

$$
x^2 + y^2 + 1 \ge 0 + 1 = 1 > 0
$$

   - Therefore, the expression $x^2 + y^2 + 1$ is strictly greater than or equal to $1$ for every possible choice of real numbers $(x, y)$.
   - It can **never** equal $0$.
   - Consequently, there are **no real points** $(x, y) \in \mathbb{R}^2$ that satisfy the equation. The solution set over $\mathbb{R}^2$ is completely empty:

$$
\{ (x, y) \in \mathbb{R}^2 \mid x^2 + y^2 + 1 = 0 \} = \emptyset
$$

---

## 5. Final Answer & Conclusion

| Equation | Canonical Form | Geometric Classification | Key Feature |
| :--- | :--- | :--- | :--- |
| **1.** $4x^2 + 9y^2 = 36$ | $\frac{x^2}{9} + \frac{y^2}{4} = 1$ | **Ellipse** | Semiaxes $a = 3, b = 2$ |
| **2.** $x^2 - y^2 = 1$ | $\frac{x^2}{1^2} - \frac{y^2}{1^2} = 1$ | **Equilateral Hyperbola** | Vertices $(\pm 1, 0)$, asymptotes $y = \pm x$ |
| **3.** $x^2 - 4y = 0$ | $x^2 = 4y$ | **Parabola** | Vertex $(0, 0)$, opens upwards |
| **4.** $x^2 + y^2 + 1 = 0$ | $x^2 + y^2 = -1$ | **Empty Set** ($\emptyset$) | No real points; $x^2 + y^2 + 1 \ge 1 > 0$ |

---

## 6. Quick Verification

1. For equation 1, test $(3, 0)$: $4(9) + 9(0) = 36$. (Verified)
2. For equation 2, test $(1, 0)$: $1^2 - 0^2 = 1$. (Verified)
3. For equation 3, test $(2, 1)$: $2^2 - 4(1) = 4 - 4 = 0$. (Verified)
4. For equation 4, test the origin $(0, 0)$ as the candidate minimum:
   $0^2 + 0^2 + 1 = 1 \neq 0$.
   Since the minimum value across all of $\mathbb{R}^2$ is $1$, the equation can never equal $0$.

---

## 7. Common Mistakes to Avoid

1. **Confusing Equilateral Hyperbola with a Circle:**
   Seeing coefficients $1$ and $1$ and thinking $x^2 - y^2 = 1$ is a circle. The minus sign completely changes the geometry from a closed circle to an open hyperbola.
2. **Calling $x^2 + y^2 + 1 = 0$ a Point:**
   Confusing $x^2 + y^2 = 0$ with $x^2 + y^2 = -1$. The equation $x^2 + y^2 = 0$ has exactly one real solution: the origin $(0, 0)$. But $x^2 + y^2 = -1$ has zero real solutions.
3. **Missing the Rectangular Property of $x^2 - y^2 = 1$:**
   Failing to note that when $a = b$, the asymptotes are perpendicular ($y = \pm x$), giving an equilateral (rectangular) hyperbola.

---

## 8. How I Would Explain This in Class

> "Every second-degree equation tells a story through its signs and powers: two positive squares give a closed oval (ellipse), a positive square minus a negative square breaks open into wings (hyperbola), and having only one square curves into a bowl (parabola). But if an equation asks two real squares to sum to $-1$, it is asking for the impossible—no real numbers squared can ever sum to a negative number, leaving your graphing paper completely blank."

