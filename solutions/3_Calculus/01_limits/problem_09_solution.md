# Problem 09: One-Sided Limits and an Asymptote

## 1. The Original Problem

Analyze the left-hand and right-hand limits of

$$
f(x)=\frac1{x-2}
$$

as $x\to2$. Does the two-sided limit exist? Interpret the result on a sketch of the graph and identify the vertical asymptote.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the **left-hand limit**: $\lim_{x \to 2^-} \frac{1}{x - 2}$.
2. Compute the **right-hand limit**: $\lim_{x \to 2^+} \frac{1}{x - 2}$.
3. Determine whether the **two-sided limit** $\lim_{x \to 2} \frac{1}{x - 2}$ exists by comparing the one-sided limits.
4. Provide a qualitative coordinate sketch illustrating the contrasting behaviors of both branches.
5. Identify the equation and geometric significance of the **vertical asymptote**.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Form $[1/0]$ and Signed Zero:**
  When evaluating $\lim_{x \to c} \frac{N(x)}{D(x)}$ where $N(c) \ne 0$ and $D(c) = 0$, the magnitude of the fraction grows without bound toward infinity. However, whether it tends to $+\infty$ or $-\infty$ depends entirely on the sign of the denominator as $x$ approaches $c$:
  - If $D(x) \to 0$ through positive values, $0^+$, then $\frac{\text{positive}}{0^+} = +\infty$.
  - If $D(x) \to 0$ through negative values, $0^-$, then $\frac{\text{positive}}{0^-} = -\infty$.
- **Left-Hand vs. Right-Hand Limits:**
  - $x \to 2^-$ means $x$ approaches $2$ strictly from the left, so $x < 2$. Therefore, $x - 2 < 0$.
  - $x \to 2^+$ means $x$ approaches $2$ strictly from the right, so $x > 2$. Therefore, $x - 2 > 0$.
- **Condition for Existence of a Two-Sided Limit:**
  A two-sided limit exists if and only if both one-sided limits exist and agree:

$$
\lim_{x \to c^-} f(x) = \lim_{x \to c^+} f(x) = L
$$

  If the one-sided limits differ, especially if one is $-\infty$ and the other is $+\infty$, the two-sided limit **does not exist**.
- **Definition of a Vertical Asymptote:**
  The line $x = c$ is a vertical asymptote of the curve $y = f(x)$ if at least one of the one-sided limits tends to infinity:

$$
\lim_{x \to c^-} f(x) = \pm\infty \quad \text{or} \quad \lim_{x \to c^+} f(x) = \pm\infty
$$

---

## 4. Step-by-Step Solution

### Step 1: Analyze the Left-Hand Limit as $x \to 2^-$

We consider values of $x$ approaching $2$ strictly from the left, with $x < 2$:

$$
\lim_{x \to 2^-} \frac{1}{x - 2}
$$

Let $x = 2 - h$, where $h > 0$ and $h \to 0$:
- The denominator is $x - 2 = (2 - h) - 2 = -h < 0$.
- As $h \to 0^+$, the denominator approaches $0$ through strictly negative numbers, denoted $0^-$: $x - 2 \to 0^-$.
- The numerator is fixed at $+1 > 0$.
- Dividing a positive constant by an infinitesimally small negative quantity yields an arbitrarily large negative number:

$$
\lim_{x \to 2^-} \frac{1}{x - 2} = \left[\frac{1}{0^-}\right] = -\infty
$$

---

### Step 2: Analyze the Right-Hand Limit as $x \to 2^+$

We consider values of $x$ approaching $2$ strictly from the right, with $x > 2$:

$$
\lim_{x \to 2^+} \frac{1}{x - 2}
$$

Let $x = 2 + h$, where $h > 0$ and $h \to 0$:
- The denominator is $x - 2 = (2 + h) - 2 = +h > 0$.
- As $h \to 0^+$, the denominator approaches $0$ through strictly positive numbers, denoted $0^+$: $x - 2 \to 0^+$.
- The numerator is fixed at $+1 > 0$.
- Dividing a positive constant by an infinitesimally small positive quantity yields an arbitrarily large positive number:

$$
\lim_{x \to 2^+} \frac{1}{x - 2} = \left[\frac{1}{0^+}\right] = +\infty
$$

---

### Step 3: Determine the Existence of the Two-Sided Limit

We compare the two one-sided limits:

$$
\lim_{x \to 2^-} f(x) = -\infty \qquad \text{and} \qquad \lim_{x \to 2^+} f(x) = +\infty
$$

Because the left-hand and right-hand limits do not match:

$$
\lim_{x \to 2^-} f(x) \ne \lim_{x \to 2^+} f(x)
$$

**The two-sided limit $\lim_{x \to 2} \frac{1}{x - 2}$ does NOT exist (DNE).**

---

### Step 4: Vertical Asymptote and Geometric Interpretation

Because the left and right limits explode to opposite infinities:

$$
\lim_{x \to 2^-} f(x) = -\infty \quad \text{and} \quad \lim_{x \to 2^+} f(x) = +\infty
$$

- The line $x = 2$ is a **vertical asymptote** for the function $f(x)$.
- **Behavior near the asymptote:**
  - As an observer moves toward $x = 2$ from the left, the curve plunges downward without bound, running parallel to the vertical line $x = 2$ toward $-\infty$.
  - As an observer moves toward $x = 2$ from the right, the curve rockets upward without bound, running parallel to $x = 2$ toward $+\infty$.

#### Qualitative ASCII Sketch of $y = \frac{1}{x - 2}$:
```
                 y
                 ^
                 |           |   (shoots to +infinity)
                 |           |  )
                 |           | (
                 |           |  \
                 |           |   .
                 |           |    \
        ---------+-----------+-----\------> x
                 |           |  x=2 \
                 |          /|
                 |         . |
                 |        /  |
                 |       /   |
                 |      (    |   (plunges to -infinity)
                 |     |     |
```
- The vertical dashed line at $x = 2$ acts as an impassable barrier.
- For $x > 2$, $y > 0$ (upper-right branch).
- For $x < 2$, $y < 0$ (lower-left branch).
- The horizontal line $y = 0$ is the horizontal asymptote as $x \to \pm\infty$.

---

## 5. Final Answer & Conclusion

1. **Left-Hand Limit:** $\lim_{x\to2^-}\frac{1}{x-2} = -\infty$
2. **Right-Hand Limit:** $\lim_{x\to2^+}\frac{1}{x-2} = +\infty$
3. **Two-Sided Limit:**
   The two-sided limit **does not exist** because the one-sided limits are unequal: $-\infty \ne +\infty$.
4. **Vertical Asymptote:**
   The line **$x = 2$** is a vertical asymptote of the graph of $f(x)$.

---

## 6. Quick Verification

1. **Concrete Numerical Values:**
   - Approaching $x = 2$ from the left, with $x < 2$:
     - $x = 1.9 \implies f(1.9) = \frac{1}{1.9 - 2} = \frac{1}{-0.1} = -10$
     - $x = 1.99 \implies f(1.99) = \frac{1}{-0.01} = -100$
     - $x = 1.999 \implies f(1.999) = \frac{1}{-0.001} = -1{,}000$
     - $x = 1.999999 \implies f(x) = -1{,}000{,}000 \to -\infty$
   - Approaching $x = 2$ from the right, with $x > 2$:
     - $x = 2.1 \implies f(2.1) = \frac{1}{2.1 - 2} = \frac{1}{0.1} = +10$
     - $x = 2.01 \implies f(2.01) = \frac{1}{0.01} = +100$
     - $x = 2.001 \implies f(2.001) = \frac{1}{0.001} = +1{,}000$
     - $x = 2.000001 \implies f(x) = +1{,}000{,}000 \to +\infty$
   The table confirms opposite infinite directions.

2. **Translation Verification:**
   The function $f(x) = \frac{1}{x - 2}$ is simply the standard hyperbola $y = \frac{1}{x}$ shifted $2$ units to the right. The standard hyperbola has vertical asymptote $x = 0$ with left limit $-\infty$ and right limit $+\infty$. Shifting by $+2$ shifts the asymptote to $x = 2$ and preserves the exact one-sided limits.

---

## 7. Common Mistakes to Avoid

1. **Writing $\lim_{x \to 2} \frac{1}{x - 2} = \infty$:**
   Saying the limit is "infinity" without specifying a sign, or implying both sides agree. Since one side goes to $-\infty$ and the other to $+\infty$, there is no unified limit even in the extended real numbers.
2. **Ignoring the Direction of Approach:**
   Forgetting that $x \to 2^-$ means $x < 2$, so $x - 2$ is negative! Writing $\frac{1}{0} = +\infty$ blindly ignores the crucial sign of the denominator.
3. **Confusing Holes with Vertical Asymptotes:**
   In Exercise 7, $\frac{x^2-4x+3}{x-3}$ had a $0/0$ form, resulting in a removable hole at $y = 2$. Here, $\frac{1}{x-2}$ has a non-zero numerator, $1/0$, which always generates an infinite discontinuity (vertical asymptote).

---

## 8. How I Would Explain This in Class

> "Imagine you are driving toward a deep canyon whose edge is at $x = 2$.
> If you approach from the west, with $x < 2$, you drive off a cliff straight down into the center of the Earth: $-\infty$!
> If you approach from the east, with $x > 2$, the road shoots straight up into the stratosphere: $+\infty$!
> If someone asks you: 'What height does the road reach at $x = 2$?', what do you say? You can't give a single answer! One side is at negative infinity and the other is at positive infinity. They don't agree at all, so the two-sided limit simply does not exist.
> That impassable boundary line at $x = 2$ where the function explodes in opposite directions is what we call a **vertical asymptote**."

