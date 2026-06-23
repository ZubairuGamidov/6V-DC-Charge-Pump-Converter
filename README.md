# Low-Cost 6V DC-DC Charge Pump Converter

## 1. Introduction
The objective of this project is to design a low-cost charge pump circuit with a single input power source of 6V DC, satisfying all requirements like output load voltage, efficiency, voltage regulation, and cost-effectiveness. 

To meet these goals, the circuit utilizes an NE555 timer configured in astable mode to generate a switching signal. This signal is buffered by a BJT push-pull driver (using BC238 and BC308) to provide sufficient current to a multi-stage diode-capacitor voltage multiplier network. LTspice was used to build and test the circuit.

---

## 2. Design Specs & Laboratory Bench Results

The physical prototype was fabricated and tested in the laboratory using an oscilloscope, power supply, and multi-meter to verify compliance with design benchmarks:

* **Output Voltage (No Load):** Measured at **17.9V**, successfully staying under the maximum 20V constraint.
* **Output Voltage (Under $560\Omega$ Load):** Delivers a stable **16.2V**, comfortably exceeding the required 15.0V threshold.
* **Peak-to-Peak Output Ripple ($V_r$):** Measured at a very low **36.0mV** under full load, satisfying the noise restrictions.
* **System Power Efficiency ($\eta$):** Achieved **75.1%** overall efficiency during hardware testing.
* **Total Component Cost:** Calculated at **17.86 TL**, keeping the prototype well under the 20 TL budget cap.

---

## 3. Circuit Architecture
* **Astable Oscillator:** Configured via resistors $R_A = 1.2\text{k}\Omega$, $R_B = 12\text{k}\Omega$, and a $2.2\text{nF}$ ceramic capacitor to establish the system's operational switching frequency.
* **Buffer/Driver Stage:** A complementary BJT pair containing the **BC238 (NPN)** and **BC308 (PNP)** acting as a low-impedance high-current buffer to rapidly charge and discharge the multiplier network.
* **Multiplier Network:** A 2-stage voltage multiplication configuration utilizing four low forward-drop **1N5819 Schottky diodes** and $100\mu\text{F}$ electrolytic storage capacitors.

---

## 4. File Guide
* `Simulation/`: Contains the native LTspice transient simulation circuit file (`.asc`) and its corresponding analysis report.
* `Hardware/`: Contains the DipTrace schematic design (`.dch`) and hardware PCB layout (`.dip`) source files.
* `Production/`: Pre-packaged, standard-compliant Gerber and NC Drill manufacturing zip archive for automated fabrication.
* `Documentation/`: Full lab implementation report containing bench test photos, oscilloscope waveforms, and detailed efficiency metrics.
