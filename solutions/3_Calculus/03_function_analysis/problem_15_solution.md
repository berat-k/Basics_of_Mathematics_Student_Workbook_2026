# Problem 15: Find the Error in the Monotonicity Analysis

## 1. The Original Problem

For the function

$$
f(x) = x^3 - 3x
$$

the derivative was correctly computed as

$$
f'(x) = 3(x - 1)(x + 1).
$$

However, a student wrote the following conclusion:

> The derivative is positive between its zeros and negative outside them. Therefore, the function is decreasing on $(-\infty, -1) \cup (1, \infty)$, increasing on $(-1, 1)$, has a local minimum at $x = -1$, and a local maximum at $x = 1$.

1. Without differentiating again, explain why merely identifying the zeros of the derivative does not justify the stated sign chart, and find the error in the student's reasoning.
2. Construct the correct sign chart for $f'(x)$.
3. Give the correct intervals of monotonicity and the character of the extrema.
4. In each of the three intervals, choose one simple test point and show that the sign of the derivative confirms your classification.

---

## 2. What Are We Trying to Find?

1. An explanation — without differentiating again — of why finding the zeros of $f'(x)$ alone does not determine its sign chart, together with an exact diagnosis of the student's mistake.
2. The complete, correct sign chart for $f'(x) = 3(x - 1)(x + 1)$.
3. The correct intervals of monotonicity and the correct classification and values of the local extrema of $f(x) = x^3 - 3x$.
4. One concrete test point in each of the three intervals $(-\infty, -1)$, $(-1, 1)$, and $(1, \infty)$ confirming the sign of $f'(x)$ and the resulting classification.

---

## 3. Before Calculating: What Idea Do We Need?

- **Zeros partition the domain, they do not fix the signs:** For a continuous function such as $f'(x)$, its real zeros divide $\mathbb{R}$ into open intervals on each of which $f'(x)$ keeps a constant sign by the Intermediate Value Theorem. However, the zeros alone tell you only *where* the sign can change, not *which* sign occurs on each interval.
- **Sign of a factored quadratic:** A quadratic $A(x - p)(x - q)$ with $p < q$ opens upward if $A > 0$, making it **positive outside** $(p, q)$ and **negative inside** $(p, q)$. It is positive inside and negative outside only when $A < 0$.
- **First Derivative Test:**
  - $f'$ changing from $+$ to $-$ gives a **local maximum**.
  - $f'$ changing from $-$ to $+$ gives a **local minimum**.
- **Precision with unions of monotonicity intervals:** Even when $f'$ has the same sign on two disjoint intervals such as $(-\infty, -1)$ and $(1, \infty)$, monotonicity must be stated on each interval separately rather than on their union.

---

## 4. Step-by-Step Solution

### Step 1: Answer Part 1 — Why Zeros Are Not Enough and What the Student Got Wrong

**Why identifying the zeros does not justify the sign chart:**
Knowing that $f'(x) = 0$ at $x = -1$ and $x = 1$ splits the real line into three open intervals:

$$
(-\infty, -1), \qquad (-1, 1), \qquad (1, \infty).
$$

Because $f'(x)$ is continuous and has no other zeros, its sign is constant on each of these three intervals. However, knowing the boundary points $-1$ and $1$ tells you nothing by itself about whether the sign pattern is $(+, -, +)$ or $(-, +, -)$. For example, both $3(x - 1)(x + 1)$ and $-3(x - 1)(x + 1)$ have the exact same zeros $-1$ and $1$, yet opposite signs on every single interval! To justify a sign chart, one must determine the actual sign using either the leading coefficient (the orientation of the parabola), a factor-by-factor sign product, or explicit test points.

**The exact error in the student's reasoning:**
The student asserted that $f'(x) = 3(x - 1)(x + 1)$ is "positive between its zeros and negative outside them." This is the exact opposite of the truth:

- Expanding gives $f'(x) = 3x^2 - 3$, a quadratic whose leading coefficient is $+3 > 0$.
- Because the leading coefficient is positive, the graph of $y = f'(x)$ is an **upward-opening parabola** with $x$-intercepts at $-1$ and $1$. Therefore, $f'(x)$ dips **below** the $x$-axis (negative) between $-1$ and $1$, and rises **above** the $x$-axis (positive) outside $[-1, 1]$.
- The student inverted every sign of $f'(x)$, treating it as a downward-opening parabola. That single sign reversal cascaded through the entire conclusion: it turned increasing intervals into decreasing ones, turned the decreasing interval into an increasing one, and swapped the local maximum at $x = -1$ with the local minimum at $x = 1$.

*(Secondary notational flaw worth noting: the student also claimed the function is decreasing on the union $(-\infty, -1) \cup (1, \infty)$. Monotonicity on two disjoint intervals should always be stated separately, because a function that is increasing — or decreasing — on two separate intervals need not preserve order across the gap between them.)*

### Step 2: Answer Part 2 — Construct the Correct Sign Chart for $f'(x)$

We analyze each factor of $f'(x) = 3(x + 1)(x - 1)$ across the intervals determined by $-1$ and $1$:

| Interval / Point | Sign of $3$ | Sign of $x + 1$ | Sign of $x - 1$ | Sign of $f'(x)$ | Behavior of $f(x)$ |
| :--- | :---: | :---: | :---: | :---: | :--- |
| $(-\infty, -1)$ | $+$ | $-$ | $-$ | $+$ | Strictly increasing |
| $x = -1$ | $+$ | $0$ | $-$ | $0$ | Strict local maximum |
| $(-1, 1)$ | $+$ | $+$ | $-$ | $-$ | Strictly decreasing |
| $x = 1$ | $+$ | $+$ | $0$ | $0$ | Strict local minimum |
| $(1, \infty)$ | $+$ | $+$ | $+$ | $+$ | Strictly increasing |

Summary sign line for $f'(x)$:

```text
          f'(x):     + + + + + + | - - - - - - | + + + + + +
          -----------------------o-------------o-----------------> x
                                -1             1
          f(x):     increasing  max  decreasing min  increasing
```

### Step 3: Answer Part 3 — Correct Monotonicity Intervals and Extrema

Reading directly from the correct sign chart:

- **Intervals of monotonicity:**
  - $f$ is **strictly increasing** on $(-\infty, -1]$ and **strictly increasing** on $[1, \infty)$ (stated separately, not as a single union).
  - $f$ is **strictly decreasing** on $[-1, 1]$.
- **Character and values of the extrema:**
  - At $x = -1$: $f'(x)$ changes sign from $+$ to $-$, so $f$ has a **strict local maximum** at $x = -1$, with value

$$
f(-1) = (-1)^3 - 3(-1) = -1 + 3 = 2.
$$

  - At $x = 1$: $f'(x)$ changes sign from $-$ to $+$, so $f$ has a **strict local minimum** at $x = 1$, with value

$$
f(1) = 1^3 - 3(1) = 1 - 3 = -2.
$$

Neither extremum is global, because $f(x) \to -\infty$ as $x \to -\infty$ and $f(x) \to +\infty$ as $x \to +\infty$.

### Step 4: Answer Part 4 — Confirmation Using Simple Test Points

Choose one simple integer inside each of the three open intervals and evaluate $f'(x) = 3(x - 1)(x + 1)$:

1. **On $(-\infty, -1)$, choose $x = -2$:**

$$
f'(-2) = 3(-2 - 1)(-2 + 1) = 3(-3)(-1) = +9 > 0.
$$

Because $f'(-2) > 0$, $f'$ is positive on $(-\infty, -1)$, confirming that $f$ is strictly increasing there.

2. **On $(-1, 1)$, choose $x = 0$:**

$$
f'(0) = 3(0 - 1)(0 + 1) = 3(-1)(1) = -3 < 0.
$$

Because $f'(0) < 0$, $f'$ is negative on $(-1, 1)$, confirming that $f$ is strictly decreasing there.

3. **On $(1, \infty)$, choose $x = 2$:**

$$
f'(2) = 3(2 - 1)(2 + 1) = 3(1)(3) = +9 > 0.
$$

Because $f'(2) > 0$, $f'$ is positive on $(1, \infty)$, confirming that $f$ is strictly increasing there.

Together, the three test values yield the sign pattern $(+, -, +)$, directly refuting the student's $(-, +, -)$ claim and confirming that $x = -1$ is a local maximum where $f'$ changes from $+$ to $-$, while $x = 1$ is a local minimum where $f'$ changes from $-$ to $+$.

---

## 5. Final Answer & Conclusion

1. **Diagnosis of the error:** Finding the zeros $-1$ and $1$ partitions $\mathbb{R}$ into constant-sign intervals but does not determine the signs themselves. The student reversed the sign of the upward-opening quadratic $f'(x) = 3(x - 1)(x + 1)$, which has leading coefficient $+3 > 0$, mistakenly claiming it is positive inside $(-1, 1)$ and negative outside, which inverted all monotonicity intervals and swapped the local maximum and minimum.
2. **Correct sign chart:** $f'(x) > 0$ on $(-\infty, -1)$, $f'(-1) = 0$, $f'(x) < 0$ on $(-1, 1)$, $f'(1) = 0$, and $f'(x) > 0$ on $(1, \infty)$.
3. **Correct monotonicity and extrema:** Strictly increasing on $(-\infty, -1]$ and on $[1, \infty)$; strictly decreasing on $[-1, 1]$; strict local maximum at $(-1, 2)$ and strict local minimum at $(1, -2)$.
4. **Test-point confirmation:** $f'(-2) = 9 > 0$, $f'(0) = -3 < 0$, and $f'(2) = 9 > 0$, confirming the $(+, -, +)$ sign pattern and the resulting classification.

---

## 6. Quick Verification

1. **Direct function-value sanity check:** Evaluate $f(x) = x^3 - 3x$ at simple points across the domain:
   - $f(-2) = -8 + 6 = -2$,
   - $f(-1) = -1 + 3 = 2$,
   - $f(0) = 0$,
   - $f(1) = 1 - 3 = -2$,
   - $f(2) = 8 - 6 = 2$.
   Watching the heights move $-2 \to 2 \to 0 \to -2 \to 2$ makes it immediately obvious that $f$ rises to a peak of $2$ at $x = -1$, falls to a valley of $-2$ at $x = 1$, and rises again afterward — completely contradicting the student's claim.

2. **Why the union notation fails here:** Notice that $-1.5 \in (-\infty, -1)$ and $1.5 \in (1, \infty)$ satisfy $-1.5 < 1.5$, yet

$$
f(-1.5) = -3.375 + 4.5 = 1.125 > -1.125 = 3.375 - 4.5 = f(1.5).
$$

This confirms that $f$ is **not** increasing on the union $(-\infty, -1) \cup (1, \infty)$ as a single set — only on each interval separately.

---

## 7. Common Mistakes to Avoid

- **Guessing the sign chart from the zeros alone:** Never fill in $+$ and $-$ signs from memory or by guessing. Always check either the leading coefficient of the factored derivative or plug in one quick test point per interval (especially $x = 0$, which takes two seconds!).
- **Confusing an upward-opening derivative parabola with a downward-opening one:** For $A(x - p)(x - q)$ with $p < q$, positive $A$ means $+$ outside and $-$ inside; negative $A$ means $-$ outside and $+$ inside.
- **Using union notation $\cup$ for intervals of monotonicity:** Claiming that a function is increasing on $(-\infty, -1) \cup (1, \infty)$ is a classic formal error because comparing a point in the left piece with a point in the right piece can violate the inequality. Always state the intervals separately: increasing on $(-\infty, -1]$ and increasing on $[1, \infty)$.
- **Skipping a quick reality check on $f(x)$ itself:** Simply computing $f(-1) = 2$ and $f(1) = -2$ would have instantly alerted the student that $f$ dropped from $2$ down to $-2$ across $(-1, 1)$, so $f$ could not possibly be increasing on $(-1, 1)$!

---

## 8. How I Would Explain This in Class

> "Finding the zeros of $f'(x)$ is like putting road signs at $x = -1$ and $x = 1$ that say 'Possible Direction Change Ahead.' Those signs tell you *where* a U-turn might happen, not whether you are walking uphill or downhill! The student looked at the road signs, guessed the wrong direction, and ended up calling the mountaintop a valley and the valley a mountaintop. One two-second check at $x = 0$ — plugging $0$ into $f'(0) = 3(-1)(1) = -3 < 0$ — instantly tells you that you are walking downhill through the middle, which locks in the whole map with zero guesswork."
