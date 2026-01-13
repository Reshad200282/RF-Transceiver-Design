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
<img width="1204" height="589" alt="image" src="https://github.com/user-attachments/assets/0665c50a-babd-4b2d-8ea6-a7d7659790ae" />
<img width="1194" height="575" alt="image" src="https://github.com/user-attachments/assets/b2159927-e8a1-4c9c-ad79-69675385a0be" />
A linear time-invariant system is a system that satisfies superposition and whose behavior does not change with time.
\\
If a signal exists for a finite duration in time, its frequency spectrum must extend to infinite bandwidth,
and if a signal is limited to a finite bandwidth, it must exist for infinite time. 
<img width="1212" height="586" alt="image" src="https://github.com/user-attachments/assets/98d4cfb5-4c4a-42f4-a2aa-8b5a78ea56de" />
<img width="1195" height="595" alt="image" src="https://github.com/user-attachments/assets/dae6aef8-2f5f-4719-8c8a-9858d4ae257b" />
<img width="1189" height="587" alt="image" src="https://github.com/user-attachments/assets/46f65cdf-8184-487c-9e9b-5ebe636e0a7c" />
<img width="1189" height="587" alt="image" src="https://github.com/user-attachments/assets/ec6cf18f-780d-48bd-a1b5-6639eaa9baf8" />


## Why we donot use sine function
Here’s a **clear, short, exam-friendly explanation** of **why we do not use an ideal sinc function**, written in **GitHub-safe Markdown**.

---

## Why We Do Not Use the Sinc Function

The **sinc function** is theoretically ideal for digital communication, but it is **not practical to use in real systems**.

---

## What the Sinc Function Does

* A sinc pulse is **bandwidth-limited**
* It satisfies the **Nyquist criterion**
* It produces **zero ISI** at sampling instants

That’s why, in theory, it looks perfect.

---

## Reasons We Do NOT Use Sinc in Practice

### 1. Infinite Time Duration

The sinc function extends infinitely in time:

```
sinc(t) ≠ 0  for  −∞ < t < +∞
```

This means:

* Transmission must start at −∞
* Reception must continue to +∞

❌ **Physically impossible**

---

### 2. Infinite Delay

Because it never truly ends:

* Receiver must wait forever to detect a symbol
* Not suitable for real-time communication

---


### 3. Extremely Sensitive to Timing Errors

* Small sampling-time errors cause large ISI
* Not robust to clock jitter

❌ Very fragile in practice

---

### 5. Not Implementable in Hardware

* Infinite impulse response
* Requires infinite memory and computation

❌ Cannot be realized using real filters

---

## What Is Used Instead

Practical systems use **approximations of sinc**:

* Raised cosine pulse
* Root raised cosine (RRC)
* Gaussian pulse (in some systems)

These:

* Have finite time duration (or fast decay)
* Trade bandwidth for robustness
* Are practical to implement

---

## One-Line Exam Answer

```
The sinc function is not used in practice because it has infinite time duration and is impossible to generate or implement in real communication systems.
```

---

## One-Line Engineering Summary

```
Sinc is perfect in theory, impossible in reality.
```

---

## Signal Constellation 
<img width="1909" height="934" alt="image" src="https://github.com/user-attachments/assets/d89a98f5-9221-45bd-aa0a-c79dd44f7d5b" />
Signal Constellation

A signal constellation is a graphical representation of modulated digital symbols in the signal space, usually plotted on the I-Q (In-phase and Quadrature) plane.

Each point in the constellation represents one symbol.
