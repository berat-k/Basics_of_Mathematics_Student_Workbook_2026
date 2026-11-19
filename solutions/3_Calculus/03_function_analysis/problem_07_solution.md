# Problem 07: A Trigonometric Function

## 1. The Original Problem

On $[0, 2\pi]$, find the intervals of monotonicity and the extrema of

$$
f(x) = \sin x + \cos x.
$$

Include the endpoints of the interval and compare the function values at the critical points and at the endpoints.

---

## 2. What Are We Trying to Find?

1. The first derivative $f'(x)$ of $f(x) = \sin x + \cos x$.
2. All critical points of $f$ in the open interval $(0, 2\pi)$.
3. The sign of $f'(x)$ on each subinterval of $[0, 2\pi]$ and the exact intervals of monotonicity.
4. The function values at every critical point and at both endpoints $x = 0$ and $x = 2\pi$.
5. A complete comparison of those values to classify all local extrema (interior and endpoint) and all global extrema on $[0, 2\pi]$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Extreme Value Theorem on a closed interval:** Since $f(x) = \sin x + \cos x$ is continuous on the closed and bounded interval $[0, 2\pi]$, it is guaranteed to attain both a global maximum and a global minimum on $[0, 2\pi]$.
- **Candidates for extrema on $[a, b]$:** Global extrema on a closed interval can occur only at interior critical points or at the endpoints $a$ and $b$. Furthermore, endpoints can be *local* extrema relative to the restricted domain $[0, 2\pi]$ depending on whether $f$ increases or decreases away from the endpoint.
- **Solving $\cos x = \sin x$ safely:** Verify that $\cos x = 0$ is never a solution before dividing both sides by $\cos x$ to rewrite the equation as $\tan x = 1$.
- **Phase-shift insight for verification:** Using the angle-addition identity, $\sin x + \cos x = \sqrt{2}\sin\left(x + \frac{\pi}{4}\right)$, which immediately explains why the amplitude is $\sqrt{2}$ and why the peaks and troughs sit at $x = \frac{\pi}{4}$ and $x = \frac{5\pi}{4}$.

---

## 4. Step-by-Step Solution

### Step 1: Derivative and Interior Critical Points

The function $f(x) = \sin x + \cos x$ is continuous on $[0, 2\pi]$ and differentiable everywhere, with derivative

$$
f'(x) = \cos x - \sin x.
$$

To find the critical points in $(0, 2\pi)$, we solve $f'(x) = 0$:

$$
\cos x - \sin x = 0 \iff \sin x = \cos x.
$$

Notice that if $\cos x = 0$, then $\sin x = \pm 1 \ne 0$, so $\cos x = 0$ is not a solution. We may therefore divide both sides by $\cos x \ne 0$ to obtain

$$
\tan x = 1.
$$

Since $\tan x$ has period $\pi$ and $\tan\left(\frac{\pi}{4}\right) = 1$, the solutions in $[0, 2\pi]$ are

$$
x_1 = \frac{\pi}{4} \quad \text{and} \quad x_2 = \frac{\pi}{4} + \pi = \frac{5\pi}{4}.
$$

Both lie strictly inside $(0, 2\pi)$.

### Step 2: Sign of $f'(x)$ and Intervals of Monotonicity

The two critical numbers divide $[0, 2\pi]$ into three subintervals: $\left[0, \frac{\pi}{4}\right]$, $\left[\frac{\pi}{4}, \frac{5\pi}{4}\right]$, and $\left[\frac{5\pi}{4}, 2\pi\right]$. Testing one simple point in each subinterval gives the sign of $f'(x) = \cos x - \sin x$:

- On $\left[0, \frac{\pi}{4}\right)$, test $x = 0$: $f'(0) = \cos 0 - \sin 0 = 1 - 0 = 1 > 0$.
- On $\left(\frac{\pi}{4}, \frac{5\pi}{4}\right)$, test $x = \frac{\pi}{2}$: $f'\left(\frac{\pi}{2}\right) = \cos\left(\frac{\pi}{2}\right) - \sin\left(\frac{\pi}{2}\right) = 0 - 1 = -1 < 0$.
- On $\left(\frac{5\pi}{4}, 2\pi\right]$, test $x = \frac{3\pi}{2}$: $f'\left(\frac{3\pi}{2}\right) = \cos\left(\frac{3\pi}{2}\right) - \sin\left(\frac{3\pi}{2}\right) = 0 - (-1) = 1 > 0$.

| Interval / Point | $x = 0$ | $\left(0, \frac{\pi}{4}\right)$ | $x = \frac{\pi}{4}$ | $\left(\frac{\pi}{4}, \frac{5\pi}{4}\right)$ | $x = \frac{5\pi}{4}$ | $\left(\frac{5\pi}{4}, 2\pi\right)$ | $x = 2\pi$ |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of $f'(x)$ | $+$ | $+$ | $0$ | $-$ | $0$ | $+$ | $+$ |
| Behavior of $f(x)$ | Endpoint min: $1$ | Increasing | Global max: $\sqrt{2}$ | Decreasing | Global min: $-\sqrt{2}$ | Increasing | Endpoint max: $1$ |

Therefore, on $[0, 2\pi]$:

- $f$ is **strictly increasing** on $\left[0, \frac{\pi}{4}\right]$ and on $\left[\frac{5\pi}{4}, 2\pi\right]$.
- $f$ is **strictly decreasing** on $\left[\frac{\pi}{4}, \frac{5\pi}{4}\right]$.

### Step 3: Function Values at Critical Points and Endpoints

We compute $f(x) = \sin x + \cos x$ at all four key points:

- **Left endpoint $x = 0$:**

$$
f(0) = \sin 0 + \cos 0 = 0 + 1 = 1.
$$

- **First critical point $x = \frac{\pi}{4}$:**

$$
f\left(\frac{\pi}{4}\right) = \sin\left(\frac{\pi}{4}\right) + \cos\left(\frac{\pi}{4}\right) = \frac{\sqrt{2}}{2} + \frac{\sqrt{2}}{2} = \sqrt{2} \approx 1.4142.
$$

- **Second critical point $x = \frac{5\pi}{4}$:**

$$
f\left(\frac{5\pi}{4}\right) = \sin\left(\frac{5\pi}{4}\right) + \cos\left(\frac{5\pi}{4}\right) = -\frac{\sqrt{2}}{2} - \frac{\sqrt{2}}{2} = -\sqrt{2} \approx -1.4142.
$$

- **Right endpoint $x = 2\pi$:**

$$
f(2\pi) = \sin(2\pi) + \cos(2\pi) = 0 + 1 = 1.
$$

### Step 4: Comparison of Values and Classification of Extrema

Comparing all four values gives the strict ordering

$$
f\left(\frac{5\pi}{4}\right) = -\sqrt{2} < f(0) = f(2\pi) = 1 < \sqrt{2} = f\left(\frac{\pi}{4}\right).
$$

This yields the complete classification of extrema on $[0, 2\pi]$:

1. **Global and local maximum:** Attained at the interior critical point $x = \frac{\pi}{4}$, with maximum value $\sqrt{2}$.
2. **Global and local minimum:** Attained at the interior critical point $x = \frac{5\pi}{4}$, with minimum value $-\sqrt{2}$.
3. **Left endpoint $x = 0$:** Because $f$ is strictly increasing on $\left[0, \frac{\pi}{4}\right]$, we have $f(0) < f(x)$ for all $x \in \left(0, \frac{\pi}{4}\right]$, so $x = 0$ is a **local minimum on $[0, 2\pi]$** with value $1$. However, since $1 > -\sqrt{2}$, it is **not** the global minimum.
4. **Right endpoint $x = 2\pi$:** Because $f$ is strictly increasing on $\left[\frac{5\pi}{4}, 2\pi\right]$, we have $f(x) < f(2\pi)$ for all $x \in \left[\frac{5\pi}{4}, 2\pi\right)$, so $x = 2\pi$ is a **local maximum on $[0, 2\pi]$** with value $1$. However, since $1 < \sqrt{2}$, it is **not** the global maximum.
5. **Periodicity comparison:** Both endpoints share the exact same height $f(0) = f(2\pi) = 1$ because $f$ is $2\pi$-periodic, and both lie strictly between the global minimum $-\sqrt{2}$ and the global maximum $\sqrt{2}$.

---

## 5. Final Answer & Conclusion

- **Derivative:** $f'(x) = \cos x - \sin x$.
- **Critical points in $[0, 2\pi]$:** $x = \frac{\pi}{4}$ and $x = \frac{5\pi}{4}$.
- **Monotonicity on $[0, 2\pi]$:**
  - Strictly increasing on $\left[0, \frac{\pi}{4}\right]$ and on $\left[\frac{5\pi}{4}, 2\pi\right]$.
  - Strictly decreasing on $\left[\frac{\pi}{4}, \frac{5\pi}{4}\right]$.
- **Comparison of values:**
  - $f(0) = 1$, $f\left(\frac{\pi}{4}\right) = \sqrt{2}$, $f\left(\frac{5\pi}{4}\right) = -\sqrt{2}$, $f(2\pi) = 1$.
  - Ordering: $-\sqrt{2} < 1 < \sqrt{2}$.
- **Extrema on $[0, 2\pi]$:**
  - Global and local maximum: $\sqrt{2}$ at $x = \frac{\pi}{4}$.
  - Global and local minimum: $-\sqrt{2}$ at $x = \frac{5\pi}{4}$.
  - Endpoint local minimum: $1$ at $x = 0$ (not global).
  - Endpoint local maximum: $1$ at $x = 2\pi$ (not global).

---

## 6. Quick Verification

1. **Trigonometric amplitude-phase identity:** Factoring out $\sqrt{2}$ gives

$$
f(x) = \sqrt{2}\left(\sin x \cdot \frac{\sqrt{2}}{2} + \cos x \cdot \frac{\sqrt{2}}{2}\right) = \sqrt{2}\left(\sin x \cos\frac{\pi}{4} + \cos x \sin\frac{\pi}{4}\right) = \sqrt{2}\sin\left(x + \frac{\pi}{4}\right).
$$

Since $-1 \le \sin\theta \le 1$, the maximum value is $\sqrt{2}$ when $x + \frac{\pi}{4} = \frac{\pi}{2}$, i.e., $x = \frac{\pi}{4}$, and the minimum value is $-\sqrt{2}$ when $x + \frac{\pi}{4} = \frac{3\pi}{2}$, i.e., $x = \frac{5\pi}{4}$. This confirms every result independently!
2. **Second Derivative Test:** $f''(x) = -\sin x - \cos x = -f(x)$. Hence $f''\left(\frac{\pi}{4}\right) = -\sqrt{2} < 0$ (local max) and $f''\left(\frac{5\pi}{4}\right) = +\sqrt{2} > 0$ (local min).

---

## 7. Common Mistakes to Avoid

- **Missing the second solution $x = \frac{5\pi}{4}$ of $\tan x = 1$:** Students often recall only the first-quadrant angle $\frac{\pi}{4}$ and forget the third-quadrant angle $\frac{5\pi}{4} \in [0, 2\pi]$, where both $\sin x$ and $\cos x$ are negative and equal.
- **Ignoring the endpoints $x = 0$ and $x = 2\pi$:** On a closed interval $[a, b]$, you must always evaluate $f(a)$ and $f(b)$ and compare them with the interior critical values; here the endpoints turn out to be non-global local extrema.
- **Guessing the maximum of $\sin x + \cos x$ is $2$:** Although $\max(\sin x) = 1$ and $\max(\cos x) = 1$, they never reach $1$ at the same $x$ because $\sin^2 x + \cos^2 x = 1$. The true maximum is $\sqrt{2} \approx 1.414$, not $2$.
- **Writing the increasing region as a union $\left[0, \frac{\pi}{4}\right] \cup \left[\frac{5\pi}{4}, 2\pi\right]$:** Even though $f$ increases on both subintervals, $f\left(\frac{\pi}{4}\right) = \sqrt{2} > -\sqrt{2} = f\left(\frac{5\pi}{4}\right)$, so list the two intervals separately.

---

## 8. How I Would Explain This in Class

> "Students are often surprised that $\sin x + \cos x$ never reaches $2$—they peak at different times, like two runners who never hit top speed simultaneously. Their best combined effort happens halfway between their peaks at $x = \frac{\pi}{4}$, reaching $\sqrt{2}$, and half a circle later at $x = \frac{5\pi}{4}$ they hit their lowest combined dip at $-\sqrt{2}$. On the closed window $[0, 2\pi]$, the curve enters at height $1$ while already climbing, goes over the peak $\sqrt{2}$, dives into the valley $-\sqrt{2}$, and climbs right back to height $1$ at the exit gate—so the endpoints create local corners at height $1$, while the true global champion and lowest point sit safely inside."
