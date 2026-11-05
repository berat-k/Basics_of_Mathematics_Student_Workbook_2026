# Problem 13: Undoing a Composite Transformation

## 1. The Original Problem

The matrices

$$
S = \begin{pmatrix} 2 & 0 \\\\ 0 & 1 \end{pmatrix}, \qquad H = \begin{pmatrix} 1 & 1 \\\\ 0 & 1 \end{pmatrix}
$$

describe nonuniform scaling and shear. For $T = HS$, find $T^{-1}$ in two ways:

1. First compute $T$, then its inverse.
2. Use $(HS)^{-1} = S^{-1}H^{-1}$.

Compare the results. Additionally compute $H^{-1}S^{-1}$ and verify that the incorrect order gives a different matrix. Explain the rule: “when undoing a composition of operations, we undo them from the end.”

---

## 2. What Are We Trying to Find?

We need to:
1. Compute the composite matrix $T = HS$ and then compute $T^{-1}$ directly via the $2 \times 2$ inverse formula (Method 1).
2. Compute the individual inverses $S^{-1}$ and $H^{-1}$, and multiply them in reverse order $S^{-1}H^{-1}$ (Method 2).
3. Confirm that both methods yield the identical matrix.
4. Compute the forward order product $H^{-1}S^{-1}$ to prove explicitly that order matters: $H^{-1}S^{-1} \neq (HS)^{-1}$.
5. Explain the foundational physical and geometric rule: *"when undoing a composition of operations, we undo them from the end."*

---

## 3. Before Calculating: What Idea Do We Need?

- **Reversal of Order in Inverses (The Unwrapping Principle):**
  For any invertible matrices $A$ and $B$:

$$
(AB)^{-1} = B^{-1} A^{-1}
$$

- **Geometric Interpretation of $T = HS$:**
  In the product $HSx = H(Sx)$:
  - Matrix $S$ acts **first**, scaling horizontal coordinates by $2$.
  - Matrix $H$ acts **second**, applying a horizontal shear ($x \mapsto x + y$).
- **Undoing the Chain:**
  To return to the original vector $x$ from the final output $y = H(Sx)$, we cannot undo $S$ first because the coordinates are currently distorted by the shear $H$. We must first strip away $H$ by applying $H^{-1}$, which recovers the scaled vector $Sx$. Only then can we apply $S^{-1}$ to undo the scaling.

---

## 4. Step-by-Step Solution

### Step 1: Method 1 — Compute $T = HS$, Then Invert

1. Compute $T = HS$:

$$
T = \begin{pmatrix} 1 & 1 \\\\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 0 \\\\ 0 & 1 \end{pmatrix}
$$

   - Row 1: $(1)(2) + (1)(0) = 2$, \quad $(1)(0) + (1)(1) = 1$
   - Row 2: $(0)(2) + (1)(0) = 0$, \quad $(0)(0) + (1)(1) = 1$

$$
T = \begin{pmatrix} 2 & 1 \\\\ 0 & 1 \end{pmatrix}
$$

2. Invert $T$ using the $2 \times 2$ formula:
   - $\det T = (2)(1) - (1)(0) = 2$.
   - Swap diagonal entries ($2 \leftrightarrow 1$) and negate off-diagonal entries ($1 \to -1$):

$$
T^{-1} = \frac{1}{2} \begin{pmatrix} 1 & -1 \\\\ 0 & 2 \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\\\ 0 & 1 \end{pmatrix}
$$

### Step 2: Method 2 — Use $(HS)^{-1} = S^{-1}H^{-1}$

1. Invert diagonal matrix $S$:
   $S$ is diagonal, so invert diagonal entries:

$$
S^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\\\ 0 & 1 \end{pmatrix}
$$

2. Invert shear matrix $H$:
   $\det H = 1(1) - 1(0) = 1$. Negate the shear entry:

$$
H^{-1} = \begin{pmatrix} 1 & -1 \\\\ 0 & 1 \end{pmatrix}
$$

3. Multiply in reversed order $S^{-1} H^{-1}$:

$$
S^{-1} H^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\\\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & -1 \\\\ 0 & 1 \end{pmatrix}
$$

   - Row 1: $\left(\frac{1}{2}\right)(1) + (0)(0) = \frac{1}{2}$, \quad $\left(\frac{1}{2}\right)(-1) + (0)(1) = -\frac{1}{2}$
   - Row 2: $(0)(1) + (1)(0) = 0$, \quad $(0)(-1) + (1)(1) = 1$

$$
S^{-1} H^{-1} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\\\ 0 & 1 \end{pmatrix}
$$

**Comparison:** Both Method 1 and Method 2 yield the exact same matrix.

### Step 3: Compute the Incorrect Order $H^{-1} S^{-1}$

Now compute the product in forward order $H^{-1} S^{-1}$:

$$
H^{-1} S^{-1} = \begin{pmatrix} 1 & -1 \\\\ 0 & 1 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & 0 \\\\ 0 & 1 \end{pmatrix}
$$

   - Row 1: $(1)\left(\frac{1}{2}\right) + (-1)(0) = \frac{1}{2}$, \quad $(1)(0) + (-1)(1) = -1$
   - Row 2: $(0)\left(\frac{1}{2}\right) + (1)(0) = 0$, \quad $(0)(0) + (1)(1) = 1$

$$
H^{-1} S^{-1} = \begin{pmatrix} \frac{1}{2} & -1 \\\\ 0 & 1 \end{pmatrix}
$$

Notice the discrepancy: entry $(1, 2)$ is $-1$, whereas in $T^{-1}$ it is $-\frac{1}{2}$.
Thus:

$$
H^{-1} S^{-1} \neq (HS)^{-1}
$$

### Step 4: Explain the Rule "Undo from the End"

Why do we undo a composition from the end?
Consider what the composite operator $T = HS$ does to an input vector $x$:

$$
x \xrightarrow{\quad S \quad} Sx \xrightarrow{\quad H \quad} y = H(Sx)
$$

The operation $H$ was applied **last**. It wraps the vector $Sx$ inside $H$.
1. To recover the original vector, we must peel off the outermost wrapper first. Multiplying $y$ by $H^{-1}$ strips away the shear:

$$
H^{-1} y = H^{-1}(H(Sx)) = (H^{-1}H)(Sx) = I(Sx) = Sx
$$

2. Now that the shear has been eliminated, the vector is purely scaled by $S$. We can safely apply $S^{-1}$ to strip away the scaling:

$$
S^{-1}(Sx) = (S^{-1}S)x = Ix = x
$$

In algebraic notation, this sequential unwrapping is:

$$
S^{-1} \left( H^{-1} y \right) = (S^{-1} H^{-1}) y = x
$$

If you attempted to apply $S^{-1}$ first directly to $y$, you would be applying scaling to a vector that still contains the shear offset; the shear would get scaled incorrectly, corrupting the geometry rather than restoring it. Just like putting on a sock and then a shoe, the shoe (the last item put on) must be removed first before the sock can be taken off.

---

## 5. Final Answer & Conclusion

- **Calculated Inverses:**

$$
T^{-1} = S^{-1}H^{-1} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\\\ 0 & 1 \end{pmatrix}
$$

- **Incorrect Order Calculation:**

$$
H^{-1}S^{-1} = \begin{pmatrix} \frac{1}{2} & -1 \\\\ 0 & 1 \end{pmatrix} \neq T^{-1}
$$

- **Conclusion:** Both valid methods agree. The rule *"undo from the end"* reflects the fundamental requirement that the outermost composite layer must be inverted first before inner layers can be accessed.

---

## 6. Quick Verification

Multiply $T$ by the incorrect order $H^{-1}S^{-1}$ to prove it fails to give $I$:

$$
T(H^{-1}S^{-1}) = \begin{pmatrix} 2 & 1 \\\\ 0 & 1 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & -1 \\\\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 2(1/2) + 1(0) & 2(-1) + 1(1) \\\\ 0(1/2) + 1(0) & 0(-1) + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & -1 \\\\ 0 & 1 \end{pmatrix} \neq I
$$

Multiply $T$ by the correct order $S^{-1}H^{-1}$:

$$
T(S^{-1}H^{-1}) = \begin{pmatrix} 2 & 1 \\\\ 0 & 1 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\\\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 2(1/2) + 0 & 2(-1/2) + 1(1) \\\\ 0 + 0 & 0 + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} = I
$$

The identity matrix is obtained exclusively by the reversed order $S^{-1}H^{-1}$.

---

## 7. Common Mistakes to Avoid

1. **Assuming Commutativity of Elementary Inverses:**
   Assuming $S^{-1} H^{-1} = H^{-1} S^{-1}$. In this exercise, the two products differ in entry $(1, 2)$ ($-\frac{1}{2}$ vs. $-1$).
2. **Confusing Forward Action with Reverse Action:**
   Writing $(HS)^{-1} = H^{-1} S^{-1}$. Always remember that the brackets flip the order of every factor.

---

## 8. How I Would Explain This in Class

> "When we apply $T = HS$, we first scale space horizontally with $S$, and then shear it horizontally with $H$. To reverse this process, we must undo the operations in the exact reverse order: first undo the shear with $H^{-1}$, and only then undo the scaling with $S^{-1}$. This is why $(HS)^{-1} = S^{-1}H^{-1}$ with rows $(1/2, -1/2)$ and $(0, 1)$. If you applied $H^{-1}S^{-1}$ instead, you would scale the sheared offset incorrectly, resulting in $(1, 2)$-entry $-1$ instead of $-1/2$, which fails to return the identity."