<img width="1184" height="573" alt="image" src="https://github.com/user-attachments/assets/6f414ff5-ead9-4f8b-bcd7-59e1065673fb" />
<img width="1201" height="585" alt="image" src="https://github.com/user-attachments/assets/64e25b68-dad0-467d-af4d-c7c79270cd91" />
<img width="1083" height="559" alt="image" src="https://github.com/user-attachments/assets/b37db174-3e3a-41fa-9714-9194925dd253" />

<img width="1203" height="434" alt="image" src="https://github.com/user-attachments/assets/b3263d8f-e560-4b42-9ae2-23e7aa7b350d" />

# 📡 Diode Noise – Useful for Noise Calculations

## 🔌 1. Practical Noise Model of a Diode

When a diode conducts a DC current $I_D$, it is modeled as:

- Series resistance: $R_s$
- Dynamic (junction) resistance: $r_d$
- Noise sources:
  - 🌡️ Thermal noise (from $R_s$)
  - 🎯 Shot noise (from DC current flow)
  - 🌊 Flicker noise (low-frequency noise)

This is the **real RF diode model**, not an ideal one.

---

## 🌡️ 2. Thermal Noise (Series Resistance)

The series resistance $R_s$ generates **thermal (Johnson–Nyquist) noise**.

### Noise voltage (mean-square)

$$
v_s^2 = 4 k T R_s \Delta f
$$

### Power Spectral Density (PSD)

$$
S_{v_s}(f) = 4 k T R_s \quad (\text{V}^2/\text{Hz})
$$

### 🧠 Physical Meaning

- Due to random thermal motion of carriers
- Exists even without DC current
- Depends only on temperature $T$ and resistance $R_s$

---

## 🎯 3. Shot Noise (Dominant Noise in Diodes)

When DC current flows, charge carriers cross the junction randomly, producing **shot noise**.

### Shot noise current (mean-square)

$$
i_s^2 = 2 q I_D \Delta f
$$

### Shot noise PSD

$$
S_{i_s}(f) = 2 q I_D \quad (\text{A}^2/\text{Hz})
$$

### 🔍 Physical Meaning

- Comes from discrete electron flow
- Proportional to DC current
- **Dominant noise in forward-biased diodes**

✔️ This is why shot noise dominates in RF diode operation.

---

## 🌊 4. Flicker Noise (1/f Noise)

At low frequencies, **flicker noise** becomes significant.

### Flicker noise PSD model

$$
S_{i_f}(f) = \frac{K I_D^a}{f^b}
$$

where:

- $K$ → device-dependent constant
- $I_D$ → DC diode current
- $a \approx 0.5 \le a \le 2$
- $b \approx 1$
- $f$ → frequency

### 📉 Key Property

$$
S(f) \propto \frac{1}{f}
$$

- Dominates at **low frequencies**
- Strongly process-dependent

---

## 🧮 5. Total Noise in a Diode

The total diode noise power spectral density is the sum of all components:

$$
S_{\text{total}} =
\underbrace{4 k T R_s}_{\text{Thermal}}
+
\underbrace{2 q I_D}_{\text{Shot}}
+
\underbrace{\frac{K I_D^a}{f^b}}_{\text{Flicker}}
$$

Each term dominates under different operating conditions.

---

## ⚖️ 6. Which Noise Dominates?

| Condition               | Dominant Noise    |
|------------------------|-------------------|
| Forward-biased RF diode | 🎯 Shot noise     |
| Large series resistance | 🌡️ Thermal noise |
| Low-frequency operation | 🌊 Flicker noise  |

---

## 🔁 7. Why This Matters in RF Systems

Diodes are widely used as:

- RF switches
- TDD / TDMA switching elements
- High-speed control devices

### ⚠️ Impact of Diode Noise

- Raises receiver noise floor
- Reduces sensitivity
- Limits weak-signal detection

Even though diodes are simple and fast, **their noise cannot be ignored**.

---

## 📝 8. Exam-Ready One-Liner ⭐

> In a forward-biased diode, shot noise due to DC current is the dominant noise source, while thermal noise arises from series resistance and flicker noise dominates at low frequencies.

---

## 🚀 9. What Comes Next

After diode noise:

- BJT noise modeling
- MOSFET / FET noise
- Linearity and distortion (1-dB compression, IP3)
