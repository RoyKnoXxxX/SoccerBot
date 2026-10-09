#mesl soccerbot

An open-source **KiCad 10** printed circuit board (PCB) hardware design for an agile, microcontroller-driven mobile soccer robot. 

This repository contains all schematic runtime hierarchies, layout net rules, and manufacturing constraints needed to replicate the control board module.

---
## 🛠 Features & Core Architecture

* **Processor Core:** Features an embedded **ESP32-C3-DevKitM-1** subsystem (2.4 GHz Wi-Fi and Bluetooth LE RISC-V SoC).
* **Locomotion Subsystem:** Utilizes a **TB6612FNG** dual-channel H-Bridge motor driver chip to manage directional traction and speed parameters for two DC motors.
* **Onboard Power Management:** Integrated step-down switching buck infrastructure powered by an **LM2596S-5** regulator (delivering stable 5V up to 3A rails from high-capacity battery inputs).
* **Power Connection:** Heavy-duty vertical **AMASS XT60-F** input termination to support standardized high-current Lithium Polymer pack configurations safely.
---

## 📂 Repository File Index

| File Structure | Description |
| :--- | :--- |
| `meslsoccerbot.kicad_pro` | Core KiCad 10 workspace config file mapping absolute path parameters. |
| `meslsoccerbot.kicad_sch` | Electronic component layout and electrical net node routing schema. |
| `meslsoccerbot.kicad_pcb` | Mechanical physical tracing layout, ground plain copper pours, and via coordinates. |

---

| Component Reference | Value / Part | Package / Footprint Type |
| :--- | :--- | :--- |
| **U4** | ESP32-C3-DevKitM-1 | Espressif dev module footprint |
| **U2** | TB6612FNG | 2x12 2.54mm pitch Vertical Header configuration |
| **U3** | LM2596S-5 | PG-TO263-5-1 SMD variant |
| **BT1** | Battery Power Input | AMASS XT60-F Through-hole Vertical Socket |
| **L1** | 33µH Inductor | Radial Choke Coil (Fastron 07M Series) |
| **D1** | D_Schottky Diode | Axial Rectifier (DO-201 Package) |
| **C3** | 220µF Polarized Capacitor | Radial Aluminum Electrolytic (D8.0mm / P3.5mm) |
| **C1** | 100µF Polarized Capacitor | Radial Aluminum Electrolytic (D8.0mm / P3.5mm) |
| **C2** | 0.1 µF Decoupling Capacitor| Ceramic THT Disc (D5.0mm / P5.0mm) |
| **J1** | Conn_01x04 Socket | Standard 2.54mm Pitch Breakout Strip |
| **J2, J3** | Conn_01x02 Sockets | Standard 2.54mm Pitch Breakout Strips |
| **H1 - H4** | Mounting Holes | M3 Hardware Clearances (Isolated Ground) |

---
## 🚀 Fabrication Instructions

1. Open the project profile using **KiCad 10.0 or later**.
2. Run a **Design Rule Check (DRC)** within both Eeschema and Pcbnew to verify that signal connectivity matches parameters.
3. Export your production zip file via `Fabrication Outputs -> Gerbers (.gbr)` and `Drill Files (.drl)`.
4. Submit generated archives directly to your contract prototype PCB manufacturer of choice.
