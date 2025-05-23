#  Micro-Mouse Power Subsystem – EEE3088F 2025

This repository contains the schematic, PCB layout, firmware, and documentation for the **Power Subsystem** of a maze-solving Micro-Mouse robot, developed as part of the EEE3088F course at the University of Cape Town.

---

##  Project Overview

This project focuses on the design, implementation, and testing of a compact and efficient **Power Subsystem** for a Micro-Mouse (MM) robot.

The power module is responsible for delivering regulated voltages, safe battery charging, motor power distribution, and real-time monitoring all within a space- and cost-constrained printed circuit board (PCB) footprint. It was developed to integrate seamlessly with the rest of the Micro-Mouse system, which includes processing, sensing, and control subsystems.

This subsystem ensures that all other modules in the robot receive stable power while providing built-in protection, control, and monitoring features. Its design includes features like dual-mode battery charging, USB-C PD negotiation, high-side switching for external loads, and I2C-based current/voltage sensing. 

The design adheres to the full set of requirements for the complete robot. The board is designed for manufacturability via JLCPCB and optimized for both performance and academic assessment.

---

##  Features

-  **Dual Motor Power Support**  
  Powers up to 4 brushed DC motors with reliable bidirectional control  including two high-current auxiliary motors (500mA each).

-  **Intelligent Battery Charging**  
  Automatically charges a single-cell LiPo battery from a 9V input using a selectable current mode: safe slow charge (~200mA) or faster charging (~600mA ±100mA).

-  **Real-Time Power Monitoring**  
  Monitors battery voltage and current in real-time using the INA219 sensor connected to the I²C bus, enabling diagnostics and data logging.

-  **USB-C Power Delivery Integration**  
  Negotiates 9V from compliant USB-C PD sources via the CH224K controller to support flexible charging and system power input.

-  **External Load Control**  
  Includes two high-side load switches for driving external 5V peripherals up to 1A each, with control via GPIO from the main processor.

-  **Precision Voltage Regulation**  
  Provides clean and accurate 3.3V (±5%) and 5V (±5%) rails for digital logic and sensor subsystems, supporting peak currents of up to 1.5A.

-  **Efficient Power Switching**  
  Features a physical ON/OFF switch that disables both 3.3V and 5V rails when inactive, reducing standby battery draw to under 30μA.

-  **Compact PCB Footprint**  
  Fully integrated on a compact 82mm × 60mm 2-layer PCB, designed for modular stacking with the micro-mouse system.

-  **Cost-Effective Design**  
  Uses carefully selected components and efficient routing to stay well within the \$70 total budget limit for the project.

---


## Repository Structure

```bash
├── hardware/
│   ├── PCB_KiCad/             # Schematic and PCB layout (KiCad)
│   ├── Gerber_Files/          # JLCPCB-ready fabrication files
│   └── BOM/                   # Bill of Materials (.xlsx and .tex)
│
├── firmware/
│   ├── PowerControl/          # Firmware for fast charge control via PB4
│   └── INA219_Test/           # Firmware to read INA219 values via I2C
│
├── test_procedures/
│   └── ATP_Documents/         # Detailed Acceptance Test Procedures
│
├── docs/
│   ├── Report_Final.pdf       # Final academic report
│   └── Images/                # System diagrams, PCB renders
│
└── README.md
