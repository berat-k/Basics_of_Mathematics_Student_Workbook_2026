# Problem 10: A Cable Through Water and Land

## 1. The Original Problem

Point $A$ lies on one bank of a river of width $100$ m, and point $B$ lies on the other bank, $500$ m along the bank from the point directly opposite $A$.

The cost per meter of cable underwater is twice the cost per meter of cable on land.

Build a cost function depending on the point where the cable comes out of the water, determine the domain, and find the solution that minimizes the cost.

---

## 2. What Are We Trying to Find?

1. **Geometric model and cost function:** Introduce a variable $x$ locating where the cable exits the water on the opposite bank, express the underwater and overland lengths in terms of $x$, and construct the total cost function $C(x)$.
2. **Domain:** Determine the physically meaningful closed interval for $x$ and explain why points outside it cannot be optimal.
3. **Optimal landing point:** Differentiate $C(x)$, solve $C'(x) = 0$, and find both the exact and decimal values of the optimal distance $x^*$.
4. **Verification and minimum cost:** Prove that $x^*$ achieves the global minimum on the domain using the second derivative and endpoint comparison, and report the optimal underwater length, overland length, and minimum total cost.

---

## 3. Before Calculating: What Idea Do We Need?

- **Coordinate setup and the Pythagorean theorem:** Let $O$ be the point on the far bank directly opposite $A$, so segment $AO$ is perpendicular to the riverbanks and has length $100\text{ m}$. If the cable exits the water at a point $P$ located $x\text{ m}$ from $O$ toward $B$, then triangle $AOP$ is a right triangle with legs $100\text{ m}$ and $x\text{ m}$, so the straight underwater path $AP$ has length $\sqrt{100^2 + x^2}\text{ m}$. The remaining straight path $PB$ along the bank has length $500 - x\text{ m}$.
- **Modeling relative unit costs:** Let $c > 0$ denote the cost per meter of cable laid on land. Since underwater cable costs twice as much per meter, its unit cost is $2c$. Because $c$ is a positive constant factor multiplying the entire cost function, the optimal location $x^*$ depends only on the $2:1$ cost ratio, not on the specific value of $c$.
- **Closed-interval optimization:** On a closed interval $[0, 500]$, a continuous function that is differentiable on $(0, 500)$ attains its global minimum either at an interior critical point where $C'(x) = 0$ or at one of the endpoints $x = 0$ or $x = 500$.
- **Chain rule for square roots:** We differentiate $\sqrt{u(x)}$ via $\frac{d}{dx}\left(\sqrt{u(x)}\right) = \frac{u'(x)}{2\sqrt{u(x)}}$.

---

## 4. Step-by-Step Solution

### Step 1: Draw the Geometry and Define Variables

Model the river as a strip of uniform width $100\text{ m}$ bounded by two parallel straight banks:

```text
  Near bank:    A
                |\
                | \
       100 m    |  \  sqrt(100^2 + x^2)   [underwater, cost 2c per m]
                |   \
                |    \
  Far bank:     O-----P----------------------B
                <- x -><------ 500 - x ------>
                                           [on land, cost c per m]
                <----------- 500 m ---------->
```

- $O$ is the point on the far bank directly across from $A$, with $AO = 100\text{ m}$.
- $P$ is the point on the far bank where the cable comes out of the water, at distance $x$ meters from $O$ in the direction of $B$.
- $c > 0$ is the cost per meter of cable on land, so $2c$ is the cost per meter of cable underwater.

By the Pythagorean theorem applied to right triangle $AOP$:

- **Underwater cable length:** $L_{\text{water}}(x) = \sqrt{100^2 + x^2} = \sqrt{10000 + x^2}\text{ m}$.
- **On-land cable length:** $L_{\text{land}}(x) = 500 - x\text{ m}$.

### Step 2: Build the Cost Function and Determine Its Domain

Multiplying each length by its unit cost and adding gives the total cost function:

$$
C(x) = 2c\sqrt{10000 + x^2} + c(500 - x) = c\left(2\sqrt{10000 + x^2} + 500 - x\right).
$$

**Domain:** The point $P$ should lie on the segment $OB$, giving the closed domain

$$
x \in [0, 500].
$$

Why can no point outside $[0, 500]$ minimize the cost?

- If $x < 0$, the cable heads upstream away from $B$, making *both* the underwater segment longer than $100\text{ m}$ and the overland segment longer than $500\text{ m}$, which is strictly more expensive than choosing $x = 0$.
- If $x > 500$, the cable overshoots $B$ underwater, making the underwater segment longer than at $x = 500$ while also adding extra overland backtracking of length $x - 500 > 0$, which is strictly more expensive than choosing $x = 500$.

Thus the global minimum must occur in $[0, 500]$.

### Step 3: Differentiate $C(x)$ and Find the Critical Point

Differentiating $C(x)$ with respect to $x$ for $x \in (0, 500)$ using the chain rule gives

$$
C'(x) = c\left(2 \cdot \frac{2x}{2\sqrt{10000 + x^2}} - 1\right) = c\left(\frac{2x}{\sqrt{10000 + x^2}} - 1\right).
$$

Since $c > 0$, setting $C'(x) = 0$ yields

$$
\frac{2x}{\sqrt{10000 + x^2}} - 1 = 0 \implies 2x = \sqrt{10000 + x^2}.
$$

Because the square root is strictly positive, any solution must satisfy $x > 0$. Squaring both sides gives

$$
4x^2 = 10000 + x^2 \implies 3x^2 = 10000 \implies x^2 = \frac{10000}{3}.
$$

Taking the positive square root produces the unique critical point in $[0, 500]$:

$$
x^* = \frac{100}{\sqrt{3}} = \frac{100\sqrt{3}}{3} \approx 57.7350\text{ m} \approx 57.74\text{ m}.
$$

Indeed, $0 < 57.74 < 500$, so $x^*$ lies strictly inside the domain. Checking the unsquared equation confirms there is no extraneous root:

$$
\frac{2x^*}{\sqrt{10000 + (x^*)^2}} = \frac{200/\sqrt{3}}{\sqrt{10000 + 10000/3}} = \frac{200/\sqrt{3}}{\sqrt{40000/3}} = \frac{200/\sqrt{3}}{200/\sqrt{3}} = 1.
$$

### Step 4: Verify That $x^*$ Gives the Global Minimum

Compute the second derivative of $C(x)$ using the quotient rule on $\frac{2x}{(10000 + x^2)^{1/2}}$:

$$
C''(x) = c \cdot \frac{2\sqrt{10000 + x^2} - 2x \cdot \frac{x}{\sqrt{10000 + x^2}}}{10000 + x^2} = c \cdot \frac{2(10000 + x^2) - 2x^2}{(10000 + x^2)^{3/2}} = \frac{20000\,c}{(10000 + x^2)^{3/2}}.
$$

Since $c > 0$ and $(10000 + x^2)^{3/2} > 0$, we have $C''(x) > 0$ for **all** $x \in [0, 500]$. At $x^* = \frac{100}{\sqrt{3}}$,

$$
C''(x^*) = \frac{20000\,c}{(40000/3)^{3/2}} = \frac{3\sqrt{3}}{400}\,c \approx 0.01299\,c > 0.
$$

Thus $C(x)$ is strictly convex on $[0, 500]$. Equivalently, $C'(x) < 0$ on $[0, x^*)$ and $C'(x) > 0$ on $(x^*, 500]$:

| Interval or point | Sign of $C'(x)$ | Behavior of $C(x)$ |
| :--- | :---: | :--- |
| $0 \le x < \frac{100}{\sqrt{3}}$ | $-$ | Strictly decreasing |
| $x = \frac{100}{\sqrt{3}}$ | $0$ | Unique global minimum |
| $\frac{100}{\sqrt{3}} < x \le 500$ | $+$ | Strictly increasing |

### Step 5: Compute the Optimal Lengths, Minimum Cost, and Compare Endpoints

At $x^* = \frac{100}{\sqrt{3}} \approx 57.74\text{ m}$, we compute the segment lengths and total cost.

**Optimal underwater length:**

$$
\sqrt{100^2 + \left(\frac{100}{\sqrt{3}}\right)^2} = \sqrt{\frac{40000}{3}} = \frac{200}{\sqrt{3}} = \frac{200\sqrt{3}}{3} \approx 115.47\text{ m}.
$$

**Optimal on-land length:**

$$
500 - \frac{100}{\sqrt{3}} = 500 - \frac{100\sqrt{3}}{3} \approx 442.26\text{ m}.
$$

**Minimum total cost:**

$$
C(x^*) = c\left(2 \cdot \frac{200}{\sqrt{3}} + 500 - \frac{100}{\sqrt{3}}\right) = c\left(500 + \frac{300}{\sqrt{3}}\right) = c\left(500 + 100\sqrt{3}\right) \approx 673.21\,c.
$$

Comparing with the two extreme strategies at the endpoints of $[0, 500]$:

**Endpoint $x = 0$, straight across then along the bank:**

$$
C(0) = c\left(2\sqrt{10000} + 500\right) = 700\,c.
$$

**Endpoint $x = 500$, straight underwater from $A$ to $B$:**

$$
C(500) = c\left(2\sqrt{100^2 + 500^2} + 0\right) = 200\sqrt{26}\,c \approx 1019.80\,c.
$$

Since $673.21\,c < 700\,c < 1019.80\,c$, the interior point $x^* = \frac{100}{\sqrt{3}}\text{ m}$ is confirmed as the global minimum, saving approximately $26.79\,c$ compared to going straight across and approximately $346.60\,c$ compared to going directly underwater.

---

## 5. Final Answer & Conclusion

- **Cost function:** With land unit cost $c > 0$ and underwater unit cost $2c$, the total cost is $C(x) = c\left(2\sqrt{10000 + x^2} + 500 - x\right)$ on the domain $x \in [0, 500]$.
- **Optimal exit point:** The cable should leave the water at $x^* = \frac{100}{\sqrt{3}} = \frac{100\sqrt{3}}{3} \approx 57.74\text{ m}$ along the opposite bank from the point directly across from $A$.
- **Optimal cable segments:** $\frac{200}{\sqrt{3}} \approx 115.47\text{ m}$ underwater and $500 - \frac{100}{\sqrt{3}} \approx 442.26\text{ m}$ on land.
- **Minimum total cost:** Exact minimum cost $c\left(500 + 100\sqrt{3}\right) \approx 673.21\,c$.

---

## 6. Quick Verification

**Check 1 — Numerical table around $x^* \approx 57.74\text{ m}$:** Evaluating the dimensionless cost $C(x)/c = 2\sqrt{10000 + x^2} + 500 - x$ at values bracketing the optimum confirms the minimum:

| $x$ in m | Underwater length in m | On-land length in m | Cost $C(x)/c$ |
| :---: | :---: | :---: | :---: |
| $0.00$ | $100.0000$ | $500.0000$ | $700.0000$ |
| $40.00$ | $107.7033$ | $460.0000$ | $675.4066$ |
| $50.00$ | $111.8034$ | $450.0000$ | $673.6068$ |
| $55.00$ | $114.1271$ | $445.0000$ | $673.2542$ |
| **$57.74$** | **$115.4701$** | **$442.2650$** | **$673.2051$** |
| $60.00$ | $116.6190$ | $440.0000$ | $673.2381$ |
| $70.00$ | $122.0656$ | $430.0000$ | $674.1311$ |
| $100.00$ | $141.4214$ | $400.0000$ | $682.8427$ |
| $500.00$ | $509.9020$ | $0.0000$ | $1019.8039$ |

**Check 2 — Snell's Law angle verification:** Let $\theta$ be the angle that the underwater cable $AP$ makes with the perpendicular $AO$. At the critical point $C'(x) = 0$, the derivative condition reads

$$
\frac{x}{\sqrt{100^2 + x^2}} = \frac{1}{2} \iff \sin\theta = \frac{1}{2} \iff \theta = 30^\circ.
$$

This matches Snell's Law of refraction: the sine of the crossing angle equals the ratio of land cost to underwater cost, $\frac{c}{2c} = \frac{1}{2}$. For a $30^\circ$-$60^\circ$-$90^\circ$ right triangle with adjacent leg $100\text{ m}$, the opposite leg is immediately $x^* = 100\tan 30^\circ = \frac{100}{\sqrt{3}}\text{ m}$ and the hypotenuse is $\frac{200}{\sqrt{3}}\text{ m}$, independently confirming our calculus result.

---

## 7. Common Mistakes to Avoid

- **Forgetting the chain rule factor $2x$ inside the square root derivative:** Differentiating $\sqrt{10000 + x^2}$ gives $\frac{2x}{2\sqrt{10000 + x^2}} = \frac{x}{\sqrt{10000 + x^2}}$, not $\frac{1}{2\sqrt{10000 + x^2}}$.
- **Dropping the factor $2$ when squaring $2x = \sqrt{10000 + x^2}$:** Squaring $2x$ produces $4x^2$, not $2x^2$. Writing $2x^2 = 10000 + x^2$ leads to the wrong answer $x = 100\text{ m}$.
- **Forgetting to check whether $x^*$ lies inside $[0, 500]$:** What if point $B$ had been only $40\text{ m}$ downstream instead of $500\text{ m}$? Then $x^* = \frac{100}{\sqrt{3}} \approx 57.74\text{ m}$ would fall *outside* the domain $[0, 40]$, and the true minimum would occur at the endpoint $x = 40\text{ m}$, meaning straight underwater to $B$. Always check domain membership!
- **Adding lengths instead of costs:** Minimizing total cable length would mean going straight from $A$ to $B$ underwater at $x = 500$, which is actually the *most expensive* option in $[0, 500]$ because underwater cable is twice as costly per meter.

---

## 8. How I Would Explain This in Class

> "This problem is a real-world version of the classic lifeguard puzzle: you run faster on sand than you swim in water, so you should neither run all the way straight to the shore perpendicular to the swimmer nor swim in a straight diagonal line the whole way. Here, laying cable underwater costs twice as much per meter as laying it on land. If you start straight across at $x = 0$ and nudge the landing point slightly downstream, your overland distance shrinks by a full meter while your underwater hypotenuse barely grows at all—so moving downstream initially saves money. You keep shifting downstream until the marginal underwater cost matches the marginal land savings, which happens at an angle of $30^\circ$, exactly $57.74\text{ m}$ downstream from the point opposite $A$."
