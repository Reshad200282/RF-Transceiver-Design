# Friis Formula — Physical Meaning and Intuition

This section explains **Friis’ formula for cascaded noise** from a *physical* point of view — not just as a formula to memorize.

---

## Friis Formula (Cascaded Noise)

For a cascade of stages (amplifiers, mixers, filters):

$$
F_{\text{total}}
=
F_1
+ \frac{F_2 - 1}{G_1}
+ \frac{F_3 - 1}{G_1 G_2}
+ \cdots
$$

where:
- $F_i$ = noise factor of stage $i$ (linear, **not dB**)
- $G_i$ = power gain of stage $i$ (linear)

---

## Physical Meaning (Key Insight)

> **Noise added early gets amplified by everything after it.  
> Noise added later is suppressed by earlier gain.**

This single idea explains the entire Friis formula.

---

## Step-by-Step Physical Picture

### Stage 1 (Front End)

- Sees the input signal plus unavoidable thermal noise
- Adds its own internal noise
- **Everything at its output is amplified by all later stages**

Therefore:
- Noise from stage 1 dominates the total noise

---

### Stage 2

- Adds noise of its own
- But this noise is **not amplified by stage 1**
- Its contribution is divided by $G_1$

Physically:

> The more gain stage 1 provides, the less noticeable stage-2 noise becomes.

---

### Stage 3 and Beyond

- Noise is divided by $G_1 G_2$
- Often negligible if early gain is high

---

## Why the Formula Looks This Way

Each stage contributes only its **excess noise**:

$$
F_i - 1
$$

That excess noise is:

- Fully counted for stage 1
- Suppressed by previous gain for later stages

General contribution of stage $i$:

$$
\text{Contribution}_i
=
\frac{F_i - 1}
{\prod_{k=1}^{i-1} G_k}
$$

---

## Equivalent Noise Temperature Form (Very Physical)

Using the relation:

$$
F = 1 + \frac{T_e}{T_0}
$$

Friis’ formula becomes:

$$
T_{e,\text{total}}
=
T_{e1}
+ \frac{T_{e2}}{G_1}
+ \frac{T_{e3}}{G_1 G_2}
+ \cdots
$$

### Physical Meaning

> The total equivalent noise temperature is the sum of each stage’s noise temperature, reduced by how much earlier gain hides it.

---

## Practical RF Intuition

### Why LNAs Must Come First

- First stage has the **lowest noise factor**
- Also provides **high gain**
- This minimizes the effect of noise from all later stages

---

### Why Passive Loss Before the LNA Is Dangerous

Consider a lossy element with loss $L$:

- Noise factor: $F = L$
- Gain: $G = \frac{1}{L}$

Placed before the LNA:

$$
F_{\text{total}}
=
L
+ \frac{F_{\text{LNA}} - 1}{1/L}
$$

### Physical Meaning

> Loss before gain behaves like a noisy amplifier at room temperature.  
> It severely degrades receiver sensitivity.

---

## One-Sentence Exam-Safe Explanation

> **Friis’ formula shows that the noise performance of a cascaded system is dominated by the first stage, because its noise is amplified by all subsequent stages, while noise added later is suppressed by earlier gain.**
