# Amplitude-Modulation-Systems-Theoretical-Modeling-and-Hardware-Validation
This project demonstrates a complete engineering workflow for Amplitude Modulation (AM). It bridges the gap between theoretical communication systems and practical hardware implementation. By utilizing a Telecoms Trainer and a Digital Storage Oscilloscope (DSO), the experiment validates mathematical models through real-time signal acquisition and analysis.

## Table of Contents
* [Part 1: Signal Metrology & Instrumentation Authority](#-part-1-signal-metrology--instrumentation-authority)
* [Part 2: Introduction to the ETT-101 Modular System](#️-part-2-introduction-to-the-ett-101-modular-system)
* [Part 3: Mathematical Operator Modeling (The Adder)](#-part-3-mathematical-operator-modeling-the-adder)
* [Part 4: AM Synthesis & Performance Analysis](#-part-4-am-synthesis--performance-analysis)

## Part 1: Signal Metrology & Instrumentation Authority
In any engineering environment, data is only as reliable as the instruments used to collect it. Part 1 focuses on the characterization and calibration of the Digital Storage Oscilloscope (DSO). Before analyzing complex communication signals, it is essential to eliminate measurement uncertainty by validating the horizontal timebase and vertical deflection systems against a known reference signal.

### 1.1 Vertical & Horizontal Trace Optimization
- Vertical System: Configured to 1V/div with AC Coupling. This removed parasitic DC offsets, ensuring that the measurement of Vpp (Peak-to-Peak Voltage) was localized to the AC signal component.
- Time-Base Calibration: Set to 0.5ms/div. The Variable (CAL) knob was locked in the detent position to eliminate timing skew, allowing for a precise calculation of the Period ($p$).
- Triggering Logic: Employed Internal Triggering (Source: CH1) with Auto Sweep Mode to stabilize periodic waveforms, a prerequisite for accurate spectral estimation.

### **1.2 Experimental Results**
<details>
<summary>View Part 1 Documentation</summary>

![Calibration Waveform](Waveform_Captures/Part1_Results/Part1_resultfig4.jpeg)
*Figure 1.2.1: Internal CAL signal showing the verified 1Vp-p square wave.*
![Calibration Waveform](Waveform_Captures/Part1_Results/Part1_resultfig5.jpeg)
*Figure 1.2.2: Internal CAL signal showing the square wave with 1khz frequency and 1ms period.*
![Calibration Waveform](Waveform_Captures/Part1_Results/Part1_resultfig6.jpeg)
*Figure 1.2.3: Internal CAL signal showing the square wave with 1khz frequency and 1ms period zoomed in for manual computation.*

</details>

## Part 2: Introduction to the ETT-101 Modular System
Modern communication systems are often designed using high-level block diagrams. Part 2 introduces the Emona Telecoms-Trainer 101 (ETT-101), a hardware platform that allows these theoretical blocks (Adders, Multipliers, Oscillators) to be physically interconnected. This phase transitions from basic waveform observation to understanding the hardware architecture required for signal processing.

### 2.1 Hardware Block Interfacing
- Master Signals: Characterized the 100kHz Sine Wave (Carrier) and the $2kHz$ Sine Wave (Message).
- Impedance & Connectivity: Utilized 2mm patching leads to establish a common ground plane between the trainer and the oscilloscope, preventing ground loops that could distort low-level message signals.

### **2.2 Diagrams**
<details>
<summary>View Part 2 Diagrams</summary>

![Trainer Diagrams](Diagrams/Part2_Diagrams/Part2_2.1setupa.jpeg)
*Figure 2.2.1: 2khz sinewave setup.*
![Trainer Diagrams](Diagrams/Part2_Diagrams/Part2_2.1diagram.jpeg)
*Figure 2.2.2: 2khz sinewave diagram.*
![Trainer Diagrams](Diagrams/Part2_Diagrams/Part2_2.1setupb.jpeg)
*Figure 2.2.3: 100khz sine&cosinewave setup.*
![Trainer Diagrams](Diagrams/Part2_Diagrams/Part2_2.1setupspeechmodule.jpeg)
*Figure 2.2.4: Speech module setup.*
![Trainer Diagrams](Diagrams/Part2_Diagrams/Part2_2.1setupmodulebuffer.jpeg)
*Figure 2.2.5: Buffer module setup.*
![Trainer Diagrams](Diagrams/Part2_Diagrams/Part2_2.1buffermodulediagram.jpeg)
*Figure 2.2.6: Buffer module diagram.*
![Trainer Diagrams](Diagrams/Part2_Diagrams/Part2_2.2setupaddermodule.jpeg)
*Figure 2.2.7: Adder module setup.*
![Trainer Diagrams](Diagrams/Part2_Diagrams/Part2_2.2adderdiagram.jpeg)
*Figure 2.2.8: Adder module diagram.*
![Trainer Diagrams](Diagrams/Part2_Diagrams/Part2_2.2setupPhaseshiftermodule.jpeg)
*Figure 2.2.9: Phase Shifter module setup.*
![Trainer Diagrams](Diagrams/Part2_Diagrams/Part2_2.2Phaseshifterdiagram.jpeg)
*Figure 2.2.10: Phase Shifter module diagram.*

</details>

### **2.3 Experimental Results**
<details>
<summary> View Part 2 Documentation</summary>
  
![Master Signals](Waveform_Captures/Part2_Results/Part2_resultfig3sincos.jpeg)
*Figure 2.3.1: Output verification of the Master Signals Module 2kHz sine signal.*
![Master Signals](Waveform_Captures/Part2_Results/Part2_resultfig1sincos.jpeg)
*Figure 2.3.2: Output verification of the Master Signals Module 100kHz sine and cosine signal.*
![Master Signals](Waveform_Captures/Part2_Results/Part2_resultfig2sincos.jpeg)
*Figure 2.3.3: Output verification of the Master Signals Module 100kHz sine and cosine signal.*
![Master Signals](Waveform_Captures/Part2_Results/Part2_resultfig1mic.jpeg)
*Figure 2.3.4: Output verification of the Speech Module output signal .*
![Master Signals](Waveform_Captures/Part2_Results/Part_2resultfig2mic.jpeg)
*Figure 2.3.5: Output verification of the Speech Module output signal.*
![Master Signals](Waveform_Captures/Part2_Results/Part2_resultfig1buffer.jpeg)
*Figure 2.3.6: Output verification of the Buffer Module output signal.*
![Master Signals](Waveform_Captures/Part2_Results/Part2_resultfig2buffer.jpeg)
*Figure 2.3.7: Output verification of the Buffer Module output signal.*
![Master Signals](Waveform_Captures/Part2_Results/Part2_fig2addert2.jpeg)
*Figure 2.3.8: Output verification of the Adder Module output signal.*
![Master Signals](Waveform_Captures/Part2_Results/Part2_fig3addert3.jpeg)
*Figure 2.3.9: Output verification of the Adder Module output signal.*
![Master Signals](Waveform_Captures/Part2_Results/Part2_fig1phaseshift.jpeg)
*Figure 2.3.10: Output verification of the Phase Shifter Module output signal.*
</details>

## Part 3: Mathematical Operator Modeling (The Adder)
Signal summation is the most fundamental operation in electronics, used in everything from audio mixing to carrier injection. Part 3 explores the Adder Module to validate the Principle of Superposition. By combining independent signals in a controlled linear environment, we can model how message signals are prepared for the modulation stage, including the critical application of DC offsets.

### 3.1 Linear Summation Validation
The Adder module was used to implement the equation:
<p align="center">
$$v_{out}(t) = G \cdot v_a(t) + g \cdot v_b(t)$$
</p>

- Gain Optimization: By varying the $G$ and $g$ weighting factors, we simulated different signal-to-noise ratios and signal mixing levels.
- Destructive Interference: Experimentally verified the Superposition Principle by summing two signals with a phase difference of 180&deg;, resulting in a null output.

### **3.2 Diagrams**
<details>
<summary>View Part 3 Diagrams</summary>
  
![Trainer Diagrams](Diagrams/Part3_Diagrams/Part3_3.1setupaddereqn.jpeg)
*Figure 3.2.1: Modeling Equations from Adder Module setup.*
![Trainer Diagrams](Diagrams/Part3_Diagrams/Part3_3.1addereqndiagram.jpeg)
*Figure 3.2.2: Modeling Equations from Adder Module Diagram.*
![Trainer Diagrams](Diagrams/Part3_Diagrams/Part3_3.2setupadderwithphaseshiftereqn.jpeg)
*Figure 3.2.3: Modeling Equations from Adder Module with Phase Shift at Siganal B setup.*
![Trainer Diagrams](Diagrams/Part3_Diagrams/Part3_3.2adderwithphaseshiftereqndiagram.jpeg)
*Figure 3.2.4: Modeling Equations from Adder Module with Phase Shift at Siganal B Diagram.*

</details>

### **3.3 Experimental Results**
<details>
<summary>View Part 3 Documentation</summary>
  
![Adder Waveform](Waveform_Captures/Part3_Results/Part3_resultsfig1modeleq.jpeg)
*Figure 3.3.1: Linear summation of two sine waves and verified destructive interference.*
![Adder Waveform](Waveform_Captures/Part3_Results/Part3_resultsfig2modeleq.jpeg)
*Figure 3.3.2: Linear summation of two sine waves and verified destructive interference.*
</details>

## Part 4: AM Synthesis & Performance Analysis
Amplitude Modulation is the process of varying the strength of a high-frequency carrier signal in proportion to a message signal. Part 4 represents the culmination of the laboratory series, integrating the calibration from Part 1, the hardware logic from Part 2, and the summation techniques from Part 3. The goal is to synthesize a stable AM envelope and utilize specialized diagnostic modes to verify the linearity of the transmitter.

### 4.1 System Integration Flow
1. DC Injection: The $2kHz$ message signal was summed with a Variable DC offset via the Adder. This established the "Offset Message" required for non-coherent detection.
2. Product Transformation: The Offset Message and the $100kHz$ Carrier were processed through the Multiplier.
3. AM Waveform Equation:
<p align="center">
$$s(t) = [A + m(t)] \cos(2\pi f_c t)$$
</p>
                                                  
### 4.2 Diagnostic Analysis XY Mode
To verify the linearity of the modulation, we utilized XY Mode to produce a Trapezoidal Pattern:
- X-Axis: Message Signal.
- Y-Axis: AM Output.
- Interpretation: A straight-edged trapezoid indicates linear modulation. Curvature or "pinching" indicates distortion or overmodulation (m > 1).

### **4.3 Diagrams**
<details>
<summary>View Part 4 Diagrams</summary>

![Trainer Diagrams](Diagrams/Part4_Diagrams/Part4_4.1setupgeneratingammessage.jpeg)
*Figure 4.3.1: Generating AM Message setup.*
![Trainer Diagrams](Diagrams/Part4_Diagrams/Part4_4.1generatingammessagediagram.jpeg)
*Figure 4.3.2: generating AM Message diagram.*
![Trainer Diagrams](Diagrams/Part4_Diagrams/Part4_4.2setupgeneratingdsbfc.jpeg)
*Figure 4.3.3: Genearting DSBFC signal setup.*
![Trainer Diagrams](Diagrams/Part4_Diagrams/Part4_4.2generatingdsbfcdiagram.jpeg)
*Figure 4.3.4: Generating DSBFC siganal diagram.*

</details>

### **4.4 Experimental Results**
<details>
<summary>View Part 4 Documentation</summary>
  
![AM Trapezoid](Waveform_Captures/Part4_Results/Part4_resultsfig1VDCinput.jpeg)
*Figure 4.4.1: Modulating signal with VDC as source input.*
![AM Trapezoid](Waveform_Captures/Part4_Results/Part4_resultfig2Mastersignalinput.jpeg)
*Figure 4.4.2: Modulating signal with Master Signals as source input.*
![AM Trapezoid](Waveform_Captures/Part4_Results/Part4_resultfig1AMwith0.32m.jpeg)
*Figure 4.4.3: AM signal with 0.32 modulating index.*
![AM Trapezoid](Waveform_Captures/Part4_Results/Part4_resultfig2AMwith0.7m.jpeg)
*Figure 4.4.4: AM signal with 0.7 modulating index.*
![AM Trapezoid](Waveform_Captures/Part4_Results/Part4_resultfig3AMwith1m.jpeg)
*Figure 4.4.5: AM signal with ~ 1 modulating index.*
![AM Trapezoid](Waveform_Captures/Part4_Results/Part4_resultfig4AMwith1.2m.jpeg)
*Figure 4.4.6: AM signal with > 1 modulating index.*
</details>


## Results & Data Analysis
This section contains the finalized data extracted from the experimental trials and the associated post-lab analysis.

### **Measured Data Summary**
| Phase | Parameter | Expected Value | Measured Value | Analysis |
| :--- | :--- | :--- | :--- | :--- |
| **Part 1** | Calibration Freq | 1.0 kHz | 1.0kHz | Instrument validated |
| **Part 2** | Master Carrier | 100 kHz | 100.2kHz | Signal source stable |
| **Part 3** | Adder Gain | Linear | Linear | Superposition verified |
| **Part 4** | Modulation Index | $m \le 1$ | $m \le 1$ | Linear AM achieved |

*(To view all complete tables, please view or download the PDF file below.)*

**[View or Download Complete Experimental Data (PDF)](Data/Amplitude_Modulation_Systems_Theoretical_Modeling_and_Hardware_Validation_Tables_and_Data.pdf)**

### **Post-Lab Q&A**
<details>
  
<summary><b>Click to view detailed Question & Answer documentation</b></summary>

> **Note:** The following questions were answered based on observations from the ETT-101 modules and Scope traces.

*(For the full list of 10+ questions and complete answers, please download the PDF file below.)*

**[View or Download Complete Experimental Q&A (PDF)](Data/Amplitude_Modulation_Systems_Theoretical_Modeling_and_Hardware_Validation_Questions_and_Answers.pdf)**

</details>

---

## Project Resources
For full access to the raw datasets, formulas, and the complete Q&A worksheet, please use the links below:

* **[Download Complete Experimental Data (PDF)](Data/Amplitude_Modulation_Systems_Theoretical_Modeling_and_Hardware_Validation_Tables_and_Data.pdf)**
* **[Download Complete Experimental Q&A (PDF)](Data/Amplitude_Modulation_Systems_Theoretical_Modeling_and_Hardware_Validation_Questions_and_Answers.pdf)**
* **[Browse All Captured Documentation](Waveform_Captures/)**

---




