# Mixed-Signal Function Generator and Signal Processing System

This project simulates a mixed-signal function generator along with various analog signal processing circuits, including filtering, modulation, mathematical operations, and ADC-DAC interfacing. The simulation is done using **LTspice**, and the main schematic file is `draft25.asc`.

>  **Note**: To properly simulate this system, **both `draft25.asc` and its associated `.asy` symbol files must be present in the same LTspice working directory**.

---

Simulation Settings     

Run the simulation with the following directive for clear and stable waveform observation:.tran 60m


Avoid using very large simulation times. A 60ms transient analysis provides a balance between visibility and detail.

---

Circuit Overview

Function Generator 

- Produces four selectable waveforms: **sine**, **square**, **triangular**, and **quadratic**.

Frequency Doubler

- A duplicated version of the function generator.
- Performs **frequency doubling** using analog manipulation techniques.

---

###Differential Equation Solver Circuits (Middle Block)

- First and second order DE solver circuits are placed next to each other.

---

Switching System for Adder (Below DE Solvers)

- Implements switching control to dynamically select input signals for a **single analog adder**.

> To test each circuit individually, **move the input to the specific circuit's input node**, as only one is controlled and switched at a time.

---

Filtering, AM, and Multiplier Circuits (Lower Section)

- **Filtering Circuit**: Basic low, high and band pass filter made
- **Amplitude Modulation (AM) Circuit**:
  - Uses a diode and LC tank to perform envelope shaping.
  - Half-wave signal is converted into a full-wave-like envelope using resonance.
- **Multiplier Circuit**:
  

---

ADC to DAC Interface (Final Block)

- Demonstrates analog-digital interfacing.
- Converts analog signals to discrete values and back to analog using:
  - ADC mock-up with comparators
  - DAC reconstruction using summing amplifiers or weighted resistors

---

Running the Simulation

1. Open `draft23.asc` in LTspice.
2. Ensure the required `.asy` custom symbol files are placed in the appropriate folder.
3. Use `.tran 60m` to view meaningful analog behavior over time.
4. Use **voltage probes** to examine waveforms at key nodes.
5. Move the input signal to the desired circuit block to test its individual response.

---

Files Required

- `draft23.asc` – Main LTspice schematic
- `.asy` files – Custom component symbols used in the schematic

> These two file types are **mandatory** to simulate and visualize the entire analog computing architecture.

---



---

