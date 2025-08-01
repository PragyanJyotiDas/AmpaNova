# Amplitude Modulation using Diode and Tank Circuit

This project implements an **Amplitude Modulation (AM)** circuit using a diode-based rectifier and a parallel **LC Tank Circuit** to perform envelope detection and waveform shaping. The simulation is carried out in **LTspice**.

## Overview

The main objective of this project is to observe and analyze how a modulated half-wave signal can be shaped into a full-wave-like envelope using a parallel LC circuit. The diode allows only one half-cycle to pass, and the energy is then used to trigger the tank circuit, which helps reconstruct the full envelope.

## Circuit Description

- **Input Waveform**: A modulated sine wave or pure carrier.
- **Diode**: Allows the positive half of the signal to pass, creating a half-wave rectified signal.
- **LC Tank**: Composed of an inductor (L) and capacitor (C) connected in parallel. Resonates at a specific frequency to complete the missing negative half.
- **10kΩ Resistors**: Placed across nodes to provide a discharge path for the capacitor and to allow DC bias current for diode conduction.

## Simulation

The simulation is run for `.tran 60ms` to clearly observe the waveform dynamics over time.

### Observed Waveform Transitions

- At **0 ms – 19 ms**, the tank circuit is idle or slowly charging depending on the modulation.
- At **0.019s**, the diode conducts as the input exceeds the forward voltage (~0.7V).
- The tank circuit gets **triggered** when energy passes through the diode and begins oscillating at its resonant frequency.
- The **oscillation builds a full-wave-like envelope**, thus restoring the missing half-wave.

## Working Principle

1. **Half-Wave Formation**:
   - The diode conducts only on positive cycles, cutting off negative parts.
   - This forms a half-wave modulated signal.

2. **Triggering the LC Tank**:
   - The energy from the rectified signal charges the capacitor.
   - The tank circuit oscillates and "fills in" the missing half.
   - The result appears as a reconstructed envelope.

3. **Why Energy Doesn't Go to Infinity**:
   - The 10kΩ resistors provide a discharge path.
   - The tank has internal loss (resistance), so oscillation dies out unless reinforced.

## Role of 10kΩ Resistors

- Ensures **bias current** flow for the diode during conduction.
- Provides a **discharge path** for the capacitor.
- Without it, the tank may **saturate or distort** due to charge buildup, and diode may not conduct properly.

## Output Observations

- After triggering, the **output waveform mimics a full-wave envelope**.
- The **oscillation dies** if not continuously reinforced by the carrier.
- This behavior **emulates an envelope detector** using analog elements.

## Future Scope

- Add envelope detector using op-amp precision rectifier.
- Vary tank parameters for different modulation frequencies.
- Observe spectral characteristics with FFT.

## Author

**Pragyan Das**

---

This project demonstrates practical amplitude modulation using basic electronic components and highlights how analog filtering and wave shaping can restore signal information.
