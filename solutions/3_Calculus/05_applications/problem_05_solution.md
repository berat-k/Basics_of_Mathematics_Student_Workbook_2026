# Problem 05: Distance from Velocity

## 1. The Original Problem

The velocity of a car during the first five seconds is described by the function

$$
v(t) = 4t + 2 \quad [\mathrm{m/s}].
$$

Compute the distance traveled and explain why the integral of velocity gives the change in position.

Then answer what would have to be changed in the reasoning if the velocity also took negative values.

---

## 2. What Are We Trying to Find?

1. The distance traveled by the car over the time interval $t \in [0, 5]$ seconds, after checking the sign of $v(t)$ on $[0, 5]$.
2. A clear conceptual and mathematical explanation of why the definite integral $\int_a^b v(t)\,dt$ represents the change in position, or displacement, over $[a, b]$.
3. A complete explanation of how the reasoning and formula must change when $v(t)$ takes negative values on part of the interval, distinguishing net displacement from total distance traveled.

---

## 3. Before Calculating: What Idea Do We Need?

- **Velocity as the rate of change of position:** If $s(t)$ denotes the car's position along a straight road at time $t$, then $v(t) = s'(t)$.
- **Fundamental Theorem of Calculus:** Integrating the derivative of position recovers the net change in position:

$$
\int_a^b v(t)\,dt = \int_a^b s'(t)\,dt = s(b) - s(a) = \Delta s.
$$

- **Accumulation of infinitesimal displacements:** Over a tiny time step $\Delta t$, the velocity is nearly constant, so the car's signed change in position is $\Delta s_i \approx v(t_i^*)\,\Delta t$. Summing these contributions and taking the limit as $\Delta t \to 0$ yields the definite integral.
- **Displacement versus total distance traveled:**
  - **Displacement** is the net signed change in position: $\Delta s = \int_a^b v(t)\,dt$.
  - **Total distance traveled** is the total path length covered regardless of direction, obtained by integrating **speed** $|v(t)|$:

$$
\text{Distance} = \int_a^b |v(t)|\,dt.
$$

  When $v(t) \ge 0$ throughout $[a, b]$, we have $|v(t)| = v(t)$, so total distance equals displacement.

---

## 4. Step-by-Step Solution

### Step 1: Check the sign of $v(t)$ on $[0, 5]$ and compute the distance traveled

For all $t \in [0, 5]$, we have $t \ge 0$, and therefore:

$$
v(t) = 4t + 2 \ge 4(0) + 2 = 2 > 0.
$$

Because $v(t) > 0$ throughout the entire five-second interval, the car moves continuously in the positive direction and never reverses. Hence $|v(t)| = v(t)$ on $[0, 5]$, and the distance traveled $d$ equals the change in position $\Delta s$:

$$
d = \int_0^5 |v(t)|\,dt = \int_0^5 (4t + 2)\,dt.
$$

Find an antiderivative of $4t + 2$:

$$
S(t) = 2t^2 + 2t.
$$

Evaluate using the Fundamental Theorem of Calculus:

$$
\begin{aligned}
d &= \left[2t^2 + 2t\right]_0^5 \\
  &= \left(2 \cdot 5^2 + 2 \cdot 5\right) - \left(2 \cdot 0^2 + 2 \cdot 0\right) \\
  &= (50 + 10) - 0 \\
  &= 60\text{ m}.
\end{aligned}
$$

Thus, the car travels $60\text{ m}$ during the first five seconds.

### Step 2: Explain why the integral of velocity gives the change in position

There are two complementary ways to see why $\int_a^b v(t)\,dt = s(b) - s(a)$:

1. **Physical accumulation via Riemann sums:**
   If a car moved at a *constant* velocity $v$ over a time interval $\Delta t$, its change in position would be simply $\Delta s = v\,\Delta t$. When the velocity $v(t)$ varies continuously, we partition $[a, b]$ into $n$ very short subintervals of duration $\Delta t_i$. On the $i$-th tiny subinterval, $v(t)$ barely changes and can be approximated by a sample value $v(t_i^*)$, giving a small position change $\Delta s_i \approx v(t_i^*)\,\Delta t_i$. Adding all small changes gives the total change in position:

$$
s(b) - s(a) = \sum_{i=1}^n \Delta s_i \approx \sum_{i=1}^n v(t_i^*)\,\Delta t_i.
$$

   As the subintervals become arbitrarily thin, $\max \Delta t_i \to 0$, the approximation becomes exact and the Riemann sum converges to the definite integral $\int_a^b v(t)\,dt$.

2. **Exact mathematical link via the Fundamental Theorem of Calculus:**
   By definition, instantaneous velocity is the derivative of position, $v(t) = s'(t)$. Therefore $s(t)$ is an antiderivative of $v(t)$. The Fundamental Theorem of Calculus immediately states:

$$
\int_a^b v(t)\,dt = \int_a^b s'(t)\,dt = s(b) - s(a).
$$

   Geometrically, the signed area between the velocity graph $y = v(t)$ and the $t$-axis equals the net change in position.

### Step 3: What must change if the velocity also takes negative values?

If $v(t)$ becomes negative on parts of $[a, b]$, then the car moves in the **opposite direction** during those subintervals. Two crucial changes in reasoning are required:

1. **Distinguish displacement from total distance:**
   The plain integral $\int_a^b v(t)\,dt = s(b) - s(a)$ still equals the **net change in position**, also called **displacement**, because negative velocity contributes negative signed area that cancels out positive forward motion. For example, driving $30\text{ m}$ forward and then $30\text{ m}$ backward yields zero net displacement, even though the odometer records $60\text{ m}$ of travel.
2. **Integrate speed $|v(t)|$ instead of velocity $v(t)$ to get distance traveled:**
   Because every meter driven — whether forward or backward — adds positively to total distance, we must integrate the non-negative **speed** $|v(t)|$:

$$
d = \int_a^b |v(t)|\,dt.
$$

   In practice, to compute this integral when $v(t)$ changes sign on $[a, b]$, we must:
   - solve $v(t) = 0$ on $[a, b]$ to locate all instants where the car stops and potentially changes direction;
   - split $[a, b]$ at those zeros into subintervals on which $v(t)$ has a constant sign;
   - integrate $v(t)$ on intervals where $v(t) \ge 0$, integrate $-v(t)$ on intervals where $v(t) \le 0$ — equivalently, take the absolute value of each sub-integral — and sum all positive contributions.

For a concrete contrast, suppose instead that $v(t) = 2t - 4$ on $[0, 4]$. It changes sign at $t = 2$:
- net displacement: $\int_0^4 (2t - 4)\,dt = \left[t^2 - 4t\right]_0^4 = 0\text{ m}$, because the car backs up $4\text{ m}$ on $[0, 2]$ and drives forward $4\text{ m}$ on $[2, 4]$;
- total distance traveled: $\int_0^4 |2t - 4|\,dt = \int_0^2 (4 - 2t)\,dt + \int_2^4 (2t - 4)\,dt = 4 + 4 = 8\text{ m}$.

---

## 5. Final Answer & Conclusion

- **Distance traveled on $[0, 5]$:** $60\text{ m}$, since $v(t) = 4t + 2 > 0$ on $[0, 5]$ and $\int_0^5 (4t + 2)\,dt = 60$.
- **Why the integral of velocity gives change in position:** Because $v(t) = s'(t)$ is the instantaneous rate of change of position, summing tiny displacements $v(t)\,\Delta t$ yields $\int_a^b v(t)\,dt = s(b) - s(a)$ by the Fundamental Theorem of Calculus.
- **When $v(t)$ takes negative values:** The plain integral $\int_a^b v(t)\,dt$ gives only the **net displacement** because forward and backward motions cancel. To find the **total distance traveled**, one must integrate speed, $d = \int_a^b |v(t)|\,dt$, by finding the roots of $v(t) = 0$, splitting the interval where $v(t)$ changes sign, and summing the absolute values of the sub-integrals.

---

## 6. Quick Verification

1. **Geometric area check using a trapezoid:**
   The graph of $v(t) = 4t + 2$ on $[0, 5]$ is a straight line segment from $(0, 2)$ to $(5, 22)$, forming a trapezoid above the $t$-axis:

```text
v (m/s)
22 +                * (5, 22)
   |             *  |
   |          *     |
12 +       *  Area  |
   |    *    = 60 m |
 2 + * (0, 2)       |
 0 +-+--------------+---> t (s)
     0              5
```

   Its parallel vertical sides have lengths $v(0) = 2\text{ m/s}$ and $v(5) = 22\text{ m/s}$, and its base width is $5\text{ s}$. Thus its area is:

$$
\text{Area} = \frac{2 + 22}{2} \cdot 5 = 12 \cdot 5 = 60\text{ m}.
$$

2. **Kinematics formula for constant acceleration:**
   From $v(t) = 4t + 2$, the initial velocity is $v_0 = 2\text{ m/s}$ and the acceleration is constant at $a = v'(t) = 4\text{ m/s}^2$. By the elementary physics formula:

$$
\Delta s = v_0 t + \frac{1}{2}at^2 = 2(5) + \frac{1}{2}(4)(5^2) = 10 + 50 = 60\text{ m}.
$$

3. **Differentiation check:**
   For $S(t) = 2t^2 + 2t$, we have $S'(t) = 4t + 2 = v(t)$ and $S(5) - S(0) = 60 - 0 = 60$.

---

## 7. Common Mistakes to Avoid

- **Equating $\int_a^b v(t)\,dt$ with total distance without checking the sign of $v(t)$:** Here it happens to work *only* because $v(t) = 4t + 2 > 0$ on $[0, 5]$. Skipping the sign check becomes a fatal error as soon as $v(t)$ crosses zero.
- **Putting absolute value bars outside the whole integral:** Writing $\left|\int_a^b v(t)\,dt\right|$ instead of $\int_a^b |v(t)|\,dt$ still lets forward and backward movements cancel *before* taking the absolute value. The absolute value must go *inside* the integral.
- **Multiplying final velocity by total time:** Computing $v(5) \cdot 5 = 22 \cdot 5 = 110\text{ m}$ mistakenly assumes the car moved at its top speed for the entire $5\text{ s}$.
- **Omitting physical units:** Integrating velocity in $\mathrm{m/s}$ with respect to time in $\mathrm{s}$ yields $\mathrm{m/s} \cdot \mathrm{s} = \mathrm{m}$; always check that units combine consistently.

---

## 8. How I Would Explain This in Class

> "Imagine your car has two displays on the dashboard: a GPS coordinate showing how far east of your garage you are, and an odometer counting every meter your tires roll. The plain definite integral of velocity tracks the GPS coordinate — it adds meters when you drive east and subtracts meters when you put the car in reverse. In this problem, $v(t) = 4t + 2$ is always positive, so you never touch reverse and both displays read 60 meters after five seconds. The moment your velocity dips below zero, however, those two displays diverge: to read the odometer, you must replace velocity with speed, $|v(t)|$, splitting the trip wherever you stop to shift gears."
