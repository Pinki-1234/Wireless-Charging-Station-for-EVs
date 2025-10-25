#  IoT-Based Wireless Charging Station for Electric Vehicles (EVs)

##  Project Overview
This project presents a **smart IoT-enabled wireless charging station prototype** for Electric Vehicles (EVs), built using the principle of **inductive power transfer**.  
The system allows wireless charging of EVs without any physical plug-in connection.  

At its core, the system is powered by an **STM32 microcontroller**, which manages vehicle detection, power transmission, and real-time status monitoring to ensure an efficient and automated charging experience.

This repository contains the **firmware developed for the STM32 microcontroller**, which acts as the central control unit for the entire system.

---

##  Key Features

###  Automated Vehicle Detection
An IR sensor automatically detects the presence of an EV in the charging zone.

###  Microcontroller-Based Control
The complete process is handled by an STM32 MCU, ensuring smooth and reliable system operation.

###  Real-Time Status Display
A 16x2 LCD shows live status messages such as **“Idle”**, **“Vehicle Detected”**, and **“Charging”**.

###  Wireless Power Transfer
Uses inductive coupling to wirelessly transfer power between the transmitter (charging pad) and receiver (vehicle).

### 🌐 IoT Integration (In Progress)
Designed to support real-time data transmission (e.g., voltage and current) for remote monitoring.

---

##  Embedded Software & Control Systems
As the lead developer for embedded systems and firmware, we were responsible for:

- Designing and programming the **STM32-based control logic**  
- Integrating all hardware components including **sensors, relays, and LCD**  
- Ensuring safe, automated, and reliable transitions between system states  

---

##  Development Details

### 1️ Firmware Architecture & Development
- Developed complete control logic in **C/C++** for the STM32 board  
- Designed a **state machine** handling modes: *Idle → Vehicle Detection → Charging → Idle*  
- Implemented **high-frequency PWM generation** to drive the MOSFET for the transmitter coil  
- Ensured **modular, well-documented, and scalable** code structure  

### 2️ Peripheral Integration & Drivers
- **IR Sensor:** Interfaced to detect vehicle arrival/departure and trigger state transitions  
- **Relay Module:** Controlled via STM32 GPIO to safely switch the main power to the transmitter coil  
- **LCD Display (16x2):** Wrote custom driver and APIs to show dynamic system status updates  

### 3️ System Logic & Control Flow
**Initialization:**  
All peripherals are initialized; LCD shows *“Status: Idle”*  

**Vehicle Detection:**  
IR sensor detects the vehicle and sends a digital signal to STM32  

**Power Activation:**  
MCU activates the relay and updates the LCD to *“Vehicle Detected”*  

**Charging:**  
MCU generates a high-frequency drive signal for the MOSFET, enabling inductive power transfer  

**Completion/Departure:**  
When the vehicle leaves, STM32 deactivates the relay, stops transmission, and resets the system to *Idle*  

---

##  Hardware Components

| Component | Description |
|------------|-------------|
| **Microcontroller** | STM32 Board |
| **Sensor** | IR Proximity Sensor |
| **Display** | 16x2 LCD |
| **Switching** | 5V Relay Module |
| **Power Control** | MOSFET, 7805 Voltage Regulator |
| **Wireless Transfer** | Custom-wound Transmitter & Receiver Coils |

---

##  Project Results
- The **control and automation system** performed flawlessly during testing  
- **Vehicle detection**, **relay operation**, and **status indication** worked exactly as intended  
- Successfully demonstrated the **core embedded control logic** for wireless EV charging  

---

##  Future Improvements
- Integration with an **IoT dashboard** for live monitoring  
- Improved **coil design** for better power transfer efficiency  
- Addition of **safety features** like overcurrent and temperature monitoring  

---
