# Amplitude-Modulation-Systems-Theoretical-Modeling-and-Hardware-Validation
This project demonstrates a complete engineering workflow for Amplitude Modulation (AM). It bridges the gap between theoretical communication systems and practical hardware implementation. By utilizing a Telecoms Trainer and a Digital Storage Oscilloscope (DSO), the experiment validates mathematical models through real-time signal acquisition and analysis.

## Part 1: Signal Metrology & Instrumentation Authority
In any engineering environment, data is only as reliable as the instruments used to collect it. Part 1 focuses on the characterization and calibration of the Digital Storage Oscilloscope (DSO). Before analyzing complex communication signals, it is essential to eliminate measurement uncertainty by validating the horizontal timebase and vertical deflection systems against a known reference signal.

### 1.1 Vertical & Horizontal Trace Optimization
- Vertical System: Configured to 1V/div with AC Coupling. This removed parasitic DC offsets, ensuring that the measurement of Vpp (Peak-to-Peak Voltage) was localized to the AC signal component.
- Time-Base Calibration: Set to 0.5ms/div. The Variable (CAL) knob was locked in the detent position to eliminate timing skew, allowing for a precise calculation of the Period ($p$).
- Triggering Logic: Employed Internal Triggering (Source: CH1) with Auto Sweep Mode to stabilize periodic waveforms, a prerequisite for accurate spectral estimation.

### **1.2 Experimental Results**
<details>
<summary>View Part 1 Documentation</summary>

![Calibration Waveform](Waveform_Captures/Part1_Results/Part1_resultfig3.jpeg)
*Figure 1: Internal CAL signal showing the verified 2Vp-p sine wave.*
![Calibration Waveform](Waveform_Captures/Part1_Results/Part1_resultfig4.jpeg)
*Figure 1: Internal CAL signal showing the verified 1Vp-p square wave.*

</details>

## Part 2: Introduction to the ETT-101 Modular System
Modern communication systems are often designed using high-level block diagrams. Part 2 introduces the Emona Telecoms-Trainer 101 (ETT-101), a hardware platform that allows these theoretical blocks (Adders, Multipliers, Oscillators) to be physically interconnected. This phase transitions from basic waveform observation to understanding the hardware architecture required for signal processing.

### 2.1 Hardware Block Interfacing
- Master Signals: Characterized the 100kHz Sine Wave (Carrier) and the $2kHz$ Sine Wave (Message).
- Impedance & Connectivity: Utilized 2mm patching leads to establish a common ground plane between the trainer and the oscilloscope, preventing ground loops that could distort low-level message signals.

### **2.2 Experimental Results**
<details>
<summary> View Part 2 Documentation</summary>
![Master Signals](Waveform_Captures/part2_signals.jpg)
*Figure 2: Output verification of the 100kHz Carrier and 2kHz Message signals.*
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

### **3.2 Experimental Results**
<details>
<summary>View Part 3 Documentation</summary>
![Adder Waveform](Waveform_Captures/part3_adder.jpg)
*Figure 3: Linear summation of two sine waves and verified destructive interference.*
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

### **4.3 Experimental Results**
<details>
<summary>View Part 4 Documentation</summary>
![AM Envelope](Waveform_Captures/part4_envelope.jpg)
![AM Trapezoid](Waveform_Captures/part4_trapezoid.jpg)
*Figure 4: Time-domain AM envelope and corresponding XY-mode trapezoidal linearity test.*
</details>




