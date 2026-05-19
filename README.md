# Digital Clock Project

## Overview
This document presents a digital clock circuit implemented without using a microcontroller. The design is based entirely on digital integrated circuits such as counters, logic gates, diodes, resistors, a transistor, and a crystal oscillator. The clock displays time in minutes and seconds using 7-segment displays. The explanation is written in a simple and clear manner suitable for beginners and academic discussion.

## Project Members
* Alyeldeen Ahmed Eldowaik 
* Youssef Mohamed 
* Yassin Hazem 

## Components Used
* IC 4060 – Oscillator and binary counter (2 pieces)
* IC 4026 – Decade counter with 7-segment driver (6 pieces)
* IC 7400 – Quad 2-input NAND gate (1 piece)
* NPN Transistor (1 piece)
* Diodes (6 pieces)
* 7-Segment Displays (6 pieces)
* Resistors (8 pieces total)
* Timing Capacitor (1 piece)
* Crystal Oscillator (1 piece)
* Power Supply

## Functional Description of Components

### IC 4026 – Counter and Display Driver
The IC 4026 is a digital counter that counts from 0 to 9. Each time it receives a pulse, it increments the displayed number by one. The IC is directly connected to a 7-segment display, so no external decoder is required. When the count reaches its maximum value, it sends a signal to the next counter. In this project, the IC 4026 is used to display seconds and minutes.

### IC 4060 – Timing Signal Generator
The IC 4060 is responsible for generating a stable timing signal for the clock. It includes an internal oscillator and a chain of counters. When connected to a crystal oscillator and a capacitor, it produces steady pulses that control the counting process. The user does not need to understand frequency calculations; the IC simply provides regular timing pulses.

### IC 7400 – NAND Logic Gates
The IC 7400 contains four NAND gates. These gates are used to detect specific counter states and determine when a reset is required. This ensures that seconds and minutes reset correctly and do not exceed their limits.

### NPN Transistor & Diodes
* **NPN Transistor:** Used as a switch to strengthen reset signals. Logic signals may be weak or unstable, so the transistor ensures a clean and reliable reset pulse is applied to the counters.
* **Diodes:** Allow current to flow in only one direction. In this project, they are used to combine reset signals safely and prevent unwanted feedback between different stages of the circuit.

### Crystal Oscillator & Resistors
* **Crystal Oscillator:** Provides a stable reference signal for the clock. This stability ensures accurate time keeping and prevents drift over long periods.
* **Resistors:** Eight resistors are used in the circuit. These are responsible for current limiting, biasing the transistor, and ensuring correct logic levels throughout the system.

## System Operation
1. When power is applied, the crystal oscillator and IC 4060 begin operating.
2. The IC 4060 generates regular timing pulses.
3. These pulses are fed into the IC 4026 counters.
4. Each 4026 updates its corresponding 7-segment display.
5. When a counter completes its cycle, it triggers the next stage.
6. NAND gates and diodes manage reset conditions.
7. The transistor ensures reliable reset operation.
8. The displays continuously show minutes and seconds.

## System Diagrams & Schematics

### Block Diagram
![Block Diagram](images/block_diagram.jpg)

### Pulse Generation Schematic
![Pulse Generation Schematic](images/pulse_generation.jpg)

### Mod-60 & Mod-12 Schematics
![Mod 60 Seconds](images/mod60_seconds.jpg)
![Mod 60 Minutes](images/mod60_minutesjpg.jpg)
![Mod 12 Hours](images/mod12_hours.jpg)

## Physical Implementation
![Physical Circuit View 1](images/physical_1.jpg)
![Physical Circuit View 2](images/physical_2.jpg)
![Physical Circuit View 3](images/physical_3.jpg)

*You can view a video of the working circuit [here](https://drive.google.com/file/d/1tiuvQU5EV8XumlfdopGbZydBgzEN-A4r/view?usp=drive_link).*

## Why Tinkercad Simulation is Not Included
We initially attempted to build and simulate this circuit using Tinkercad. However, we found that Tinkercad's component library lacks some of the specific ICs and exact capacitor values required for our design. Because the simulator couldn't accurately reflect our real-world components, the simulation was incomplete. Therefore, we relied entirely on our physical breadboard implementation, which represents the final, fully functional project.

## Conclusion

This digital clock demonstrates how accurate timekeeping can be achieved using basic digital electronics without programming or microcontrollers. The design is reliable, educational, and well-suited for understanding counters, logic control, and timing circuits.
