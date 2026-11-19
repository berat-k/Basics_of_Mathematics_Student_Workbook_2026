# Problem 11: Derivative from the Definition

## 1. The Original Problem

Using only

$$
f'(x) = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h},
$$

find the derivative of $f(x) = x^2$. Compare the result with the power rule and indicate where the limit is used in the calculation.

---

## 2. What Are We Trying to Find?

1. The derivative $f'(x)$ of $f(x) = x^2$ derived directly from first principles using the limit definition of the derivative, without invoking any differentiation shortcut rules.
2. A clear comparison between the result obtained from the definition and the formula given by the power rule.
3. A precise explanation of where and how the limit $\lim_{h \to 0}$ is actually used in the calculation—including why we must simplify algebraically before taking the limit.

---

## 3. Before Calculating: What Idea Do We Need?

- **Difference quotient as a secant slope:** For any nonzero increment $h \ne 0$, the ratio

$$
\frac{f(x + h) - f(x)}{h}
$$

measures the slope of the secant line joining the points $(x, f(x))$ and $(x + h, f(x + h))$ on the graph of $f$.
- **Why direct substitution fails initially:** Setting $h = 0$ directly into the difference quotient produces $\frac{f(x) - f(x)}{0} = \frac{0}{0}$, an indeterminate form. Algebraic simplification is needed to cancel the factor $h$ in the denominator.
- **Role of $h \ne 0$ inside a limit:** In the definition of $\lim_{h \to 0}$, the variable $h$ approaches $0$ through nonzero values, never equaling $0$ during the approach. This guarantees that dividing numerator and denominator by $h$ is valid.
- **Holding $x$ fixed while $h \to 0$:** When computing $\lim_{h \to 0}$, the point $x$ is treated as a fixed constant while only $h$ varies.

---

## 4. Step-by-Step Solution

### Step 1: Set Up the Difference Quotient

For $f(x) = x^2$, replace the input $x$ with $x + h$ to get $f(x + h) = (x + h)^2$. Substituting into the definition of the derivative gives

$$
f'(x) = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h} = \lim_{h \to 0} \frac{(x + h)^2 - x^2}{h}.
$$

Note that we cannot substitute $h = 0$ yet because both the numerator and the denominator approach $0$, yielding the indeterminate form $\frac{0}{0}$.

### Step 2: Expand and Simplify Algebraically for $h \ne 0$

Expand the binomial $(x + h)^2 = x^2 + 2xh + h^2$:

$$
\frac{(x + h)^2 - x^2}{h} = \frac{(x^2 + 2xh + h^2) - x^2}{h} = \frac{2xh + h^2}{h}.
$$

Factor $h$ out of every remaining term in the numerator:

$$
\frac{2xh + h^2}{h} = \frac{h(2x + h)}{h}.
$$

Because the limit as $h \to 0$ evaluates the expression only for $h \ne 0$, we may legally cancel the common nonzero factor $h$:

$$
\frac{h(2x + h)}{h} = 2x + h \qquad \text{for all } h \ne 0.
$$

Up to this point, every step has been pure algebra; the limit has not been evaluated yet.

### Step 3: Take the Limit as $h \to 0$

Now substitute the simplified expression back into the limit:

$$
f'(x) = \lim_{h \to 0} (2x + h).
$$

Here is the exact place where the limit is used: treating $x$ as a fixed real number and letting $h \to 0$, the linear function $g(h) = 2x + h$ is continuous in $h$, so by the sum law for limits we obtain

$$
f'(x) = \lim_{h \to 0} (2x) + \lim_{h \to 0} h = 2x + 0 = 2x.
$$

### Step 4: Indicate Exactly Where the Limit Was Used

The limit plays two distinct, essential roles in the calculation:

1. **Before cancellation, justifying division by $h$:** Because $\lim_{h \to 0}$ considers only values of $h$ close to $0$ with $h \ne 0$, we are permitted to cancel $\frac{h}{h} = 1$ even though the original difference quotient is undefined at $h = 0$.
2. **After cancellation, collapsing the secant slope to the tangent slope:** In the final step

$$
\lim_{h \to 0} (2x + h) = 2x,
$$

the limit eliminates the residual term $+h$, turning the secant slope $2x + h$ into the exact instantaneous slope $2x$. Without the limit, the term $+h$ would remain, and we would only have an average rate of change over an interval of length $h$.

### Step 5: Compare with the Power Rule

The power rule states that for $f(x) = x^n$, the derivative is $f'(x) = nx^{n - 1}$. For $n = 2$, the power rule gives

$$
f'(x) = 2x^{2 - 1} = 2x^1 = 2x.
$$

The two results match identically. More importantly, this comparison shows that the power rule is not an arbitrary memorized recipe—the calculation from the limit definition is the actual proof of why the power rule works for $n = 2$.

---

## 5. Final Answer & Conclusion

- **Derivative from the definition:**

$$
f'(x) = \lim_{h \to 0} \frac{(x + h)^2 - x^2}{h} = \lim_{h \to 0} (2x + h) = 2x.
$$

- **Comparison with the power rule:** The result $2x$ agrees completely with the power rule applied to $x^2$, and serves as its derivation.
- **Where the limit is used:** First, the limit definition guarantees $h \ne 0$, which justifies canceling $h$ from $\frac{h(2x + h)}{h}$ to remove the $\frac{0}{0}$ indeterminacy. Second, the limit is actually evaluated in the final step $\lim_{h \to 0}(2x + h) = 2x$, where the term $h$ vanishes.

---

## 6. Quick Verification

1. **Alternative limit definition of the derivative:** Using the equivalent $t \to x$ formulation:

$$
f'(x) = \lim_{t \to x} \frac{f(t) - f(x)}{t - x} = \lim_{t \to x} \frac{t^2 - x^2}{t - x} = \lim_{t \to x} \frac{(t - x)(t + x)}{t - x} = \lim_{t \to x} (t + x) = 2x.
$$

Both limit formulations produce the exact same derivative $2x$.

2. **Numerical secant-slope check at $x = 3$:** Our formula predicts $f'(3) = 2(3) = 6$. Computing $\frac{(3 + h)^2 - 3^2}{h}$ directly:
  - For $h = 0.1$: $\frac{3.1^2 - 9}{0.1} = \frac{9.61 - 9}{0.1} = 6.1$.
  - For $h = 0.01$: $\frac{3.01^2 - 9}{0.01} = \frac{9.0601 - 9}{0.01} = 6.01$.
  - For $h = 0.001$: $\frac{3.001^2 - 9}{0.001} = \frac{9.006001 - 9}{0.001} = 6.001$.

The secant slopes march straight toward $6$ as $h \to 0$, confirming $f'(3) = 6$.

3. **Geometric area interpretation for $x > 0$:** Imagine a square of side length $x$, whose area is $A(x) = x^2$. Increasing the side length by a small amount $h > 0$ adds two thin rectangular strips of area $xh$ each, plus one tiny corner square of area $h^2$:

```text
+---------------+---+
|               | h |  <- top strip: area x*h, corner: area h^2
+---------------+---+
|               |   |
|    x^2        |x*h|  <- right strip: area x*h
|               |   |
+---------------+---+
```

Dividing the added area $2xh + h^2$ by $h$ gives $2x + h$, and as $h \to 0$ the tiny corner contribution $h$ vanishes, leaving the perimeter rate of growth $2x$.

---

## 7. Common Mistakes to Avoid

- **Expanding $(x + h)^2$ as $x^2 + h^2$:** Forgetting the middle term $2xh$ gives $\frac{h^2}{h} = h \to 0$, falsely claiming the derivative of $x^2$ is $0$. Always use $(x + h)^2 = x^2 + 2xh + h^2$.
- **Dropping the limit notation too early:** Writing $\frac{(x + h)^2 - x^2}{h} = 2x + h = 2x$ is logically wrong because $2x + h$ does not equal $2x$ unless $h = 0$. Keep writing $\lim_{h \to 0}$ on every line until the step where you actually evaluate the limit.
- **Plugging $h = 0$ in before canceling $h$:** Substituting $h = 0$ into $\frac{(x + h)^2 - x^2}{h}$ yields $\frac{0}{0}$, which is undefined and gives no information about the slope.
- **Writing $f(x + h) = x^2 + h$:** Replacing $x$ by $x + h$ means the *entire input* $x + h$ is squared, giving $(x + h)^2$, not $x^2 + h$.

---

## 8. How I Would Explain This in Class

> "Computing a derivative from the definition is a three-act play: expand, cancel, and then let $h$ vanish. When we write $\frac{(x + h)^2 - x^2}{h}$, the denominator $h$ is blocking us from plugging in $h = 0$. Expanding $(x + h)^2$ makes the $x^2$ terms cancel, leaving $2xh + h^2$—every surviving term contains an $h$, so the troublesome denominator divides out cleanly for $h \ne 0$, leaving $2x + h$. Only then does the limit step onto the stage: as $h$ shrinks to zero, the extra piece $+h$ melts away, leaving the exact slope $2x$ that the power rule promised all along."
