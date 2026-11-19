# Problem 01: Motion — from Position to Velocity

## 1. The Original Problem

The position of a point is described by

$$
s(t) = t^3 - 6t^2 + 9t + 2, \qquad t \ge 0.
$$

1. Determine the velocity and acceleration.
2. Find the times at which the point stops.
3. Determine on which intervals the point moves in the positive direction of the axis and on which intervals it moves in the negative direction.

---

## 2. What Are We Trying to Find?

1. Explicit formulas for the instantaneous velocity function $v(t)$ and the instantaneous acceleration function $a(t)$ for $t \ge 0$.
2. All non-negative times $t \ge 0$ at which the point is instantaneously at rest, meaning $v(t) = 0$.
3. The time intervals on $[0, \infty)$ where the point moves in the positive direction of the coordinate axis, meaning $v(t) > 0$, and the intervals where it moves in the negative direction, meaning $v(t) < 0$.

---

## 3. Before Calculating: What Idea Do We Need?

- **Kinematics via derivatives:** If $s(t)$ gives the signed position of a particle along a coordinate axis at time $t$, then:
  - the **velocity** is the first derivative of position with respect to time: $v(t) = s'(t)$;
  - the **acceleration** is the derivative of velocity, or the second derivative of position: $a(t) = v'(t) = s''(t)$.
- **Stopping times:** A particle stops instantaneously when its velocity is zero, so we solve $v(t) = 0$ within the physical time domain $t \ge 0$.
- **Direction of motion from the sign of $v(t)$:**
  - When $v(t) > 0$, the position $s(t)$ is strictly increasing, so the point moves in the **positive direction** of the axis.
  - When $v(t) < 0$, the position $s(t)$ is strictly decreasing, so the point moves in the **negative direction** of the axis.
- **Factoring polynomials for sign analysis:** Because $s(t)$ is a cubic polynomial, $v(t)$ is a quadratic polynomial. Factoring $v(t)$ makes finding its roots and building a sign chart straightforward and error-free.

---

## 4. Step-by-Step Solution

### Step 1: Determine the velocity and acceleration

We differentiate the position function $s(t) = t^3 - 6t^2 + 9t + 2$ term by term using the power rule and constant rule.

First, compute the velocity $v(t) = s'(t)$:

$$
v(t) = s'(t) = \frac{d}{dt}\left(t^3 - 6t^2 + 9t + 2\right) = 3t^2 - 12t + 9, \qquad t \ge 0.
$$

Next, differentiate $v(t)$ to find the acceleration $a(t) = v'(t) = s''(t)$:

$$
a(t) = v'(t) = \frac{d}{dt}\left(3t^2 - 12t + 9\right) = 6t - 12, \qquad t \ge 0.
$$

We can also write both functions in factored form for clarity:

$$
v(t) = 3(t - 1)(t - 3), \qquad a(t) = 6(t - 2).
$$

### Step 2: Find the times at which the point stops

The point stops when its instantaneous velocity equals zero, that is, $v(t) = 0$:

$$
3t^2 - 12t + 9 = 0.
$$

Divide both sides by $3$:

$$
t^2 - 4t + 3 = 0.
$$

Factor the quadratic expression:

$$
(t - 1)(t - 3) = 0.
$$

This gives two solutions:

$$
t = 1 \qquad \text{or} \qquad t = 3.
$$

Both values satisfy the domain condition $t \ge 0$. Therefore, the point stops instantaneously at $t = 1$ and at $t = 3$.

At these stopping times, the positions and accelerations are:
- at $t = 1$: $s(1) = 1 - 6 + 9 + 2 = 6$, and $a(1) = 6(1) - 12 = -6 < 0$;
- at $t = 3$: $s(3) = 27 - 54 + 27 + 2 = 2$, and $a(3) = 6(3) - 12 = 6 > 0$.

Because the acceleration is nonzero at both moments, the point does not remain at rest; instead, it reverses direction immediately at both $t = 1$ and $t = 3$.

### Step 3: Determine the intervals of positive and negative motion

The roots $t = 1$ and $t = 3$ divide the time domain $[0, \infty)$ into three subintervals: $[0, 1)$, $(1, 3)$, and $(3, \infty)$. Note that at the initial instant $t = 0$, the velocity is $v(0) = 9 > 0$, so the point starts moving in the positive direction immediately from $t = 0$.

We analyze the sign of $v(t) = 3(t - 1)(t - 3)$ on each subinterval:

| Time interval or point | Sign of $t - 1$ | Sign of $t - 3$ | Sign of $v(t) = 3(t - 1)(t - 3)$ | Direction of motion |
| :--- | :---: | :---: | :---: | :--- |
| $t = 0$ | $-$ | $-$ | $+$ with $v(0) = 9$ | Starts moving in positive direction |
| $0 \le t < 1$ | $-$ | $-$ | $+$ | Positive direction, $s(t)$ increases from $2$ to $6$ |
| $t = 1$ | $0$ | $-$ | $0$ | Instantaneous stop at $s(1) = 6$, turns around |
| $1 < t < 3$ | $+$ | $-$ | $-$ | Negative direction, $s(t)$ decreases from $6$ to $2$ |
| $t = 3$ | $+$ | $0$ | $0$ | Instantaneous stop at $s(3) = 2$, turns around |
| $t > 3$ | $+$ | $+$ | $+$ | Positive direction, $s(t)$ increases without bound |

A schematic picture of the back-and-forth motion along the $s$-axis illustrates the trajectory:

```text
s-axis:     0         2         4         6         8  ---> +s
                      *==================>*
                    t=0 (s=2)           t=1 (s=6), stops & reverses
                      *<==================*
                    t=3 (s=2), stops & reverses
                      *===================================>
                    t>3 (moves in positive direction forever)
```

Thus:
- The point moves in the **positive direction** on $[0, 1)$ and $(3, \infty)$, where $v(t) > 0$. If strictly open intervals are preferred for monotonicity statements, one may also write $(0, 1)$ and $(3, \infty)$, noting that $v(0) = 9 > 0$ as well.
- The point moves in the **negative direction** on $(1, 3)$, where $v(t) < 0$.

---

## 5. Final Answer & Conclusion

1. **Velocity and acceleration:**

$$
v(t) = 3t^2 - 12t + 9, \qquad a(t) = 6t - 12 \qquad \text{for } t \ge 0.
$$

2. **Stopping times:** The point stops instantaneously at $t = 1$ and $t = 3$.
3. **Direction of motion:**
   - **Positive direction:** on $[0, 1)$ and $(3, \infty)$.
   - **Negative direction:** on $(1, 3)$.

---

## 6. Quick Verification

1. **Check velocity by test points and position values:**
   - At $t = 0$: $s(0) = 2$ and $v(0) = 9 > 0$.
   - At $t = 0.5$: $v(0.5) = 3(0.25) - 6 + 9 = 3.75 > 0$, and $s(0.5) = 0.125 - 1.5 + 4.5 + 2 = 5.125$, indeed rising from $s(0) = 2$ toward $s(1) = 6$.
   - At $t = 2$: $v(2) = 3(4) - 24 + 9 = -3 < 0$, and $s(2) = 8 - 24 + 18 + 2 = 4$, indeed falling from $s(1) = 6$ toward $s(3) = 2$.
   - At $t = 4$: $v(4) = 3(16) - 48 + 9 = 9 > 0$, and $s(4) = 64 - 96 + 36 + 2 = 6$, indeed rising again from $s(3) = 2$.
2. **Check algebraic consistency via integration:**
   Integrating $a(t) = 6t - 12$ gives $v(t) = 3t^2 - 12t + C_1$. Since $v(0) = 9$, we recover $v(t) = 3t^2 - 12t + 9$. Integrating again gives $s(t) = t^3 - 6t^2 + 9t + C_2$, and with $s(0) = 2$ we recover the original $s(t)$.
3. **Check vertex symmetry of the parabola $v(t)$:**
   The quadratic $v(t) = 3t^2 - 12t + 9$ opens upward with vertex at $t = \frac{12}{6} = 2$, which is the exact midpoint of the roots $t = 1$ and $t = 3$, and coincides with the zero of $a(t) = 6t - 12$.

---

## 7. Common Mistakes to Avoid

- **Confusing the sign of position $s(t)$ with the direction of motion:** Even on $(1, 3)$ where the point moves backward, its position $s(t)$ remains positive, between $2$ and $6$. Position tells you *where* the point is; the sign of $v(t) = s'(t)$ tells you *which way* it is moving.
- **Confusing stopping with zero acceleration:** Setting $a(t) = 0$ gives $t = 2$, where $v(2) = -3 \ne 0$. At $t = 2$ the point is moving at its fastest speed in the negative direction, not stopping! Zero acceleration means constant instantaneous velocity, not zero velocity.
- **Forgetting the domain restriction $t \ge 0$:** Without checking $t \ge 0$, students sometimes write $(-\infty, 1)$ instead of $[0, 1)$ for the first positive-motion interval.
- **Including $t = 1$ or $t = 3$ as times of positive or negative motion:** At $t = 1$ and $t = 3$, the velocity is $0$, so the point is momentarily stationary rather than moving in either direction.

---

## 8. How I Would Explain This in Class

> "Think of $s(t)$ as the milepost marker you pass on a straight highway, and $v(t) = s'(t)$ as your speedometer with a plus or minus sign attached. You do not care whether you are at milepost 2 or milepost 6 when deciding whether you are driving forward or in reverse — you only look at the sign of your velocity. Whenever $v(t)$ crosses zero, your car briefly hits zero speed and switches gears: here you drive forward from milepost 2 to milepost 6 during the first second, stop at $t = 1$, back up to milepost 2 between $t = 1$ and $t = 3$, stop again at $t = 3$, and then drive forward forever."
