# Problem 06: From a Sequence to a Function — Limit at Infinity

## 1. The Original Problem

Compute

$$
\lim_{x\to\infty}\frac{3x^2-x+1}{5x^2+4x-2}.
$$

Compare the method with Exercise 1. Explain what changes when moving from $n$ to a real variable $x$, and what stays the same.

---

## 2. What Are We Trying to Find?

We need to:
1. Evaluate the function limit $L = \lim_{x \to \infty} \frac{3x^2 - x + 1}{5x^2 + 4x - 2}$ as the continuous real variable $x$ increases without bound, with $x \to +\infty$.
2. Apply the algebraic technique of isolating dominant powers to resolve the indeterminate form $[\infty / \infty]$.
3. Compare this computation directly with the sequence limit in Exercise 1, where $\lim_{n \to \infty} \frac{4n^2 - 3n + 1}{2n^2 + 5n - 7}$ was calculated.
4. Explain clearly and precisely:
   - **What stays the same:** The algebraic operations, the dominance of leading powers, and the limit laws.
   - **What changes:** The fundamental transition from a discrete integer domain, $n \in \mathbb{N}$, to a continuous real continuum, $x \in \mathbb{R}$, and how Heine's characterization bridges the two concepts.

---

## 3. Before Calculating: What Idea Do We Need?

- **Discrete Domain vs. Continuous Domain:**
  - In a sequence $(a_n)$, the index $n$ takes only isolated integer values $1, 2, 3, \dots$. There are gaps between terms, such as between $n = 5$ and $n = 6$.
  - In a function $f(x)$, $x$ flows continuously through all real numbers (including fractions, irrationals, decimals, $x = 5.01$, etc.).
- **Heine's Theorem (Sequential Characterization of Function Limits):**
  A function limit:

$$
\lim_{x \to \infty} f(x) = L
$$

  holds if and only if for every sequence of real numbers $(x_n)$ tending to infinity:

$$
\lim_{n \to \infty} x_n = +\infty
$$

  the corresponding sequence of function values converges to the same limit:

$$
\lim_{n \to \infty} f(x_n) = L
$$

  Because this must hold for *all* sequences tending to infinity (not just integer steps), a function limit is a stronger statement than an integer sequence limit.
- **Algebraic Invariance of Dominant Powers:**
  Despite the difference in domain, polynomials $P(x)$ and $Q(x)$ obey the exact same algebraic laws as $P(n)$ and $Q(n)$. As $x \to \infty$, terms like $\frac{1}{x}$ and $\frac{1}{x^2}$ still approach zero continuously.

---

## 4. Step-by-Step Solution

### Step 1: Identify the Indeterminate Form

Consider the real-valued function:

$$
f(x) = \frac{3x^2 - x + 1}{5x^2 + 4x - 2}
$$

As $x \to \infty$:
- Numerator: $3x^2 - x + 1 \to +\infty$
- Denominator: $5x^2 + 4x - 2 \to +\infty$

This yields the indeterminate form $\left[\frac{\infty}{\infty}\right]$.

---

### Step 2: Factor Out the Dominant Power $x^2$

The highest power of the continuous variable $x$ in both numerator and denominator is $x^2$.
Factor $x^2$ out:

$$
f(x) = \frac{x^2 \left(3 - \frac{1}{x} + \frac{1}{x^2}\right)}{x^2 \left(5 + \frac{4}{x} - \frac{2}{x^2}\right)}
$$

For all $x > 0$, we have $x^2 \ne 0$, so we can cancel $x^2$:

$$
f(x) = \frac{3 - \frac{1}{x} + \frac{1}{x^2}}{5 + \frac{4}{x} - \frac{2}{x^2}}
$$

---

### Step 3: Evaluate the Limit Using Basic Function Limit Laws

As the continuous real variable $x \to \infty$:

$$
\lim_{x \to \infty} \frac{1}{x} = 0 \quad \text{and} \quad \lim_{x \to \infty} \frac{1}{x^2} = 0
$$

Applying the limit laws for sums, differences, and quotients of continuous functions:
- Numerator limit: $\lim_{x \to \infty} \left(3 - \frac{1}{x} + \frac{1}{x^2}\right) = 3 - 0 + 0 = 3$
- Denominator limit: $\lim_{x \to \infty} \left(5 + \frac{4}{x} - \frac{2}{x^2}\right) = 5 + 0 - 0 = 5 \ne 0$

By the quotient law:

$$
\lim_{x \to \infty} \frac{3x^2 - x + 1}{5x^2 + 4x - 2} = \frac{3}{5} = 0.6
$$

---

### Step 4: Comparison with Exercise 1 — What Stays the Same?

1. **The Algebraic Factoring Strategy:**
   In both cases, we divide numerator and denominator by the highest power of the variable, $n^2$ in Exercise 1 and $x^2$ here.
2. **The Mechanism of Subordinate Terms:**
   In both cases, terms of the form $\frac{c}{n^k}$ and $\frac{c}{x^k}$ with $k \ge 1$ vanish to $0$.
3. **The Leading-Coefficient Principle:**
   The result in both problems is purely the ratio of the coefficients of the second-degree terms:
   - In Exercise 1: $\frac{4n^2}{2n^2} \implies \frac{4}{2} = 2$.
   - In Exercise 6: $\frac{3x^2}{5x^2} \implies \frac{3}{5} = 0.6$.

---

### Step 5: Comparison with Exercise 1 — What Changes?

1. **Domain: Discrete vs. Continuum:**
   - In Exercise 1, $n \in \{1, 2, 3, 4, \dots\}$ jumps by integer increments $\Delta n = 1$. The sequence is a collection of isolated points $(n, a_n)$ on a 2D plot.
   - In Exercise 6, $x \in \mathbb{R}$ moves continuously across all real numbers (such as $x = 100.5$, $\pi \times 10^4$, etc.). The function is represented by a solid, unbroken curve.
2. **The Nature of Convergence:**
   - A sequence limit only requires that the values $a_n$ enter and stay within an $\varepsilon$-band for all integer indices $n > N$.
   - A function limit requires that $f(x)$ stays within the $\varepsilon$-band for all real numbers with $x > M$. If a function oscillated wildly between integers, for instance $\sin(2\pi x)$, its sequence limit along integers $x = n$ might exist while its continuous function limit would fail to exist.
   - Because our function $f(x)$ is a rational function without such high-frequency oscillations, Heine's theorem guarantees that the continuous limit exists and coincides with the sequential limit.
3. **Geometric Interpretation — Horizontal Asymptote:**
   In function calculus, the statement $\lim_{x \to \infty} f(x) = \frac{3}{5}$ has a direct geometric meaning: the horizontal line $y = \frac{3}{5}$ is a **horizontal asymptote** of the curve $y = f(x)$ as $x \to +\infty$.

---

## 5. Final Answer & Conclusion

The limit is:

$$
\lim_{x\to\infty}\frac{3x^2-x+1}{5x^2+4x-2} = \frac{3}{5}
$$

### Summary of Comparison:

| Feature | Sequence Limit (Exercise 1) | Function Limit (Exercise 6) |
| :--- | :--- | :--- |
| **Variable** | $n \in \mathbb{N}$ (discrete integers) | $x \in \mathbb{R}$ (continuous real continuum) |
| **Algebraic Method** | Divide by dominant power $n^2$ | Divide by dominant power $x^2$ |
| **Vanishing Terms** | $\frac{1}{n^k} \to 0$ | $\frac{1}{x^k} \to 0$ |
| **Result Determinant** | Ratio of leading coefficients | Ratio of leading coefficients |
| **Geometric Meaning** | Values approach a line | Curve approaches horizontal asymptote $y = \frac{3}{5}$ |

---

## 6. Quick Verification

1. **Numerical Evaluation for Large Real $x$:**
   - At $x = 100$: $f(100) = \frac{3(10000) - 100 + 1}{5(10000) + 400 - 2} = \frac{29901}{50398} \approx 0.593297$.
   - At $x = 1{,}000$: $f(1000) = \frac{3(10^6) - 1000 + 1}{5(10^6) + 4000 - 2} = \frac{2999001}{5003998} \approx 0.599321$.
   - At $x = 10{,}000$: $f(10000) = \frac{299990001}{500039998} \approx 0.599932 \approx 0.6 = \frac{3}{5}$.
   The function values continuously converge toward $0.6$.

2. **Verification via Heine's Theorem:**
   For any arbitrary sequence $x_n = n^2 + \sqrt{n} \to \infty$, substituting into $f(x)$ and factoring out the leading power yields $\frac{3}{5}$, confirming universal convergence along all paths to infinity.

---

## 7. Common Mistakes to Avoid

1. **Believing Sequences and Functions Use Different Algebra at Infinity:**
   Assuming that because $x$ is real and $n$ is an integer, the method of factoring out leading powers changes. The algebraic technique is identical.
2. **Assuming Sequence Convergence Always Implies Function Convergence:**
   A common mistake is thinking that if $f(n)$ converges for integers $n$, then $f(x)$ must converge. Counterexample: $f(x) = \sin(\pi x)$ has $f(n) = 0 \to 0$, but $\lim_{x \to \infty} \sin(\pi x)$ does not exist. For rational functions, however, the behavior is smooth and the limits always agree.
3. **Forgetting Horizontal Asymptotes in Function Context:**
   In sequences, limits are just numbers. In functions, limits at infinity define horizontal asymptotes, connecting algebra to graph sketching.

---

## 8. How I Would Explain This in Class

> "If Exercise 1 was watching a movie frame by frame, with $n = 1, 2, 3\dots$, Exercise 6 is watching the movie play at normal speed, with $x$ flowing continuously.
> In both cases, the plot is the same: when you look far into the future (at infinity), the biggest power $x^2$ is the superstar that commands the entire screen. The smaller terms like $-x$ and $+4x$ are just background extras that fade away into nothing.
> The math doesn't care whether you count in integer steps $1, 2, 3$ or slide smoothly through all the decimals in between: dividing by $x^2$ washes away all the lower powers, leaving only the ratio of the superstars: $3/5$.
> But functions give us one extra gift that sequences don't: on a graph, $y = 3/5$ is a horizontal ceiling that our curve hugs tighter and tighter as it travels to the right—a horizontal asymptote!"
