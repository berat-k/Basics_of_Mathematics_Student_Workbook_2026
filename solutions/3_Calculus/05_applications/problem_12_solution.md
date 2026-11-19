# Problem 12: Complete Model and Computer Verification

## 1. The Original Problem

A museum wants to create a rectangular exhibition room next to an existing straight wall. The side along the wall does not need to be built. The remaining three sides are to be constructed to two different standards: the two sides perpendicular to the wall cost $300\ \mathrm{PLN/m}$ each, while the side parallel to the wall costs $500\ \mathrm{PLN/m}$. The budget is $30\,000\ \mathrm{PLN}$.

Build a model that maximizes the area of the room and prepare a complete analysis containing:

- definition of variables and units,
- mathematical model,
- domain resulting from the problem statement,
- computation of the derivative,
- determination and verification of the optimum,
- interpretation of the result,
- graph of the objective function,
- numerical verification of several values near the optimum found.

Finally, indicate which part of the solution required modeling the problem and which part was only the execution of the calculation. Produce the graph and computer calculations only after completing the mathematical solution, and treat them as verification.

---

## 2. What Are We Trying to Find?

1. **Variables and units:** Define clear mathematical variables with physical units for the room dimensions, total construction cost, and floor area.
2. **Mathematical model:** Express the budget constraint and the floor area, eliminate one variable, and obtain a single-variable objective function $A(x)$.
3. **Domain:** Identify the physically meaningful interval of valid side lengths $x$ dictated by the geometry and the budget.
4. **Derivative and optimum:** Compute $A'(x)$, find the critical point $x^*$, determine the corresponding length $y^*$ and maximum area $A(x^*)$, and prove rigorously that this point gives the global maximum.
5. **Contextual interpretation:** Translate the optimal dimensions, maximum area, and cost breakdown back into practical recommendations for the museum.
6. **Post-solution verification (graph and numerical table):** After completing the analytical calculus solution, produce a graph of $A(x)$ and a computer-verified numerical table of values near the optimum to confirm the result independently.
7. **Modeling versus calculation reflection:** Explicitly separate the steps that required mathematical modeling from the steps that were purely mechanical calculation.

---

## 3. Before Calculating: What Idea Do We Need?

- **Geometry of a three-sided rectangular enclosure:** Because one side is formed by an existing straight wall, only three new walls must be constructed: two equal sides of length $x$ perpendicular to the wall, and one side of length $y$ parallel to the wall.
- **Why the budget constraint binds with equality:** The available budget imposes $600x + 500y \le 30\,000$. Because the area $A = xy$ is strictly increasing in both $x$ and $y$, any design leaving unspent money could be enlarged to produce strictly more floor area. Therefore, the maximum area must occur on the boundary where the entire budget is spent: $600x + 500y = 30\,000$.
- **Reduction to a single variable:** Solving the linear budget equation for $y$ in terms of $x$ turns $A = xy$ into a concave-down quadratic function $A(x)$.
- **Calculus optimization on an open interval:** A twice-differentiable function with $A''(x) < 0$ everywhere on $(0, 50)$ is strictly concave, so any point where $A'(x) = 0$ is automatically the **unique global maximum**.
- **Separation of modeling and verification:** Analytical calculus yields the exact answer first; plotting the graph and tabulating nearby values afterward serves as an independent sanity check against algebra or modeling errors.

---

## 4. Step-by-Step Solution

### Step 1: Definition of Variables and Units

Sketch the layout of the rectangular exhibition room against the existing museum wall:

```text
  ================= Existing Museum Wall =================
              |                              |
        x [m] |      Exhibition Room         | x [m]
  (300 PLN/m) |         Area = x * y         | (300 PLN/m)
              |                              |
              +------------------------------+
                           y [m]
                       (500 PLN/m)
```

Define the variables and their physical units:

- $x$: length of each of the two walls perpendicular to the existing wall, measured in meters, denoted $\text{m}$.
- $y$: length of the single wall parallel to the existing wall, measured in meters, denoted $\text{m}$.
- $C$: total construction cost of the three new walls, measured in Polish zlotys, denoted $\text{PLN}$.
- $A$: floor area of the rectangular exhibition room, measured in square meters, denoted $\text{m}^2$.

### Step 2: Mathematical Model

The objective is to maximize the rectangular floor area:

$$
A = x y \quad [\text{m}^2].
$$

The cost of building the two perpendicular walls at $300\ \mathrm{PLN/m}$ each is $2 \cdot 300 x = 600x\ \mathrm{PLN}$, and the cost of building the parallel wall at $500\ \mathrm{PLN/m}$ is $500y\ \mathrm{PLN}$. Using the full budget of $30\,000\ \mathrm{PLN}$ to maximize area gives the budget constraint:

$$
600x + 500y = 30\,000.
$$

Divide both sides by $100$ to simplify:

$$
6x + 5y = 300.
$$

Solve this constraint for $y$ in terms of $x$:

$$
5y = 300 - 6x \implies y = 60 - \frac{6}{5}x = 60 - 1.2x.
$$

Substitute $y = 60 - \frac{6}{5}x$ into the area formula $A = xy$ to obtain the single-variable objective function:

$$
A(x) = x\left(60 - \frac{6}{5}x\right) = 60x - \frac{6}{5}x^2 = 60x - 1.2x^2.
$$

### Step 3: Domain Resulting from the Problem Statement

A real rectangular room must have strictly positive dimensions, so both $x > 0$ and $y > 0$ are required:

$$
x > 0 \qquad \text{and} \qquad y = 60 - \frac{6}{5}x > 0.
$$

Solving the second inequality gives

$$
60 > \frac{6}{5}x \implies x < 60 \cdot \frac{5}{6} = 50.
$$

Therefore, the physically meaningful open domain is

$$
x \in (0, 50) \quad [\text{m}].
$$

If we extend $A(x)$ continuously to the closed interval $[0, 50]$, the endpoints represent degenerate rooms of zero area: at $x = 0\text{ m}$ we get $y = 60\text{ m}$ and $A(0) = 0\text{ m}^2$, while at $x = 50\text{ m}$ we get $y = 0\text{ m}$ and $A(50) = 0\text{ m}^2$.

### Step 4: Computation of the Derivative

Differentiate $A(x) = 60x - \frac{6}{5}x^2$ with respect to $x$:

$$
A'(x) = 60 - \frac{12}{5}x = 60 - 2.4x.
$$

The unit of $A'(x)$ is $\text{m}^2/\text{m} = \text{m}$, representing the marginal change in floor area per additional meter of depth $x$ while keeping total spending fixed at $30\,000\ \mathrm{PLN}$.

### Step 5: Determination and Verification of the Optimum

Set the first derivative equal to zero to find all critical points in $(0, 50)$:

$$
A'(x) = 0 \implies 60 - \frac{12}{5}x = 0 \implies \frac{12}{5}x = 60 \implies x^* = 60 \cdot \frac{5}{12} = 25\text{ m}.
$$

First check that $x^* = 25\text{ m}$ lies strictly inside the domain $(0, 50)$, which it does since $0 < 25 < 50$.

Next verify that $x^* = 25\text{ m}$ gives the **unique global maximum**.

**Second derivative test:** Differentiating $A'(x) = 60 - 2.4x$ yields

$$
A''(x) = -\frac{12}{5} = -2.4 < 0 \qquad \text{for all } x \in (0, 50).
$$

Because $A''(x) < 0$ everywhere on the domain, $A(x)$ is strictly concave down on $(0, 50)$, so the unique stationary point $x^* = 25\text{ m}$ is the **global maximum**.

**First derivative sign chart:**

| Interval or point | Sign of $A'(x) = 60 - 2.4x$ | Behavior of $A(x)$ |
| :--- | :---: | :--- |
| $0 < x < 25$ | $+$ | Strictly increasing |
| $x = 25$ | $0$ | Unique global maximum |
| $25 < x < 50$ | $-$ | Strictly decreasing |

Now compute the corresponding optimal parallel length $y^*$ and maximum area $A(25)$:

$$
y^* = 60 - \frac{6}{5}(25) = 60 - 30 = 30\text{ m},
$$

$$
A(25) = x^* y^* = 25 \cdot 30 = 750\text{ m}^2.
$$

### Step 6: Interpretation of the Result

To maximize the exhibition space within the $30\,000\ \mathrm{PLN}$ budget, the museum should build a rectangular room measuring **$25\text{ m}$ perpendicular to the existing wall** and **$30\text{ m}$ parallel to the existing wall**, yielding a maximum floor area of **$750\text{ m}^2$**.

Examining the budget breakdown reveals a striking structural feature:

- **Cost of the two perpendicular walls:** $2 \times 25\text{ m} \times 300\ \mathrm{PLN/m} = 15\,000\ \mathrm{PLN}$, which is $50\%$ of the budget.
- **Cost of the single parallel wall:** $30\text{ m} \times 500\ \mathrm{PLN/m} = 15\,000\ \mathrm{PLN}$, which is $50\%$ of the budget.
- **Total cost:** $15\,000 + 15\,000 = 30\,000\ \mathrm{PLN}$.

Even though the construction costs per meter differ between the perpendicular and parallel walls, the optimal layout allocates **exactly half of the budget to the perpendicular direction and half to the parallel direction**. Because the parallel wall costs $500\ \mathrm{PLN/m}$ while the pair of perpendicular walls together costs $600\ \mathrm{PLN/m}$, the optimal room is slightly wider along the existing wall at $30\text{ m}$ than it is deep at $25\text{ m}$.

### Step 7: Post-Solution Verification — Graph of $A(x)$ and Numerical Table

Having completed the analytical solution, we now plot the objective function $A(x) = 60x - 1.2x^2$ over $[0, 50]$ and evaluate values near $x^* = 25\text{ m}$ as an independent verification.

**Graph of the objective function $A(x) = 60x - 1.2x^2$ on $[0, 50]$:**

```text
A(x) [m^2]
     |                         Peak (25, 750)
 750 |                    *****@*****
 675 |                ****     :     ****
 600 |             ***         :         ***
 525 |           **            :            **
 450 |         **              :              **
 375 |       **                :                **
 300 |     **                  :                  **
 225 |    *                    :                    *
 150 |  **                     :                     **
  75 | *                       :                       *
   0 |*                        :                        *
     +---------------------------------------------------> x [m]
      0    5   10   15   20   25   30   35   40   45   50
```

The graph is a downward-opening parabola crossing the horizontal axis at $x = 0$ and $x = 50$, symmetric about the vertical axis $x = 25$, with its unique peak at $(25, 750)$.

**Computer-verified numerical table around $x^* = 25\text{ m}$:**

| $x$ in m | $y = 60 - 1.2x$ in m | Total Cost in PLN | Area $A(x)$ in $\text{m}^2$ | $A(x) - 750$ in $\text{m}^2$ |
| :---: | :---: | :---: | :---: | :---: |
| $10.0$ | $48.0$ | $30\,000$ | $480.00$ | $-270.00$ |
| $20.0$ | $36.0$ | $30\,000$ | $720.00$ | $-30.00$ |
| $22.0$ | $33.6$ | $30\,000$ | $739.20$ | $-10.80$ |
| $24.0$ | $31.2$ | $30\,000$ | $748.80$ | $-1.20$ |
| $24.5$ | $30.6$ | $30\,000$ | $749.70$ | $-0.30$ |
| **$25.0$** | **$30.0$** | **$30\,000$** | **$750.00$** | **$0.00$** |
| $25.5$ | $29.4$ | $30\,000$ | $749.70$ | $-0.30$ |
| $26.0$ | $28.8$ | $30\,000$ | $748.80$ | $-1.20$ |
| $28.0$ | $26.4$ | $30\,000$ | $739.20$ | $-10.80$ |
| $30.0$ | $24.0$ | $30\,000$ | $720.00$ | $-30.00$ |
| $40.0$ | $12.0$ | $30\,000$ | $480.00$ | $-270.00$ |

Every test point uses the exact budget of $30\,000\ \mathrm{PLN}$, and moving even $0.5\text{ m}$ away from $x = 25\text{ m}$ in either direction lowers the area by $0.30\text{ m}^2$.

### Step 8: Modeling Versus Execution of Calculation

A crucial skill in applied mathematics is recognizing which steps require **modeling** (translating a real-world situation into mathematics and back again) versus **calculation** (executing algebraic and calculus procedures once the equations are set):

| Stage of the Solution | Modeling or Calculation? | Why? |
| :--- | :--- | :--- |
| Choosing variables $x, y, A, C$ and tracking units | **Modeling** | Decides which geometric quantities represent the physical design. |
| Recognizing only $3$ walls are built, with unequal costs $2 \cdot 300x + 500y$ | **Modeling** | Translates the verbal architectural description into an algebraic cost expression. |
| Justifying that the full budget $600x + 500y = 30\,000$ is used | **Modeling** | Uses economic and geometric reasoning to turn an inequality into an equality. |
| Determining the physical domain $x \in (0, 50)$ | **Modeling** | Imposes real-world positivity constraints $x > 0$ and $y > 0$. |
| Solving $6x + 5y = 300$ for $y$ and expanding $A(x) = 60x - 1.2x^2$ | **Calculation** | Pure algebraic manipulation of equations already formulated. |
| Computing $A'(x) = 60 - 2.4x$, solving $A'(x) = 0$, and checking $A''(x) = -2.4 < 0$ | **Calculation** | Mechanical execution of differentiation and linear equation solving. |
| Evaluating $y^* = 30\text{ m}$, $A(25) = 750\text{ m}^2$, and tabulating numerical values | **Calculation** | Direct substitution and arithmetic verification. |
| Interpreting $25\text{ m} \times 30\text{ m}$, $750\text{ m}^2$, and the $50\% / 50\%$ budget split | **Modeling** | Translates numerical outputs back into actionable museum planning decisions. |

Notice that once the model $A(x) = 60x - 1.2x^2$ on $(0, 50)$ is built, the calculus takes only a few lines; almost all real difficulty and risk of conceptual error lives in the **modeling** stages.

---

## 5. Final Answer & Conclusion

- **Variables:** $x$ is the perpendicular wall length in $\text{m}$, $y$ is the parallel wall length in $\text{m}$, and $A$ is the area in $\text{m}^2$.
- **Model and domain:** $600x + 500y = 30\,000 \implies y = 60 - 1.2x$, giving $A(x) = 60x - 1.2x^2$ on the physically meaningful domain $x \in (0, 50)$.
- **Derivative and verification:** $A'(x) = 60 - 2.4x = 0$ gives $x^* = 25\text{ m}$, and $A''(x) = -2.4 < 0$ confirms a unique global maximum.
- **Optimal dimensions and maximum area:** Build the room **$25\text{ m}$ perpendicular to the existing wall** and **$30\text{ m}$ parallel to the existing wall** for a maximum area of **$750\text{ m}^2$**, splitting the $30\,000\ \mathrm{PLN}$ budget evenly with $15\,000\ \mathrm{PLN}$ on the two perpendicular sides and $15\,000\ \mathrm{PLN}$ on the parallel side.
- **Modeling vs. calculation:** Formulating the three-wall cost constraint, setting the domain $0 < x < 50$, and interpreting the results are **modeling**; algebraic substitution, differentiation, solving $A'(x) = 0$, and computing verification values are **calculation**.

---

## 6. Quick Verification

**Check 1 — Completing the square (algebraic proof without calculus):** Factor $-1.2$ out of $A(x) = -1.2x^2 + 60x$:

$$
A(x) = -1.2\left(x^2 - 50x\right) = -1.2\left[(x - 25)^2 - 625\right] = 750 - 1.2(x - 25)^2.
$$

Because $-1.2(x - 25)^2 \le 0$ for every real $x$, with equality if and only if $x = 25$, this proves purely algebraically that $A(x) \le 750$ and the unique global maximum is $750\text{ m}^2$ at $x = 25\text{ m}$. It also explains the exact quadratic drop $A(25 \pm h) - 750 = -1.2 h^2$ seen in our verification table: for $h = 1$, the loss is $-1.2\text{ m}^2$; for $h = 5$, the loss is $-30\text{ m}^2$.

**Check 2 — AM-GM inequality on the budget shares:** Set $u = 600x$ (spending on the perpendicular walls) and $v = 500y$ (spending on the parallel wall). Then $u + v = 30\,000$ and $xy = \frac{uv}{600 \cdot 500} = \frac{uv}{300\,000}$. By AM-GM,

$$
A = \frac{uv}{300\,000} \le \frac{1}{300\,000}\left(\frac{u + v}{2}\right)^2 = \frac{15\,000^2}{300\,000} = \frac{225\,000\,000}{300\,000} = 750\text{ m}^2,
$$

with equality if and only if $u = v = 15\,000\ \mathrm{PLN}$, yielding $x = \frac{15\,000}{600} = 25\text{ m}$ and $y = \frac{15\,000}{500} = 30\text{ m}$.

---

## 7. Common Mistakes to Avoid

- **Forgetting that there are TWO perpendicular walls:** Writing the budget constraint as $300x + 500y = 30\,000$ instead of $2(300x) + 500y = 30\,000$ forgets the second perpendicular side and leads to a room that exceeds the budget by $15\,000\ \mathrm{PLN}$.
- **Including a fourth wall along the existing museum wall:** Writing $600x + 1000y = 30\,000$ ignores the statement that the side along the existing straight wall does not need to be built.
- **Assuming the optimal room must be a square with $x = y$:** A square maximizes area only when all four sides are built at identical unit cost. Here only three sides are built and their unit costs differ, so the optimal room is $25\text{ m} \times 30\text{ m}$, not a square.
- **Confusing modeling with graphing/computation:** Trying to guess the answer purely from a coarse computer table before deriving the mathematical model risks missing the true optimum or overlooking the budget constraint. The math should guide the design, and the computer should verify it.

---

## 8. How I Would Explain This in Class

> "Whenever you optimize a rectangle under a fixed budget, there is a remarkably clean rule hiding behind the algebra: you always want to spend half your money in the horizontal direction and half your money in the vertical direction. Here, the museum has $30\,000\ \mathrm{PLN}$. Putting $15\,000\ \mathrm{PLN}$ into the two perpendicular walls at a combined $600\ \mathrm{PLN/m}$ buys a depth of $25\text{ m}$, and putting the other $15\,000\ \mathrm{PLN}$ into the single parallel wall at $500\ \mathrm{PLN/m}$ buys a width of $30\text{ m}$, giving $750\text{ m}^2$ of exhibition space. Notice how the calculus itself is just taking the derivative of a parabola—the real brainwork was setting up the model carefully, making sure we counted two perpendicular walls and zero wall along the existing building, and then using the graph and numerical table afterward to verify our answer."
