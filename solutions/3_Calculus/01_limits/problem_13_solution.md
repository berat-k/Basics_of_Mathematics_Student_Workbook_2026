# Problem 13: Fundamental Trigonometric Limit

## 1. The Original Problem

Using

$$
\lim_{x\to0}\frac{\sin x}{x}=1,
$$

compute

$$
\lim_{x\to0}\frac{\sin5x}{x},\qquad \lim_{x\to0}\frac{\sin2x}{\sin3x}.
$$

In each case, show how you reduce the expression to the fundamental limit.

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the first limit $L_1 = \lim_{x \to 0} \frac{\sin 5x}{x}$.
2. Compute the second limit $L_2 = \lim_{x \to 0} \frac{\sin 2x}{\sin 3x}$.
3. In both calculations, explicitly show the step-by-step reduction to the fundamental trigonometric limit: $\lim_{u \to 0} \frac{\sin u}{u} = 1$.
4. Explain the algebraic technique of multiplying and dividing by matching argument factors, such as $5$ and $\frac{2x}{3x}$, without resorting to l'Hôpital's rule.
5. Formulate the general formula for trigonometric limits of the form $\frac{\sin(ax)}{\sin(bx)}$ and $\frac{\sin(ax)}{bx}$ as $x \to 0$.

---

## 3. Before Calculating: What Idea Do We Need?

- **The Fundamental Principle of the Sine Limit:**
  The fundamental identity:

$$
\lim_{u \to 0} \frac{\sin u}{u} = 1
$$

  holds whenever the argument of the sine function is **identical** to the denominator, and that common argument approaches $0$:

$$
\lim_{\text{expression} \to 0} \frac{\sin(\text{expression})}{\text{expression}} = 1
$$

- **Argument Balancing Strategy:**
  - In $\frac{\sin 5x}{x}$, the sine has argument $5x$, but the denominator is merely $x$. To create the required form $\frac{\sin 5x}{5x}$, we multiply and divide the fraction by $5$: $\frac{\sin 5x}{x} = 5 \cdot \frac{\sin 5x}{5x}$.
  - In $\frac{\sin 2x}{\sin 3x}$, we have two sine functions and no polynomial denominator. We divide both the numerator and denominator by $x$, and then balance the arguments: $\frac{\sin 2x}{\sin 3x} = \frac{\frac{\sin 2x}{x}}{\frac{\sin 3x}{x}} = \frac{2 \cdot \frac{\sin 2x}{2x}}{3 \cdot \frac{\sin 3x}{3x}}$. Each piece reduces cleanly to $1$, leaving the ratio $\frac{2}{3}$.

---

## 4. Step-by-Step Solution

### Part 1: Computing $\lim_{x \to 0} \frac{\sin 5x}{x}$

#### Step 1: Identify the Indeterminate Form
At $x = 0$:
- Numerator: $\sin(5 \cdot 0) = \sin 0 = 0$
- Denominator: $0$
This gives the indeterminate form $\left[\frac{0}{0}\right]$.

#### Step 2: Multiply and Divide by $5$ to Balance the Argument
The argument of the sine is $5x$. We need a $5x$ in the denominator.
Multiply both numerator and denominator by $5$:

$$
\frac{\sin 5x}{x} = \frac{5 \sin 5x}{5x} = 5 \cdot \frac{\sin 5x}{5x}
$$

#### Step 3: Perform the Variable Substitution $u = 5x$
Let $u = 5x$.
As $x \to 0$, we have $u = 5(0) = 0$.
Substitute $u$ into the expression:

$$
\lim_{x \to 0} \frac{\sin 5x}{5x} = \lim_{u \to 0} \frac{\sin u}{u} = 1
$$

#### Step 4: Apply the Constant Multiple Rule
Applying the limit rule for scalar multiplication:

$$
\lim_{x \to 0} \frac{\sin 5x}{x} = \lim_{x \to 0} \left[5 \cdot \frac{\sin 5x}{5x}\right] = 5 \cdot \lim_{x \to 0} \frac{\sin 5x}{5x} = 5 \cdot 1 = 5
$$

---

### Part 2: Computing $\lim_{x \to 0} \frac{\sin 2x}{\sin 3x}$

#### Step 1: Identify the Indeterminate Form
At $x = 0$:
- Numerator: $\sin(2 \cdot 0) = 0$
- Denominator: $\sin(3 \cdot 0) = 0$
This gives the indeterminate form $\left[\frac{0}{0}\right]$.

#### Step 2: Introduce $x$ into Both Numerator and Denominator
For all $x \ne 0$, divide both the numerator and the denominator by $x$:

$$
\frac{\sin 2x}{\sin 3x} = \frac{\frac{\sin 2x}{x}}{\frac{\sin 3x}{x}}
$$

#### Step 3: Balance the Arguments of Both Sines
- In the numerator, multiply and divide by $2$: $\frac{\sin 2x}{x} = 2 \cdot \frac{\sin 2x}{2x}$.
- In the denominator, multiply and divide by $3$: $\frac{\sin 3x}{x} = 3 \cdot \frac{\sin 3x}{3x}$.

Substitute these balanced expressions back into the fraction:

$$
\frac{\sin 2x}{\sin 3x} = \frac{2 \cdot \frac{\sin 2x}{2x}}{3 \cdot \frac{\sin 3x}{3x}} = \frac{2}{3} \cdot \frac{\frac{\sin 2x}{2x}}{\frac{\sin 3x}{3x}}
$$

#### Step 4: Evaluate the Limits Using the Fundamental Limit
Let $u = 2x$ and $v = 3x$. As $x \to 0$, both $u \to 0$ and $v \to 0$:
- Numerator limit: $\lim_{x \to 0} \frac{\sin 2x}{2x} = \lim_{u \to 0} \frac{\sin u}{u} = 1$.
- Denominator limit: $\lim_{x \to 0} \frac{\sin 3x}{3x} = \lim_{v \to 0} \frac{\sin v}{v} = 1 \ne 0$.

By the quotient rule for limits:

$$
\lim_{x \to 0} \frac{\sin 2x}{\sin 3x} = \frac{2}{3} \cdot \frac{\lim_{x \to 0} \frac{\sin 2x}{2x}}{\lim_{x \to 0} \frac{\sin 3x}{3x}} = \frac{2}{3} \cdot \frac{1}{1} = \frac{2}{3}
$$

---

## 5. Final Answer & Conclusion

The values of the limits are:

$$
\lim_{x\to0}\frac{\sin5x}{x} = 5
$$

$$
\lim_{x\to0}\frac{\sin2x}{\sin3x} = \frac{2}{3}
$$

### General Formulas:
For any non-zero real constants $a, b \ne 0$:
1. $\lim_{x \to 0} \frac{\sin(ax)}{x} = a$
2. $\lim_{x \to 0} \frac{\sin(ax)}{bx} = \frac{a}{b}$
3. $\lim_{x \to 0} \frac{\sin(ax)}{\sin(bx)} = \frac{a}{b}$

---

## 6. Quick Verification

1. **Small-Angle Taylor Approximation, where $\sin \theta \approx \theta$:**
   Near $\theta = 0$, the first term of the Taylor series is $\sin \theta = \theta - \frac{\theta^3}{6} + \dots \approx \theta$.
   - For Part 1: $\frac{\sin 5x}{x} \approx \frac{5x}{x} = 5$.
   - For Part 2: $\frac{\sin 2x}{\sin 3x} \approx \frac{2x}{3x} = \frac{2}{3}$.
   This physical/geometric approximation confirms both results instantly.

2. **Numerical Verification:**
   - For Part 1 at $x = 0.01$ rad: $\frac{\sin(0.05)}{0.01} = \frac{0.04997917}{0.01} \approx 4.9979 \to 5$.
   - For Part 2 at $x = 0.01$ rad: $\frac{\sin(0.02)}{\sin(0.03)} = \frac{0.01999867}{0.02999550} \approx 0.666722 \approx \frac{2}{3}$.

3. **L'Hôpital's Rule Verification:**
   - $\lim_{x \to 0} \frac{\sin 5x}{x} \overset{\text{H}}{=} \lim_{x \to 0} \frac{5\cos 5x}{1} = 5(1) = 5$.
   - $\lim_{x \to 0} \frac{\sin 2x}{\sin 3x} \overset{\text{H}}{=} \lim_{x \to 0} \frac{2\cos 2x}{3\cos 3x} = \frac{2(1)}{3(1)} = \frac{2}{3}$.
   Both match without a shadow of doubt.

---

## 7. Common Mistakes to Avoid

1. **Pulling Constants Out of the Sine Function:**
   Writing $\sin 5x = 5 \sin x$. The sine function is **not** linear, because $\sin(kx) \ne k \sin x$. You must balance the denominator, not pull $5$ out of the argument.
2. **Treating Arguments in Degrees Instead of Radians:**
   The fundamental limit:

$$
\lim_{x \to 0} \frac{\sin x}{x} = 1
$$

   is valid strictly in radians. In degrees, the limit is:

$$
\lim_{x \to 0} \frac{\sin x^\circ}{x} = \frac{\pi}{180}
$$

3. **Canceling the Trigonometric Operator:**
   Treating the sine function as an algebraic variable and canceling $\sin$ by writing $\frac{\sin 2x}{\sin 3x} = \frac{2x}{3x} = \frac{2}{3}$. While the answer $\frac{2}{3}$ is coincidentally correct, canceling a trigonometric operator is an algebraic fallacy.

---

## 8. How I Would Explain This in Class

> "The fundamental limit $\frac{\sin x}{x} \to 1$ says something beautiful: for tiny angles, a circle's arc is practically identical to its chord. A sine wave and a straight $45^\circ$ line are twins near zero.
> But the rule has one strict requirement: the expression inside the sine and the expression underneath must be exact twins!
> In $\frac{\sin 5x}{x}$, the sine has $5x$, but the denominator only has $x$. They are not twins yet.
> So we give the denominator a five, and to keep things fair, we multiply the whole fraction by five: $5 \times \frac{\sin 5x}{5x}$.
> Now the fraction is an official twin pair, which happily turns into 1, leaving $5 \times 1 = 5$.
> In $\frac{\sin 2x}{\sin 3x}$, neither sine has a denominator. So we give both of them an $x$ underneath. The top becomes $2 \times \frac{\sin 2x}{2x} \to 2$, and the bottom becomes $3 \times \frac{\sin 3x}{3x} \to 3$. The result is simply $2/3$!"
