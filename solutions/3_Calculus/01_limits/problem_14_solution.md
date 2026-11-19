# Problem 14: A 0/0 Limit with Trigonometry

## 1. The Original Problem

Compute

$$
\lim_{x\to0}\frac{1-\cos x}{x^2}.
$$

Justify the result without using l'Hôpital's rule, using a trigonometric identity and the fundamental limit.

---

## 2. What Are We Trying to Find?

We need to:
1. Evaluate the classical limit $L = \lim_{x \to 0} \frac{1 - \cos x}{x^2}$.
2. Identify the indeterminate form $\left[\frac{0}{0}\right]$ resulting from $1 - \cos 0 = 1 - 1 = 0$ and $0^2 = 0$.
3. Provide a complete, rigorous proof **strictly without using l'Hôpital's rule**, following the explicit constraint of the problem.
4. Demonstrate two elegant trigonometric approaches:
   - **Method 1 (Trigonometric Conjugate):** Multiplying and dividing by $(1 + \cos x)$ and using the Pythagorean identity $\sin^2 x + \cos^2 x = 1$.
   - **Method 2 (Half-Angle Identity):** Using $1 - \cos x = 2\sin^2\left(\frac{x}{2}\right)$.
5. Connect both methods directly to the fundamental trigonometric limit $\lim_{u \to 0} \frac{\sin u}{u} = 1$.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Pythagorean Conjugate Identity:**
  Just as with square roots in Exercises 3 and 8, the difference of squares eliminates $(1 - \cos x)$ by pairing it with its trigonometric conjugate $(1 + \cos x)$: $(1 - \cos x)(1 + \cos x) = 1 - \cos^2 x = \sin^2 x$. This transforms the cosine difference into a sine squared, which pairs naturally with the $x^2$ in the denominator: $\frac{\sin^2 x}{x^2} = \left(\frac{\sin x}{x}\right)^2 \xrightarrow{x \to 0} 1^2 = 1$.
- **The Half-Angle Identity:**
  From the double-angle formula $\cos(2\theta) = 1 - 2\sin^2\theta$, setting $\theta = \frac{x}{2}$ gives $1 - \cos x = 2\sin^2(x/2)$. Dividing by $x^2$ allows us to group the sine and its argument: $\frac{2\sin^2(x/2)}{x^2} = 2 \cdot \frac{\sin^2(x/2)}{4 \cdot (x/2)^2} = \frac{2}{4} \left(\frac{\sin(x/2)}{x/2}\right)^2 = \frac{1}{2} \cdot 1^2 = \frac{1}{2}$.
- **Why L'Hôpital's Rule Is Avoided Here:**
  In circular logic, proving $\frac{d}{dx}(\cos x) = -\sin x$ (which l'Hôpital's rule would require) depends fundamentally on the limit $\lim_{x \to 0} \frac{1 - \cos x}{x} = 0$. Using l'Hôpital's rule to evaluate $\frac{1 - \cos x}{x^2}$ would be circular if one hasn't first established the derivative of cosine geometrically! The purely trigonometric algebraic proof is self-contained.

---

## 4. Step-by-Step Solution

### Step 1: Identify the Indeterminate Form

Consider the function:

$$
f(x) = \frac{1 - \cos x}{x^2}
$$

As $x \to 0$:
- Numerator: $1 - \cos 0 = 1 - 1 = 0$
- Denominator: $0^2 = 0$

This yields the indeterminate form:

$$
\left[\frac{0}{0}\right]
$$

Direct substitution gives no information. We must transform the expression using trigonometry.

---

### Step 2: Method 1 — The Trigonometric Conjugate

Multiply both the numerator and denominator by the conjugate $(1 + \cos x)$:

$$
\frac{1 - \cos x}{x^2} = \frac{(1 - \cos x)(1 + \cos x)}{x^2 (1 + \cos x)}
$$

Expand the numerator as a difference of squares:

$$
(1 - \cos x)(1 + \cos x) = 1 - \cos^2 x
$$

Apply the fundamental Pythagorean trigonometric identity $\sin^2 x + \cos^2 x = 1 \implies 1 - \cos^2 x = \sin^2 x$:

$$
\frac{1 - \cos x}{x^2} = \frac{\sin^2 x}{x^2 (1 + \cos x)}
$$

Group the factors to isolate the fundamental trigonometric limit:

$$
\frac{1 - \cos x}{x^2} = \left(\frac{\sin x}{x}\right)^2 \cdot \frac{1}{1 + \cos x}
$$

Now evaluate the limit of each factor as $x \to 0$:
1. For the first factor, by the fundamental trigonometric limit: $\lim_{x \to 0} \frac{\sin x}{x} = 1 \implies \lim_{x \to 0} \left(\frac{\sin x}{x}\right)^2 = 1^2 = 1$.
2. For the second factor, since $\cos x$ is continuous and $\cos 0 = 1$: $\lim_{x \to 0} \frac{1}{1 + \cos x} = \frac{1}{1 + \cos 0} = \frac{1}{1 + 1} = \frac{1}{2}$.

By the product rule for limits:

$$
\lim_{x \to 0} \frac{1 - \cos x}{x^2} = 1 \cdot \frac{1}{2} = \frac{1}{2}
$$

---

### Step 3: Method 2 — The Half-Angle Identity

Recall the double-angle identity for cosine:

$$
\cos(2\theta) = 1 - 2\sin^2\theta
$$

Rearranging for $1 - \cos(2\theta)$:

$$
1 - \cos(2\theta) = 2\sin^2\theta
$$

Setting $\theta = \frac{x}{2}$:

$$
1 - \cos x = 2\sin^2\left(\frac{x}{2}\right)
$$

Substitute this directly into the given limit:

$$
\frac{1 - \cos x}{x^2} = \frac{2\sin^2(x/2)}{x^2}
$$

To create the fundamental limit with argument $u = \frac{x}{2}$, we need $\left(\frac{x}{2}\right)^2 = \frac{x^2}{4}$ in the denominator.
Multiply the denominator by $\frac{4}{4}$:

$$
\frac{2\sin^2(x/2)}{x^2} = 2 \cdot \frac{\sin^2(x/2)}{4 \cdot \frac{x^2}{4}} = \frac{2}{4} \cdot \left(\frac{\sin(x/2)}{x/2}\right)^2 = \frac{1}{2} \cdot \left(\frac{\sin(x/2)}{x/2}\right)^2
$$

Let $u = \frac{x}{2}$. As $x \to 0$, $u \to 0$:

$$
\lim_{x \to 0} \frac{\sin(x/2)}{x/2} = \lim_{u \to 0} \frac{\sin u}{u} = 1
$$

Therefore:

$$
\lim_{x \to 0} \frac{1 - \cos x}{x^2} = \frac{1}{2} \cdot (1)^2 = \frac{1}{2}
$$

Both methods arrive at the identical value $\frac{1}{2}$ through purely trigonometric identities, without any appeal to derivatives or l'Hôpital's rule.

---

## 5. Final Answer & Conclusion

The limit is:

$$
\lim_{x\to0}\frac{1-\cos x}{x^2} = \frac{1}{2}
$$

### Summary of Key Principles:
- Direct evaluation produced $\left[\frac{0}{0}\right]$.
- The conjugate identity $(1 - \cos x)(1 + \cos x) = \sin^2 x$ converts the cosine difference into $\sin^2 x$.
- Factoring gives $\left(\frac{\sin x}{x}\right)^2 \cdot \frac{1}{1 + \cos x} \to 1^2 \cdot \frac{1}{2} = \frac{1}{2}$.
- Alternatively, the half-angle identity $1 - \cos x = 2\sin^2(x/2)$ yields $\frac{1}{2}\left(\frac{\sin(x/2)}{x/2}\right)^2 \to \frac{1}{2}$.
- This fundamental result establishes the second-order Taylor approximation: $\cos x \approx 1 - \frac{1}{2}x^2$ for $x \approx 0$.

---

## 6. Quick Verification

1. **Numerical Table for Small $x$:**
   - At $x = 0.1$ rad: $\cos(0.1) \approx 0.995004165 \implies \frac{1 - 0.995004165}{0.01} = \frac{0.004995835}{0.01} = 0.49958$.
   - At $x = 0.01$ rad: $\cos(0.01) \approx 0.9999500004 \implies \frac{1 - 0.9999500004}{0.0001} = 0.499996 \approx 0.5$.
   - At $x = 0.001$ rad: $\frac{1 - \cos(0.001)}{(0.001)^2} = 0.49999996 \to \frac{1}{2}$.
   The numerical values converge steadily to $0.5$.

2. **Taylor Series Expansion Verification:**
   The Maclaurin series for $\cos x$ is $\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \dots = 1 - \frac{x^2}{2} + \mathcal{O}(x^4)$.
   Subtracting from $1$ gives $1 - \cos x = \frac{x^2}{2} - \frac{x^4}{24} + \dots$.
   Dividing by $x^2$ gives $\frac{1 - \cos x}{x^2} = \frac{1}{2} - \frac{x^2}{24} + \dots \xrightarrow{x \to 0} \frac{1}{2}$.
   Matches our trigonometric proof perfectly.

---

## 7. Common Mistakes to Avoid

1. **Using L'Hôpital's Rule When Explicitly Forbidden:**
   The problem prompt states: *"Justify the result without using l'Hôpital's rule."* Applying l'Hôpital's rule disregards the core pedagogical objective of the exercise.
2. **Missing the Square on the Denominator — $x$ vs. $x^2$:**
   - $\lim_{x \to 0} \frac{1 - \cos x}{x} = 0$ (first-order difference).
   - $\lim_{x \to 0} \frac{1 - \cos x}{x^2} = \frac{1}{2}$ (second-order difference).
   Confusing these two limits is a frequent exam blunder.
3. **Misapplying the Half-Angle Formula:**
   Forgetting the factor of $2$: writing $1 - \cos x = \sin^2(x/2)$ instead of $2\sin^2(x/2)$, or failing to account for $(x/2)^2 = x^2/4$ in the denominator.

---

## 8. How I Would Explain This in Class

> "If you look at the graph of $y = \cos x$ near $x = 0$, it has a flat hilltop at height 1. Because the top of the hill is flat, the curve drops very slowly at first—much slower than a straight line.
> In fact, it drops like an upside-down parabola: $y \approx 1 - \frac{1}{2}x^2$.
> Rearranging that picture gives $1 - \cos x \approx \frac{1}{2}x^2$, which immediately tells us that $\frac{1 - \cos x}{x^2}$ should be $\frac{1}{2}$.
> But how do we prove it without calculus or derivatives?
> We use trigonometry's secret weapon: $(1 - \cos x)(1 + \cos x) = \sin^2 x$.
> That turns the flat cosine hill into two bouncing sines: $\left(\frac{\sin x}{x}\right) \times \left(\frac{\sin x}{x}\right)$.
> Each of those sines pairs with an $x$ to become 1. And the leftover denominator is $1 + \cos 0 = 2$.
> Two 1's on top and a 2 on the bottom gives exactly $1/2$!"
