# LIC_Amplifier_Configurations_Experiment-2
Design and comparative analysis of three amplifier configurations using 180nm CMOS in LTspice.
## AIM

To design and analyze a Common Source (CS) amplifier with PMOS active load using 180nm CMOS technology and evaluate its DC, Transient and AC performance.
## GIVEN SPECIFICATIONS

| Parameter | Value |
|------------|--------|
| VDD | 1.5 V |
| Power Constraint | ≤ 0.5 mW |
| Load Capacitor (CL) | 1 pF |
| Channel Length (L) | 180 nm |
| Assumed Overdrive Voltage (Vov) | 0.25 V |
| Source Voltage Drop (VRS) | 0.2 V |
---

# CIRCUIT 1  
## Common Source Amplifier with PMOS Active Load
### Circuit Diagram

![Circuit 1](Circuit1_Schematic.png)
### Circuit Description

This circuit is a **Common Source (CS) amplifier with PMOS active load**.

- **M1 (NMOS)** acts as the amplifying transistor.
- **M2 (PMOS)** acts as an active load to increase gain.
- **RS** provides source degeneration for bias stabilization.
- **VB1** biases the PMOS transistor.
- Input signal is applied at the gate of M1.
- Output is taken at the drain node (Vout).

The circuit is designed to operate all transistors in the **saturation region** to ensure proper amplification.

## DC Analysis and Design Calculations

### Step 1: Drain Current from Power Constraint

Given:
VDD = 1.5 V  
P ≤ 0.5 mW  

P = VDD × ID  

ID = 0.5 mW / 1.5  
ID = 0.334 mA  

---

### Step 2: NMOS (M1) Width Calculation

Saturation current equation:

ID = (1/2) kn' (W/L) (Vov)²  

Rearranging for W:

W = (2 ID L) / (kn' (Vov)²)

Substituting values:

kn' = 2.30 × 10⁻⁴ A/V²  
L = 180 nm  
Vov = 0.25 V  
ID = 0.334 mA  

Wn ≈ 8.36 µm  

---

### Step 3: PMOS (M2) Width Calculation

ID = (1/2) kp' (W/L) (Vov)²  

W = (2 ID L) / (kp' (Vov)²)

kp' = 9.73 × 10⁻⁵ A/V²  

Wp ≈ 19.7 µm  

---

### Step 4: Source Resistor (RS)

Given VRS = 0.2 V  

RS = VRS / ID  
RS = 0.2 / 0.334mA  

RS ≈ 598.8 Ω  

---

### Final Designed Values

| Parameter | Value |
|------------|--------|
| ID | 0.334 mA |
| Wn | 8.36 µm |
| Wp | 19.7 µm |
| RS | 598.8 Ω |

The above calculations ensure proper DC biasing and saturation region operation.

![Circuit 1 DC Operating Point](Circuit1_DC_OperatingPoint.png)

### Observations

- ID(M1) ≈ 0.335 mA  
- ID(M2) ≈ 0.335 mA  
- Vout ≈ 0.946 V  
- Source voltage ≈ 0.20 V  

The simulated drain current matches the calculated value (0.334 mA), confirming correct DC biasing.
