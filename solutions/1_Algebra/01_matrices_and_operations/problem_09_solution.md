# Problem 09: Composing Transformations

## 1. The Original Problem

Let

$$

S=\begin{pmatrix}2&0\\0&1\end{pmatrix},\qquad R=\begin{pmatrix}0&-1\\1&0\end{pmatrix}.

$$

The matrix $S$ describes nonuniform scaling, while $R$ describes a $90^\circ$ counterclockwise rotation.
For

$$

x=\begin{pmatrix}1\\2\end{pmatrix}

$$

compute $RSx$ and $SRx$. Compare the results and explain geometrically why the order of these transformations matters.

---

## 2. What Are We Trying to Find?

We want to apply two geometric transformations (horizontal scaling $S$ and $90^\circ$ rotation $R$) to the vector $x$ in both possible orders:
1. $RSx$: scale first, then rotate.
2. $SRx$: rotate first, then scale.
We will compare the resulting vectors and explain why their order matters from a geometric perspective.

---

## 3. Before Calculating: What Idea Do We Need?

- **Matrix Composition from Right to Left:**
  In the product $M_2 M_1 x$, the matrix closest to $x$ ($M_1$) acts first, and the outer matrix ($M_2$) acts second:

$$

M_2 M_1 x = M_2 (M_1 x).

$$

- **Geometric Roles of $S$ and $R$:**
  - $S = \begin{pmatrix}2&0\\0&1\end{pmatrix}$ doubles the horizontal $x$-coordinate while leaving the vertical $y$-coordinate unchanged: $(x, y) \mapsto (2x, y)$.
  - $R = \begin{pmatrix}0&-1\\1&0\end{pmatrix}$ rotates vectors $90^\circ$ counterclockwise: $(x, y) \mapsto (-y, x)$.

---

## 4. Step-by-Step Solution

### Step 1: Compute $RSx$ (Scale first, then Rotate)
1. **Apply scaling $S$ to $x = \begin{pmatrix}1\\2\end{pmatrix}$:**

$$

Sx = \begin{pmatrix}2&0\\0&1\end{pmatrix}\begin{pmatrix}1\\2\end{pmatrix} = \begin{pmatrix}2(1)+0(2) \\ 0(1)+1(2)\end{pmatrix} = \begin{pmatrix}2\\2\end{pmatrix}.

$$

2. **Apply rotation $R$ to the scaled vector $\begin{pmatrix}2\\2\end{pmatrix}$:**

$$

RSx = R(Sx) = \begin{pmatrix}0&-1\\1&0\end{pmatrix}\begin{pmatrix}2\\2\end{pmatrix} = \begin{pmatrix}0(2)+(-1)(2) \\ 1(2)+0(2)\end{pmatrix} = \begin{pmatrix}-2\\2\end{pmatrix}.

$$

### Step 2: Compute $SRx$ (Rotate first, then Scale)
1. **Apply rotation $R$ to $x = \begin{pmatrix}1\\2\end{pmatrix}$:**

$$

Rx = \begin{pmatrix}0&-1\\1&0\end{pmatrix}\begin{pmatrix}1\\2\end{pmatrix} = \begin{pmatrix}0(1)+(-1)(2) \\ 1(1)+0(2)\end{pmatrix} = \begin{pmatrix}-2\\1\end{pmatrix}.

$$

2. **Apply scaling $S$ to the rotated vector $\begin{pmatrix}-2\\1\end{pmatrix}$:**

$$

SRx = S(Rx) = \begin{pmatrix}2&0\\0&1\end{pmatrix}\begin{pmatrix}-2\\1\end{pmatrix} = \begin{pmatrix}2(-2)+0(1) \\ 0(-2)+1(1)\end{pmatrix} = \begin{pmatrix}-4\\1\end{pmatrix}.

$$

### Step 3: Compare the Results
Comparing the two vectors:

$$

RSx = \begin{pmatrix}-2\\2\end{pmatrix} \neq \begin{pmatrix}-4\\1\end{pmatrix} = SRx.

$$

---

## 5. Final Answer & Conclusion

- $RSx = \begin{pmatrix}-2\\2\end{pmatrix}$
- $SRx = \begin{pmatrix}-4\\1\end{pmatrix}$
- **Geometric Explanation:**
  - In $RSx$, the initial vector $(1, 2)$ is first stretched horizontally to $(2, 2)$. The subsequent $90^\circ$ rotation turns this entire stretched vector into the second quadrant, placing the doubled length along the vertical axis, giving $(-2, 2)$.
  - In $SRx$, the initial vector $(1, 2)$ is rotated first into the second quadrant, becoming $(-2, 1)$. Now its original vertical component ($2$) has become its horizontal component ($-2$). Applying the horizontal scaling $S$ at this point doubles this new horizontal component to $-4$, yielding $(-4, 1)$.
  - **Why order matters:** Non-uniform scaling is tied to a specific fixed axis (the $x$-axis). Because rotation changes which direction points along the $x$-axis, scaling before rotating stretches a different physical feature of the vector than rotating before scaling. Hence $RS \neq SR$.

---

## 6. Quick Verification

We can multiply the composite transformation matrices directly:

$$

RS = \begin{pmatrix}0&-1\\1&0\end{pmatrix}\begin{pmatrix}2&0\\0&1\end{pmatrix} = \begin{pmatrix}0&-1\\2&0\end{pmatrix} \implies (RS)x = \begin{pmatrix}0&-1\\2&0\end{pmatrix}\begin{pmatrix}1\\2\end{pmatrix} = \begin{pmatrix}-2\\2\end{pmatrix}.

$$

$$

SR = \begin{pmatrix}2&0\\0&1\end{pmatrix}\begin{pmatrix}0&-1\\1&0\end{pmatrix} = \begin{pmatrix}0&-2\\1&0\end{pmatrix} \implies (SR)x = \begin{pmatrix}0&-2\\1&0\end{pmatrix}\begin{pmatrix}1\\2\end{pmatrix} = \begin{pmatrix}-4\\1\end{pmatrix}.

$$

Both matrix-first and vector-first evaluations match identically.

---

## 7. Common Mistakes to Avoid

1. **Reading operations left-to-right:** In $RSx$, beginners often mistakenly apply $R$ first because $R$ is written first on the left. In mathematical notation, functions and matrices apply from **right to left**: $S$ acts on $x$ first, then $R$ acts on that result.
2. **Confusing rotation with reflection:** $R = \begin{pmatrix}0&-1\\1&0\end{pmatrix}$ maps $(x, y) \mapsto (-y, x)$, which is a counterclockwise rotation, not a reflection.

---

## 8. How I Would Explain This in Class

> "When composing geometric transformations, order is crucial because matrices apply from right to left. In $RSx$, we scale horizontally first to get $(2, 2)$ and then rotate to $(-2, 2)$. In $SRx$, we rotate first to $(-2, 1)$ and then scale horizontally to $(-4, 1)$. Because the scaling stretches along only one fixed axis, turning the vector before stretching affects a completely different component than turning it after."
