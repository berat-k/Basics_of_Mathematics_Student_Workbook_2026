# Problem 07: Exponential Growth

## 1. The Original Problem

Assume the model

$$
N(t) = N_0 e^{kt}, \qquad k > 0.
$$

1. Verify by differentiation that the model satisfies the relation $N'(t) = kN(t)$.
2. Find the population doubling time.
3. Explain why the doubling time does not depend on $N_0$.

---

## 2. What Are We Trying to Find?

1. **Differentiation check:** Compute the derivative $N'(t)$ of the given exponential function and show explicitly that $N'(t) = kN(t)$ holds for all $t$.
2. **Doubling time:** Determine the time $T$ required for the population to reach twice its initial size, and verify that the same time $T$ doubles the population starting from any time $t$.
3. **Conceptual explanation:** Explain, both algebraically and intuitively in terms of growth rates, why the doubling time is completely independent of the initial population $N_0$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Constant multiple rule and chain rule:** For a constant $C$ and a composite function $e^{u(t)}$, the derivative is $\frac{d}{dt}\left(C e^{u(t)}\right) = C e^{u(t)} u'(t)$. Here $N_0$ and $k$ are constants with respect to $t$, and the inner function is $u(t) = kt$, whose derivative is $u'(t) = k$.
- **Meaning of the initial value:** Substituting $t = 0$ gives $N(0) = N_0 e^{0} = N_0$, so $N_0$ is the initial population. For a nontrivial growing population, we assume $N_0 > 0$.
- **Definition of doubling time:** The doubling time $T$ is the length of time needed for the population to multiply by $2$, meaning $N(T) = 2N(0) = 2N_0$, or more generally $N(t + T) = 2N(t)$.
- **Inverse relationship between $e^x$ and $\ln x$:** To solve an exponential equation of the form $e^{kT} = 2$, we apply the natural logarithm $\ln$, using the identity $\ln\left(e^{x}\right) = x$.
- **Relative growth rate:** Rewriting $N'(t) = kN(t)$ as $\frac{N'(t)}{N(t)} = k$ shows that the growth rate per individual, or percentage growth rate per unit time, is constant.

---

## 4. Step-by-Step Solution

### Step 1: Verify That $N'(t) = kN(t)$

We are given

$$
N(t) = N_0 e^{kt}, \qquad k > 0,
$$

where $N_0$ and $k$ are constants. Differentiating with respect to $t$ using the constant multiple rule and the chain rule gives

$$
N'(t) = \frac{d}{dt}\left(N_0 e^{kt}\right) = N_0 \frac{d}{dt}\left(e^{kt}\right) = N_0 e^{kt} \cdot \frac{d}{dt}(kt) = N_0 e^{kt} \cdot k.
$$

Rearranging the factors, we obtain

$$
N'(t) = k \left(N_0 e^{kt}\right) = k N(t).
$$

Thus, the function $N(t) = N_0 e^{kt}$ satisfies the differential relation $N'(t) = kN(t)$ for all real $t$.

### Step 2: Find the Population Doubling Time

Let $T$ denote the doubling time, assuming a positive initial population $N_0 > 0$. By definition, at time $t = T$ the population is twice its initial value $N(0) = N_0$:

$$
N(T) = 2N_0.
$$

Substituting the formula $N(T) = N_0 e^{kT}$ yields

$$
N_0 e^{kT} = 2N_0.
$$

Because $N_0 > 0$, we can divide both sides of the equation by $N_0$:

$$
e^{kT} = 2.
$$

Taking the natural logarithm of both sides gives

$$
\ln\left(e^{kT}\right) = \ln 2 \implies kT = \ln 2.
$$

Since $k > 0$, we divide both sides by $k$ to isolate $T$:

$$
T = \frac{\ln 2}{k} \approx \frac{0.6931}{k}.
$$

We can also check that $T$ is the doubling time starting from **any** moment $t$, not just from $t = 0$. Evaluating $N(t + T)$ gives

$$
N(t + T) = N_0 e^{k(t + T)} = N_0 e^{kt} e^{kT} = N(t) \cdot e^{k \cdot (\ln 2)/k} = N(t) \cdot e^{\ln 2} = 2N(t).
$$

Therefore, over every time interval of length $T = \frac{\ln 2}{k}$, the population exactly doubles.

### Step 3: Explain Why the Doubling Time Does Not Depend on $N_0$

There are two complementary ways to understand why $N_0$ disappears from the formula for $T$:

**First, algebraic scale invariance:** Doubling is a *relative* condition defined by the ratio $\frac{N(t + T)}{N(t)} = 2$, not by a fixed numerical increase. In the model $N(t) = N_0 e^{kt}$, the initial size $N_0$ enters only as an overall multiplicative factor. When we form the ratio

$$
\frac{N(t + T)}{N(t)} = \frac{N_0 e^{k(t + T)}}{N_0 e^{kt}} = e^{kT},
$$

the factor $N_0$ cancels completely. Hence the condition $e^{kT} = 2$ depends only on the growth constant $k$.

**Second, proportional growth mechanism:** From Step 1, the instantaneous rate of growth is $N'(t) = kN(t)$, which means the *per-capita* or *relative* growth rate

$$
\frac{N'(t)}{N(t)} = k
$$

is constant. If we start with a population that is $10$ times larger, we need to add $10$ times as many new members in order to double, but because the current population is $10$ times larger, it also grows $10$ times faster at every instant. The larger target and the proportionally larger growth speed compensate for each other exactly, so the time needed to double remains $T = \frac{\ln 2}{k}$.

---

## 5. Final Answer & Conclusion

- **Verification:** Differentiating $N(t) = N_0 e^{kt}$ yields $N'(t) = k N_0 e^{kt} = kN(t)$.
- **Doubling time:** For $N_0 > 0$ and $k > 0$, the population doubling time is $T = \frac{\ln 2}{k} \approx \frac{0.6931}{k}$.
- **Independence from $N_0$:** Because the growth rate is strictly proportional to the current population size, the initial value $N_0$ acts purely as a vertical scaling factor that cancels when taking the ratio $N(t+T)/N(t) = 2$. A larger starting population requires a larger absolute increase to double, yet grows proportionally faster, keeping the doubling time invariant.

---

## 6. Quick Verification

**Check 1 — Concrete numerical test with two different initial populations:** Let $k = 0.05\text{ yr}^{-1}$. Then the predicted doubling time is

$$
T = \frac{\ln 2}{0.05} \approx 13.862944\text{ yr}.
$$

- If $N_0 = 100$, then $N(T) = 100 e^{0.05 \cdot (\ln 2)/0.05} = 100 e^{\ln 2} = 200 = 2 \cdot 100$.
- If $N_0 = 5000$, then $N(T) = 5000 e^{0.05 \cdot (\ln 2)/0.05} = 5000 e^{\ln 2} = 10000 = 2 \cdot 5000$.
- After two doubling periods, $N(2T) = N_0 e^{2\ln 2} = 4N_0$, confirming repeated doubling every $T$ units of time.

**Check 2 — Numerical derivative check at a specific time:** Using $N_0 = 100$, $k = 0.05$, and $t = 10$, we compute

$$
N(10) = 100 e^{0.5} \approx 164.8721, \qquad k N(10) = 0.05 \cdot 164.8721 \approx 8.2436.
$$

A symmetric finite-difference approximation with $h = 10^{-4}$ gives

$$
\frac{N(10 + 10^{-4}) - N(10 - 10^{-4})}{2 \cdot 10^{-4}} \approx 8.2436,
$$

which matches $kN(10)$ to four decimal places.

---

## 7. Common Mistakes to Avoid

- **Forgetting the chain rule factor $k$:** Writing $\frac{d}{dt}\left(e^{kt}\right) = e^{kt}$ omits the derivative of the exponent $kt$. Without the factor $k$, you cannot recover $N'(t) = kN(t)$.
- **Confusing $N_0$ with a variable:** Both $N_0$ and $k$ are constants with respect to $t$. Treating $N_0$ as a function of $t$ or applying the product rule unnecessarily leads to errors.
- **Setting $N(T) = 2$ instead of $N(T) = 2N_0$:** Doubling means reaching *twice the initial amount*, not reaching the number $2$. Setting $N_0 e^{kT} = 2$ gives a wrong answer that depends on $N_0$.
- **Forgetting the condition $N_0 > 0$:** Dividing both sides of $N_0 e^{kT} = 2N_0$ by $N_0$ is valid only when $N_0 \ne 0$. If $N_0 = 0$, the population remains identically zero and never grows.

---

## 8. How I Would Explain This in Class

> "Imagine a bank account earning continuous compound interest, or a colony of bacteria where every cell divides at the same steady average pace. Whether you start with $100$ bacteria or $10{,}000$ bacteria, you can think of the big colony as $100$ identical copies of the small colony growing side by side. If each copy takes $T = \frac{\ln 2}{k}$ hours to double, then all $100$ copies double in that exact same time $T$ as well. That is the heart of exponential growth: because each individual contributes the same fractional growth rate $k$, the clock for doubling depends only on $k$ and never on how many individuals you started with."
