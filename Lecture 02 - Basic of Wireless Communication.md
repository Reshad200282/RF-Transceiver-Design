Lecture 02 - Basic of Wireless Communication - II
<img width="1199" height="570" alt="image" src="https://github.com/user-attachments/assets/4bab5172-c74a-4a9a-ae4e-828c64b29e7f" />
Ah yep — GitHub is picky 😅
It only supports **inline math with `$ ... $`** and **display math with `$$ ... $$`**, not full LaTeX document commands like `\section{}` or `\subsection{}`.

Below is a **GitHub-Markdown–friendly version**.
You can paste this **directly into a README.md** and it’ll render.

---

## Why inductors are low-Q components at RF

Inductors are not inherently low-Q devices, but at radio frequencies their losses increase rapidly and parasitic effects dominate, causing the effective quality factor to drop.

---

### Quality factor of an inductor

The quality factor of an inductor is

$$
Q = \frac{\omega L}{R_{\text{loss}}}
$$

where

* $\omega$ is the angular frequency
* $L$ is the inductance
* $R_{\text{loss}}$ is the effective loss resistance

At RF, $R_{\text{loss}}$ increases faster than $\omega L$, so $Q$ decreases.

---

### Reasons inductors have low $Q$ at RF

#### 1. Skin effect

At high frequency, current flows only near the surface of the conductor.

* Effective cross-section decreases
* AC resistance increases
* $R_{\text{loss}} \uparrow \Rightarrow Q \downarrow$

---

#### 2. Proximity effect

Magnetic fields from adjacent turns force non-uniform current distribution.

* Current crowding in the conductor
* Additional resistive loss
* Further reduction in $Q$

---

#### 3. Parasitic capacitance and self-resonant frequency

All inductors have parasitic capacitance due to:

* Turn-to-turn capacitance
* Pad and package capacitance

This results in a **self-resonant frequency (SRF)**.

* Near SRF, $Q$ drops sharply
* Above SRF, the inductor behaves like a capacitor

---

#### 4. Core losses

Inductors with magnetic cores experience:

* Eddy current losses
* Hysteresis losses
* Reduced permeability at high frequency

For this reason, RF inductors are usually **air-core**.

---

#### 5. Radiation losses

At RF, inductors can radiate electromagnetic energy.

* Stored energy is lost as radiation
* Radiation appears as loss
* $Q$ is reduced

---

### Comparison with capacitors at RF

Capacitors generally have higher $Q$ at RF because they:

* Do not use wound conductors
* Have lower parasitic resistance
* Can achieve very high $Q$ (e.g., NP0/C0G, mica)

As frequency increases, inductors are often replaced by:

* Transmission lines
* Stubs
* Distributed elements

---

### Typical $Q$ values

* Audio inductors: $Q \approx 100$–$1000$
* RF inductors: $Q \approx 10$–$100$
* Microwave inductors: $Q < 20$

---

### Practical RF design guidelines

* Use the smallest inductance possible
* Operate well below the SRF
* Prefer air-core or planar inductors
* Use distributed elements at high frequency

---

If you want, I can also give you:

* a **very short exam answer version**, or
* a **single-page README summary**, or
* diagrams explaining **SRF and parasitics**
