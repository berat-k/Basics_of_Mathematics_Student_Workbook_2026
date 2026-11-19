# Problem 12: Exponential Function Limit

## 1. The Original Problem

Compute

$$
\lim_{x\to0}(1+3x)^{1/x}.
$$

Connect the result with the limit from Exercise 5 and show the appropriate transformation.

---

## 2. What Are We Trying to Find?

We need to:
1. Evaluate the function limit $L = \lim_{x \to 0} (1 + 3x)^{1/x}$ as $x$ approaches $0$.
2. Identify the indeterminate form $[1^\infty]$ arising from base $1 + 3(0) = 1$ and exponent $\frac{1}{0} \to \pm\infty$.
3. Connect this limit to the fundamental definition of Euler's number $e$ studied in Exercise 5:
   $\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n = e \iff \lim_{u \to 0} (1 + u)^{1/u} = e$.
4. Demonstrate the appropriate algebraic transformation (exponent scaling or variable substitution) to rigorously reduce the given limit to a power of $e$.
5. Compute the exact value $e^3$ and provide verification.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Continuous $e$-Limit Formulation:**
  In Exercise 5, we studied the sequence limit: $\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n = e$.
  Let $u = \frac{1}{n}$. As $n \to +\infty$, $u \to 0^+$.
  Extending this to continuous real variables approaching $0$ from both sides, with $u \to 0$, we have the fundamental calculus limit: $\lim_{u \to 0} (1 + u)^{1/u} = e$.
- **Matching the Exponent with the Base:**
  The fundamental limit requires the exponent to be the **exact reciprocal** of the vanishing term inside the base:
  - If the base contains $(1 + u)$, the exponent must be $\frac{1}{u}$.
  - Here, the base contains $(1 + 3x)$, so the vanishing term is $u = 3x$.
  - Its exact reciprocal is $\frac{1}{3x}$.
- **Algebraic Exponent Scaling:**
  The given exponent is $\frac{1}{x}$. We can rewrite $\frac{1}{x}$ by multiplying and dividing by $3$: $\frac{1}{x} = \frac{3}{3x} = \left(\frac{1}{3x}\right) \cdot 3$.
  Using the power of a power law $(A^{BC}) = (A^B)^C$: $(1 + 3x)^{1/x} = \left[(1 + 3x)^{\frac{1}{3x}}\right]^3$.
  Since the inner bracket approaches $e$ as $x \to 0$, the entire expression approaches $e^3$.

---

## 4. Step-by-Step Solution

### Step 1: Identify the Indeterminate Form

Consider the expression:

$$
f(x) = (1 + 3x)^{1/x}
$$

As $x \to 0$:
- Base: $1 + 3x \to 1 + 0 = 1$
- Exponent: $\frac{1}{x} \to \pm\infty$

This gives the classical indeterminate form:

$$
\left[1^\infty\right]
$$

As established in Exercise 5, $1^\infty$ is an indeterminate form because the base is not identically $1$, and the exponent magnifies small deviations from $1$.

---

### Step 2: Connection with the Fundamental Limit from Exercise 5

In Exercise 5, we established that:

$$
\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n = e
$$

By setting $u = \frac{1}{n}$, as $n \to \infty$ we have $u \to 0$. In general, for any continuous variable $u \to 0$:

$$
\lim_{u \to 0} (1 + u)^{1/u} = e
$$

This is the standard continuous form of Euler's limit.
Our goal is to reshape $(1 + 3x)^{1/x}$ so that the exponent matches the reciprocal of the term added to $1$.

---

### Step 3: Transformation Method 1 — Exponent Manipulation

In our given expression $(1 + 3x)^{1/x}$, the term inside the parenthesis is $3x$.
Its reciprocal is $\frac{1}{3x}$.
We manipulate the exponent $\frac{1}{x}$ to artificially introduce $\frac{1}{3x}$:

$$
\frac{1}{x} = \frac{1}{3x} \cdot 3
$$

Using the laws of exponents $a^{bc} = (a^b)^c$:

$$
(1 + 3x)^{1/x} = (1 + 3x)^{\frac{1}{3x} \cdot 3} = \left[(1 + 3x)^{\frac{1}{3x}}\right]^3
$$

Now let $u = 3x$.
As $x \to 0$, we have $u = 3x \to 0$.
The inner expression is:

$$
\lim_{x \to 0} (1 + 3x)^{\frac{1}{3x}} = \lim_{u \to 0} (1 + u)^{1/u} = e
$$

Because the cubing function $g(t) = t^3$ is continuous everywhere on $\mathbb{R}$, we can pass the limit inside the power:

$$
\lim_{x \to 0} \left[(1 + 3x)^{\frac{1}{3x}}\right]^3 = \left[\lim_{x \to 0} (1 + 3x)^{\frac{1}{3x}}\right]^3 = e^3
$$

---

### Step 4: Transformation Method 2 — Substitution Method

Let $u = 3x$.
Then:

$$
x = \frac{u}{3} \implies \frac{1}{x} = \frac{3}{u}
$$

As $x \to 0$, $u \to 0$. Substitute these into the limit:

$$
\lim_{x \to 0} (1 + 3x)^{1/x} = \lim_{u \to 0} (1 + u)^{\frac{3}{u}} = \lim_{u \to 0} \left[(1 + u)^{\frac{1}{u}}\right]^3 = \left(\lim_{u \to 0} (1 + u)^{1/u}\right)^3 = e^3
$$

Both transformation methods yield identical, completely rigorous derivations.

---

### Step 5: Transformation Method 3 — Logarithmic Identity using $e^{\ln}$

Alternatively, using the natural exponential and logarithm identity $y = e^{\ln y}$:

$$
(1 + 3x)^{1/x} = \exp\left(\ln\left((1 + 3x)^{1/x}\right)\right) = \exp\left(\frac{1}{x} \ln(1 + 3x)\right) = \exp\left(\frac{\ln(1 + 3x)}{x}\right)
$$

Now compute the limit of the exponent:

$$
L_{\text{exp}} = \lim_{x \to 0} \frac{\ln(1 + 3x)}{x}
$$

This is a $\left[\frac{0}{0}\right]$ form. Multiply numerator and denominator by $3$:

$$
L_{\text{exp}} = \lim_{x \to 0} 3 \cdot \frac{\ln(1 + 3x)}{3x}
$$

Let $u = 3x \to 0$. By the standard derivative definition of $\ln$ at $1$:

$$
\lim_{u \to 0} \frac{\ln(1 + u)}{u} = 1
$$

Therefore:

$$
L_{\text{exp}} = 3 \cdot 1 = 3
$$

Since the exponential function $t \mapsto e^t$ is continuous:

$$
\lim_{x \to 0} (1 + 3x)^{1/x} = e^{L_{\text{exp}}} = e^3
$$

---

## 5. Final Answer & Conclusion

The limit is:

$$
\lim_{x\to0}(1+3x)^{1/x} = e^3
$$

In decimal form:

$$
e^3 \approx (2.718281828)^3 \approx 20.0855369\dots
$$

### General Rule for Limits of Form $(1 + kx)^{1/x}$:
For any real constant $k$:

$$
\lim_{x \to 0} (1 + kx)^{1/x} = e^k
$$

In this problem, $k = 3$, which immediately produces $e^3$.

---

## 6. Quick Verification

1. **Numerical Table for Small $x$:**
   Let $f(x) = (1 + 3x)^{1/x}$. We evaluate for values of $x$ approaching $0$ from both sides:
   - For $x = 0.1$: $f(0.1) = (1 + 0.3)^{10} = (1.3)^{10} \approx 13.7858$.
   - For $x = 0.01$: $f(0.01) = (1 + 0.03)^{100} = (1.03)^{100} \approx 19.2186$.
   - For $x = 0.001$: $f(0.001) = (1 + 0.003)^{1000} \approx 19.9955$.
   - For $x = 0.0001$: $f(0.0001) = (1 + 0.0003)^{10000} \approx 20.0765$.
   - For $x = 0.00001$: $f(0.00001) \approx 20.0846$.
   - From the left, with $x = -0.0001$: $f(-0.0001) = (1 - 0.0003)^{-10000} \approx 20.0945$.
   As $|x| \to 0$, the values converge symmetrically to $e^3 \approx 20.085537$.

2. **L'Hôpital's Rule on Logarithm:**
   $\lim_{x \to 0} \frac{\frac{d}{dx}\ln(1 + 3x)}{\frac{d}{dx}x} = \lim_{x \to 0} \frac{\frac{3}{1 + 3x}}{1} = \frac{3}{1 + 0} = 3 \implies e^3$.
   This independently confirms our exponent manipulation.

---

## 7. Common Mistakes to Avoid

1. **Confusing $(1 + 3x)^{1/x}$ with $1^{1/0} = 1$:**
   Directly substituting $x = 0$ gives $1^\infty$. The limit is **not** $1$.
2. **Forgetting to Multiply and Divide by $3$ in the Exponent:**
   Writing $(1 + 3x)^{1/x} \to e$ because "it looks like the $e$ limit." The coefficient $3$ in $3x$ triples the rate at which the base departs from $1$, which raises the result to the power of $3$, giving $e^3$.
3. **Writing $3e$ Instead of $e^3$:**
   Multiplying $e$ by $3$ instead of raising $e$ to the third power. The factor $3$ is in the exponent, so it acts multiplicatively on the logarithm, which translates to a power on $e$.

---

## 8. How I Would Explain This in Class

> "Remember Exercise 5, where we discovered that $(1 + \frac{1}{n})^n \to e$?
> In that problem, whatever was added to 1 was perfectly matched by its exact upside-down flip in the exponent: you had $\frac{1}{n}$ inside and $n$ outside.
> In this exercise, we have $(1 + 3x)^{1/x}$.
> Inside the parenthesis, we have $3x$. To get our friend $e$, the exponent needs to be the exact reciprocal of $3x$, which is $\frac{1}{3x}$.
> But we only have $\frac{1}{x}$!
> No problem: we borrow a 3 by writing $\frac{1}{x} = \frac{1}{3x} \times 3$.
> Now group it: $\left[(1 + 3x)^{\frac{1}{3x}}\right]^3$.
> The term inside the square brackets is the textbook definition of $e$. And that borrowed 3 is waiting outside as a power.
> So the whole expression effortlessly becomes $e^3$!"
