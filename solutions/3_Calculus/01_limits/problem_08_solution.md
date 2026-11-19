# Problem 08: A Square Root in a Function Limit

## 1. The Original Problem

Compute

$$
\lim_{x\to4}\frac{\sqrt{x}-2}{x-4}
$$

by rationalizing the numerator. Compare the idea with Exercise 3 involving a sequence.

---

## 2. What Are We Trying to Find?

We need to:
1. Evaluate the limit of the function $f(x) = \frac{\sqrt{x} - 2}{x - 4}$ as $x \to 4$.
2. Identify the indeterminate form $\left[\frac{0}{0}\right]$ upon direct substitution.
3. Apply the technique of **rationalizing the numerator** by multiplying and dividing by the conjugate expression $(\sqrt{x} + 2)$.
4. Cancel the common vanishing factor $(x - 4)$ for $x \ne 4$ to evaluate the limit.
5. Compare this method conceptually with Exercise 3, where $\lim_{n \to \infty} (\sqrt{n^2 + 5n} - n)$ was evaluated, identifying how the algebraic conjugate identity is transferred between sequences at infinity and functions at a finite point.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Indeterminate Form $\left[\frac{0}{0}\right]$ with Square Roots:**
  At $x = 4$, $\sqrt{4} - 2 = 0$ and $4 - 4 = 0$. Because the zero in the numerator is locked inside a square root, we cannot simply factor polynomials by inspection.
- **Rationalizing the Numerator via Conjugates:**
  The identity $(A - B)(A + B) = A^2 - B^2$ converts a difference of square roots into a simple polynomial: $(\sqrt{x} - 2)(\sqrt{x} + 2) = (\sqrt{x})^2 - 2^2 = x - 4$.
  This generates the exact factor $(x - 4)$ that was causing the denominator to vanish!
- **Comparison with Exercise 3:**
  - In Exercise 3, we had an $[\infty - \infty]$ sequence limit at infinity: $\sqrt{n^2+5n} - n$. Multiplying by the conjugate converted a catastrophic cancellation of infinite quantities into an addition in the denominator.
  - In Exercise 8, we have a $\left[\frac{0}{0}\right]$ function limit at a finite point: $\frac{\sqrt{x}-2}{x-4}$. Multiplying by the conjugate exposes the hidden zero-factor $(x - 4)$, allowing it to cancel against the denominator.
  - In both problems, the core algebraic mechanism is identical: **using $(A - B)(A + B) = A^2 - B^2$ to eliminate a radical that obscures the true asymptotic behavior.**

---

## 4. Step-by-Step Solution

### Step 1: Identify the Indeterminate Form

Consider the function:

$$
f(x) = \frac{\sqrt{x} - 2}{x - 4}
$$

Domain: $x \ge 0$ and $x \ne 4$, so $\text{Dom}(f) = [0, 4) \cup (4, \infty)$.
Substitute $x = 4$:
- Numerator: $\sqrt{4} - 2 = 2 - 2 = 0$
- Denominator: $4 - 4 = 0$

This produces the indeterminate form $\left[\frac{0}{0}\right]$.

---

### Step 2: Rationalize the Numerator Using the Conjugate

The conjugate of the numerator $(\sqrt{x} - 2)$ is $(\sqrt{x} + 2)$.
Multiply both numerator and denominator by $(\sqrt{x} + 2)$:

$$
f(x) = \frac{(\sqrt{x} - 2)(\sqrt{x} + 2)}{(x - 4)(\sqrt{x} + 2)}
$$

Apply $(A - B)(A + B) = A^2 - B^2$ in the numerator:

$$
(\sqrt{x} - 2)(\sqrt{x} + 2) = (\sqrt{x})^2 - 2^2 = x - 4
$$

Substitute this back into the fraction:

$$
f(x) = \frac{x - 4}{(x - 4)(\sqrt{x} + 2)}
$$

---

### Step 3: Cancel the Common Factor for $x \ne 4$

Because we are taking the limit as $x \to 4$, we consider points in a punctured neighborhood $0 < |x - 4| < \delta$, meaning $x \ne 4$.
Since $x \ne 4$, the factor $x - 4 \ne 0$. We can cancel $(x - 4)$ from the top and bottom:

$$
f(x) = \frac{1}{\sqrt{x} + 2} \quad \text{for all } x \ne 4
$$

---

### Step 4: Evaluate the Limit

Now that the indeterminate zero-factor has been removed, the remaining expression $\frac{1}{\sqrt{x} + 2}$ is continuous at $x = 4$.
We evaluate the limit by direct substitution:

$$
\lim_{x\to4}\frac{\sqrt{x}-2}{x-4} = \lim_{x\to4}\frac{1}{\sqrt{x} + 2} = \frac{1}{\sqrt{4} + 2} = \frac{1}{2 + 2} = \frac{1}{4} = 0.25
$$

---

### Step 5: Transfer of Technique — Comparison with Exercise 3

| Aspect | Exercise 3 (Sequence Limit) | Exercise 8 (Function Limit) |
| :--- | :--- | :--- |
| **Expression** | Exercise 3: $\sqrt{n^2 + 5n} - n$ | Exercise 8: $\frac{\sqrt{x} - 2}{x - 4}$ |
| **Context** | Sequence as $n \to \infty$ | Function at a finite point $x \to 4$ |
| **Indeterminate Form** | $[\infty - \infty]$ | $\left[\frac{0}{0}\right]$ |
| **Conjugate Pair** | $\sqrt{n^2 + 5n} + n$ | $\sqrt{x} + 2$ |
| **Algebraic Identity** | $(A - B)(A + B) = A^2 - B^2$ | $(A - B)(A + B) = A^2 - B^2$ |
| **Numerator Result** | $(n^2 + 5n) - n^2 = 5n$ | $(\sqrt{x})^2 - 2^2 = x - 4$ |
| **Role of the Conjugate** | Turns $[\infty - \infty]$ into $[\infty + \infty] = 2n$ | Unmasks the vanishing factor $(x - 4)$ |
| **Final Operation** | Divide top and bottom by $n$ | Cancel common factor $(x - 4)$ |
| **Final Limit** | $\frac{5}{2} = 2.5$ | $\frac{1}{4} = 0.25$ |

#### The Common Core Principle:
In both problems, a square root creates an indeterminate trap. Direct evaluation is blocked because the radical hides the leading algebraic term. By multiplying and dividing by the conjugate $(A + B)$, the difference of squares strips away the radical:
- At infinity (Exercise 3), it neutralizes the runaway infinity: $n^2 - n^2 = 0$.
- At a finite point (Exercise 8), it exposes the invisible zero-factor, $x - 4$, enabling direct cancellation.

---

## 5. Final Answer & Conclusion

The limit is:

$$
\lim_{x\to4}\frac{\sqrt{x}-2}{x-4} = \frac{1}{4}
$$

### Key Insights:
- Direct substitution gave $[0/0]$.
- Rationalizing the numerator produced $\frac{x - 4}{(x - 4)(\sqrt{x} + 2)}$.
- For $x \ne 4$, canceling $(x - 4)$ left $\frac{1}{\sqrt{x} + 2}$.
- Evaluating at $x = 4$ yields $\frac{1}{2 + 2} = \frac{1}{4}$.
- The conjugate technique works universally across both $[\infty - \infty]$ and $[0/0]$ forms.

---

## 6. Quick Verification

1. **Numerical Table Near $x = 4$:**
   - Approaching from the left, with $x < 4$:
     - $x = 3.9 \implies \frac{\sqrt{3.9} - 2}{3.9 - 4} = \frac{1.97484 - 2}{-0.1} = \frac{-0.02516}{-0.1} \approx 0.25158$
     - $x = 3.99 \implies \frac{\sqrt{3.99} - 2}{-0.01} = \frac{1.997498 - 2}{-0.01} \approx 0.25016$
     - $x = 3.999 \implies \approx 0.25002$
   - Approaching from the right, with $x > 4$:
     - $x = 4.1 \implies \frac{\sqrt{4.1} - 2}{4.1 - 4} = \frac{2.02485 - 2}{0.1} = \frac{0.02485}{0.1} \approx 0.24846$
     - $x = 4.01 \implies \frac{\sqrt{4.01} - 2}{0.01} \approx 0.24984$
     - $x = 4.001 \implies \approx 0.24998$
   Both sides steadily converge to $0.25 = \frac{1}{4}$.

2. **Alternative Method via Factoring the Denominator:**
   Notice that $x - 4$ can be viewed as a difference of squares: $x - 4 = (\sqrt{x})^2 - 2^2 = (\sqrt{x} - 2)(\sqrt{x} + 2)$.
   Substituting this directly into the fraction:
   $\frac{\sqrt{x} - 2}{x - 4} = \frac{\sqrt{x} - 2}{(\sqrt{x} - 2)(\sqrt{x} + 2)} = \frac{1}{\sqrt{x} + 2}$.
   Taking $x \to 4$ yields $\frac{1}{\sqrt{4} + 2} = \frac{1}{4}$. This proves the result without rationalizing!

3. **Derivative Definition Verification:**
   Recall the definition of the derivative $g'(c) = \lim_{x \to c} \frac{g(x) - g(c)}{x - c}$.
   Here $g(x) = \sqrt{x}$ and $c = 4$. Since $g'(x) = \frac{1}{2\sqrt{x}}$, we have $g'(4) = \frac{1}{2\sqrt{4}} = \frac{1}{4}$.
   The limit is literally the derivative of $\sqrt{x}$ at $x = 4$.

---

## 7. Common Mistakes to Avoid

1. **Multiplying Only the Numerator by the Conjugate:**
   Forgetting to multiply the denominator by $(\sqrt{x} + 2)$ changes the value of the function.
2. **Expanding the Denominator:**
   Writing the denominator as $(x - 4)(\sqrt{x} + 2) = x\sqrt{x} + 2x - 4\sqrt{x} - 8$ makes it impossible to see the factor $(x - 4)$ that needs to cancel. Always keep the non-conjugate part factored!
3. **Writing $\sqrt{x} - 2 = \sqrt{x - 4}$:**
   A serious algebra error, because $\sqrt{A} - \sqrt{B} \ne \sqrt{A - B}$.

---

## 8. How I Would Explain This in Class

> "When you plug $x = 4$ into $\frac{\sqrt{x}-2}{x-4}$, you get $0/0$. That zero in the numerator is trapped inside a radical prison: $\sqrt{x} - 2$.
> How do we break it out of prison? We use its conjugate key: $\sqrt{x} + 2$.
> When you multiply $(\sqrt{x} - 2)$ by $(\sqrt{x} + 2)$, the square root squares away, leaving $x - 4$.
> And look what is waiting in the denominator: another $(x - 4)$!
> Because $x \ne 4$, they cancel each other out completely with a satisfying 'click', leaving just $1$ on top and $\sqrt{x} + 2$ on the bottom.
> Now plug in $x = 4$: $\frac{1}{\sqrt{4} + 2} = \frac{1}{2 + 2} = \frac{1}{4}$.
> Notice how this is the exact same conjugate trick we used in Exercise 3 for $\sqrt{n^2+5n} - n$: the conjugate is mathematics' universal master key for unlocking square roots!"

