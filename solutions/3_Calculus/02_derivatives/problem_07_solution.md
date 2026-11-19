# Problem 07: A Trigonometric Composition

## 1. The Original Problem

For

$$
f(x)=\sin(x^2+1)
$$

compute the derivative. Explicitly identify the outer function, the inner function, and the derivative of the inner function. Finally, determine the sign of $f'(0)$.

---

## 2. What Are We Trying to Find?

1. Explicit identification of the **outer function**, the **inner function**, and the **derivative of the inner function**.
2. The complete derivative $f'(x)$ using the chain rule.
3. The exact value $f'(0)$ and a precise statement of its sign.

---

## 3. Before Calculating: What Idea Do We Need?

- **Recognizing a composition:** In $\sin(x^2 + 1)$, the expression $x^2 + 1$ sits **inside** the sine function; this is **not** a product of $\sin$ and $(x^2 + 1)$.

```text
x  --->  u = x^2 + 1  --->  y = sin(u)
       (inner layer g)     (outer layer h)
```

- **The chain rule:** For $f(x) = h(g(x))$,

$$
f'(x) = h'(g(x)) \cdot g'(x).
$$

- **Derivative of sine:** $\frac{d}{du}(\sin u) = \cos u$, with angles measured in radians.
- **Sign of a real number:** Every real number falls into exactly one of three sign categories: **positive** if $> 0$, **negative** if $< 0$, or **zero**, which is neither positive nor negative.

---

## 4. Step-by-Step Solution

### Step 1: Identify the Outer Function, Inner Function, and Inner Derivative

Decompose $f(x) = \sin(x^2 + 1)$ into its two layers:

- **Outer function:**

$$
h(u) = \sin u, \qquad \text{with derivative } h'(u) = \cos u.
$$

- **Inner function:**

$$
g(x) = x^2 + 1.
$$

- **Derivative of the inner function:**

$$
g'(x) = \frac{d}{dx}\left(x^2 + 1\right) = 2x.
$$

### Step 2: Apply the Chain Rule to Compute $f'(x)$

Substitute $u = g(x) = x^2 + 1$ into $h'(u) = \cos u$, and multiply by $g'(x) = 2x$:

$$
f'(x) = h'(g(x)) \cdot g'(x) = \cos(x^2 + 1) \cdot 2x.
$$

Writing the algebraic factor in front of the trigonometric function avoids any confusion about what lies inside the cosine:

$$
f'(x) = 2x\cos(x^2 + 1).
$$

### Step 3: Evaluate $f'(0)$ and Determine Its Sign

Substitute $x = 0$ into $f'(x) = 2x\cos(x^2 + 1)$:

$$
f'(0) = 2(0)\cos(0^2 + 1) = 0 \cdot \cos(1) = 0.
$$

**Sign of $f'(0)$:** Since $f'(0) = 0$, the derivative at $x = 0$ is **zero** — it is **neither positive nor negative**.

Notice what happens immediately to the left and right of $x = 0$: because $1 \text{ rad} \in \left(0, \frac{\pi}{2}\right)$ and $\cos(1) \approx 0.5403 > 0$, for all sufficiently small $x$ we have $\cos(x^2 + 1) > 0$. Therefore:

- For small $x < 0$: $2x < 0$ and $\cos(x^2 + 1) > 0$, so $f'(x) < 0$.
- At $x = 0$: $f'(0) = 0$.
- For small $x > 0$: $2x > 0$ and $\cos(x^2 + 1) > 0$, so $f'(x) > 0$.

Thus $f'(x)$ changes sign from negative to positive at $x = 0$, so the tangent line at $(0, \sin(1))$ is horizontal and the function has a local minimum there.

---

## 5. Final Answer & Conclusion

- **Outer function:** $h(u) = \sin u$, with $h'(u) = \cos u$.
- **Inner function:** $g(x) = x^2 + 1$.
- **Derivative of the inner function:** $g'(x) = 2x$.
- **Derivative of $f$:**

$$
f'(x) = 2x\cos(x^2 + 1).
$$

- **Sign of $f'(0)$:** $f'(0) = 0$, so its sign is **zero** — neither positive nor negative, corresponding to a horizontal tangent at $x = 0$.

---

## 6. Quick Verification

1. **Even-symmetry check:** Observe that

$$
f(-x) = \sin\left((-x)^2 + 1\right) = \sin(x^2 + 1) = f(x).
$$

   Because $f$ is an even, differentiable function, its graph is symmetric with respect to the $y$-axis, so its derivative at $x = 0$ **must** equal $0$, matching $f'(0) = 0$. Moreover, $f'(-x) = 2(-x)\cos((-x)^2 + 1) = -f'(x)$ is odd, as required.

2. **Numerical difference-quotient check at $x = 0$ and $x = 1$:**
   - At $x = 0$ with $h = 0.001$: $f(0) = \sin(1) \approx 0.841471$ and $f(0.001) = \sin(1.000001) \approx 0.84147154$, so

$$
\frac{f(0.001) - f(0)}{0.001} \approx 0.000540 \approx 0 = f'(0).
$$

   - At $x = 1$ with $h = 0.001$: exact value $f'(1) = 2\cos(2) \approx -0.832294$. Meanwhile $f(1) = \sin(2) \approx 0.909297$ and $f(1.001) = \sin(2.002001) \approx 0.908463$, giving

$$
\frac{f(1.001) - f(1)}{0.001} \approx -0.834530 \approx -0.832294.
$$

---

## 7. Common Mistakes to Avoid

- **Writing $\cos(2x)$ instead of $2x\cos(x^2 + 1)$:** This differentiates the inside *inside* the outer derivative, computing $h'(g'(x))$ instead of $h'(g(x)) \cdot g'(x)$. The argument $x^2 + 1$ must stay intact inside $\cos$.
- **Forgetting the inner derivative $2x$:** Writing $f'(x) = \cos(x^2 + 1)$ would give $f'(0) = \cos(1) \approx 0.5403 > 0$, falsely claiming the curve is rising at $x = 0$ despite being symmetric across the $y$-axis!
- **Misreading $\cos(x^2 + 1) \cdot 2x$ as $\cos\left((x^2 + 1) \cdot 2x\right)$:** Multiplying $2x$ into the angle inside cosine completely changes the function. Always place algebraic factors **in front** of trig functions: $2x\cos(x^2 + 1)$.
- **Claiming $0$ is positive or negative:** When asked for the sign of $f'(0)$, remember that $0$ is its own category — neither positive nor negative.

---

## 8. How I Would Explain This in Class

> "Whenever you see something more complicated than plain $x$ tucked inside $\sin(\,\cdot\,)$, think of it as a sealed parcel. First differentiate the outer wrapper $\sin$ into $\cos$ while keeping the parcel $x^2 + 1$ sealed inside, and only then multiply outside by the derivative of what was inside the parcel, $2x$. Writing $2x$ in front gives $2x\cos(x^2 + 1)$ so nobody accidentally shoves $2x$ back inside the cosine. And at $x = 0$, the inner parabola $x^2 + 1$ sits right at its bottom vertex with zero slope — so even though $\cos(1)$ is positive, multiplying by $0$ flattens the whole curve to a horizontal tangent!"
