# M.A.R.I. Drone: Integrated Power Distribution Network (PDN)

## Project Overview
This repository documents the design, simulation, and physical implementation of a high-performance Power Distribution Network (PDN) for the M.A.R.I. Quadcopter. As the **Power Systems Lead**, I engineered a triple-domain power architecture capable of supporting high-current flight demands while maintaining clean, isolated voltage rails for sensitive avionics and sensors.

## Key Technical Specifications
* **Dual Battery Support:** Validated for both **3S (12.6V)** and **4S (16.8V)** LiPo configurations.
* **Peak Current Capacity:** Engineered to handle **71.6A peak** during maximum ascent maneuvers.
* **Triple-Domain Architecture:** * **16.8V High-Power Bus:** Direct battery rail for the 40A ESCs and motors.
    * **5V Logic Rail:** Driven by the **AP63300** Buck regulator for the MCU and LoRa modules.
    * **3.3V Analog Rail:** Dual **TLV75533** LDOs providing isolated power for the IMU and Barometer.
* **Flight Endurance:** Optimized for a **9.4-minute** hover time.
* **Safety Systems:** Integrated hardware-level voltage divider for a **1.4V** battery monitoring threshold.

## Repository Structure
The project is organized into a professional engineering hierarchy for technical validation and production:

### 📁 `/analysis`
Contains all theoretical and simulated validation for the power system.
* **`/mathcad`**: Static power integrity and thermal loading worksheets.
* **`/spice`**: LTspice transient and noise analysis for 12.6V and 16.8V domains.
* **`/power_budget`**: System loading models and endurance calculations.

### 📁 `/design`
Includes the physical and logical implementation of the hardware.
* **`/hardware`**: Hierarchical schematics, PCB layout captures, and 3D renders.
* **`Block Diagram.pdf`**: High-level system architecture and signal flow.

### 📁 `/budget`
Focuses on the production and component selection.
* **`Bill of Materials.xlsx`**: Full parts list with 35V+ rated components for 4S compatibility.

### 📁 `/reports`
Executive summaries and performance verification.
* **`Final_Design_Review.pdf`**: Comprehensive system overview.
* **`Project_Report.pdf`**: Final flight testing and hardware validation results.

## Engineering Highlights
* **Parasitic Modeling:** Used LTspice to simulate the impact of **12 AWG** wiring and **XT90** connector inductance ($L_w$) on voltage ripple using parametric stepping.
* **EMI Isolation:** Implemented dual LDOs to decouple high-frequency switching noise from sensitive flight sensors.
* **Robustness:** All power components are rated for **25V-35V** to ensure safety during the high-voltage swings of a 4S battery.
