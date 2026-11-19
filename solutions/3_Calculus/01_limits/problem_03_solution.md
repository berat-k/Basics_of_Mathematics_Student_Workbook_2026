# Problem 03: A Square Root and Removing an Indeterminate Form

## 1. The Original Problem

Compute

$$
\lim_{n\to\infty}\left(\sqrt{n^2+5n}-n\right).
$$

Use the conjugate expression and explain why this transformation removes the difficulty.

---

## 2. What Are We Trying to Find?

We need to:
1. Evaluate the limit of the sequence $a_n = \sqrt{n^2 + 5n} - n$ as $n \to \infty$.
2. Identify the indeterminate form $[\infty - \infty]$ produced by direct evaluation.
3. Apply the method of algebraic conjugation by multiplying and dividing by $\sqrt{n^2 + 5n} + n$ to rationalize the expression.
4. Explain clearly why and how the conjugate transformation removes the difficulty by converting an indeterminate subtraction of two infinitely large quantities into a determinate ratio.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Indeterminate Form $[\infty - \infty]$:**
  As $n \to \infty$:
  - $\sqrt{n^2 + 5n} \to +\infty$
  - $n \to +\infty$
  The expression becomes $[\infty - \infty]$. We cannot simply say $\infty - \infty = 0$, because the two terms may grow at slightly different rates, leaving a finite or infinite difference.
- **The Difference of Two Squares Identity:**
  The identity $(A - B)(A + B) = A^2 - B^2$ eliminates square roots: $(\sqrt{X} - Y)(\sqrt{X} + Y) = X - Y^2$.
  Here, setting $A = \sqrt{n^2 + 5n}$ and $B = n$, their difference of squares is: $A^2 - B^2 = (n^2 + 5n) - n^2 = 5n$.
  The leading quadratic terms $n^2$ cancel each other out completely!
- **Converting Subtraction to Addition:**
  Multiplying and dividing by the conjugate $A + B = \sqrt{n^2 + 5n} + n$ moves the radical expression into the denominator where the two terms add rather than subtract: $A - B = \frac{A^2 - B^2}{A + B} = \frac{5n}{\sqrt{n^2 + 5n} + n}$.
  The denominator is now $[\infty + \infty] = +\infty$, so we have transformed $[\infty - \infty]$ into a standard rational form $\left[\frac{\infty}{\infty}\right]$, which we resolve by dividing by $n$.

---

## 4. Step-by-Step Solution

### Step 1: Identify the Indeterminate Form

Consider the sequence:

$$
a_n = \sqrt{n^2 + 5n} - n
$$

Taking the naive limit term by term:

$$
\lim_{n \to \infty} \sqrt{n^2 + 5n} = +\infty \quad \text{and} \quad \lim_{n \to \infty} n = +\infty
$$

This gives the indeterminate form:

$$
\left[\infty - \infty\right]
$$

We cannot conclude what the limit is without algebraic transformation.

---

### Step 2: Multiply and Divide by the Conjugate Expression

The conjugate of $(\sqrt{n^2 + 5n} - n)$ is $(\sqrt{n^2 + 5n} + n)$.
Multiply and divide the entire expression by this non-zero conjugate:

$$
a_n = \frac{\left(\sqrt{n^2 + 5n} - n\right)\left(\sqrt{n^2 + 5n} + n\right)}{\sqrt{n^2 + 5n} + n}
$$

Apply the algebraic identity $(A - B)(A + B) = A^2 - B^2$ to the numerator:

$$
\left(\sqrt{n^2 + 5n}\right)^2 - n^2 = (n^2 + 5n) - n^2 = 5n
$$

The expression becomes:

$$
a_n = \frac{5n}{\sqrt{n^2 + 5n} + n}
$$

Notice that the problematic subtraction in the numerator has been completely resolved into the simple linear term $5n$.

---

### Step 3: Factor the Dominant Term from the Denominator

We now evaluate the resulting rational limit as $n \to \infty$:

$$
\lim_{n \to \infty} \frac{5n}{\sqrt{n^2 + 5n} + n}
$$

Inside the square root in the denominator, factor out $n^2$:

$$
\sqrt{n^2 + 5n} = \sqrt{n^2 \left(1 + \frac{5}{n}\right)}
$$

Since $n > 0$, we have $\sqrt{n^2} = |n| = n$:

$$
\sqrt{n^2 + 5n} = n \sqrt{1 + \frac{5}{n}}
$$

Substitute this back into the denominator:

$$
\sqrt{n^2 + 5n} + n = n \sqrt{1 + \frac{5}{n}} + n = n \left(\sqrt{1 + \frac{5}{n}} + 1\right)
$$

The full expression is therefore:

$$
a_n = \frac{5n}{n \left(\sqrt{1 + \frac{5}{n}} + 1\right)}
$$

---

### Step 4: Cancel $n$ and Compute the Limit

Since $n \ge 1$, we cancel the factor $n$ from the numerator and denominator:

$$
a_n = \frac{5}{\sqrt{1 + \frac{5}{n}} + 1}
$$

Now take the limit as $n \to \infty$:

$$
\lim_{n \to \infty} \frac{5}{n} = 0
$$

Substitute this into the expression:

$$
\lim_{n \to \infty} a_n = \frac{5}{\sqrt{1 + 0} + 1} = \frac{5}{1 + 1} = \frac{5}{2} = 2.5
$$

---

### Step 5: Why This Transformation Removes the Difficulty

Why is the conjugate technique so effective?

1. **Destructive Interference in the Original Form:**
   In $\sqrt{n^2 + 5n} - n$, both terms grow at rate $\sim n$. When we subtract two quantities that are nearly identical and both infinitely large, their leading terms, $n - n$, cancel, but the leftover difference is hidden inside the square root. Floating-point computers suffer severe catastrophic cancellation when subtracting nearly equal large numbers; symbolically, mathematics encounters the indeterminate form $[\infty - \infty]$.
2. **Elimination of the Root via Squares:**
   By multiplying by the conjugate, the difference of squares $(A - B)(A + B) = A^2 - B^2$ forces the square root to square itself: $\left(\sqrt{n^2 + 5n}\right)^2 = n^2 + 5n$. This pulls the hidden $+5n$ out from beneath the radical and cleanly subtracts $n^2 - n^2 = 0$.
3. **Changing Subtraction into Addition:**
   The conjugate placed in the denominator is $\sqrt{n^2 + 5n} + n$. Crucially, this has a **plus** sign! Because both terms are positive and growing, they reinforce each other: $\sqrt{n^2 + 5n} + n \sim n + n = 2n$. Instead of a delicate subtraction $[\infty - \infty]$, we get a robust sum $[\infty + \infty] = 2n$. The fraction then becomes $\frac{5n}{2n} = \frac{5}{2}$.

---

## 5. Final Answer & Conclusion

The limit is:

$$
\lim_{n\to\infty}\left(\sqrt{n^2+5n}-n\right) = \frac{5}{2}
$$

### Key Insights:
- The initial indeterminate form was $[\infty - \infty]$.
- Multiplying and dividing by the conjugate $\sqrt{n^2 + 5n} + n$ yields $\frac{5n}{\sqrt{n^2 + 5n} + n}$.
- Factoring $n$ from the denominator shows that $\sqrt{n^2 + 5n} + n \sim 2n$ for large $n$.
- The ratio of the linear terms is $\frac{5n}{2n} = \frac{5}{2}$.

---

## 6. Quick Verification

1. **Numerical Evaluation for Large $n$:**
   - At $n = 10$: $\sqrt{100 + 50} - 10 = \sqrt{150} - 10 \approx 12.2474 - 10 = 2.2474$.
   - At $n = 100$: $\sqrt{10000 + 500} - 100 = \sqrt{10500} - 100 \approx 102.4695 - 100 = 2.4695$.
   - At $n = 1{,}000$: $\sqrt{1000000 + 5000} - 1000 = \sqrt{1005000} - 1000 \approx 1002.4969 - 1000 = 2.4969$.
   - At $n = 10{,}000$: $\sqrt{10^8 + 50000} - 10000 \approx 10002.49969 - 10000 = 2.49969$.
   The sequence visibly and monotonically climbs toward $2.5 = \frac{5}{2}$.

2. **Taylor / Binomial Series Verification:**
   Factor $n$ out of the radical first: $\sqrt{n^2 + 5n} = n \sqrt{1 + \frac{5}{n}} = n \left(1 + \frac{5}{n}\right)^{1/2}$.
   Using the binomial expansion $(1 + u)^{1/2} = 1 + \frac{1}{2}u - \frac{1}{8}u^2 + \dots$ with $u = \frac{5}{n}$:
   $n \left(1 + \frac{1}{2}\left(\frac{5}{n}\right) - \frac{1}{8}\left(\frac{5}{n}\right)^2 + \dots\right) = n + \frac{5}{2} - \frac{25}{8n} + \dots$.
   Subtracting $n$: $\sqrt{n^2 + 5n} - n = \frac{5}{2} - \frac{25}{8n} + \mathcal{O}\left(\frac{1}{n^2}\right) \xrightarrow{n \to \infty} \frac{5}{2}$.

---

## 7. Common Mistakes to Avoid

1. **Assuming $\infty - \infty = 0$:**
   Writing $\lim (\sqrt{n^2 + 5n} - n) = \infty - \infty = 0$ is a critical algebraic misconception.
2. **Assuming $\sqrt{n^2 + 5n} \approx \sqrt{n^2} = n$, so the Limit is $0$:**
   While $\sqrt{n^2 + 5n}$ is asymptotically proportional to $n$, the difference $\sqrt{n^2 + 5n} - n$ does not tend to zero because the linear term $5n$ generates a persistent offset of $+2.5$.
3. **Pulling $n$ Out of the Root Incorrectly:**
   Writing $\sqrt{n^2 + 5n} = n + \sqrt{5n}$ is completely wrong because $\sqrt{A + B} \ne \sqrt{A} + \sqrt{B}$.
4. **Forgetting to Divide by the Conjugate:**
   Multiplying by $(\sqrt{n^2+5n} + n)$ without also dividing by it changes the value of the expression. You must multiply by $\frac{\text{conjugate}}{\text{conjugate}} = 1$.

---

## 8. How I Would Explain This in Class

> "Imagine you have two huge piles of sand. The first pile has $n^2 + 5n$ grains of sand inside a square box of side $\sqrt{n^2 + 5n}$, and the second pile is a square of side $n$. You want to know the difference in their side lengths as $n$ becomes enormous.
> If you look at them from a distance, both sides are practically $n$. But if you subtract them directly, your eyes get blinded by the infinity: $\infty - \infty$ tells you nothing!
> So what do we do? We use the oldest trick in algebra: the conjugate $(A - B)(A + B) = A^2 - B^2$.
> When you multiply by the conjugate, the square root vanishes like magic, and $n^2$ cancels against $n^2$, leaving $5n$ on top. And down below, the minus sign has turned into a plus sign: $\sqrt{n^2 + 5n} + n \approx n + n = 2n$.
> Now the battle is simple: $5n$ on top divided by $2n$ on the bottom. The $n$'s cancel, and we get the exact answer: $5/2 = 2.5$!"
