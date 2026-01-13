## Lecture 07 - Noise in RF Systems - I
In RF we use Power in dBm
<img width="1206" height="593" alt="image" src="https://github.com/user-attachments/assets/f0f6dafc-63b2-4006-a999-cc7696e4d99c" />


## Step 1: Convert both dBm values to linear power (milliwatts) <br>
Formula:
P (mW) = 10^(dBm / 10)
<br>
30 dBm → 10^(30/10) = 10³ = 1000 mW (1 watt)
20 dBm → 10^(20/10) = 10² = 100 mW
<br>
## Step 2: Add the powers in the linear domain (normal addition)
Total power = 1000 mW + 100 mW = 1100 mW
<br>
## Step 3: Convert total power back to dBm
Formula:
dBm = 10 × log₁₀(P in mW)
dBm = 10 × log₁₀(1100) ≈ 10 × 3.04139  ≈ 30.4139 dBm  <br>

<img width="1207" height="599" alt="image" src="https://github.com/user-attachments/assets/46a06cd5-f170-4587-b663-10f386468ef1" />
<img width="1206" height="591" alt="image" src="https://github.com/user-attachments/assets/d8816e1c-7d9b-4fc8-a874-6eb7586e58cb" />

<img width="1207" height="595" alt="image" src="https://github.com/user-attachments/assets/98468d5e-165b-4c6b-9caa-428dc2a31062" />
<img width="1199" height="593" alt="image" src="https://github.com/user-attachments/assets/09dc5bb4-1ca9-4a06-a6af-d16ce1d7fb00" />
