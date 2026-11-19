# Problem 01: Recognizing Curves from Canonical Form

## 1. The Original Problem

Recognize the curves

$$
x^2 + y^2 = 9,
$$

$$
\frac{x^2}{16} + \frac{y^2}{9} = 1,
$$

$$
y^2 = 8x,
$$

$$
\frac{x^2}{9} - \frac{y^2}{4} = 1.
$$

For each one, identify the most important features and make a sketch. Explain which parts of the equation let you recognize the type of curve.

---

## 2. What Are We Trying to Find?

We need to:
1. Classify each of the four second-degree planar equations into its standard geometric curve type.
2. Identify the signature algebraic hallmarks in each equation that reveal its type.
3. Determine the key geometric features (center, vertex, axes, radii, asymptotes, and domain/range) for each curve.
4. Provide qualitative coordinate sketches and structural layouts for all four curves.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Canonical Zoo of Second-Degree Curves:**
  In the 2D Cartesian plane, second-degree polynomial equations in $x$ and $y$ define conic sections:
  1. **Circle ($x^2 + y^2 = R^2$):** Both variables are squared, with positive and **equal** coefficients. Radius is $R$.
  2. **Ellipse ($\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$):** Both variables are squared, with positive and **unequal** coefficients. Semiaxes are $a$ and $b$.
  3. **Parabola ($y^2 = 2px$ or $x^2 = 2py$):** Exactly **one** variable is squared while the other is linear (first power).
  4. **Hyperbola ($\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$):** Both variables are squared, but with **opposite signs** ($+/-$), equaling a positive constant.

---

## 4. Step-by-Step Solution

### Curve 1: $x^2 + y^2 = 9$

1. **Recognition:**
   - Both $x$ and $y$ appear to the second power.
   - The coefficients of $x^2$ and $y^2$ are both $+1$ (positive and equal).
   - The right-hand side is positive ($9 > 0$).
   - **Classification:** **Circle** centered at the origin.

2. **Key Geometric Features:**
   - Center: $S = (0, 0)$
   - Radius: $R = \sqrt{9} = 3$
   - Intercepts: $(\pm 3, 0)$ on the $x$-axis and $(0, \pm 3)$ on the $y$-axis
   - Domain and Range: $x \in [-3, 3]$, $y \in [-3, 3]$
   - Symmetry: Full rotational symmetry about the origin.

3. **Qualitative Sketch Layout:**
   A perfectly round closed loop centered at $(0, 0)$ passing through $(3, 0)$, $(0, 3)$, $(-3, 0)$, and $(0, -3)$.

---

### Curve 2: $\frac{x^2}{16} + \frac{y^2}{9} = 1$

1. **Recognition:**
   - Both $x$ and $y$ appear squared with a plus sign between them, equaling $1$.
   - The denominators are unequal ($16 \neq 9$), meaning the scaling factors along $x$ and $y$ differ.
   - **Classification:** **Ellipse** centered at the origin.

2. **Key Geometric Features:**
   - Center: $S = (0, 0)$
   - Horizontal semimajor axis: $a = \sqrt{16} = 4$
   - Vertical semiminor axis: $b = \sqrt{9} = 3$
   - Major vertices: $(\pm 4, 0)$ on the $x$-axis
   - Minor vertices: $(0, \pm 3)$ on the $y$-axis
   - Domain: $x \in [-4, 4]$; Range: $y \in [-3, 3]$
   - Orientation: Elongated horizontally because $a = 4 > 3 = b$.

3. **Qualitative Sketch Layout:**
   A smooth oval centered at the origin, stretched wider horizontally (width $8$) than vertically (height $6$).

---

### Curve 3: $y^2 = 8x$

1. **Recognition:**
   - Variable $y$ is squared, while variable $x$ appears only to the first power.
   - **Classification:** **Parabola** with horizontal axis of symmetry.

2. **Key Geometric Features:**
   - Vertex: $V = (0, 0)$
   - Axis of symmetry: The $x$-axis ($y = 0$), because $(-y)^2 = y^2 = 8x$
   - Parameter $p$: In standard form $y^2 = 2px$, $2p = 8 \implies p = 4$ (focal distance $p/2 = 2$)
   - Focus: $F = (2, 0)$; Directrix line: $x = -2$
   - Opening direction: Since $y^2 \ge 0$, we must have $8x \ge 0 \implies x \ge 0$. The parabola opens to the **right**
   - Sample points: For $x = 2$, $y^2 = 16 \implies y = \pm 4$, giving points $(2, 4)$ and $(2, -4)$.

3. **Qualitative Sketch Layout:**
   An open U-shaped curve resting its vertex at $(0, 0)$ and spreading symmetrically to the right across the positive $x$-axis.

---

### Curve 4: $\frac{x^2}{9} - \frac{y^2}{4} = 1$

1. **Recognition:**
   - Both variables are squared, but they have **opposite signs** ($+x^2$ and $-y^2$).
   - The positive term is associated with $x$, and the equation equals $+1$.
   - **Classification:** **Hyperbola** opening horizontally.

2. **Key Geometric Features:**
   - Center: $S = (0, 0)$
   - Real semiaxis: $a = \sqrt{9} = 3$ along the $x$-axis
   - Imaginary semiaxis: $b = \sqrt{4} = 2$ along the $y$-axis
   - Vertices: $(\pm 3, 0)$ on the $x$-axis
   - Intercepts: No $y$-intercepts (setting $x = 0$ gives $-y^2/4 = 1 \implies y^2 = -4$, impossible over $\mathbb{R}$)
   - Domain: $x \in (-\infty, -3] \cup [3, \infty)$; Range: $y \in \mathbb{R}$
   - Asymptotes: Obtained by replacing $1$ with $0$:

$$
\frac{x^2}{9} - \frac{y^2}{4} = 0 \implies \frac{y^2}{4} = \frac{x^2}{9} \implies y = \pm \frac{2}{3} x
$$

3. **Qualitative Sketch Layout:**
   Two distinct, symmetric open branches curving away from vertices $(-3, 0)$ and $(3, 0)$, approaching the diagonal asymptote lines $y = \frac{2}{3}x$ and $y = -\frac{2}{3}x$ at infinity.

---

## 5. Final Answer & Conclusion

| Curve Equation | Recognized Type | Center / Vertex | Key Dimensions | Key Identification Feature |
| :--- | :--- | :--- | :--- | :--- |
| $x^2 + y^2 = 9$ | **Circle** | Center $(0, 0)$ | Radius $R = 3$ | Equal squared coefficients ($+1$) |
| $\frac{x^2}{16} + \frac{y^2}{9} = 1$ | **Ellipse** | Center $(0, 0)$ | Semiaxes $a = 4, b = 3$ | Sum of squares with unequal denominators |
| $y^2 = 8x$ | **Parabola** | Vertex $(0, 0)$ | Focus $(2, 0)$, opens right | Only one variable squared ($y^2$), one linear ($x$) |
| $\frac{x^2}{9} - \frac{y^2}{4} = 1$ | **Hyperbola** | Center $(0, 0)$ | Vertices $(\pm 3, 0)$, asymptotes $y = \pm \frac{2}{3}x$ | Difference of squares equaling $+1$ |

---

## 6. Quick Verification

Verify key sample points on each curve:
1. Circle $x^2 + y^2 = 9$: Point $(0, 3) \implies 0^2 + 3^2 = 9$. (Correct)
2. Ellipse $\frac{x^2}{16} + \frac{y^2}{9} = 1$: Point $(4, 0) \implies \frac{16}{16} + 0 = 1$. (Correct)
3. Parabola $y^2 = 8x$: Point $(2, 4) \implies 4^2 = 16 = 8(2)$. (Correct)
4. Hyperbola $\frac{x^2}{9} - \frac{y^2}{4} = 1$: Point $(3, 0) \implies \frac{9}{9} - 0 = 1$. (Correct)

All equations are satisfied by their principal characteristic points.

---

## 7. Common Mistakes to Avoid

1. **Confusing Ellipses and Hyperbolas:**
   Overlooking the minus sign between terms. A plus sign indicates a bounded ellipse; a minus sign indicates an unbounded hyperbola with two branches.
2. **Confusing Major and Minor Semiaxes:**
   Thinking $a$ must always be horizontal. The semimajor axis is always the *larger* of the two denominators. Here $16 > 9$, so the major axis is indeed horizontal.
3. **Misidentifying the Parabola Opening Direction:**
   Assuming $y^2 = 8x$ opens upwards. Because $y$ is squared, symmetry is across the horizontal axis, and $x \ge 0$ forces opening to the right.

---

## 8. How I Would Explain This in Class

> "Recognizing curves from canonical equations is like checking ID cards: if both $x$ and $y$ are squared with the exact same plus sign and weight, you have a circle; if they have different weights, that circle is stretched into an ellipse. If one of the plus signs turns into a minus, the shape breaks open into two hyperbola wings flying toward diagonal asymptotes. And if only one variable is squared while the other is linear, you have a parabola shooting out from the origin."

