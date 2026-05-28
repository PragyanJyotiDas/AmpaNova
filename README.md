# ⚡ Mixed-Signal Function Generator & Signal Processing System

A comprehensive **LTspice simulation** of a mixed-signal function generator paired with analog signal processing circuits — covering filtering, modulation, mathematical operations, and ADC-DAC interfacing.

> 📁 **Important**: `Main_circuit.asc`, `Draft23symbiol.asc`, and its associated `Draft23symbiol.asy` symbol file **must all be present in the same LTspice working directory** for the simulation to run correctly.

---

## 🗂️ Table of Contents

- [Circuit Overview](#-circuit-overview)
- [Simulation Settings](#-simulation-settings)
- [Running the Simulation](#-running-the-simulation)
- [Files Required](#-files-required)

---

## 🔭 Circuit Overview

### 🌊 Function Generator
Produces four selectable waveforms:
- 🔵 **Sine**
- 🟥 **Square**
- 🔺 **Triangular**
- 📈 **Quadratic**

---

### 📡 Frequency Doubler
- A duplicated version of the function generator.
- Performs **frequency doubling** using analog manipulation techniques.

---

### 🧮 Differential Equation Solver Circuits *(Middle Block)*
- **First-order** and **second-order** DE solver circuits placed side by side.

---

### 🔀 Switching System for Adder *(Below DE Solvers)*
- Implements switching control to dynamically select input signals for a **single analog adder**.

> ⚠️ To test each circuit individually, **move the input to that circuit's specific input node** — only one is controlled and switched at a time.

---

### 📻 Filtering, AM & Multiplier Circuits *(Lower Section)*

| Block | Description |
|---|---|
| 🎛️ **Filter Circuit** | Low-pass, high-pass, and band-pass filter implementations |
| 📶 **AM Circuit** | Uses a diode + LC tank for envelope shaping; half-wave converted to full-wave-like envelope via resonance |
| ✖️ **Multiplier Circuit** | Analog signal multiplication |

---

### 🔄 ADC ↔ DAC Interface *(Final Block)*
Demonstrates full analog-digital interfacing:
- 🔢 **ADC mock-up** using comparators
- 🔁 **DAC reconstruction** via summing amplifiers or weighted resistors

---

## ⚙️ Simulation Settings

Run the simulation with the following SPICE directive for clear and stable waveform observation:

```spice
.tran 60m
```

> 🕒 A **60 ms transient analysis** provides the ideal balance between waveform visibility and detail. Avoid excessively large simulation times.

---

## ▶️ Running the Simulation

1. 📂 Open `Main_circuit.asc` in **LTspice**.
2. ✅ Ensure `Draft23symbiol.asy` and `Draft23symbiol.asc` are in the **same folder**.
3. ⏱️ Set the simulation directive to `.tran 60m`.
4. 🔍 Use **voltage probes** to examine waveforms at key nodes.
5. 🔌 Move the input signal to the desired circuit block to test its individual response.

---

## 📋 Files Required

| File | Purpose |
|---|---|
| `Main_circuit.asc` | 🗺️ Main LTspice schematic |
| `Draft23symbiol.asc` | 🧩 Supporting subcircuit schematic |
| `Draft23symbiol.asy` | 🎨 Custom component symbol file |

> 🚨 The `.asc` and `.asy` files are **mandatory** and must reside in the **same directory** as the main schematic to simulate and visualize the circuits correctly.
