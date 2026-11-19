# Problem 01: Dominant Terms in a Sequence

## 1. The Original Problem

Compute

$$
\lim_{n\to\infty}\frac{4n^2-3n+1}{2n^2+5n-7}.
$$

Explain why the highest-degree terms determine the result.

---

## 2. What Are We Trying to Find?

We need to:
1. Evaluate the limit of the rational sequence $a_n = \frac{4n^2 - 3n + 1}{2n^2 + 5n - 7}$ as $n \to \infty$.
2. Identify the indeterminate form $[\infty/\infty]$ that arises upon direct inspection.
3. Apply the standard rigorous algebraic method of factoring out the highest power of $n$ (the dominant term) from both the numerator and denominator.
4. Explain clearly and conceptually why the highest-degree terms, $4n^2$ and $2n^2$, dictate the ultimate asymptotic behavior, while all lower-degree terms, namely $-3n$, $1$, $5n$, and $-7$, become negligible.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Indeterminate Form $\frac{\infty}{\infty}$:**
  As $n \to \infty$, both the numerator $4n^2 - 3n + 1$ and denominator $2n^2 + 5n - 7$ grow without bound toward $+\infty$. We cannot apply the quotient rule of limits directly to $\frac{\infty}{\infty}$ because infinity is not a real number.
- **The Concept of Dominant Terms:**
  For very large $n$, different powers of $n$ grow at drastically different rates: $n^2 \gg n \gg 1$.
  For instance, when $n = 1{,}000$:
  - $n^2 = 1{,}000{,}000$,
  - $n = 1{,}000$,
  - $1 = 1$.
  Here $n^2$ is a thousand times larger than $n$ and a million times larger than $1$. The lower-order terms contribute only tiny fractions to the total value.
- **Algebraic Isolation via Factoring:**
  To make this rigorous, we divide both numerator and denominator by $n^2$ (the highest power of $n$ in the expression). Since $\lim_{n \to \infty} \frac{1}{n^p} = 0$ for any $p > 0$, all lower-order terms vanish, leaving only the ratio of the leading coefficients.

---

## 4. Step-by-Step Solution

### Step 1: State the Given Limit and Identify the Form

Consider the sequence:

$$
a_n = \frac{4n^2 - 3n + 1}{2n^2 + 5n - 7}
$$

As $n \to \infty$:
- Numerator: $4n^2 - 3n + 1 \to +\infty$
- Denominator: $2n^2 + 5n - 7 \to +\infty$

This gives the indeterminate form $\left[\frac{\infty}{\infty}\right]$.

---

### Step 2: Factor Out the Dominant Power $n^2$

The highest power of $n$ appearing in the rational expression is $n^2$. We factor $n^2$ out of both the numerator and the denominator:

$$
a_n = \frac{n^2 \left(4 - \frac{3}{n} + \frac{1}{n^2}\right)}{n^2 \left(2 + \frac{5}{n} - \frac{7}{n^2}\right)}
$$

For all $n \ge 1$, we have $n^2 \ne 0$, so we can cancel $n^2$ from the top and bottom:

$$
a_n = \frac{4 - \frac{3}{n} + \frac{1}{n^2}}{2 + \frac{5}{n} - \frac{7}{n^2}}
$$

---

### Step 3: Apply the Limit Laws

We now evaluate the limit as $n \to \infty$. By the basic limit theorem for powers of $n$:

$$
\lim_{n \to \infty} \frac{1}{n} = 0 \quad \text{and} \quad \lim_{n \to \infty} \frac{1}{n^2} = 0
$$

Applying the sum and difference laws for limits in the numerator:

$$
\lim_{n \to \infty} \left(4 - \frac{3}{n} + \frac{1}{n^2}\right) = 4 - 3(0) + 0 = 4
$$

Applying the sum and difference laws for limits in the denominator:

$$
\lim_{n \to \infty} \left(2 + \frac{5}{n} - \frac{7}{n^2}\right) = 2 + 5(0) - 7(0) = 2
$$

Since the limit of the denominator is $2 \ne 0$, we can safely apply the quotient law for limits:

$$
\lim_{n \to \infty} a_n = \frac{\lim_{n \to \infty} \left(4 - \frac{3}{n} + \frac{1}{n^2}\right)}{\lim_{n \to \infty} \left(2 + \frac{5}{n} - \frac{7}{n^2}\right)} = \frac{4}{2} = 2
$$

---

### Step 4: Explanation of Why the Highest-Degree Terms Determine the Result

Why do $4n^2$ and $2n^2$ completely control the limit, while $-3n, +1, +5n, -7$ have zero influence?

1. **Relative Scale Comparison:**
   Consider the ratio of a lower-degree term to the highest-degree term: $\frac{-3n}{4n^2} = -\frac{3}{4n} \xrightarrow{n \to \infty} 0$, and $\frac{1}{4n^2} \xrightarrow{n \to \infty} 0$. This proves that as $n$ grows, the lower-degree terms become an infinitely small percentage of the leading term.
2. **Behavior at Extreme Values:**
   - At $n = 10$: Numerator $371$ (where the leading term $400$ accounts for $107.8\%$ of the sum), Denominator $243$ (where the leading term $200$ accounts for $82.3\%$ of the sum), Ratio $\frac{371}{243} \approx 1.5267$.
   - At $n = 1{,}000$: Numerator $3{,}997{,}001$ (where $4n^2$ accounts for 99.92%), Denominator $2{,}004{,}993$ (where $2n^2$ accounts for 99.75%), Ratio $\frac{3{,}997{,}001}{2{,}004{,}993} \approx 1.9935$.
   - At $n = 1{,}000{,}000$: Numerator $\approx 4 \times 10^{12}$, Denominator $\approx 2 \times 10^{12}$, Ratio $\approx 1.9999935 \approx 2$.
3. **Conclusion:**
   The highest power grows so much faster than all lower powers combined that, in the infinite limit, the lower powers contribute exactly zero to the ratio. The asymptotic behavior of the entire rational fraction is identical to the ratio of its leading terms:

$$
\lim_{n \to \infty} \frac{4n^2 - 3n + 1}{2n^2 + 5n - 7} = \lim_{n \to \infty} \frac{4n^2}{2n^2} = \frac{4}{2} = 2
$$

---

## 5. Final Answer & Conclusion

The limit of the sequence is:

$$
\lim_{n\to\infty}\frac{4n^2-3n+1}{2n^2+5n-7} = 2
$$

### Summary of Key Insights:
- Direct evaluation yields an indeterminate form $[ \infty / \infty ]$.
- Dividing both numerator and denominator by the dominant power $n^2$ transforms each lower-degree term into expressions of the form $\frac{c}{n^k}$ with $k \ge 1$.
- Because $\lim_{n \to \infty} \frac{c}{n^k} = 0$, all subordinate terms vanish.
- The value of the limit is strictly determined by the ratio of the coefficients of the highest-degree terms: $\frac{4}{2} = 2$.

---

## 6. Quick Verification

1. **Numerical Check for Large $n$:**
   Substitute $n = 10^4 = 10{,}000$:
   - Numerator: $4(10^8) - 3(10^4) + 1 = 400{,}000{,}000 - 30{,}000 + 1 = 399{,}970{,}001$.
   - Denominator: $2(10^8) + 5(10^4) - 7 = 200{,}000{,}000 + 50{,}000 - 7 = 200{,}049{,}993$.
   - Ratio: $\frac{399{,}970{,}001}{200{,}049{,}993} \approx 1.99935$.
   As $n$ increases by another order of magnitude, at $n = 10^5$, the ratio becomes $1.999935$, converging directly and steadily toward $2$.

2. **Heuristic Check via Leading Coefficients:**
   For any rational sequence where $p = q = 2$:

$$
L = \frac{a_2}{b_2} = \frac{4}{2} = 2
$$

   Both methods agree completely.

---

## 7. Common Mistakes to Avoid

1. **Treating $\infty / \infty$ as $1$:**
   $\infty$ is not a fixed number, and expressions of the form $\infty / \infty$ can evaluate to any non-negative number, zero, or infinity depending on the rates of growth.
2. **Dividing by Different Powers in Numerator and Denominator:**
   Dividing the numerator by $n^2$ and the denominator by $n$ changes the value of the fraction. You must divide both numerator and denominator by the exact same expression, $n^2$.
3. **Canceling Terms Individually:**
   Attempting to cancel $n^2$ between $4n^2$ and $2n^2$ without factoring $n^2$ out of the *entire* numerator and denominator is an algebraic violation.
4. **Writing the Shortcut Without Justification:**
   In an exam or rigorous study note, writing that the limit is $4/2 = 2$ without factoring out $n^2$ or mentioning why lower terms vanish can cost marks. Always show the division by $n^2$.

---

## 8. How I Would Explain This in Class

> "Imagine two billionaires comparing their net worth. The first billionaire has $4$ billion dollars, minus $3$ thousand dollars he spent on a suit, plus $1$ dollar he found on the street. The second billionaire has $2$ billion dollars, plus $5$ thousand in interest, minus $7$ dollars for a sandwich.
> If you calculate the ratio of their wealth, do the $3$ thousand dollars or the $7$ sandwich matter at all? Of course not! When numbers reach billions, the pocket change becomes completely invisible.
> In mathematics, as $n$ goes to infinity, $n^2$ is the billionaire on the scale of $10^{12}$, $n$ is the pocket money on the scale of $10^6$, and $1$ is a speck of dust. When we divide numerator and denominator by $n^2$, we mathematically wash away the dust: the pocket change terms become fractions like $3/n$ which shrink to $0$. All that remains is the ratio of the billionaires: $4/2 = 2$."
