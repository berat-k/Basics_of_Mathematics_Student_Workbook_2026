# Problem 02: Maximum Area of a Rectangle

## 1. The Original Problem

A rectangle has perimeter $40$.

1. Write its area as a function of the length of one side.
2. Determine the domain of this function resulting from the geometry of the problem.
3. Find the dimensions that give the maximum area.
4. Justify that the point found actually gives a maximum.

---

## 2. What Are We Trying to Find?

1. A single-variable formula $A(x)$ expressing the rectangle's area solely in terms of one side length $x$.
2. The geometrically valid interval of values for $x$ so that both side lengths are strictly positive.
3. The optimal side lengths $x$ and $y$ that maximize $A(x)$, together with the resulting maximum area.
4. A rigorous mathematical justification proving that the critical point gives a global maximum of $A(x)$ on its domain.

---

## 3. Before Calculating: What Idea Do We Need?

- **Translating geometry into a constraint and an objective function:** A rectangle has two adjacent side lengths $x$ and $y$. Its perimeter is $P = 2x + 2y$ and its area is $A = xy$. Using the fixed perimeter $P = 40$, we eliminate $y$ so that $A$ becomes a function of $x$ alone.
- **Geometric domain:** Every physical side of a non-degenerate rectangle must be strictly positive, so both $x > 0$ and $y > 0$ must hold simultaneously.
- **Fermat's Theorem and optimization tests:** Any interior extremum of a differentiable function $A(x)$ occurs at a critical point where $A'(x) = 0$. To confirm that a critical point is truly a global maximum rather than a minimum or saddle point, we can use:
  - the **first-derivative sign test**, showing $A'(x) > 0$ to the left and $A'(x) < 0$ to the right across the entire domain;
  - the **second-derivative test**, checking $A''(x) < 0$;
  - an **algebraic check**, rewriting the quadratic in vertex form.

---

## 4. Step-by-Step Solution

### Step 1: Write the area as a function of one side length

Let $x$ and $y$ denote the lengths of two adjacent sides of the rectangle.

```text
          x
   +--------------+
   |              |
 y |   Area = xy  | y
   |              |
   +--------------+
          x
```

The perimeter constraint is:

$$
2x + 2y = 40.
$$

Divide both sides by $2$ and solve for $y$:

$$
x + y = 20 \implies y = 20 - x.
$$

Substitute $y = 20 - x$ into the area formula $A = xy$ to obtain the area as a function of $x$:

$$
A(x) = x(20 - x) = 20x - x^2.
$$

### Step 2: Determine the geometric domain

For a genuine, non-degenerate rectangle, both side lengths must be strictly positive:

$$
x > 0 \qquad \text{and} \qquad y = 20 - x > 0.
$$

The second inequality gives $x < 20$. Combining both conditions yields the open interval:

$$
D = (0, 20), \qquad \text{that is, } 0 < x < 20.
$$

Notice that if degenerate rectangles of zero area were allowed, the closed domain would be $[0, 20]$ with $A(0) = A(20) = 0$, which still cannot compete with positive interior values.

### Step 3: Find the dimensions that give the maximum area

Differentiate $A(x) = 20x - x^2$ with respect to $x$:

$$
A'(x) = 20 - 2x.
$$

Set the first derivative equal to zero to locate the critical points:

$$
20 - 2x = 0 \implies 2x = 20 \implies x = 10.
$$

Since $10 \in (0, 20)$, this critical point lies inside the geometric domain. The corresponding adjacent side length is:

$$
y = 20 - x = 20 - 10 = 10.
$$

The area for these dimensions is:

$$
A(10) = 10 \cdot 10 = 100.
$$

Thus, the dimensions giving the maximum area are $10 \times 10$, meaning the rectangle is a **square** of side length $10$.

### Step 4: Justify that $x = 10$ gives a global maximum

We provide two calculus justifications and confirm them with an algebraic proof.

**Justification 1: First-derivative sign analysis, proving a global maximum on $(0, 20)$.**

From $A'(x) = 2(10 - x)$, we examine the sign of $A'(x)$ across the entire domain $(0, 20)$:

| Interval or point | Sign of $A'(x) = 2(10 - x)$ | Behavior of $A(x)$ |
| :--- | :---: | :--- |
| $0 < x < 10$ | $+$ | Strictly increasing |
| $x = 10$ | $0$ | Critical point, $A(10) = 100$ |
| $10 < x < 20$ | $-$ | Strictly decreasing |

Because $A(x)$ strictly increases for all $x \in (0, 10)$ and strictly decreases for all $x \in (10, 20)$, the value $A(10) = 100$ is strictly greater than $A(x)$ for every other $x \in (0, 20)$. Therefore, $x = 10$ gives the unique **global maximum** on the entire domain.

**Justification 2: Second-derivative test and concavity.**

Differentiating $A'(x) = 20 - 2x$ gives:

$$
A''(x) = -2 < 0 \qquad \text{for all } x \in (0, 20).
$$

Because $A''(10) = -2 < 0$, the critical point $x = 10$ is a strict local maximum. Moreover, because $A''(x) < 0$ everywhere on $(0, 20)$, the function $A(x)$ is strictly concave on its entire domain, so its unique critical point is automatically the unique global maximum.

**Geometric sketch of $A(x) = 20x - x^2$:**

```text
A(x)
100 |            * (10, 100)  <-- global maximum
    |         *     *
 75 |       *         *
    |     *             *
 50 |    *               *
    |  *                   *
  0 +-o---------------------o--> x
      0         10         20
```

---

## 5. Final Answer & Conclusion

1. **Area function:** $A(x) = x(20 - x) = 20x - x^2$.
2. **Geometric domain:** $x \in (0, 20)$, meaning $0 < x < 20$.
3. **Optimal dimensions:** $x = 10$ and $y = 10$, forming a square of side $10$, with maximum area $A_{\max} = 100$.
4. **Justification:** $A'(x) = 20 - 2x$ changes sign from positive on $(0, 10)$ to negative on $(10, 20)$, and $A''(x) = -2 < 0$ everywhere, proving that $x = 10$ gives the unique global maximum on $(0, 20)$.

---

## 6. Quick Verification

1. **Completing the square without calculus:**

$$
A(x) = 20x - x^2 = 100 - (x^2 - 20x + 100) = 100 - (x - 10)^2.
$$

Since $(x - 10)^2 \ge 0$ for all real $x$, with equality if and only if $x = 10$, it follows immediately that $A(x) \le 100$ for all $x$, and the maximum $100$ is uniquely attained at $x = 10$.

2. **Numerical comparison with nearby rectangles of perimeter $40$:**
   - $x = 8$, $y = 12$: perimeter $2(8 + 12) = 40$, area $8 \times 12 = 96 < 100$.
   - $x = 9$, $y = 11$: perimeter $2(9 + 11) = 40$, area $9 \times 11 = 99 < 100$.
   - $x = 10$, $y = 10$: perimeter $2(10 + 10) = 40$, area $10 \times 10 = 100$.
   - $x = 11$, $y = 9$: perimeter $2(11 + 9) = 40$, area $11 \times 9 = 99 < 100$.
   - $x = 15$, $y = 5$: perimeter $2(15 + 5) = 40$, area $15 \times 5 = 75 < 100$.

---

## 7. Common Mistakes to Avoid

- **Writing $x + y = 40$ instead of $2x + 2y = 40$:** A rectangle has four sides, two of length $x$ and two of length $y$. Forgetting the factor of $2$ yields the wrong semiperimeter $40$ instead of $20$.
- **Forgetting to restrict the domain to $x < 20$:** Writing $x > 0$ alone overlooks that $y = 20 - x$ becomes zero or negative once $x \ge 20$.
- **Stopping after solving $A'(x) = 0$ without justification:** Finding a critical point only identifies a *candidate* for an extremum; you must still prove using $A'$, $A''$, or concavity that it is a maximum rather than a minimum.
- **Reporting only $x = 10$ instead of both dimensions:** The problem asks for the *dimensions* of the rectangle, so you should explicitly compute $y = 20 - 10 = 10$ and identify the shape as a $10 \times 10$ square.

---

## 8. How I Would Explain This in Class

> "Whenever you have a fixed amount of fencing to enclose a rectangular yard, stretching the rectangle long and skinny wastes fence on the two long sides while squeezing the interior almost flat. Calculus confirms our symmetry intuition: among all rectangles with perimeter 40, the most balanced shape — the 10 by 10 square — encloses the largest possible area of 100. And notice the reusable recipe we just practiced: write the constraint, eliminate one variable, state the physical domain, differentiate to find the critical point, and finally prove it really is a maximum."
