# Problem 13: A Multi-Layer Composition

## 1. The Original Problem

For

$$
f(x) = e^{\sin(x^2)}
$$

compute the derivative. First write the layers

$$
x \longrightarrow x^2 \longrightarrow \sin(x^2) \longrightarrow e^{\sin(x^2)}
$$

and explain why differentiation moves through them in the reverse order.

---

## 2. What Are We Trying to Find?

1. The explicit sequence of composition layers transforming the input $x$ into the output $f(x) = e^{\sin(x^2)}$, with each intermediate variable clearly named.
2. A clear conceptual and mathematical explanation of why differentiating a multi-layer composition works through those layers in the *reverse* order (from outside to inside).
3. The derivative $f'(x)$, computed cleanly by applying the chain rule across all three layers.

---

## 3. Before Calculating: What Idea Do We Need?

- **Multi-layer chain rule:** If $y = h(v)$, $v = g(u)$, and $u = p(x)$ are all differentiable, then the composite function $y = h(g(p(x)))$ is differentiable and

$$
\frac{dy}{dx} = \frac{dy}{dv} \cdot \frac{dv}{du} \cdot \frac{du}{dx} = h'\bigl(g(p(x))\bigr) \cdot g'\bigl(p(x)\bigr) \cdot p'(x).
$$

- **Rates of change multiply along a chain:** If $u$ changes at rate $\frac{du}{dx}$ per unit change in $x$, $v$ changes at rate $\frac{dv}{du}$ per unit change in $u$, and $y$ changes at rate $\frac{dy}{dv}$ per unit change in $v$, then a tiny change $\Delta x$ is amplified sequentially into $\Delta y \approx \frac{dy}{dv} \cdot \frac{dv}{du} \cdot \frac{du}{dx} \, \Delta x$.
- **Basic derivatives needed for the three layers:**
  - $\frac{d}{dv}(e^v) = e^v$,
  - $\frac{d}{du}(\sin u) = \cos u$,
  - $\frac{d}{dx}(x^2) = 2x$.

---

## 4. Step-by-Step Solution

### Step 1: Write Out the Layers of the Composition

To evaluate $f(x) = e^{\sin(x^2)}$ starting from a real number $x$, we apply three operations one after another:

$$
x \longrightarrow x^2 \longrightarrow \sin(x^2) \longrightarrow e^{\sin(x^2)}.
$$

Introducing intermediate variables makes the three layers completely explicit:
- **Layer 1, innermost:** $u = x^2$ (square the input).
- **Layer 2, middle:** $v = \sin u = \sin(x^2)$ (take the sine of the result).
- **Layer 3, outermost:** $y = e^v = e^{\sin(x^2)}$ (exponentiate base $e$ to that power).

### Step 2: Explain Why Differentiation Moves in the Reverse Order

Evaluation moves **inside-out**, from Layer 1 to Layer 2 to Layer 3:

$$
\text{Evaluation:} \quad x \xrightarrow{\text{Layer 1}} u = x^2 \xrightarrow{\text{Layer 2}} v = \sin u \xrightarrow{\text{Layer 3}} y = e^v.
$$

Differentiation moves in the **reverse order — outside-in**, from Layer 3 to Layer 2 to Layer 1:

$$
\text{Differentiation:} \quad \underbrace{\frac{dy}{dv}}_{\text{Layer 3}} \longrightarrow \underbrace{\frac{dv}{du}}_{\text{Layer 2}} \longrightarrow \underbrace{\frac{du}{dx}}_{\text{Layer 1}}.
$$

There are two complementary ways to see why this reversal is unavoidable:

1. **Structural dependence (peeling nested shells):** At the very top level, $f(x) = e^{\sin(x^2)}$ is an *exponential function* $e^{(\text{something})}$, not a sine function and not a squaring function. You cannot differentiate the inner sine or $x^2$ directly while they are trapped inside the exponential—just as you must open the outermost box before you can reach the boxes packed inside it. Only after differentiating the outer exponential (leaving its exponent $\sin(x^2)$ untouched!) can you step down to differentiate $\sin(x^2)$ (leaving $x^2$ untouched!), and only then step down to differentiate $x^2$.
2. **Repeated application of the two-layer chain rule:** Group the two inner layers together as $v(x) = \sin(x^2)$. Applying the ordinary chain rule to $y = e^{v(x)}$ immediately differentiates the outermost layer first:

$$
\frac{d}{dx}\bigl(e^{v(x)}\bigr) = e^{v(x)} \cdot v'(x).
$$

Now we are left with the task of computing $v'(x) = \frac{d}{dx}\bigl[\sin(x^2)\bigr]$. Applying the chain rule a second time differentiates the middle layer next and leaves the innermost layer for last:

$$
v'(x) = \cos(x^2) \cdot \frac{d}{dx}(x^2) = \cos(x^2) \cdot 2x.
$$

Thus, each application of the chain rule strips off the current outermost layer and defers the inner expression to the next step, automatically traversing the layers in reverse order.

### Step 3: Differentiate Each Layer from Outside to Inside

Compute the derivative of each layer in reverse order:

1. **Outermost layer, $y = e^v$:**

$$
\frac{dy}{dv} = e^v = e^{\sin(x^2)}.
$$

2. **Middle layer, $v = \sin u$:**

$$
\frac{dv}{du} = \cos u = \cos(x^2).
$$

3. **Innermost layer, $u = x^2$:**

$$
\frac{du}{dx} = 2x.
$$

### Step 4: Multiply the Layer Derivatives Together

Combine all three factors via the chain rule:

$$
f'(x) = \frac{dy}{dv} \cdot \frac{dv}{du} \cdot \frac{du}{dx} = e^{\sin(x^2)} \cdot \cos(x^2) \cdot 2x.
$$

Writing the algebraic and trigonometric factors before the exponential gives the standard clean form:

$$
f'(x) = 2x \cos(x^2) e^{\sin(x^2)}.
$$

---

## 5. Final Answer & Conclusion

- **Composition layers:**

$$
x \longrightarrow x^2 \longrightarrow \sin(x^2) \longrightarrow e^{\sin(x^2)}.
$$

- **Why differentiation runs in reverse order:** Evaluating $f(x)$ builds the function from the inside out, wrapping each result inside the next function. Differentiating must unwrap those nested functions from the outside in, differentiating the outermost shell at its untouched inner argument first and then multiplying by the derivative of the next shell inward, down to the innermost variable $x$.
- **Derivative:**

$$
f'(x) = 2x \cos(x^2) e^{\sin(x^2)}.
$$

---

## 6. Quick Verification

1. **Logarithmic differentiation check:** Since $f(x) = e^{\sin(x^2)} > 0$ for all $x \in \mathbb{R}$, taking the natural logarithm strips off the outer exponential layer before differentiating:

$$
\ln f(x) = \sin(x^2).
$$

Differentiating both sides gives

$$
\frac{f'(x)}{f(x)} = \cos(x^2) \cdot 2x \implies f'(x) = 2x \cos(x^2) f(x) = 2x \cos(x^2) e^{\sin(x^2)}.
$$

2. **Even-function symmetry and critical-point check:** Since $(-x)^2 = x^2$, we have $f(-x) = f(x)$, so $f$ is an even function. Therefore $f'$ must be odd, and indeed

$$
f'(-x) = 2(-x)\cos((-x)^2)e^{\sin((-x)^2)} = -2x\cos(x^2)e^{\sin(x^2)} = -f'(x),
$$

with $f'(0) = 0$. Moreover, when $x = \sqrt{\frac{\pi}{2}}$, the exponent $\sin(x^2) = \sin\left(\frac{\pi}{2}\right) = 1$ attains its maximum possible value, so $f(x)$ attains its global maximum $e^1 = e$. Our derivative gives $f'\left(\sqrt{\frac{\pi}{2}}\right) = 2\sqrt{\frac{\pi}{2}} \cos\left(\frac{\pi}{2}\right) e = 0$, matching the horizontal tangent at the peak.

3. **Numerical slope check at $x = 1$:** Our formula gives

$$
f'(1) = 2(1)\cos(1)e^{\sin(1)} \approx 2(0.54030231)(2.31977682) \approx 2.50676153.
$$

Comparing with the numerical central difference at $x = 1$ using $h = 10^{-6}$ yields $\frac{f(1 + 10^{-6}) - f(1 - 10^{-6})}{2 \times 10^{-6}} \approx 2.50676154$, agreeing to $8$ significant digits.

---

## 7. Common Mistakes to Avoid

- **Differentiating inside the function simultaneously instead of multiplying:** Writing $f'(x) = e^{\cos(2x)}$ is completely wrong! When you differentiate an outer layer, its argument *stays intact*—you never plug the inner derivative *inside* the outer derivative. Instead, you multiply by the inner derivative on the outside.
- **Stopping after one chain rule step:** Writing $f'(x) = e^{\sin(x^2)} \cdot \cos(x^2)$ forgets the third layer $\frac{d}{dx}(x^2) = 2x$. Always count how many layers are in your arrow diagram—three arrows mean three factors multiplied together.
- **Confusing $\sin(x^2)$ with $\sin^2(x)$:** Here only the $x$ is squared, not the sine. The derivative of $\sin(x^2)$ is $2x\cos(x^2)$, whereas the derivative of $(\sin x)^2$ would be $2\sin x \cos x$.
- **Dropping parentheses around $x^2$:** Writing $2x\cos x^2$ can be ambiguous; writing $2x\cos(x^2)$ makes it crystal clear that $x^2$ is the argument of $\cos$.

---

## 8. How I Would Explain This in Class

> "Think of $e^{\sin(x^2)}$ as three nested Russian dolls: $x^2$ sits inside $\sin(\,\cdot\,)$, which sits inside $e^{(\,\cdot\,)}$. When you build the function, you pack from the smallest doll outward—first square $x$, then take sine, then exponentiate. When you differentiate, you have to unpack the dolls in the exact opposite order: you cannot touch the sine doll until you open the exponential doll on the outside, and you cannot touch $x^2$ until you open the sine doll. Each time you open a doll, you write down its derivative evaluated at whatever unopened dolls are still sitting inside, and multiply by the derivative of the next doll in line. Three layers to pack means three factors to multiply on the way out."
