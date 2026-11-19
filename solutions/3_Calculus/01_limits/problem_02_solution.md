# Problem 02: Different Growth Rates

## 1. The Original Problem

Compute

$$
\lim_{n\to\infty}\frac{3n+1}{n^2+4},\qquad \lim_{n\to\infty}\frac{2n^3-n}{5n^2+1}.
$$

Compare the two cases and formulate a general observation about the degrees of the polynomials in the numerator and denominator.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the first limit $L_1 = \lim_{n \to \infty} \frac{3n + 1}{n^2 + 4}$, where the degree of the numerator is strictly smaller than the degree of the denominator: $\deg(P) < \deg(Q)$.
2. Compute the second limit $L_2 = \lim_{n \to \infty} \frac{2n^3 - n}{5n^2 + 1}$, where the degree of the numerator is strictly larger than the degree of the denominator: $\deg(P) > \deg(Q)$.
3. Compare the contrasting asymptotic behaviors of these two cases alongside the equal-degree case from Exercise 1.
4. Formulate a general, comprehensive mathematical rule for any rational sequence $\lim_{n \to \infty} \frac{P(n)}{Q(n)}$ based purely on comparing the polynomial degrees $\deg(P)$ and $\deg(Q)$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Growth Competition Between Numerator and Denominator:**
  A rational sequence $\frac{P(n)}{Q(n)}$ is a tug-of-war between the top and the bottom:
  - If the bottom grows faster than the top, the denominator crushes the entire fraction down to $0$.
  - If the top grows faster than the bottom, the numerator overpowers the denominator and pulls the fraction toward infinity: $+\infty$ or $-\infty$.
  - If both grow at the exact same polynomial rate (same degree), they balance each other out, yielding a finite non-zero constant (the ratio of leading coefficients).
- **The Rigorous Tool — Dividing by the Dominant Power of the Denominator:**
  The most reliable algebraic technique is to factor or divide both numerator and denominator by the highest power of $n$ present in the **denominator**, say $n^q$:
  - In $L_1$: denominator has highest power $n^2$, so divide by $n^2$.
  - In $L_2$: denominator has highest power $n^2$, so divide by $n^2$.
  This guarantees that the denominator approaches a finite non-zero constant, eliminating any ambiguity about division by zero or infinite indeterminacy.

---

## 4. Step-by-Step Solution

### Part 1: Computing the First Limit where $\deg(P) < \deg(Q)$

We consider:

$$
a_n = \frac{3n + 1}{n^2 + 4}
$$

The numerator $P(n) = 3n + 1$ has degree $\deg(P) = 1$.
The denominator $Q(n) = n^2 + 4$ has degree $\deg(Q) = 2$.
As $n \to \infty$, both $P(n) \to \infty$ and $Q(n) \to \infty$, giving the indeterminate form $[\infty / \infty]$.

#### Step 1: Divide by the Highest Power of the Denominator, $n^2$
Divide numerator and denominator by $n^2$:

$$
a_n = \frac{\frac{3n + 1}{n^2}}{\frac{n^2 + 4}{n^2}} = \frac{\frac{3}{n} + \frac{1}{n^2}}{1 + \frac{4}{n^2}}
$$

#### Step 2: Evaluate the Limits of Numerator and Denominator
Using the basic limit facts that $\frac{1}{n} \to 0$ and $\frac{1}{n^2} \to 0$ as $n \to \infty$:
- Limit of numerator: $\lim_{n \to \infty} \left(\frac{3}{n} + \frac{1}{n^2}\right) = 0 + 0 = 0$
- Limit of denominator: $\lim_{n \to \infty} \left(1 + \frac{4}{n^2}\right) = 1 + 0 = 1 \ne 0$

#### Step 3: Apply the Quotient Rule
Since the denominator tends to $1 \ne 0$:

$$
L_1 = \lim_{n \to \infty} \frac{3n + 1}{n^2 + 4} = \frac{0}{1} = 0
$$

---

### Part 2: Computing the Second Limit where $\deg(P) > \deg(Q)$

We consider:

$$
b_n = \frac{2n^3 - n}{5n^2 + 1}
$$

The numerator $P(n) = 2n^3 - n$ has degree $\deg(P) = 3$.
The denominator $Q(n) = 5n^2 + 1$ has degree $\deg(Q) = 2$.
Both $P(n) \to \infty$ and $Q(n) \to \infty$ as $n \to \infty$, giving the indeterminate form $[\infty / \infty]$.

#### Step 1: Divide by the Highest Power of the Denominator, $n^2$
Divide numerator and denominator by $n^2$ (the dominant power of the denominator):

$$
b_n = \frac{\frac{2n^3 - n}{n^2}}{\frac{5n^2 + 1}{n^2}} = \frac{2n - \frac{1}{n}}{5 + \frac{1}{n^2}}
$$

#### Step 2: Evaluate the Asymptotic Behavior
- Denominator behavior: $\lim_{n \to \infty} \left(5 + \frac{1}{n^2}\right) = 5 + 0 = 5 > 0$, stabilizing at the finite positive number $5$.
- Numerator behavior: As $n \to \infty$, $2n \to +\infty$ and $\frac{1}{n} \to 0$, so $2n - \frac{1}{n} \xrightarrow{n \to \infty} +\infty$.

#### Step 3: Conclusion for the Second Limit
Since the numerator grows without bound while the denominator approaches a fixed positive constant $5$:

$$
L_2 = \lim_{n \to \infty} \frac{2n^3 - n}{5n^2 + 1} = +\infty
$$

The sequence diverges to positive infinity.

---

### Part 3: Comparison and General Degree Theorem for Rational Sequences

Let:

$$
P(n) = a_p n^p + a_{p-1} n^{p-1} + \dots + a_0 \quad (a_p \ne 0)
$$

and

$$
Q(n) = b_q n^q + b_{q-1} n^{q-1} + \dots + b_0 \quad (b_q \ne 0)
$$

Consider the general limit:

$$
L = \lim_{n \to \infty} \frac{P(n)}{Q(n)} = \lim_{n \to \infty} \frac{a_p n^p + \dots + a_0}{b_q n^q + \dots + b_0}
$$

Dividing both by $n^q$ yields:

$$
L = \lim_{n \to \infty} \frac{a_p n^{p-q} + \frac{a_{p-1}}{n^{q-p+1}} + \dots}{b_q + \frac{b_{q-1}}{n} + \dots} = \frac{a_p}{b_q} \lim_{n \to \infty} n^{p-q}
$$

This leads directly to the **Three-Case Polynomial Degree Theorem**:

1. **Case 1: Denominator Dominates — $\deg(P) < \deg(Q)$ with $p < q$:**
   - Here $p - q < 0$, so $n^{p-q} = \frac{1}{n^{q-p}} \to 0$.
   - **Result:** The limit is always **zero**: $L = 0$.
   - *Example:* Exercise 2, Part 1, where $\frac{3n+1}{n^2+4}$ has $p=1 < q=2 \implies L = 0$.

2. **Case 2: Balanced Growth — $\deg(P) = \deg(Q)$ with $p = q$:**
   - Here $p - q = 0$, so $n^{p-q} = n^0 = 1$.
   - **Result:** The limit is a **finite non-zero constant**, equal to the ratio of leading coefficients: $L = \frac{a_p}{b_q}$.
   - *Example:* Exercise 1, where $\frac{4n^2-3n+1}{2n^2+5n-7}$ has $p=2, q=2 \implies L = \frac{4}{2} = 2$.

3. **Case 3: Numerator Dominates — $\deg(P) > \deg(Q)$ with $p > q$:**
   - Here $p - q > 0$, so $n^{p-q} \to +\infty$.
   - **Result:** The sequence diverges to **infinity**: $L = +\infty$ if the leading coefficients have the same sign, and $L = -\infty$ if they have opposite signs.
   - *Example:* Exercise 2, Part 2, where $\frac{2n^3-n}{5n^2+1}$ has $p=3 > q=2 \implies L = +\infty$.

---

## 5. Final Answer & Conclusion

### Calculated Limits:
1. First limit: $\lim_{n\to\infty}\frac{3n+1}{n^2+4} = 0$
2. Second limit: $\lim_{n\to\infty}\frac{2n^3-n}{5n^2+1} = +\infty$, which diverges to $+\infty$.

### General Rule:
For any rational sequence $\lim_{n \to \infty} \frac{P(n)}{Q(n)}$:
- If $\deg(P) < \deg(Q)$, the limit is **$0$**.
- If $\deg(P) = \deg(Q)$, the limit is **$\frac{\text{leading coefficient of } P}{\text{leading coefficient of } Q}$**.
- If $\deg(P) > \deg(Q)$, the sequence **diverges to $\pm\infty$** (sign depends on the leading coefficients).

---

## 6. Quick Verification

1. **Numerical Check for Limit 1:**
   - At $n = 10$: $a_{10} = \frac{31}{104} \approx 0.298$.
   - At $n = 100$: $a_{100} = \frac{301}{10004} \approx 0.03009$.
   - At $n = 1{,}000$: $a_{1000} = \frac{3001}{1000004} \approx 0.003001$.
   The values decrease by a factor of 10 for each tenfold increase in $n$, clearly converging to $0$.

2. **Numerical Check for Limit 2:**
   - At $n = 10$: $b_{10} = \frac{2000 - 10}{500 + 1} = \frac{1990}{501} \approx 3.97$.
   - At $n = 100$: $b_{100} = \frac{2000000 - 100}{50000 + 1} = \frac{1999900}{50001} \approx 39.997 \approx \frac{2}{5}(100) = 40$.
   - At $n = 1{,}000$: $b_{1000} \approx \frac{2}{5}(1{,}000) = 400$.
   The terms grow without bound, scaling asymptotically as $\frac{2}{5}n \to +\infty$.

---

## 7. Common Mistakes to Avoid

1. **Stating that the Expression Has No Limit Without Specifying $+\infty$:**
   In calculus, distinguishing between divergent sequences that grow without bound, such as $+\infty$, and those that oscillate without approaching anything (like $(-1)^n$ ) is essential. Always write $+\infty$ rather than merely "divergent."
2. **Dividing by the Numerator's Degree in Case 2:**
   If you divide $b_n$ by $n^3$, you get $\frac{2 - 1/n^2}{5/n + 1/n^3} \to \frac{2}{0^+}$. Dividing by zero can confuse students about signs. Dividing by the **denominator's** degree, $n^2$, keeps the denominator finite at $5$ and makes the numerator manifestly $2n \to +\infty$.
3. **Ignoring the Signs of Leading Coefficients:**
   If the numerator had been $-2n^3 - n$, the limit would be $-\infty$. The sign of infinity is determined by $\text{sgn}(a_p / b_q)$.

---

## 8. How I Would Explain This in Class

> "Think of a rational sequence as an athletic race between the numerator and the denominator.
> In our first fraction, $\frac{3n+1}{n^2+4}$, the denominator runs at speed $n^2$, while the numerator only runs at speed $n$. A runner with speed $n^2$ leaves the other in the dust! When the denominator is vastly larger than the numerator, you are dividing a small number by a gigantic number, so the fraction shrinks to $0$.
> In our second fraction, $\frac{2n^3-n}{5n^2+1}$, the tables are turned: the numerator runs at $n^3$ while the denominator runs at $n^2$. Now the top outruns the bottom by an entire factor of $n$. The fraction blows up to $+\infty$.
> The rule is simple: just compare the highest powers! If the bottom wins, you get $0$. If the top wins, you get $\pm\infty$. If it's a tie, they share the prize: the ratio of their leading numbers."
