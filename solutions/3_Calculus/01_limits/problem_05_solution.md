# Problem 05: The Classical Limit Leading to the Number e

## 1. The Original Problem

Compute

$$
\lim_{n\to\infty}\left(1+\frac1n\right)^n.
$$

Calculate several values for increasing $n$ and compare the observed behavior with the value of the limit. Explain why a few values do not constitute a proof.

---

## 2. What Are We Trying to Find?

We need to:
1. Identify and compute the classical limit of the sequence $e_n = \left(1 + \frac{1}{n}\right)^n$ as $n \to \infty$.
2. Recognize the subtle indeterminate form $[1^\infty]$ underlying this expression, representing the competition between a base shrinking to $1$ and an exponent growing to $\infty$.
3. Compute explicit numerical values for increasing orders of magnitude of $n$, such as $n = 1, 2, 5, 10, 100, 1{,}000, 10{,}000$.
4. Compare this observed numerical progression with the fundamental mathematical constant $e \approx 2.718281828\dots$.
5. Provide a rigorous epistemological explanation of why empirical calculations and tables of numbers **never constitute a mathematical proof** of convergence or of the limit's exact value.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Indeterminate Form $[1^\infty]$:**
  As $n \to \infty$:
  - The base $1 + \frac{1}{n}$ decreases toward $1$.
  - The exponent $n$ increases toward $+\infty$.
  If the base were *identically* $1$, then $1^n = 1$ for all $n$. But here, the base is always strictly greater than $1$, with $1 + \frac{1}{n} > 1$. Raising a number greater than $1$ to an infinitely large power tends to blow up toward $+\infty$.
  The limit represents a delicate balance between these two opposing forces: the shrinking base and the expanding exponent. Their compromise settles at the transcendental constant $e$.

- **The Monotone Convergence Theorem for Sequences:**
  A sequence of real numbers that is:
  1. **Monotonically increasing:** $e_n \le e_{n+1}$ for all $n$, and
  2. **Bounded above:** $e_n \le M$ for some finite constant $M$, such as $M = 3$,
  is guaranteed by the completeness of the real numbers $\mathbb{R}$ to converge to a unique finite limit. This limit is defined as Euler's number $e$:

$$
e \equiv \lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n \approx 2.718281828459\dots
$$

- **Observation vs. Proof:**
  Calculating finitely many terms can provide intuition and suggest conjectures, but it cannot guarantee that the sequence will not eventually oscillate, drop, or diverge for vastly larger numbers, such as $n = 10^{100}$. Only deductive mathematical proof establishes the truth for all infinitely many $n$.

---

## 4. Step-by-Step Solution

### Step 1: The Definition of the Limit

The limit:

$$
\lim_{n\to\infty}\left(1+\frac1n\right)^n
$$

is the standard definition of the base of natural logarithms, Euler's number $e$:

$$
\lim_{n\to\infty}\left(1+\frac1n\right)^n = e
$$

where $e$ is an irrational, transcendental number with decimal expansion:

$$
e \approx 2.718281828459045\dots
$$

---

### Step 2: Numerical Computations for Increasing $n$

Let us compute $e_n = \left(1 + \frac{1}{n}\right)^n$ for several representative values of $n$:

1. **For $n = 1$:** $e_1 = \left(1 + \frac{1}{1}\right)^1 = 2^1 = 2.000000$
2. **For $n = 2$:** $e_2 = \left(1 + \frac{1}{2}\right)^2 = (1.5)^2 = 2.250000$
3. **For $n = 5$:** $e_5 = \left(1 + \frac{1}{5}\right)^5 = (1.2)^5 = 2.488320$
4. **For $n = 10$:** $e_{10} = \left(1 + \frac{1}{10}\right)^{10} = (1.1)^{10} \approx 2.593742$
5. **For $n = 50$:** $e_{50} = \left(1 + \frac{1}{50}\right)^{50} = (1.02)^{50} \approx 2.691588$
6. **For $n = 100$:** $e_{100} = \left(1 + \frac{1}{100}\right)^{100} = (1.01)^{100} \approx 2.704814$
7. **For $n = 1{,}000$:** $e_{1000} = \left(1 + \frac{1}{1000}\right)^{1000} = (1.001)^{1000} \approx 2.716924$
8. **For $n = 10{,}000$:** $e_{10000} = \left(1 + \frac{1}{10000}\right)^{10000} = (1.0001)^{10000} \approx 2.718146$
9. **For $n = 100{,}000$:** $e_{100000} = \left(1 + 10^{-5}\right)^{10^5} \approx 2.718268$
10. **For $n = 1{,}000{,}000$:** $e_{1000000} = \left(1 + 10^{-6}\right)^{10^6} \approx 2.718280$

#### Observations from the Data:
- The terms are **strictly increasing**: $e_1 < e_2 < e_5 < e_{10} < e_{100} < e_{1000} < e_{10000} < \dots$
- The growth is decelerating rapidly: it gains $0.25$ between $n=1$ and $n=2$, but only $0.0012$ between $n=1{,}000$ and $n=10{,}000$.
- The values are clearly approaching an upper ceiling near $2.718\dots$, but they never exceed it.

---

### Step 3: Analytical Outline of the True Mathematical Proof

To prove that the limit exists, mathematics does not rely on tables. It uses the **Binomial Theorem**:

$$
\left(1 + \frac{1}{n}\right)^n = \sum_{k=0}^n \binom{n}{k} \frac{1}{n^k} = 1 + \sum_{k=1}^n \frac{n(n-1)\dots(n-k+1)}{k! \, n^k}
$$

Writing the general term:

$$
\frac{n(n-1)\dots(n-k+1)}{n^k} = 1 \cdot \left(1 - \frac{1}{n}\right)\left(1 - \frac{2}{n}\right)\dots\left(1 - \frac{k-1}{n}\right)
$$

Thus:

$$
e_n = 1 + 1 + \frac{1}{2!}\left(1 - \frac{1}{n}\right) + \frac{1}{3!}\left(1 - \frac{1}{n}\right)\left(1 - \frac{2}{n}\right) + \dots + \frac{1}{n!}\left(1 - \frac{1}{n}\right)\dots\left(1 - \frac{n-1}{n}\right)
$$

From this algebraic expansion, two facts emerge rigorously:
1. **Monotonicity:**
   When $n$ increases to $n+1$, every factor $\left(1 - \frac{j}{n}\right)$ increases to $\left(1 - \frac{j}{n+1}\right)$, and an additional positive term is added to the sum. Therefore, the sequence strictly increases:

$$
e_n < e_{n+1}
$$

2. **Boundedness:**
   Since each factor $\left(1 - \frac{j}{n}\right) < 1$:

$$
e_n < 1 + 1 + \frac{1}{2!} + \frac{1}{3!} + \dots + \frac{1}{n!} < 1 + 1 + \frac{1}{2} + \frac{1}{4} + \dots + \frac{1}{2^{n-1}} = 1 + \frac{1 - (1/2)^n}{1 - 1/2} < 1 + 2 = 3.
$$

Because the sequence is monotonically increasing and bounded above by $3$, the **Monotone Convergence Theorem** guarantees that the finite limit $\lim_{n \to \infty} e_n$ exists. We denote this limit by $e \in (2, 3)$.

---

### Step 4: Why a Few Numerical Values Do Not Constitute a Proof

Why can a mathematician never accept a table of 10, or 1,000, or even 1 billion values as a proof?

1. **Finite Sampling vs. Infinite Behavior:**
   A sequence has infinitely many terms, $n = 1, 2, 3, \dots$. Computing values up to $n = 10^6$ explores a set of size $10^6$, which is $0\%$ of the infinite set of natural numbers $\mathbb{N}$. What happens at $n = 10^{100}$ cannot be inferred simply from what happened at $n = 10^6$.
2. **False Patterns in Numerical Approximations (The Illusion of Convergence):**
   Consider the harmonic sequence partial sums $H_n = \sum_{k=1}^n \frac{1}{k}$.
   - For $n = 10^6$, $H_n \approx 14.39$.
   - For $n = 10^7$, $H_n \approx 16.69$.
   If an observer stopped calculating after thousands of steps, they might falsely conclude that $H_n$ is leveling off and converging near $15$ or $17$. In reality, $H_n$ slowly and relentlessly diverges to $+\infty$!
3. **Late-Onset Oscillations or Jumps:**
   A sequence could be defined as $a_n = \left(1 + \frac{1}{n}\right)^n$ for $n < 10^{10}$, but $a_n = 0$ for $n \ge 10^{10}$. No calculation up to $n = 10^9$ could detect this sudden collapse.
4. **Limits Are Global Asymptotic Truths, Not Floating-Point Truncations:**
   A computer calculates using floating-point arithmetic with limited precision (e.g., 64-bit IEEE 754). For very large $n$, such as $n = 10^{16}$, a computer evaluates $1 + 10^{-16} = 1.0$ due to machine epsilon round-off, which mistakenly outputs $(1.0)^{10^{16}} = 1.0$, completely contradicting the true limit $e$!

Therefore, numerical evidence is valuable for **conjecture generation**, but only deductive logical reasoning constitutes **mathematical proof**.

---

## 5. Final Answer & Conclusion

The limit of the sequence is Euler's number $e$:

$$
\lim_{n\to\infty}\left(1+\frac1n\right)^n = e \approx 2.718281828459\dots
$$

### Value Comparison Summary:

| Index $n$ | Calculated Value $e_n = (1 + 1/n)^n$ | Distance to Limit $|e - e_n|$ |
| :--- | :--- | :--- |
| **$n = 1$** | $2.000000$ | $0.718282$ |
| **$n = 2$** | $2.250000$ | $0.468282$ |
| **$n = 5$** | $2.488320$ | $0.229962$ |
| **$n = 10$** | $2.593742$ | $0.124540$ |
| **$n = 100$** | $2.704814$ | $0.013468$ |
| **$n = 1{,}000$** | $2.716924$ | $0.001358$ |
| **$n = 10{,}000$** | $2.718146$ | $0.000136$ |
| **$\mathbf{n \to \infty}$** | **$e \approx 2.718282$** | **$0$** |

### Why Calculation is Not Proof:
Finitely many calculations cannot survey infinity, cannot detect extremely slow divergence (like the harmonic series), are vulnerable to floating-point round-off errors, and cannot rule out sudden behavioral shifts for unimaginably large $n$. Proof requires structural deductive arguments (such as the Monotone Convergence Theorem).

---

## 6. Quick Verification

1. **Continuous Compounding Interpretation:**
   If an initial principal of 1 unit of currency is invested at 100% annual interest compounded $n$ times per year, after 1 year the accumulated balance is $\left(1 + \frac{1}{n}\right)^n$:
   - Compounded yearly, where $n = 1$: $2.0000$ units.
   - Compounded semi-annually, where $n = 2$: $2.2500$ units.
   - Compounded monthly, where $n = 12$: $2.6130$ units.
   - Compounded daily, where $n = 365$: $2.7145$ units.
   - Compounded continuously, as $n \to \infty$: $e^1 \approx 2.71828$ units.
   This matches the standard financial formula $A = P e^{rt}$.

2. **Series Expansion Verification:**
   The series expansion $e = \sum_{k=0}^\infty \frac{1}{k!} = 1 + 1 + \frac{1}{2} + \frac{1}{6} + \frac{1}{24} + \frac{1}{120} = 2.71666\dots$ converges to the exact same value $2.71828\dots$.

---

## 7. Common Mistakes to Avoid

1. **Evaluating $1^\infty$ as $1$:**
   Thinking that because the base approaches $1$, raising $1$ to any power yields $1$. This is the classic $1^\infty$ fallacy: the base is not identically $1$; it is strictly greater than $1$, and the exponent $n$ amplifies that excess.
2. **Evaluating $1^\infty$ as $\infty$:**
   Thinking that a number greater than $1$ to the power $\infty$ is always $\infty$. While $(1.01)^\infty = \infty$, here the base is not fixed at $1.01$; it shrinks toward $1$ at rate $1/n$ as the exponent grows.
3. **Assuming Empirical Verification Equals Proof:**
   In empirical sciences (physics, chemistry), consistent observations support a hypothesis. In pure mathematics, an unproven pattern—no matter how many billions of examples satisfy it—remains merely a conjecture until proven deductively.

---

## 8. How I Would Explain This in Class

> "Imagine a tug-of-war between two giants:
> The first giant is the base: $1 + \frac{1}{n}$. As $n$ grows, this giant wants to pull the whole number down to $1$, because $1$ raised to anything wants to stay $1$.
> The second giant is the exponent: $n$. As $n$ grows, this giant wants to blow the number up to $+\infty$, because any number even slightly above $1$ multiplied by itself a million times explodes.
> Neither giant wins! They pull against each other with equal strength, and their rope comes to rest at the magical number $e \approx 2.718$.
> But here is the deepest lesson of calculus: calculating this on your calculator for $n = 10, 100, 1000$ gives you a strong hunch, but it is NOT a proof. A sequence might look calm for a million steps and then blow up at step one billion. In mathematics, we don't trust our eyes; we trust our logic. We prove it by showing the sequence is always climbing and trapped under $3$, so by the laws of the real numbers, it has nowhere to go but to land on a limit!"
