# Problem 11: An n-th Root

## 1. The Original Problem

Compute

$$
\lim_{n\to\infty}\sqrt[n]{5^n+2^n}.
$$

Explain which term dominates and why the transformation looks different from the case of a quotient of polynomials.

---

## 2. What Are We Trying to Find?

We need to:
1. Evaluate the limit of the sequence $a_n = \sqrt[n]{5^n + 2^n}$ as $n \to \infty$.
2. Identify the dominant exponential base between $5^n$ and $2^n$.
3. Apply the Squeeze (Sandwich) Theorem and algebraic factoring to compute the exact limit.
4. Explain clearly and conceptually:
   - Why $5^n$ overwhelmingly dominates $2^n$ as $n \to \infty$.
   - Why the required algebraic transformation differs fundamentally from dividing by the leading power in a quotient of polynomials.

---

## 3. Before Calculating: What Idea Do We Need?

- **Exponential Dominance:**
  For bases $a > b > 0$, the ratio $\frac{b^n}{a^n} = \left(\frac{b}{a}\right)^n$ decays exponentially to $0$ because $\frac{b}{a} < 1$.
  Here, $\frac{2^n}{5^n} = (0.4)^n \xrightarrow{n \to \infty} 0$. As $n$ grows, $2^n$ becomes an infinitesimal fraction of $5^n$.
- **The Squeeze Theorem for $n$-th Roots:**
  Because all terms inside the radical are positive, we have the chain of inequalities:
  $5^n < 5^n + 2^n < 5^n + 5^n = 2 \cdot 5^n$.
  Taking the $n$-th root gives $5 < \sqrt[n]{5^n + 2^n} < 5 \cdot \sqrt[n]{2}$.
  Since $\lim_{n \to \infty} \sqrt[n]{2} = 1$, the upper and lower bounds both converge to $5$, squeezing the sequence to $5$.
- **Why Radical Sums Differ from Rational Polynomials:**
  In a quotient of polynomials $\frac{P(n)}{Q(n)}$, we have an explicit fraction with a numerator and a denominator. We divide both top and bottom by $n^k$.
  Here, we have a **single sum locked under an $n$-th root**—there is no denominator! We cannot "divide" by $5^n$ without altering the expression. Instead, we must **factor out** $5^n$ inside the radical:

$$
\sqrt[n]{5^n + 2^n} = \sqrt[n]{5^n\left(1 + \left(\frac{2}{5}\right)^n\right)} = \left(5^n\right)^{1/n} \cdot \left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n} = 5 \cdot \left(1 + (0.4)^n\right)^{1/n}
$$

---

## 4. Step-by-Step Solution

### Step 1: Identify the Dominant Exponential Term

Consider the expression inside the $n$-th root:

$$
S_n = 5^n + 2^n
$$

Compare the growth of the two terms by examining their ratio:

$$
\frac{2^n}{5^n} = \left(\frac{2}{5}\right)^n = (0.4)^n
$$

Because $0 < \frac{2}{5} < 1$, by the geometric sequence convergence theorem:

$$
\lim_{n \to \infty} \left(\frac{2}{5}\right)^n = 0
$$

This proves that **$5^n$ is the dominant term**. The term $2^n$ contributes an increasingly negligible percentage to the sum:
- At $n = 1$: $5^1 = 5$, $2^1 = 2$, where $2^n$ is 40% of $5^n$.
- At $n = 5$: $5^5 = 3{,}125$, $2^5 = 32$, where $2^n$ is 1.02% of $5^n$.
- At $n = 10$: $5^{10} = 9{,}765{,}625$, $2^{10} = 1{,}024$, where $2^n$ is 0.01% of $5^n$.
- At $n = 100$: $2^{100} / 5^{100} \approx 1.6 \times 10^{-40}$, an utterly vanishing speck.

---

### Step 2: Method 1 — Factoring the Dominant Term Out of the Radical

Factor $5^n$ inside the radical:

$$
\sqrt[n]{5^n + 2^n} = \sqrt[n]{5^n \left(1 + \frac{2^n}{5^n}\right)}
$$

Apply the product rule for radicals $\sqrt[n]{A \cdot B} = \sqrt[n]{A} \cdot \sqrt[n]{B}$, valid since $A > 0$ and $B > 0$:

$$
\sqrt[n]{5^n + 2^n} = \sqrt[n]{5^n} \cdot \sqrt[n]{1 + \left(\frac{2}{5}\right)^n}
$$

Because $5 > 0$, the $n$-th root of $5^n$ simplifies to:

$$
\sqrt[n]{5^n} = \left(5^n\right)^{1/n} = 5^{n/n} = 5
$$

Thus, the sequence takes the form:

$$
a_n = 5 \cdot \left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n}
$$

Now evaluate the limit of the second factor as $n \to \infty$:
- Inside the base: $\left(\frac{2}{5}\right)^n \to 0$, so the base $1 + \left(\frac{2}{5}\right)^n \to 1$.
- The exponent is $\frac{1}{n} \to 0$.
- Because $1 \le 1 + (2/5)^n \le 2$ for all $n \ge 1$:
  $1^{1/n} \le \left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n} \le 2^{1/n}$.
  Since both outer sequences converge to $1$:

$$
\lim_{n \to \infty} 1^{1/n} = 1 \quad \text{and} \quad \lim_{n \to \infty} 2^{1/n} = 1
$$

  the Squeeze Theorem yields:

$$
\lim_{n \to \infty} \left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n} = 1
$$

Multiplying by the outer constant $5$:

$$
\lim_{n \to \infty} a_n = 5 \cdot 1 = 5
$$

---

### Step 3: Method 2 — The Classical Squeeze (Sandwich) Theorem

For any $n \ge 1$, we establish strict lower and upper bounds:
1. **Lower Bound:**
   Since $2^n > 0$, we have $5^n < 5^n + 2^n$.
2. **Upper Bound:**
   Since $2 < 5$, we have $2^n < 5^n$. Replacing $2^n$ with the strictly larger term $5^n$ yields $5^n + 2^n < 5^n + 5^n = 2 \cdot 5^n$.

Combine the inequalities:

$$
5^n < 5^n + 2^n < 2 \cdot 5^n
$$

Because the function $x \mapsto x^{1/n}$ is strictly increasing on $(0, \infty)$, taking the $n$-th root of all three sides preserves the order:

$$
\sqrt[n]{5^n} < \sqrt[n]{5^n + 2^n} < \sqrt[n]{2 \cdot 5^n}
$$

Simplify the outer expressions:

$$
5 < \sqrt[n]{5^n + 2^n} < 5 \cdot \sqrt[n]{2}
$$

Now compute the limits of the bounding sequences:
- Lower bound limit: $\lim_{n \to \infty} 5 = 5$.
- Upper bound limit: $\lim_{n \to \infty} \left(5 \cdot \sqrt[n]{2}\right) = 5 \cdot 1 = 5$.

Since the lower and upper bounds both converge to $5$, the **Squeeze Theorem** guarantees:

$$
\lim_{n \to \infty} \sqrt[n]{5^n + 2^n} = 5.
$$

---

### Step 4: Why the Transformation Looks Different from Polynomial Quotients

Why does this problem require a completely different algebraic structure than Exercise 1, where $\frac{4n^2-3n+1}{2n^2+5n-7}$ was analyzed?

1. **Absence of a Denominator:**
   In Exercise 1, we had a fraction $\frac{P(n)}{Q(n)}$. A fraction possesses the invariant scaling property: dividing both top and bottom by $n^2$ leaves the value unchanged: $\frac{P/n^2}{Q/n^2} = \frac{P}{Q}$.
   In $\sqrt[n]{5^n + 2^n}$, there is **no denominator**. If you divide by $5^n$, you change the expression by a factor of $5^{-n}$. We cannot divide; we can only **factor within the expression**.
2. **Exponential Scaling vs. Polynomial Scaling:**
   In polynomials, the dominant power is an algebraic power $n^k$ with a fixed exponent $k$.
   In exponentials, the variable $n$ is in the **exponent itself**, as in $c^n$.
3. **The Role of the Root, $1/n$:**
   The $n$-th root has power $\frac{1}{n}$. When the dominant base $5^n$ is factored out of the radical, the exponent $n$ and the root index $n$ cancel each other out perfectly: $(5^n)^{1/n} = 5^1 = 5$.
   The radical absorbs the explosive exponential growth of $5^n$ and converts it into a finite, constant coefficient $5$, while compressing the leftover sum into a factor converging to $1$.

---

## 5. Final Answer & Conclusion

The limit is:

$$
\lim_{n\to\infty}\sqrt[n]{5^n+2^n} = 5
$$

### Conceptual Takeaways:
- **Dominant Base:** $5^n$ dominates $2^n$ because the ratio $(2/5)^n \to 0$.
- **General Principle:** For any positive real numbers $c_1, c_2, \dots, c_k > 0$:

$$
\lim_{n \to \infty} \sqrt[n]{c_1^n + c_2^n + \dots + c_k^n} = \max(c_1, c_2, \dots, c_k)
$$

  The $n$-th root acts as a "maximum selector" in the limit as $n \to \infty$.
- **Structural Difference:** Quotients of polynomials use division of top and bottom by $n^k$; radical sums use extraction of the dominant exponential base from under the root followed by the Squeeze Theorem.

---

## 6. Quick Verification

1. **Numerical Table for Increasing $n$:**
   - At $n = 1$: $\sqrt[1]{5 + 2} = 7$.
   - At $n = 2$: $\sqrt{25 + 4} = \sqrt{29} \approx 5.3852$.
   - At $n = 5$: $\sqrt[5]{3125 + 32} = \sqrt[5]{3157} \approx 5.0203$.
   - At $n = 10$: $\sqrt[10]{5^{10} + 2^{10}} = \sqrt[10]{9765625 + 1024} = \sqrt[10]{9766649} \approx 5.00052$.
   - At $n = 20$: $\sqrt[20]{5^{20} + 2^{20}} \approx 5.00000005$.
   The values decrease monotonically and rapidly toward $5.00000$.

2. **Check with $L_\infty$ Norm:**
   In vector space $\mathbb{R}^2$, the $\ell_p$ norm of the vector $(5, 2)$ is $\|(5, 2)\|_p = (5^p + 2^p)^{1/p}$. As $p \to \infty$, the $\ell_p$ norm converges to the maximum norm:

$$
\lim_{p \to \infty} \|(5, 2)\|_p = \|(5, 2)\|_\infty = \max(5, 2) = 5
$$

   This classical functional analysis theorem confirms our result.

---

## 7. Common Mistakes to Avoid

1. **Distributing the $n$-th Root:**
   Writing $\sqrt[n]{5^n + 2^n} = \sqrt[n]{5^n} + \sqrt[n]{2^n} = 5 + 2 = 7$. Roots do not distribute over addition: $\sqrt[n]{A + B} \ne \sqrt[n]{A} + \sqrt[n]{B}$.
2. **Ignoring the $n$-th Root When Deciding the Limit:**
   Observing that $5^n + 2^n \to \infty$ and concluding the limit is $\infty$. The outer $n$-th root counteracts the exponential explosion, pulling the magnitude back down to $5$.
3. **Dividing by $5^n$ Incorrectly:**
   Writing $\frac{\sqrt[n]{5^n + 2^n}}{5^n}$. Dividing the expression by $5^n$ changes its value. You must factor out $5^n$ from inside the radical, which yields an outer factor of $(5^n)^{1/n} = 5$.

---

## 8. How I Would Explain This in Class

> "Imagine two runners in a race: Runner A running at $5^n$ and Runner B running at $2^n$.
> At first, when $n = 1$, they are close: 5 and 2.
> But exponential growth with base 5 is a monster compared to base 2. By step 10, Runner A is at nearly ten million while Runner B is barely at one thousand. Runner B has practically become a statue compared to Runner A.
> So inside the radical, $5^n + 2^n$ is virtually identical to $5^n$.
> Now the $n$-th root comes in: it undoes the power of $n$. The $n$-th root of $5^n$ is just 5!
> In mathematics, the $n$-th root of a sum of powers acts like a spotlight that only sees the biggest base: whether you have $5^n + 2^n$ or $5^n + 4^n + 3^n + 2^n + 1^n$, the $n$-th root will always pick out the maximum base: 5!"

