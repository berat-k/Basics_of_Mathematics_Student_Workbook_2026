# Problem 03: Recognizing Basic Antiderivatives

## 1. The Original Problem

Compute

$$
\int \left(2e^x + 3\cos x - 4\sin x\right)\,dx.
$$

Match each term with a known derivative and verify the entire result with one differentiation.

---

## 2. What Are We Trying to Find?

1. Match each elementary function $e^x$, $\cos x$, and $\sin x$ appearing in the integrand with a known differentiation formula.
2. Combine the resulting basic antiderivatives using linearity to compute $\int (2e^x + 3\cos x - 4\sin x)\,dx$.
3. Verify the entire family of antiderivatives with a single differentiation.

---

## 3. Before Calculating: What Idea Do We Need?

- **Catalogue of basic derivatives reversed:** Every known differentiation rule immediately supplies a basic integration rule:
  - Since $\frac{d}{dx}(e^x) = e^x$, we have $\int e^x\,dx = e^x + C$.
  - Since $\frac{d}{dx}(\sin x) = \cos x$, we have $\int \cos x\,dx = \sin x + C$.
  - Since $\frac{d}{dx}(\cos x) = -\sin x$, multiplying by $-1$ gives $\frac{d}{dx}(-\cos x) = \sin x$, so $\int \sin x\,dx = -\cos x + C$.
- **Linearity of integration:** Constant factors pass outside the integral sign, and the integral of a sum or difference equals the sum or difference of the integrals.
- **Domain:** All three functions $e^x$, $\cos x$, and $\sin x$ are defined and smooth on the entire real line $\mathbb{R}$, so the antiderivative family is valid on $\mathbb{R}$ with a single arbitrary constant $C \in \mathbb{R}$.

---

## 4. Step-by-Step Solution

### Step 1: Match Each Term with a Known Derivative

Before applying any formulas mechanically, we explicitly pair each term of $f(x) = 2e^x + 3\cos x - 4\sin x$ with the function whose derivative reproduces it:

| Term in integrand | Known differentiation rule | Matching antiderivative |
| :--- | :--- | :--- |
| $2e^x$ | $\frac{d}{dx}(e^x) = e^x$ | $2e^x$ |
| $3\cos x$ | $\frac{d}{dx}(\sin x) = \cos x$ | $3\sin x$ |
| $-4\sin x$ | $\frac{d}{dx}(\cos x) = -\sin x$ | $+4\cos x$ |

Pay special attention to the third row: because $(\cos x)' = -\sin x$, the minus sign already in front of $4\sin x$ combines directly with the derivative of $\cos x$, giving

$$
\frac{d}{dx}(4\cos x) = 4(-\sin x) = -4\sin x.
$$

### Step 2: Compute the Indefinite Integral by Linearity

Splitting the integral across the three terms and pulling out the constant coefficients gives

$$
\begin{aligned}
\int \left(2e^x + 3\cos x - 4\sin x\right)\,dx
&= 2\int e^x\,dx + 3\int \cos x\,dx - 4\int \sin x\,dx \\
&= 2e^x + 3\sin x - 4(-\cos x) + C \\
&= 2e^x + 3\sin x + 4\cos x + C,
\end{aligned}
$$

where $C \in \mathbb{R}$ is an arbitrary constant of integration.

### Step 3: Verify the Entire Result with One Differentiation

Let $F(x) = 2e^x + 3\sin x + 4\cos x + C$. Differentiating the entire expression in one pass yields

$$
\begin{aligned}
F'(x) &= \frac{d}{dx}\bigl(2e^x + 3\sin x + 4\cos x + C\bigr) \\
&= 2\frac{d}{dx}(e^x) + 3\frac{d}{dx}(\sin x) + 4\frac{d}{dx}(\cos x) + \frac{d}{dx}(C) \\
&= 2e^x + 3\cos x + 4(-\sin x) + 0 \\
&= 2e^x + 3\cos x - 4\sin x.
\end{aligned}
$$

Every coefficient and every sign matches the original integrand identically for all $x \in \mathbb{R}$.

---

## 5. Final Answer & Conclusion

- **Indefinite integral on $\mathbb{R}$:**

$$
\int \left(2e^x + 3\cos x - 4\sin x\right)\,dx = 2e^x + 3\sin x + 4\cos x + C, \qquad C \in \mathbb{R}.
$$

- **Term-by-term derivative matching:** $(2e^x)' = 2e^x$, $(3\sin x)' = 3\cos x$, and $(4\cos x)' = -4\sin x$.
- **Verification:** A single differentiation of $2e^x + 3\sin x + 4\cos x + C$ recovers $2e^x + 3\cos x - 4\sin x$ exactly.

---

## 6. Quick Verification

1. **Exact pointwise derivative check at $x = 0$ and $x = \frac{\pi}{2}$:**
   - At $x = 0$: the integrand equals $2e^0 + 3\cos 0 - 4\sin 0 = 2 + 3 - 0 = 5$, and $F'(0) = 2(1) + 3(1) - 4(0) = 5$.
   - At $x = \frac{\pi}{2}$: the integrand equals $2e^{\pi/2} + 3(0) - 4(1) = 2e^{\pi/2} - 4$, and $F'(\frac{\pi}{2}) = 2e^{\pi/2} + 3(0) - 4(1) = 2e^{\pi/2} - 4$.

2. **Numerical difference-quotient check at $x = 0$ with $F(x) = 2e^x + 3\sin x + 4\cos x$:**
   Using $h = 0.001$:
   - $F(0.001) \approx 2(1.00100050) + 3(0.0009999998) + 4(0.99999950) \approx 6.00499900$,
   - $F(-0.001) \approx 2(0.99900050) + 3(-0.0009999998) + 4(0.99999950) \approx 5.99499900$,
   - Therefore,

$$
\frac{F(0.001) - F(-0.001)}{0.002} \approx \frac{0.01000000}{0.002} = 5.00000 = f(0).
$$

   If the sign of $4\cos x$ had been wrong, i.e., $-4\cos x$, then at $x = \frac{\pi}{2}$ the numerical slope would equal $2e^{\pi/2} + 4$ instead of $2e^{\pi/2} - 4$, immediately exposing the error.

---

## 7. Common Mistakes to Avoid

- **Sign swap on $\int \sin x\,dx$ and $\int \cos x\,dx$:** Many students remember that $(\sin x)' = \cos x$ and $(\cos x)' = -\sin x$, then mistakenly keep the same signs when integrating. For integration, the signs reverse: $\int \cos x\,dx = +\sin x + C$ and $\int \sin x\,dx = -\cos x + C$.
- **Double-negative slip on $-4\sin x$:** Writing $-4\int \sin x\,dx = -4\cos x$ loses the extra minus sign from $\int \sin x\,dx = -\cos x$. Always write $-4(-\cos x) = +4\cos x$.
- **Applying the power rule to $e^x$:** Writing $\int e^x\,dx = \frac{e^{x+1}}{x+1}$ confuses an exponential function with a power function $x^n$. The variable $x$ is in the exponent, not the base, so $e^x$ is its own antiderivative.
- **Forgetting $+ C$:** Even when every term comes from a basic catalogue formula, the indefinite integral still represents an entire family shifted by $+ C$.

---

## 8. How I Would Explain This in Class

> "Instead of trying to memorize a separate list of signs for integrating sine and cosine, just ask one simple question for every term: what function differentiates to this? For $2e^x$, the answer is $2e^x$ itself because the exponential never changes under differentiation. For $3\cos x$, the answer is $3\sin x$. And for $-4\sin x$, notice how lucky we are—the minus sign is already sitting there waiting for $4\cos x$, whose derivative is $-4\sin x$. One quick differentiation at the end locks in every sign with total certainty."
