# Music Rhythm LEDs

This repository contains the design files and documentation for a Music Rhythm LEDs PCB project. The circuit uses a microphone to detect sound and flashes LEDs in sync with the rhythm of the music. This project was developed as part of the Electrical Electronic Circuits assignment at the University of Technology, Ho Chi Minh City.

## Introduction

The Music Rhythm LEDs is a simple yet engaging PCB-based device that visualizes music rhythms through LED flashing. A microphone captures audio input, amplifies it, and drives transistors to light up LEDs in response to sound intensity variations, creating a synchronized light show.

## Schematic and Conceptual Design

### Schematic Design

The schematic was designed in Altium Designer. It includes a microphone for sound detection, amplification via transistors, and LED drivers.

<p align="center">
  <img src="https://github.com/user-attachments/assets/f67de60f-2fb2-46e4-a79f-7e93092ca0e2" 
       alt="3D views of the assembled PCB" 
       width="1200"/>
  <br>
  <i>Figure 1: Schematic design</i>
</p>

#### Working Principle

1. **Sound Detection and Amplification**:
   - The microphone converts sound into an AC signal, coupled through C1 to Q1's base.
   - Q1 amplifies the signal, with fluctuations based on sound intensity.

2. **LED Flashing Circuit**:
   - The amplified signal drives Q2 to Q7, each controlling one LED.
   - Resistors R4 to R9 limit current to protect LEDs.

3. **Synchronization with Music Rhythm**:
   - Sound intensity changes cause transistors to switch, flashing LEDs in rhythm.

### Functional Blocks

- **Power Supply**: 9V DC battery.
- **Function**: Flashing LEDs in sync with input music.
- **Human Interface**: Switch for on/off, microphone for input, LEDs for output.

## Hardware Specification

Detailed components and calculations:

1. **Electret Condenser Microphone (56dB DIP)**:
   - Omnidirectional.
   - Operating Voltage: 3-5V (typically 4V).
   - Frequency Range: 50-16kHz.
   - Current Consumption: Max 0.5mA.
   - Sensitivity: -56 ± 2 dB.

2. **Capacitor C1 (100nF)**:
   - Blocks DC bias, passes AC signal.
   - Forms high-pass filter with R2 (fc ≈ 1.6Hz).

3. **Resistors R1, R2, R3**:
   - R1 (10kΩ): Pull-up for microphone bias (Imic = 0.5mA).
   - R2 (1MΩ): High-pass filter resistor.
   - R3 (10kΩ): Bias for Q1.

4. **Transistors (BC547)**:
   - Q1: Amplifies microphone signal.
   - Q2-Q7: Drive LEDs.

5. **LEDs (D1-D6, 10mm)**:
   - Red LEDs (D1-D3): Max 2.3V (typical 2.2V), 20mA.
   - Green LEDs (D4-D6): Max 3-3.3V (typical 3.2V), 20mA.

6. **Resistors R4-R9 (22Ω)**:
   - Limit current for LEDs.
   - For Red: VCE = 6.36V < 45V max.
   - For Green: VCE = 5.36V < 45V max.

7. **9V Battery**:
   - Supplies power; suitable for circuit calculations.

8. **Switch**:
   - Rocker switch for on/off, wired to PCB.

## PCB Layout

Designed in Altium Designer as a single-layer PCB (bottom layer only).

### 2D Layout
<p align="center">
  <img src="https://github.com/user-attachments/assets/9f07527b-e28a-4e15-9de6-a48416ad4357" 
       alt="Basys 3" 
       width="800"/>
  <br>
  <i>Figure 2: Bottom layer after polygon pour and mounting holes</i>
</p>

### 3D Layout

<p align="center">
  <img src="https://github.com/user-attachments/assets/ed3211d0-1d2c-42a2-8d65-aab56afa04b9" 
       alt="3D views of the assembled PCB" 
       width="800"/>
  <br>
  <i>Figure 3: Bottom layer after polygon pour and mounting holes</i>
</p>

### Final PCB Device Layout

Physical one-layer PCB.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/6aa8b66a-ab49-40a2-b026-a45f979c440a" />
<img width="500" alt="image" src="https://github.com/user-attachments/assets/3aad6bb4-a08a-4f7d-b92d-ed7b997db5e3" />

## Device Demonstration

Watch the video demo showing the device in action: [Demo](https://www.youtube.com/watch?v=cwNKPTRDnqY)  

## How to Build

1. Open the project in Altium Designer.
2. Fabricate the PCB (single-layer).
3. Solder components as per the schematic.
4. Connect a 9V battery and rocker switch.
5. Test with music input near the microphone.
