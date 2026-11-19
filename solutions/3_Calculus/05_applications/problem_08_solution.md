# Problem 08: Number of Requests Handled by a Server

## 1. The Original Problem

The rate at which requests arrive at a server during the first 5 minutes is described by the function

$$
r(t) = 100 + 20t \quad [\text{requests/min}], \qquad 0 \le t \le 5.
$$

1. Compute the total number of requests that arrived during this time.
2. Compute the average rate of incoming requests over this interval.
3. Compare the average rate with the values $r(0)$ and $r(5)$.

---

## 2. What Are We Trying to Find?

1. **Total accumulated requests:** Evaluate the definite integral of the arrival rate $r(t)$ over the time interval $[0, 5]$ to obtain the total number of requests received by the server.
2. **Average arrival rate:** Compute the average value of $r(t)$ on $[0, 5]$ by dividing the total number of requests by the duration of the interval.
3. **Comparison with endpoint values:** Compute $r(0)$ and $r(5)$, compare them with the average rate, and explain geometrically and algebraically why this relationship holds for a linear rate function.

---

## 3. Before Calculating: What Idea Do We Need?

- **Integral as accumulation of a rate:** When a quantity arrives at a continuous rate $r(t) \ge 0$ measured in $\text{requests/min}$, the total amount accumulated over an interval $[a, b]$ is given by the definite integral $\int_a^b r(t)\,dt$. Over a tiny time slice $dt$, approximately $r(t)\,dt$ requests arrive, and integration sums all these contributions.
- **Fundamental Theorem of Calculus:** If $F'(t) = r(t)$, then $\int_a^b r(t)\,dt = F(b) - F(a)$.
- **Average value of a continuous function:** The average value of $r(t)$ over $[a, b]$ is $\frac{1}{b - a}\int_a^b r(t)\,dt$. Physically, it is the constant arrival rate that would deliver the exact same total number of requests over the same time span.
- **Linearity and trapezoidal geometry:** Since $r(t) = 100 + 20t$ is linear and positive on $[0, 5]$, the region beneath its graph is a trapezoid, giving a direct geometric interpretation of both the total count and the average rate.

---

## 4. Step-by-Step Solution

### Step 1: Compute the Total Number of Requests

Because $r(t) = 100 + 20t > 0$ for all $t \in [0, 5]$, the total number of requests $R$ arriving during the first $5$ minutes is the definite integral of $r(t)$ from $t = 0$ to $t = 5$:

$$
R = \int_0^5 r(t)\,dt = \int_0^5 (100 + 20t)\,dt.
$$

An antiderivative of $100 + 20t$ is $F(t) = 100t + 10t^2$. Applying the Fundamental Theorem of Calculus yields

$$
R = \left[100t + 10t^2\right]_0^5 = \left(100 \cdot 5 + 10 \cdot 5^2\right) - \left(100 \cdot 0 + 10 \cdot 0^2\right) = 500 + 250 = 750.
$$

Therefore, a total of **$750$ requests** arrived at the server during the first $5$ minutes.

### Step 2: Compute the Average Rate of Incoming Requests

The average value of $r(t)$ over the interval $[0, 5]$ is

$$
r_{\text{avg}} = \frac{1}{5 - 0} \int_0^5 r(t)\,dt = \frac{750}{5} = 150\text{ requests/min}.
$$

In other words, a steady server load of $150\text{ requests/min}$ over $5$ minutes produces the exact same total of $750$ requests as the linearly increasing load $r(t) = 100 + 20t$.

### Step 3: Compare the Average Rate with $r(0)$ and $r(5)$

Evaluating the arrival rate at the two endpoints of the time interval $[0, 5]$ gives

$$
r(0) = 100 + 20(0) = 100\text{ requests/min},
$$

$$
r(5) = 100 + 20(5) = 200\text{ requests/min}.
$$

Comparing these values with the average rate $150\text{ requests/min}$, we see that

$$
r(0) = 100 < r_{\text{avg}} = 150 < r(5) = 200,
$$

and in fact the average rate is **exactly the arithmetic mean of the initial and final rates**:

$$
r_{\text{avg}} = \frac{r(0) + r(5)}{2} = \frac{100 + 200}{2} = 150\text{ requests/min}.
$$

Moreover, this average rate is attained precisely at the midpoint $t = 2.5\text{ min}$, since $r(2.5) = 100 + 20(2.5) = 150\text{ requests/min}$.

**Why does the arithmetic mean of the endpoints work here?** Because $r(t)$ is a **linear** function, its rate of increase is constant at $20\text{ requests/min}^2$. The deficit below $150\text{ requests/min}$ during the first half of the interval, namely on $[0, 2.5]$, is completely symmetric to the surplus above $150\text{ requests/min}$ during the second half, namely on $[2.5, 5]$.

```text
r(t) [requests/min]
200 |                         *  r(5) = 200
    |                      *  |
150 | - - - - - - - - - * - - |  r_avg = 150
    |               *   |     |
100 |            *      |     |  r(0) = 100
    |            |      |     |
  0 +------------+------+-----+----> t [min]
                 0     2.5    5
```

Important caution: this equality $r_{\text{avg}} = \frac{r(0) + r(5)}{2}$ is a special property of linear functions. For a nonlinear arrival rate, such as quadratic or exponential traffic growth, the average rate must be computed from the integral and generally does not equal the average of the endpoint values.

---

## 5. Final Answer & Conclusion

- **Total number of requests:** $750\text{ requests}$ arrived during the first $5$ minutes.
- **Average arrival rate:** $150\text{ requests/min}$ over the interval $[0, 5]$.
- **Comparison with endpoints:** We have $r(0) = 100\text{ requests/min}$ and $r(5) = 200\text{ requests/min}$. The average rate $150\text{ requests/min}$ lies exactly halfway between $r(0)$ and $r(5)$, which occurs because the arrival rate increases linearly with time.

---

## 6. Quick Verification

**Check 1 — Geometric trapezoid area check:** The region under $r(t) = 100 + 20t$ on $[0, 5]$ is a right trapezoid with parallel heights $r(0) = 100$ and $r(5) = 200$, and base width $5$. Its area is

$$
\text{Area} = \frac{100 + 200}{2} \cdot 5 = 150 \cdot 5 = 750\text{ requests}.
$$

Dividing by the duration $5\text{ min}$ confirms the average rate $150\text{ requests/min}$.

**Check 2 — Antiderivative and minute-by-minute check:** Differentiating $F(t) = 100t + 10t^2$ yields $F'(t) = 100 + 20t = r(t)$, verifying the antiderivative. Computing the requests arriving in each individual minute gives:

| Minute interval | Rate at start | Rate at end | Requests in minute |
| :--- | :---: | :---: | :---: |
| $[0, 1]$ | $100$ | $120$ | $110$ |
| $[1, 2]$ | $120$ | $140$ | $130$ |
| $[2, 3]$ | $140$ | $160$ | $150$ |
| $[3, 4]$ | $160$ | $180$ | $170$ |
| $[4, 5]$ | $180$ | $200$ | $190$ |

Summing the five minutes gives $110 + 130 + 150 + 170 + 190 = 750\text{ requests}$, and the mean of the five per-minute counts is $\frac{750}{5} = 150\text{ requests/min}$. Units also match cleanly: $[\text{requests/min}] \times [\text{min}] = [\text{requests}]$.

---

## 7. Common Mistakes to Avoid

- **Evaluating $r(5)$ instead of integrating:** The value $r(5) = 200$ is the instantaneous arrival rate at minute $5$, not the total number of requests. To get a total count from a rate, you must integrate.
- **Forgetting to divide by the interval length when computing the average rate:** The integral $\int_0^5 r(t)\,dt = 750$ gives total requests, not the average rate. You must divide by $5 - 0 = 5$ to obtain $150\text{ requests/min}$.
- **Differentiating $r(t)$ instead of integrating:** Computing $r'(t) = 20\text{ requests/min}^2$ finds the acceleration of traffic, not the total number of requests handled.
- **Assuming the average of endpoints works for every rate function:** While $\frac{r(0) + r(5)}{2}$ equals the true average rate here because $r(t)$ is linear, applying this shortcut to a curved rate function such as $r(t) = 100 + 20t^2$ produces the wrong answer.

---

## 8. How I Would Explain This in Class

> "Think of the server's traffic graph as a ramp that starts at a height of $100$ requests per minute and climbs smoothly in a straight line to $200$ requests per minute over $5$ minutes. The total number of requests handled is simply the area under that ramp, which is $750$ requests. Now imagine leveling the top of the ramp into a flat shelf without changing the total area: the triangular piece above the middle height of $150$ on the right fits upside-down with zero leftover space into the missing triangle on the left. That is why the average load is $150$ requests per minute, right in the middle of $100$ and $200$."
