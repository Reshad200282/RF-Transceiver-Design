Passive and Active Elements

In electrical and electronic circuits, elements are classified as passive or active based on whether they can supply energy to the circuit.

Passive Elements

Passive elements cannot generate energy.
They only store, dissipate, or transfer energy.

Characteristics

Do not provide power gain

Cannot amplify signals

Operate without an external power source

Examples

Resistor ($R$) — dissipates energy as heat

Capacitor ($C$) — stores energy in an electric field

Inductor ($L$) — stores energy in a magnetic field

Energy expressions

Equations (GitHub LaTeX compatible)
### Resistor

$$
V = I R
$$

$$
P = V I = I^2 R = \frac{V^2}{R}
$$

---

### Capacitor

$$
I = C \frac{dV}{dt}
$$

$$
E = \frac{1}{2} C V^2
$$

---

### Inductor

$$
V = L \frac{dI}{dt}
$$

$$
E = \frac{1}{2} L I^2
$$

---​

LI
2
Active Elements

Active elements can supply energy to the circuit or provide power gain.

Characteristics

Can amplify signals

Require an external power source

Can control current or voltage

Examples

Voltage and current sources

Transistors (BJT, MOSFET)

Operational amplifiers

Vacuum tubes

| Feature               | Passive Element | Active Element     |
| --------------------- | --------------- | ------------------ |
| Energy generation     | No              | Yes                |
| Power gain            | No              | Yes                |
| External power needed | No              | Yes                |
| Signal amplification  | No              | Yes                |
| Examples              | $R, L, C$       | Transistor, Op-amp |


Ahh, I see what you mean now 👍
You want **everything written *in LaTeX style*** (math mode), not plain text labels — and still **GitHub-compatible**.

Here it is **clean, correct, and copy-paste ready**.

---

## Passive Elements

### Resistor

$$
V = I R
$$

$$
P = V I = I^2 R = \frac{V^2}{R}
$$

---

### Capacitor

$$
I = C \frac{dV}{dt}
$$

$$
E = \frac{1}{2} C V^2
$$

---

### Inductor

$$
V = L \frac{dI}{dt}
$$

$$
E = \frac{1}{2} L I^2
$$

---

## Active Elements

### Voltage source

$$
V = V_s
$$

---

### Current source

$$
I = I_s
$$

---

### Amplification (active behavior)

$$
A_v = \frac{V_{\text{out}}}{V_{\text{in}}}
$$

---

### Power gain (active element)

$$
G_p = \frac{P_{\text{out}}}{P_{\text{in}}} > 1
$$

---

This uses **only math-mode LaTeX**, and it **renders correctly on GitHub**.

If you want:

* **definitions also in math form**, or
* **dependent source equations**, or
* **RF-specific active/passive criteria**

I’ve got you covered 👍

