# Ozgun-UKB-Flight-Computer
Avionics Flight Control Computer (UKB) for Teknofest Rocket. Features dual-stage deployment (Main/Drogue), MS5611/LSM6DSOX sensors, LoRa telemetry, and custom power management. Includes hardware design and C# Ground Station GUI.
# Özgün Uçuş Kontrol Bilgisayarı (Flight Control Computer)

<img width="882" height="688" alt="image" src="https://github.com/user-attachments/assets/59fdadab-01f5-4df1-bfa4-ffdd569909f7" />
<img width="1280" height="960" alt="image" src="https://github.com/user-attachments/assets/a007463a-993e-4d52-bc77-6fa2b23fdb52" />
<img width="960" height="1280" alt="image" src="https://github.com/user-attachments/assets/eeafdce4-9909-4bc7-a827-6e54c73254c0" />
<img width="1280" height="960" alt="image" src="https://github.com/user-attachments/assets/c6cd71b2-d415-44bf-98d5-8aaeb6c3145d" />
<img width="576" height="1280" alt="image" src="https://github.com/user-attachments/assets/4063704e-8555-4404-bdf0-645eafdfc4bb" />
<img width="1280" height="960" alt="image" src="https://github.com/user-attachments/assets/95c10744-663a-48d4-b030-619eee4a2598" />




## 📌 Project Overview
"Özgün UKB" is a custom-designed Flight Control Computer developed for high-altitude rocket competitions (Teknofest / IREC). It is engineered to perform real-time flight dynamics tracking, autonomous dual-stage parachute deployment, and long-range telemetry communication under high vibration and extreme G-force environments.

### ⚙️ Core System Architecture
The hardware architecture is built around the Arduino Nano ESP32, integrating industrial-grade sensors and power management:
* **Inertial Measurement (IMU):** LSM6DSOX (6-axis accelerometer and gyroscope) for precise orientation and acceleration tracking.
* **Altitude Tracking:** MS5611 high-resolution barometric pressure sensor for apogee detection.
* **Positioning:** Quectel L86-M33 GPS module for exact payload location and recovery operations.
* **Long-Range Telemetry:** LoRa E22-900T22D module operating at 900MHz for robust air-to-ground data links.
* **Power Management:** On-board MP1584 Buck Switching Regulator stepping down the main battery to a stable 3.3V logic supply.
* **Deployment System:** Custom-designed "Main" and "Drogue" pyro-channels driven by logic-level N-Channel MOSFETs.

---

## 🛠️ Hardware Design & Reliability
To ensure survivability during launch, the following engineering practices were implemented:
* **Separated Power Domains:** The logic circuitry (Sensors/MCU) and high-current pyro-channels are isolated to prevent voltage drops or brownouts during parachute deployment.
* **Vibration Resistance:** Decoupling capacitors (100nF and 10µF) are placed as close as possible to the IC supply pins to prevent power fluctuations induced by mechanical stress.
* **Interface Standards:** An onboard MAX3232 IC is utilized to provide RS232 level-shifting for standard D-SUB 9 communication.

---

## 💻 Ground Station Interface (C# & OOP)
This repository also includes the Ground Station Software developed specifically for this Flight Control Computer.
* **Technology:** C# (.NET Framework) with Object-Oriented Programming (OOP) principles.
* **Features:**
    * Real-time decoding of incoming LoRa telemetry packets.
    * Live data visualization (Altitude vs. Time, 3D Orientation).
    * GPS mapping interface for recovery tracking.
    * Serial port management and data logging (CSV format) for post-flight analysis.

---

## 📁 Repository Structure
* `\Hardware`: Altium Designer Schematic (.SchDoc) and PCB Layout files.
* `\Manufacturing`: Assembly files, BOM, and Gerbers used for the actual flight hardware production.
