<img width="1020" height="586" alt="image" src="https://github.com/user-attachments/assets/cbf9a7ba-93e6-4c0b-a48c-3347412323a6" />


# 🔊 Noise in RF Devices — Deep Dive (Diode, BJT, MOSFET)

---

## 1️⃣ What is Noise *Physically*? 🧠

Noise comes from **random motion of charge carriers**:

- Electrons do **not** move smoothly
- They arrive **randomly in time**
- This randomness produces **unpredictable voltage and current**

**Key idea**

> **Noise = uncertainty added to the signal**

In RF systems, noise sets the **minimum detectable signal (MDS)**.

---

## 2️⃣ Thermal Noise — The Foundation 🔥

Every resistive element at temperature $T > 0$ generates noise.

### 🔹 Voltage Power Spectral Density (PSD)

$$
S_v(f) = 4kTR \quad [\text{V}^2/\text{Hz}]
$$

### 🔹 Noise power in bandwidth $B$

$$
P_n = kTB
$$

📌 **Important facts**

- Independent of frequency → **white noise**
- Exists even with **no DC current**

---

## 3️⃣ Shot Noise — Charge Quantization 🎯

### 🧩 Physical Origin

Electric current consists of **discrete electrons**, not a continuous flow.

- Each electron has charge $q$
- Arrival time is random (Poisson process)

---

### 🔹 Shot Noise PSD

$$
S_i(f) = 2qI \quad [\text{A}^2/\text{Hz}]
$$

- Proportional to **DC current**
- Frequency independent → white noise

---

## 4️⃣ Flicker Noise (1/f Noise) 🌊

### 🧩 Physical Origin

- Carrier trapping and de-trapping
- Interface defects
- Surface states

---

### 🔹 Flicker Noise PSD

$$
S(f) = \frac{K I^a}{f}
$$

where:

- $0.5 \le a \le 2$
- $K$ depends on device and fabrication process

📉 On a log–log plot → slope = **–1**

📌 Dominant at:

- Low frequency
- Baseband / IF
- Switches and mixers

---

## 5️⃣ Noise in **Diode** ⚡

### 🔹 Diode Model

- Series resistance: $R_s$
- Junction resistance:

$$
r_d = \frac{kT}{qI_D}
$$

---

### 🧨 Noise Sources

#### (a) Series Resistance Thermal Noise

$$
\overline{v_s^2} = 4kTR_s \Delta f
$$

---

#### (b) Shot Noise (Dominant)

$$
\overline{i_s^2} = 2qI_D \Delta f
$$

---

#### (c) Flicker Noise

$$
\overline{i_f^2} = \frac{K I_D^a}{f} \Delta f
$$

---

### 📌 Diode Noise Summary

| Noise Type | Physical Cause | Importance |
|----------|---------------|------------|
| Thermal  | $R_s$          | Medium     |
| Shot     | $I_D$          | **Dominant** |
| Flicker  | Traps          | Low-frequency |

➡️ **Why important?**  
Diodes are used as:

- RF switches
- Mixers
- T/R switches (TDD)

Noise directly degrades **receiver sensitivity**.

---

## 6️⃣ Noise in **BJT** 🔴

### 🧩 Why BJTs Are Low-Noise

- Current-controlled devices
- Efficient carrier transport
- Low flicker noise

---

### 🔹 BJT Noise Sources

#### (a) Base Resistance Thermal Noise

$$
\overline{v_b^2} = 4kTr_b \Delta f
$$

---

#### (b) Collector Shot Noise (Dominant)

$$
\overline{i_c^2} = 2qI_C \Delta f
$$

---

#### (c) Base Shot Noise

$$
\overline{i_b^2} = 2qI_B \Delta f
$$

---

#### (d) Flicker Noise

$$
\overline{i_f^2} = \frac{K I_B^2}{f} \Delta f
$$

---

### 📌 Why BJTs Are Preferred in RF LNAs 🎧

- Shot noise ∝ $I_C$
- High transconductance $g_m$ per mA
- Lower noise figure than MOSFETs

---

## 7️⃣ Noise in **MOSFET** 🟢

MOSFETs do **not** exhibit shot noise in the channel.

---

### 🔹 Channel Thermal Noise (Main RF Noise)

$$
\overline{i_d^2} = 4kT\gamma g_m \Delta f
$$

where:

- $\gamma = \frac{2}{3}$ for long-channel devices
- $\gamma \approx 1$ for short-channel devices

---

### 🔹 Gate-Induced Noise

$$
\overline{i_g^2} = \frac{16}{15} kT \omega^2 C_{gs}^2 \Delta f
$$

📌 Important at **GHz and above**

---

### 🔹 Flicker Noise in MOSFETs

$$
S_{i_f}(f) = \frac{K}{WLC_{ox}} \cdot \frac{1}{f}
$$

Reduced by:

- Larger device area
- PMOS instead of NMOS

---

## 8️⃣ Why **1-dB Compression Point** Matters ⚠️

### ❓ Does compression affect noise?

👉 **Indirectly, yes**

---

### 🔹 Relationship

| Parameter | Affects |
|--------|--------|
| Noise | Small-signal behavior |
| 1-dB compression | Large-signal behavior |
| Dynamic range | **Both** |

---

### 🧠 Key Insight

> A receiver must amplify **weak signals (noise-limited)**  
> and survive **strong signals (linearity-limited)**

Low $P_{1\text{dB}}$ leads to:

- Gain compression
- Intermodulation
- Desensitization (noise floor appears higher)

---

## 9️⃣ Big RF Picture 📡

$$
\text{Sensitivity} \approx kTB \times \text{NF}
$$

$$
\text{Dynamic Range} = P_{1\text{dB}} - \text{Noise Floor}
$$

Noise and linearity **must be designed together**.

---

## 🔑 Final Exam-Ready Takeaways 🧠

- Thermal noise → always present
- Shot noise → dominant in diodes and BJTs
- MOSFET RF noise → channel thermal noise
- Flicker noise → low-frequency problem
- 1-dB compression → limits usable gain
- Noise + compression → define receiver performance


<img width="1065" height="588" alt="image" src="https://github.com/user-attachments/assets/63f8738a-38f3-48c1-a93c-ddef295e7afe" />

Great, let’s go **one more level deeper**—this time I’ll be **very explicit**, slow, and physical.
Think of this as a **“from electrons → equations → RF system”** explanation 🧠📡

I’ll structure it so you can **study + revise + write answers**.

---

# 🔊 Deep Dive: Noise, Noise Figure, and What This Diagram *Really* Means

We’ll answer **four big questions**:

1. **Where does noise actually come from?**
2. **Why passive circuits increase noise figure**
3. **Step-by-step meaning of every term in your derivation**
4. **How this connects to RF design, LNA, and dynamic range**

---

## 1️⃣ What is noise at the physical level? ⚛️

At the most fundamental level:

* Electrons move randomly due to **thermal energy**
* This motion exists **even with no signal**
* Any resistance at temperature $T > 0$ generates noise

This is unavoidable ❌
It’s a **law of physics**, not bad design.

---

### 🔥 Thermal (Johnson–Nyquist) Noise

For a resistor $R$:

[
\boxed{
S_v(f) = 4kTR \quad \text{(V²/Hz)}
}
]

Over bandwidth $B$:

[
\boxed{
v_n^2 = 4kTRB
}
]

📌 Key properties:

* White (flat vs frequency)
* Independent of DC current
* Exists even at zero signal

---

## 2️⃣ Why noise limits receiver sensitivity 🎧

A receiver detects a signal **only if**:

[
\text{Signal} ; > ; \text{Noise}
]

Minimum detectable signal:
[
\boxed{
P_{\min} \approx kTB \cdot F \cdot \text{SNR}_{\min}
}
]

So:

* More noise → higher $P_{\min}$
* Worse noise figure → worse sensitivity

This is why **noise figure matters more than gain** in RF front-ends.

---

## 3️⃣ What exactly is Noise Figure (NF)? 📊

### Definition (core idea):

[
\boxed{
F = \frac{\text{SNR}*{\text{in}}}{\text{SNR}*{\text{out}}}
}
]

* Ideal device: $F = 1$ (0 dB)
* Real device: $F > 1$

Noise figure measures **how much SNR is destroyed**.

---

## 4️⃣ Now let’s decode YOUR diagram step by step 🧩

### Circuit:

* Source resistance: $R_s$
* Load resistance: $R_p$
* Both at temperature $T$
* No active device → only passive loss

---

### 4.1 Signal transfer (voltage gain) ⚙️

This is just a voltage divider:

[
\boxed{
A_v = \frac{R_p}{R_s + R_p}
}
]

🔎 Meaning:

* Signal power is **partially lost** in $R_s$
* Lost power → heat → noise stays

---

### 4.2 Noise generated by resistors 🔊

Each resistor generates noise, but at the output:

[
R_{\text{eq}} = R_s \parallel R_p
]

So output noise:

[
\boxed{
v_{o,n}^2 = 4kT(R_s \parallel R_p)B
}
]

Important:

* Noise adds as **power**, not voltage
* Noise sources are **uncorrelated**

---

### 4.3 Input-referred noise (very important) 🎯

Noise figure is defined at the **input**, so we must refer noise back:

[
v_{n,\text{in}}^2 = \frac{v_{o,n}^2}{A_v^2}
]

Substitute:

[
v_{n,\text{in}}^2
= \frac{4kT \left(\frac{R_sR_p}{R_s+R_p}\right)B}{\left(\frac{R_p}{R_s+R_p}\right)^2}
]

After simplification:

[
\boxed{
v_{n,\text{in}}^2 = 4kTR_sB \left(1 + \frac{R_s}{R_p}\right)
}
]

---

### 4.4 Noise Figure calculation 📐

Noise from source alone:

[
v_{n,s}^2 = 4kTR_sB
]

So:

[
F = \frac{v_{n,\text{in}}^2}{v_{n,s}^2}
= \boxed{1 + \frac{R_s}{R_p}}
]

🎯 **This is the key result in your slide**

---

## 5️⃣ Physical interpretation (this is the “why”) 🧠

### 🟢 Case 1: $R_p \gg R_s$

[
F \approx 1
]

* Almost no signal loss
* Noise unchanged
* Ideal RF input

---

### 🟡 Case 2: $R_p = R_s$

[
F = 2 \Rightarrow 3\text{ dB}
]

* Half the signal power is lost
* Noise stays
* Classic **3 dB penalty**

---

### 🔴 Case 3: $R_p < R_s$

[
F \gg 1
]

* Severe SNR degradation
* Bad RF design

---

## 6️⃣ Why passive loss ALWAYS hurts NF 🚨

Passive devices:

* Do **not** generate extra noise actively
* But they **attenuate signal**

Noise at the output is:
[
kTB \quad \text{(unchanged)}
]

Signal is reduced:
[
S_{\text{out}} = \frac{S_{\text{in}}}{L}
]

So:
[
F = L
]

📌 **1 dB loss → 1 dB NF degradation**

---

## 7️⃣ Connection to LNA placement 🧩

This explains a **golden RF rule**:

> Put the **LNA first**, before any lossy element

Why?

Because Friis formula:
[
F_{\text{total}} = F_1 + \frac{F_2-1}{G_1} + \cdots
]

If the first block has loss:

* $G_1 < 1$
* Noise explodes ❌

---

## 8️⃣ Relation to dynamic range 📉📈

* **Lower bound** → noise floor
* **Upper bound** → compression (1 dB CP)
* Dynamic range:

[
\text{DR} = P_{1\text{dB}} - P_{\text{noise}}
]

More noise:

* Noise floor ↑
* Dynamic range ↓

---

## 9️⃣ Exam-ready one-paragraph answer ✍️

> Noise figure quantifies the degradation of signal-to-noise ratio caused by a component or system. Even passive circuits increase noise figure because they attenuate the signal while thermal noise remains unchanged. For a source resistance $R_s$ driving a load $R_p$, the noise figure is $F = 1 + R_s/R_p$. This demonstrates that impedance mismatch and passive loss directly increase the receiver noise floor and reduce sensitivity.

---

## 🔑 Final mental picture 🧠✨

* Noise = unavoidable thermal motion
* Passive loss = signal destroyed, noise survives
* NF = how much SNR you lose
* First stage dominates everything

---

If you want next 🔥:

* Same derivation using **noise temperature**
* Numerical RF exam problem
* Apply to **LNA + switch + filter**
* Link to **1-dB compression & intermodulation**

Just say the word 📡📘

