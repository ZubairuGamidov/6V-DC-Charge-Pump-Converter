# Low-Cost 6V DC-DC Charge Pump Converter

## 1. Introduction
[cite_start]The objective of this project is to design a low-cost charge pump circuit with a single input power source of 6V DC, satisfying all requirements like output load voltage, efficiency, voltage regulation, and cost-effectiveness[cite: 12]. 

[cite_start]To meet these goals, the circuit utilizes an NE555 timer configured in astable mode to generate a switching signal[cite: 13]. [cite_start]This signal is buffered by a BJT push-pull driver (using BC238 and BC308) to provide sufficient current to a multi-stage diode-capacitor voltage multiplier network[cite: 14]. [cite_start]LTspice was used to build and test the circuit[cite: 15].

---

## 2. Design Specs & Laboratory Bench Results

The physical prototype was fabricated and tested in the laboratory using an oscilloscope, power supply, and multi-meter to verify compliance with design benchmarks:

* [cite_start]**Output Voltage (No Load):** Measured at **17.9V**, successfully staying under the maximum 20V constraint[cite: 113, 240].
* [cite_start]**Output Voltage (Under $560\Omega$ Load):** Delivers a stable **16.2V**, comfortably exceeding the required 15.0V threshold[cite: 56, 246, 253].
* [cite_start]**Peak-to-Peak Output Ripple ($V_r$):** Measured at a very low **36.0mV** under full load, satisfying the noise restrictions[cite: 294, 301].
* **System Power Efficiency ($\eta$):** Achieved **75%** overall efficiency during hardware testing[cite: 281].
* [cite_start]**Total Component Cost:** Calculated at **17.86 TL**, keeping the prototype well under the 20 TL budget cap[cite: 209, 303].

---

## 3. Circuit Architecture
* [cite_start]**Astable Oscillator:** Configured via resistors $R_A = 1.2\text{k}\Omega$, $R_B = 12\text{k}\Omega$, and a $2.2\text{nF}$ ceramic capacitor to establish the system's operational switching frequency[cite: 36, 42, 45, 59].
* **Buffer/Driver Stage:** A complementary BJT pair containing the **BC238 (NPN)** and **BC308 (PNP)** acting as a low-impedance high-current buffer to rapidly charge and discharge the multiplier network[cite: 64, 66].
* [cite_start]**Multiplier Network:** A 2-stage voltage multiplication configuration utilizing four low forward-drop **1N5819 Schottky diodes** and $100\mu\text{F}$ electrolytic storage capacitors[cite: 72].

---

## 4. File Guide
* `NE555_ChargePump_Simulation.asc`: Local LTspice transient simulation file.
* `Gamidov.dch` / `Gamidov.dip`: DipTrace schematic and hardware PCB layout design files.
* `Gamidov.zip`: Production-ready Gerber and NC Drill manufacturing bundle for automated PCB fabrication.
* [cite_start]`Hardware_Implementation_Report.pdf`: Lab report covering the physical board assembly, oscilloscope waveforms, and efficiency metrics[cite: 220].
