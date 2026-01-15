<img width="1210" height="487" alt="image" src="https://github.com/user-attachments/assets/cc2939c6-b669-4026-8650-0598888f9db1" />
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

