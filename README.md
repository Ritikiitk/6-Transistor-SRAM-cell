# 🧬 6-Transistor SRAM Cell

A **6T SRAM cell** contains two cross-coupled CMOS inverters and two NMOS access transistors.  
Once active, the access transistors allow the cell's internal nodes to communicate with the cell's input/output ports.  
The input/output ports of the cell are termed **bit lines** (`BL` and `BLbar`).

The flip-flop is mostly used for alternate storage.  
As long as a new value is pushed to it, one flip-flop will preserve the value.

---

## 🧪 Working in LTspice

**LTspice** contains an integrated schematic editor, waveform viewer, and advanced features.  
It is easy to use once you learn some basic commands.

The book _"CMOS SRAM Circuit Design and Parametric Test in Nano-Scaled Technologies"_ by **Manoj Sachdeva** is my first choice, and I have used LTspice to create the schematic diagram for a **6T SRAM cell**.

![LTspice Schematic](https://github.com/user-attachments/assets/c83e321c-ef0d-491d-851c-6f37c6840ceb)

---

## 🧠 Working in Cadence Virtuoso

**Cadence Virtuoso** is a powerful EDA tool that helps in learning IC design and circuit analysis.

First, we create a **schematic**.  
There are various libraries available in the software:

- Go to: `Tools` → `Library Manager`
- Then: `File` → `New` → `Library`

For example, I have a library that contains components of the **90 nm technology node**.

After completing the circuit design and supplying the required power rails, we verify the design.

![Cadence Design](https://github.com/user-attachments/assets/2630abcc-93a8-44bf-b904-566deb6be8e9)

Next, we simulate the circuit design.  
**Simulation in Cadence** helps us understand how the circuit will behave in real life if fabricated.

---

## ⚡ DC Analysis

DC analysis examines only the output of the circuit for a specific input from a DC power supply.  
This involves sweeping through different input voltage values and monitoring the output voltage/current.

![DC Analysis - Butterfly Curve](https://github.com/user-attachments/assets/37ae2bd8-e64c-42e5-aa87-b9d41e0575cf)

The **VTC characteristics** of one inverter are plotted against the **inverse VTC** of the other, resulting in a "butterfly" shaped curve.  
Observe the line with blue and red strokes.

> The intersections of the butterfly curve with the diagonal green line (representing a stable state) indicate the **stable operating points** of the cell (where it stores a `0` or `1`).

---

## 🌡️ Corner Analysis

**Corner analysis** determines how a circuit performs under various **process, voltage, and temperature (PVT)** settings.  
Cadence uses this method to spot performance issues and ensure the circuit's reliability in different conditions.

In **ADE XL**, I define "corners" for different process variations:

- Slow
- Fast
- Typical

You can specify variables to be swept or varied in your simulation.  
Here is a snapshot of my variable setting for reference:

👉 [Corner Analysis Variable Settings](https://github.com/Ritikiitk/6-Transistor-SRAM-cell/blob/main/DataviewOfCorner.PNG)

---

📌 _This project is part of my exploration into CMOS memory design and simulation using both open-source and industry-standard tools._

![cornerAnalysis](https://github.com/user-attachments/assets/1df61517-3991-4cc7-bd92-a1b06fad41ea)

<br>
