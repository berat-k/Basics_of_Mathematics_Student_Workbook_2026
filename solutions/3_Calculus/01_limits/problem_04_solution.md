# Problem 04: Powers and Oscillation

## 1. The Original Problem

Analyze

$$
\left(\frac23\right)^n,\qquad \left(\frac32\right)^n,\qquad (-1)^n,\qquad \frac{(-1)^n}{n}.
$$

For each sequence, describe the type of behavior and justify your answer.

---

## 2. What Are We Trying to Find?

We need to:
1. Analyze each of the four given sequences:
   - $a_n = \left(\frac{2}{3}\right)^n$
   - $b_n = \left(\frac{3}{2}\right)^n$
   - $c_n = (-1)^n$
   - $d_n = \frac{(-1)^n}{n}$
2. For each sequence:
   - Determine whether it converges (to a finite limit) or diverges (to $\pm\infty$ or through oscillation).
   - Describe its qualitative behavioral mode (monotonic decay, monotonic growth, pure bounded oscillation, damped oscillation).
   - Provide a rigorous mathematical justification (using geometric sequence convergence criteria, limit definitions, or the Squeeze Theorem).
3. Synthesize the findings to demonstrate that **oscillation does not necessarily preclude convergence**—distinguishing between undamped oscillation and damped (decaying) oscillation.

---

## 3. Before Calculating: What Idea Do We Need?

- **Behavior of Geometric Sequences $q^n$:**
  For any real constant $q$, the sequence $x_n = q^n$ is characterized by the magnitude $|q|$:
  1. If $|q| < 1$: $q^n \to 0$ as $n \to \infty$ (exponential decay toward zero).
  2. If $q = 1$: $q^n = 1^n = 1 \to 1$ (constant sequence).
  3. If $q > 1$: $q^n \to +\infty$ (exponential growth without bound).
  4. If $q \le -1$: the signs alternate, and the terms either bounce endlessly between $\pm 1$ when $q = -1$, or blow up in alternating magnitude when $q < -1$. Neither converges.
- **The Squeeze (Sandwich) Theorem for Sequences:**
  If three sequences satisfy $u_n \le x_n \le v_n$ for all $n \ge N_0$, and:

$$
\lim_{n \to \infty} u_n = \lim_{n \to \infty} v_n = L
$$

  then:

$$
\lim_{n \to \infty} x_n = L
$$

  In particular, if $|x_n| \le v_n$ with $v_n \to 0$ as $n \to \infty$, then:

$$
\lim_{n \to \infty} x_n = 0
$$

- **Oscillation vs. Convergence:**
  - An oscillating sequence changes sign or direction repeatedly.
  - If the oscillation amplitude stays constant, as in $(-1)^n$, the sequence has multiple limit points and diverges.
  - If the oscillation amplitude shrinks to zero, as in $\frac{(-1)^n}{n}$, the sequence is trapped and converges to zero.

---

## 4. Step-by-Step Solution

### Part 1: Sequence 1: $a_n = \left(\frac{2}{3}\right)^n$

#### 1. Identification and Evaluation:
This is a standard geometric sequence $q^n$ with common ratio:

$$
q = \frac{2}{3}
$$

Because $|q| = \left|\frac{2}{3}\right| = \frac{2}{3} < 1$, each successive term is obtained by multiplying the previous term by a factor strictly between $0$ and $1$:

$$
a_1 = \frac{2}{3} \approx 0.667, \quad a_2 = \frac{4}{9} \approx 0.444, \quad a_3 = \frac{8}{27} \approx 0.296, \quad a_4 = \frac{16}{81} \approx 0.198, \dots
$$

#### 2. Rigorous Justification:
For any real number $q$ with $|q| < 1$:

$$
\lim_{n \to \infty} q^n = 0
$$

*Proof using Bernoulli's inequality:*
Let $\frac{1}{|q|} = 1 + h$ with $h = \frac{3}{2} - 1 = \frac{1}{2} > 0$.
Then $\left(\frac{3}{2}\right)^n = (1 + h)^n \ge 1 + nh$ by Bernoulli's inequality.
Taking reciprocals:

$$
0 < a_n = \left(\frac{2}{3}\right)^n \le \frac{1}{1 + n(0.5)} < \frac{2}{n} \xrightarrow{n \to \infty} 0
$$

By the Squeeze Theorem, $\lim_{n \to \infty} a_n = 0$.

#### 3. Behavioral Description:
- **Status:** **Convergent** to $0$.
- **Mode:** **Monotonically decreasing** and strictly positive for all $n \ge 1$.

---

### Part 2: Sequence 2: $b_n = \left(\frac{3}{2}\right)^n$

#### 1. Identification and Evaluation:
This is a geometric sequence $q^n$ with common ratio:

$$
q = \frac{3}{2} = 1.5 > 1
$$

Each term is $1.5$ times the preceding term:

$$
b_1 = 1.5, \quad b_2 = 2.25, \quad b_3 = 3.375, \quad b_4 = 5.0625, \quad b_5 \approx 7.59, \quad b_{10} \approx 57.67, \quad b_{20} \approx 3325.26
$$

#### 2. Rigorous Justification:
Write $q = 1 + h$ where $h = 0.5 > 0$.
By Bernoulli's inequality:

$$
b_n = (1 + 0.5)^n \ge 1 + 0.5n
$$

As $n \to \infty$, the linear lower bound $1 + 0.5n \to +\infty$.
Therefore, by the comparison test for limits:

$$
\lim_{n \to \infty} \left(\frac{3}{2}\right)^n = +\infty
$$

#### 3. Behavioral Description:
- **Status:** **Divergent** to $+\infty$.
- **Mode:** **Monotonically increasing** and grows exponentially without bound.

---

### Part 3: Sequence 3: $c_n = (-1)^n$

#### 1. Term-by-Term Values:
Let us write out the first few terms for $n = 1, 2, 3, 4, 5, \dots$:

$$
c_1 = -1, \quad c_2 = +1, \quad c_3 = -1, \quad c_4 = +1, \quad c_5 = -1, \quad \dots
$$

The terms alternate endlessly between $-1$ and $+1$:

$$
c_n = \begin{cases} -1 & \text{if } n \text{ is odd} \\\\ +1 & \text{if } n \text{ is even} \end{cases}
$$

#### 2. Rigorous Justification of Divergence:
Consider the two complementary subsequences:
- The even-index subsequence $c_{2k} = 1$ is constant and converges to $1$.
- The odd-index subsequence $c_{2k-1} = -1$ is constant and converges to $-1$.

A fundamental theorem of analysis states that a sequence converges to a limit $L$ if and only if **every** subsequence converges to that exact same limit $L$.
Since the two subsequences converge to distinct limits, namely $1 \ne -1$, the full sequence cannot converge.

#### 3. Behavioral Description:
- **Status:** **Divergent** (no limit exists, neither finite nor infinite).
- **Mode:** **Pure bounded oscillation** (undamped periodic alternation between two discrete values, $+1$ and $-1$, with constant unit amplitude).

---

### Part 4: Sequence 4: $d_n = \frac{(-1)^n}{n}$

#### 1. Term-by-Term Values:
Let us write out the first few terms:

$$
d_1 = -\frac{1}{1} = -1, \quad d_2 = +\frac{1}{2} = 0.5, \quad d_3 = -\frac{1}{3} \approx -0.333, \quad d_4 = +\frac{1}{4} = 0.25, \quad d_5 = -\frac{1}{5} = -0.2
$$

The signs alternate at every step between positive and negative, but the magnitudes $|d_n| = \frac{1}{n}$ decrease monotonically toward zero.

#### 2. Rigorous Justification via Squeeze Theorem:
For all $n \ge 1$, since $-1 \le (-1)^n \le 1$, dividing by the positive integer $n$ preserves the inequalities:

$$
-\frac{1}{n} \le \frac{(-1)^n}{n} \le \frac{1}{n}
$$

Now take the limits of the outer bounding sequences:

$$
\lim_{n \to \infty} \left(-\frac{1}{n}\right) = 0 \quad \text{and} \quad \lim_{n \to \infty} \left(\frac{1}{n}\right) = 0
$$

Because both the lower bound and the upper bound converge to the identical value $0$, the **Squeeze Theorem** guarantees:

$$
\lim_{n \to \infty} \frac{(-1)^n}{n} = 0
$$

#### 3. Behavioral Description:
- **Status:** **Convergent** to $0$.
- **Mode:** **Damped oscillation**, alternating signs around $0$ with decaying amplitude where $\frac{1}{n} \to 0$.

---

### Part 5: Conceptual Synthesis — Does Oscillation Rule Out Convergence?

Comparing Sequence 3, $c_n = (-1)^n$, and Sequence 4, $d_n = \frac{(-1)^n}{n}$, reveals a crucial mathematical lesson:

- **Oscillation alone does NOT determine whether a sequence diverges.**
- What determines convergence is the **amplitude of the oscillations as $n \to \infty$**:
  1. In $c_n = (-1)^n$, the amplitude remains constant with $\text{amplitude} = 1$. The terms bounce back and forth across a fixed distance $2$, never settling down. Thus, it **diverges**.
  2. In $d_n = \frac{(-1)^n}{n}$, the oscillation is multiplied by a damping factor $\frac{1}{n}$ that vanishes as $n \to \infty$. The swinging motion is squeezed tighter and tighter against the horizontal axis $0$, forcing the terms into every $\varepsilon$-neighborhood of $0$. Thus, it **converges**.

---

## 5. Final Answer & Conclusion

### Summary Comparison Table:

| Sequence | Formula | Limit as $n \to \infty$ | Convergence Status | Qualitative Type of Behavior |
| :--- | :--- | :--- | :--- | :--- |
| **$a_n$** | $\left(\frac{2}{3}\right)^n$ | **$0$** | **Convergent** | Monotonic geometric decay with $0 < q < 1$ |
| **$b_n$** | $\left(\frac{3}{2}\right)^n$ | **$+\infty$** | **Divergent** to $+\infty$ | Monotonic geometric growth with $q > 1$ |
| **$c_n$** | $(-1)^n$ | **Does not exist** | **Divergent** (oscillates) | Undamped bounded oscillation between $+1$ and $-1$ |
| **$d_n$** | $\frac{(-1)^n}{n}$ | **$0$** | **Convergent** | Damped oscillation squeezed to $0$ |

---

## 6. Quick Verification

1. **Epsilon-Definition Verification for $d_n = \frac{(-1)^n}{n}$:**
   Let $\varepsilon > 0$ be given. We must find $N \in \mathbb{N}$ such that for all $n > N$: $|d_n - 0| = \left|\frac{(-1)^n}{n}\right| = \frac{1}{n} < \varepsilon \iff n > \frac{1}{\varepsilon}$. Choosing $N = \left\lceil \frac{1}{\varepsilon} \right\rceil$ satisfies the formal $(\varepsilon, N)$-definition of a limit for any $\varepsilon > 0$. This rigorously proves convergence to $0$.

2. **Ratio Test Verification for $a_n$ and $b_n$:**
   - For sequence $a$, the ratio test gives $|a_{n+1} / a_n| = 2/3 < 1$, which confirms convergence to $0$.
   - For sequence $b$, the ratio test gives $|b_{n+1} / b_n| = 3/2 > 1$, which confirms divergence to $+\infty$.
   Both results are fully consistent with standard convergence tests.

---

## 7. Common Mistakes to Avoid

1. **Equating Oscillation with Divergence:**
   Assuming that any sequence with alternating signs must diverge. Damped oscillations like $\frac{(-1)^n}{n}$, $\frac{\sin n}{n}$, and $\left(-\frac{1}{2}\right)^n$ all converge to $0$.
2. **Claiming $\lim_{n \to \infty} (-1)^n = 0$ by Averaging:**
   The limit of a sequence is not the average of its terms. A sequence only converges if its terms eventually stay arbitrarily close to a single point. Since $(-1)^n$ is always at least distance $1$ away from $0$, its limit cannot be $0$.
3. **Confusing $\left(\frac{2}{3}\right)^n$ with $\frac{2}{3n}$:**
   Both tend to $0$, but $\left(\frac{2}{3}\right)^n$ decays exponentially, whereas $\frac{2}{3n}$ decays harmonically (much slower).

---

## 8. How I Would Explain This in Class

> "Think of these four sequences as four different objects in physics:
> 1. $\left(\frac{2}{3}\right)^n$ is a ball rolling smoothly to a stop on grass. Every second, it loses one-third of its speed. It glides steadily straight into zero.
> 2. $\left(\frac{3}{2}\right)^n$ is a rocket accelerating without friction. Every second, it becomes $1.5$ times faster. It shoots straight up into infinite space.
> 3. $(-1)^n$ is an electric light switch being flipped on and off every single second forever: ON, OFF, ON, OFF... It never settles down, so it has no final resting state. It diverges.
> 4. $\frac{(-1)^n}{n}$ is a plucked guitar string or a swinging pendulum. It swings left and right, alternating positive and negative, but each swing is smaller than the last because of air resistance, $1/n$. The swings die out, and the string comes to rest at zero. Oscillation does not stop it from converging—friction wins in the end!"

