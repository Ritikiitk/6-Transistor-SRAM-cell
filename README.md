# 6-Transistor SRAM cell
A 6T SRAM cell contains two cross-coupled CMOS inverters and two NMOS access transistors. 
Once active, access transistors allow the cell's internal nodes to communicate with the cell's input/output ports. 
The input/output ports of the cell unit of measurement are termed bit lines (BL and ~BL).
The flip-flop is mostly used for alternate 
storage. As long as the other value is pushed to it, one flip-flop will 
preserve the value.
<H2> Working in LTspice </H2>
LTspice contains an integrated schematic editor, waveform viewer and advanced features. It is easy to use once you learn some basic commands.
The book (CMOS SRAM Circuit Design and Parametric Test in Nano-Scaled Technologies by Manoj Sachdeva) is my first choice, and I have used LTSpice to create the schematic diagram for a 6T SRAM cell.

![Image](https://github.com/user-attachments/assets/c83e321c-ef0d-491d-851c-6f37c6840ceb)
<br>
<H2> Working in Cadence Virtuoso </H2>
<p>Cadence virtuoso is good EDA tool for us by which we can learn about how to design Integrated Circuit, analysis circuits based their characterstics.
First we create a schematic.</p>
<p>There are various libraries present in the software. Click Tools--->Library Manager. Click File ---> New ---> Library</p>For example, I have a library which contains components of the 90 nm technology node.
 <p>After completing our circuit designing and supplying the power rails based on requirement, we have to verify our design.</p> 

![clearimg](https://github.com/user-attachments/assets/2630abcc-93a8-44bf-b904-566deb6be8e9)
After that we have to simulate our circuit design.
Simulation in cadence is the step where we use the tool to understand how this circuit will work in real life, if fabricated.
<br>
<H2> DC Analysis </H2>
Only the output of your circuit for a specific input from a DC power supply is being examined in DC analysis.
This involves sweeping through different input voltage values and monitoring the output voltage/current from the circuit.

![DC_analysis_butterflycurve](https://github.com/user-attachments/assets/37ae2bd8-e64c-42e5-aa87-b9d41e0575cf)
The VTC characterstics of one inverter is plotted against the inverse VTC of the other inverter. This results in a "butterfly" shaped curve, with two lobes. Observe line with blue and red strokes.
<p>The intersections of the butterfly curve with the diagonal green line (representing a stable state) indicate the stable operating points of the cell (where it stores a 0 or 1).</p>

<H2> Corner Analysis </H2>
To determine how a circuit performs differently under various process, voltage, and temperature settings, Cadence uses corner analysis. This aids in spotting possible performance problems and guarantees the circuit's dependability under various operating circumstances.
<p>In ADE XL, Here I define "corners" for different process variations (e.g., Slow, Fast, Typical).</p> You can specify the variables to be swept or varied in your simulation. I have attached my variable setting you can follow this for reference. https://github.com/Ritikiitk/6-Transistor-SRAM-cell/blob/main/DataviewOfCorner.PNG

![cornerAnalysis](https://github.com/user-attachments/assets/1df61517-3991-4cc7-bd92-a1b06fad41ea)

<br>
