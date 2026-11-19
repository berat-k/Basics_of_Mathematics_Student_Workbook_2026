# Problem 15: Observation Versus Proof

## 1. The Original Problem

Choose one sequence and one function from this set. For the sequence, compute several values for increasingly large $n$. For the function, prepare a table of values with arguments approaching the limit point from the left and right. Sketch the behavior of both objects.

Compare the observation with the analytical result and explain why a finite number of calculations or a sketch does not constitute a proof that the limit exists.

---

## 2. What Are We Trying to Find?

We need to:
1. Select one representative sequence from this set, $a_n = \sqrt{n^2 + 5n} - n$ from Exercise 3, and compute explicit numerical terms for increasing $n$ from $n = 1$ to $n = 10^6$.
2. Select one representative function from this set, $f(x) = \frac{\sin 5x}{x}$ from Exercise 13, and construct a two-sided numerical table approaching the limit point $x_0 = 0$ from both the left, with $x \to 0^-$, and the right, with $x \to 0^+$.
3. Provide qualitative structural sketches for both objects illustrating their convergence pathways.
4. Compare empirical observations with formal analytical proofs.
5. Provide a deep epistemological explanation of why numerical tables and visual sketches—no matter how detailed or accurate—**can never serve as a mathematical proof** of the existence or exact value of a limit.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Role of Numerical Experimentation:**
  In mathematical discovery, empirical calculations serve as an essential heuristic: they help formulate conjectures, detect patterns, and spot errors. However, observation is not proof.
- **The Epistemological Divide Between Observation and Proof:**
  1. **Finite vs. Infinite:** An observation can only compute a finite number of points, such as $10$ or $1{,}000$. A limit statement is a universal quantification over an **infinite** domain, asserting a property for all $n > N$ or for all $x \in (c-\delta, c+\delta) \setminus \{c\}$. A finite sample cannot guarantee the behavior of the infinite tail.
  2. **Resolution and Pathological Functions:** A graph or table has finite resolution. Functions can hide rapid oscillations between plotted points (e.g., $g(x) = \sin(5x) + 10^{-6}\sin(10^8 x)$ or $f(x) = \sin(1/x)$ near zero).
  3. **Floating-Point Artifacts:** Computers evaluate arithmetic with fixed precision (64-bit IEEE 754 floats). At extreme arguments, catastrophic cancellation or machine epsilon round-off can create artificial numbers that completely contradict mathematical truth.
  4. **The Definition of Proof:** In mathematics, a proof must be a deductive chain of logical steps grounded in axioms and established theorems (such as the $(\varepsilon, \delta)$ definition, the Squeeze Theorem, or the Monotone Convergence Theorem).

---

## 4. Step-by-Step Solution

### Part 1: Analysis of the Chosen Sequence: $a_n = \sqrt{n^2 + 5n} - n$

#### 1. Numerical Table for Increasing $n$:

| Index $n$ | Expression $\sqrt{n^2 + 5n} - n$ | Approximate Value $a_n$ | Distance to Limit $|2.5 - a_n|$ |
| :--- | :--- | :--- | :--- |
| **$n = 1$** | $\sqrt{1 + 5} - 1 = \sqrt{6} - 1$ | $1.449490$ | $1.050510$ |
| **$n = 2$** | $\sqrt{4 + 10} - 2 = \sqrt{14} - 2$ | $1.741657$ | $0.758343$ |
| **$n = 5$** | $\sqrt{25 + 25} - 5 = \sqrt{50} - 5$ | $2.071068$ | $0.428932$ |
| **$n = 10$** | $\sqrt{100 + 50} - 10 = \sqrt{150} - 10$ | $2.247449$ | $0.252551$ |
| **$n = 100$** | $\sqrt{10000 + 500} - 100 = \sqrt{10500} - 100$ | $2.469508$ | $0.030492$ |
| **$n = 1{,}000$** | $\sqrt{10^6 + 5000} - 1000$ | $2.496883$ | $0.003117$ |
| **$n = 10{,}000$** | $\sqrt{10^8 + 50000} - 10000$ | $2.499688$ | $0.000312$ |
| **$n = 100{,}000$** | $\sqrt{10^{10} + 500000} - 100000$ | $2.499969$ | $0.000031$ |
| **$n = 1{,}000{,}000$** | $\sqrt{10^{12} + 5000000} - 1000000$ | $2.499997$ | $0.000003$ |

#### 2. Qualitative Sketch of the Sequence Behavior:
```
       a_n
        ^
    2.5 + - - - - - - - - - - - - - - - - - - - - - - - - - -  Limit L = 2.5
        |                                        *   *   *
        |                            *   *   *
        |                *   *   *
        |        *   *
        |    *
    1.0 + *
        |
      0 +----+-------+-------+-------+-------+-------+---------> n
        0   10      20      30      40      50      60
```
- The sequence is strictly increasing and concave down.
- It climbs steadily toward the horizontal ceiling $L = 2.5$.

#### 3. Analytical Result:
In Exercise 3, we proved analytically by conjugate multiplication:

$$
\lim_{n \to \infty} (\sqrt{n^2 + 5n} - n) = \lim_{n \to \infty} \frac{5n}{\sqrt{n^2 + 5n} + n} = \frac{5}{1 + 1} = 2.5.
$$

The observation aligns with the mathematical truth.

---

### Part 2: Analysis of the Chosen Function: $f(x) = \frac{\sin 5x}{x}$

#### 1. Two-Sided Numerical Table Approaching $x = 0$:

| Direction | Argument $x$ (radians) | Numerator $\sin(5x)$ | Value $f(x) = \frac{\sin 5x}{x}$ | Distance $|5 - f(x)|$ |
| :--- | :--- | :--- | :--- | :--- |
| **Left, with $x \to 0^-$** | $-0.1$ | $\sin(-0.5) \approx -0.4794255$ | $4.794255$ | $0.205745$ |
| | $-0.05$ | $\sin(-0.25) \approx -0.2474040$ | $4.948079$ | $0.051921$ |
| | $-0.01$ | $\sin(-0.05) \approx -0.0499792$ | $4.997917$ | $0.002083$ |
| | $-0.001$ | $\sin(-0.005) \approx -0.00499998$ | $4.999979$ | $0.000021$ |
| | $-0.0001$ | $\sin(-0.0005) \approx -0.00049999998$| $4.9999998$ | $0.0000002$ |
| **Center, with $x = 0$** | **$0$** | **$\sin(0) = 0$** | **Undefined (zero denominator)** | **Hole in graph** |
| **Right, with $x \to 0^+$**| $+0.0001$ | $\sin(0.0005) \approx +0.00049999998$| $4.9999998$ | $0.0000002$ |
| | $+0.001$ | $\sin(0.005) \approx +0.00499998$ | $4.999979$ | $0.000021$ |
| | $+0.01$ | $\sin(0.05) \approx +0.0499792$ | $4.997917$ | $0.002083$ |
| | $+0.05$ | $\sin(0.25) \approx +0.2474040$ | $4.948079$ | $0.051921$ |
| | $+0.1$ | $\sin(0.5) \approx +0.4794255$ | $4.794255$ | $0.205745$ |

#### 2. Qualitative Sketch of the Function Behavior:
```
                 y
                 ^
                 |
               5 + - - - - - - o - - - - - - -  Limit = 5 (Hole at (0, 5))
                 |           /   \
                 |          /     \
               3 +         /       \
                 |        /         \
               1 +       /           \
        ---------+------/-------------\--------> x
                -0.2  -0.1      0     0.1   0.2
                 |
```
- The function is symmetric across the $y$-axis: an even function satisfying $f(-x) = f(x)$.
- As $x \to 0$ from both sides, the curve forms a smooth arch aiming directly at the coordinate $(0, 5)$.
- At $x = 0$, there is a removable hole (isolated puncture), because division by zero is undefined.

#### 3. Analytical Result:
In Exercise 13, we proved analytically:

$$
\lim_{x \to 0} \frac{\sin 5x}{x} = \lim_{x \to 0} 5 \cdot \frac{\sin 5x}{5x} = 5 \cdot 1 = 5.
$$

The observation agrees with the analytical result.

---

### Part 3: Why Observations and Sketches Do Not Constitute a Proof

Why does mathematics strictly insist that neither a table of values nor a computer graph can serve as a proof?

1. **The Inadequacy of Finite Sampling for Infinite Statements:**
   - A formal limit statement asserts that for every $\varepsilon > 0$, there exists an index $N$ such that $|a_n - L| < \varepsilon$ for all $n > N$.
   - A table of 9 values checks only $n \in \{1, 2, 5, 10, 100, 1000, 10^4, 10^5, 10^6\}$.
   - It tells us nothing about what happens at $n = 10^{20}$ or $n = 10^{100}$. A sequence could behave like $2.5$ for a trillion steps and then suddenly diverge to infinity.
2. **False Patterns and Visual Illusions:**
   - Consider the function $f(x) = \sin\left(\frac{\pi}{x}\right)$. If we sample $x = 1, \frac{1}{2}, \frac{1}{3}, \frac{1}{4}, \dots, \frac{1}{1000}$, every single calculated value is $f(1/k) = \sin(k\pi) = 0$.
   - A student looking at that table would conclude that $\lim_{x \to 0} f(x) = 0$.
   - In reality, $\lim_{x \to 0} \sin(\pi/x)$ **does not exist at all**—it oscillates infinitely between $-1$ and $+1$ in every neighborhood of $0$! The table completely missed the peaks between the sample points.
3. **Floating-Point Round-Off and Catastrophic Cancellation:**
   - When calculating $\frac{\sqrt{n^2 + 5n} - n}{1}$ on a standard computer with $n = 10^{16}$, the computer evaluates $n^2 = 10^{32}$, but 64-bit double precision only stores 15-17 significant digits.
   - The term $5n = 5 \times 10^{16}$ is completely wiped out by round-off error: $10^{32} + 5 \times 10^{16} = 10^{32}$.
   - Taking the square root gives $10^{16}$, and subtracting $n = 10^{16}$ outputs **$0.000000$**!
   - An uncritical reliance on computer calculation would declare that the limit is $0$, which is completely false, as the true limit is $L = 2.5$.
4. **Sketches Lack Infinite Precision:**
   - Any drawn sketch has a physical pen thickness or pixel width. A line drawn on paper covers a range of $\Delta y \approx 0.1\text{ mm}$, which represents a vast band of real numbers.
   - A sketch cannot distinguish whether a curve is approaching $2.500000$ or $2.500001$. Only algebraic deduction provides infinite precision.

---

## 5. Final Answer & Conclusion

### Summary Comparison of Observation vs. Proof:

| Criterion | Empirical Observation (Table / Sketch) | Mathematical Proof (Analytical Deduction) |
| :--- | :--- | :--- |
| **Domain Sampled** | Finitely many isolated points | The entire infinite continuum or index set |
| **Precision** | Limited by screen pixels or floating-point bits | Absolute, infinite, exact algebraic precision |
| **Vulnerability** | Blind to wild oscillations between sample points | Accounts for every possible fluctuation via bounds |
| **Epistemological Role**| **Discovery & Intuition** (conjecturing) | **Certainty & Truth** (verification) |
| **Status in Mathematics**| Not accepted as proof | The sole standard of mathematical truth |

### Final Takeaway:
Observation gives us the **hypothesis** — such as conjecturing the limit is $2.5$ or $5$ — but only rigorous deductive proof establishes it as an eternal mathematical truth.

---

## 6. Quick Verification

1. **Independent Verification of Sequence Limit:**
   By the binomial series $(1 + 5/n)^{1/2} = 1 + \frac{5}{2n} - \frac{25}{8n^2} + \dots$:
   $n\left(\sqrt{1 + \frac{5}{n}} - 1\right) = n\left(\frac{5}{2n} - \frac{25}{8n^2} + \dots\right) = 2.5 - \frac{25}{8n} + \dots \xrightarrow{n \to \infty} 2.5$.
   The analytical series expansion confirms that the error decays exactly as $\frac{25}{8n} = \frac{3.125}{n}$.
   Checking our table at $n = 1{,}000$: error is $0.003117 \approx \frac{3.125}{1000} = 0.003125$. The empirical numbers match the analytical error formula to four decimal places!

2. **Independent Verification of Function Limit:**
   By Taylor series $\sin(5x) = 5x - \frac{(5x)^3}{6} + \dots$:
   $\frac{\sin 5x}{x} = 5 - \frac{125}{6}x^2 + \dots \xrightarrow{x \to 0} 5$.
   The error decays as $\frac{125}{6}x^2 \approx 20.833 x^2$.
   At $x = 0.01$: error is $20.833(0.0001) \approx 0.002083$.
   Matches our table entry $|5 - 4.997917| = 0.002083$ perfectly!

---

## 7. Common Mistakes to Avoid

1. **Believing Numerical Closeness Proves Convergence:**
   Assuming that because consecutive calculated terms differ by less than $0.0001$, the sequence must converge. The harmonic series partial sums satisfy:

$$
H_{n+1} - H_n = \frac{1}{n+1} \to 0
$$

   yet $H_n \to +\infty$!
2. **Discarding Proof as "Unnecessary" When a Calculator Gives the Answer:**
   Thinking that if a calculator shows $2.5$, algebraic conjugation was a waste of time. Calculators frequently output wrong answers for limits due to catastrophic cancellation.
3. **Conflating the Limit with the Value at the Hole:**
   Asserting that $f(0) = 5$ from the table. The table shows that $f(x) \to 5$ as $x \to 0$, but at $x = 0$, $f(0)$ is strictly undefined, in $0/0$ form.

---

## 8. How I Would Explain This in Class

> "Imagine you look out your window every morning for ten days, and every morning a black crow lands on your fence.
> Can you conclude that all crows in the universe are black? In science, you might say it's a good theory. But in mathematics, the answer is a flat NO! Day eleven could bring an albino crow.
> A table of numbers is just ten days of looking out the window. It shows you a pattern, gives you confidence, and helps you guess the answer.
> But mathematics demands something far higher: mathematical proof is proving why an albino crow is physically impossible under the laws of the universe!
> With our sequence, computing $n = 10, 100, 1000$ points to $2.5$. That's the observation.
> Multiplying by the conjugate to show that $a_n = \frac{5}{\sqrt{1 + 5/n} + 1}$ for *every single integer* $n$ from 1 to infinity—that is the proof.
> Observation sparks the question; proof delivers the truth."

