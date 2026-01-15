## Physical Difference Between Characteristic Impedance and Input Impedance

| Parameter | Characteristic Impedance ($Z_0$) | Input / Normal Impedance ($Z_{in}$) |
|---------|----------------------------------|-------------------------------------|
| **What it really is** | Intrinsic property of the transmission line itself | What the source or driver actually sees looking into the line |
| **Depends on** | Only geometry and materials (conductor width, spacing, dielectric constant) | $Z_0$, line length, load impedance ($Z_L$), and frequency |
| **Length dependence** | Independent of length (same for 1 cm or 10 km) | Strongly length-dependent (changes every $\lambda/4$) |
| **Physical meaning** | Ratio $V/I$ of a **single traveling wave** (no reflection) | Total $V/I$ including **incident + reflected waves** |
| **When they are equal** | — | Only when the line is infinitely long or perfectly matched ($Z_L = Z_0$) |
| **Reflections included?** | Assumes **no reflections** (infinite or matched line) | Usually includes reflections unless perfectly matched |
| **Real-world example** | Good coaxial cable → always $\approx 50\,\Omega$ or $75\,\Omega$ | 50 Ω cable with open end → $Z_{in}$ may be very large or very small depending on length and frequency |
| **Time-domain view** | Impedance the wave “feels” at the instant it starts propagating | Steady-state impedance after reflections settle (or keep bouncing) |

---

## Key Physical Insight 🧠

- **$Z_0$ belongs to the line**
- **$Z_{in}$ belongs to the system**
- Reflections are what make $Z_{in}$ change
- Matching ($Z_L = Z_0$) eliminates reflections and makes  
  $$
  Z_{in} = Z_0
  $$

---

## One-Line Exam Answer ✍️

> Characteristic impedance is an intrinsic property of a transmission line determined by its geometry and materials, while input impedance is the impedance seen by the source and depends on line length, load impedance, frequency, and reflections.
