# RISC-V Internship program powered by SAMSUNG and VSD
This RISC-V Internship using VSDSquadron Mini is based on RISC-V architecture and uses open-source tools to teach students about VLSI SoC Design and RISC-V. The instructor and guide for this internship is Kunal Ghosh Sir, Founder of VSD.
## Basic Details
Name    : Sanjana K L <br>
college : Sahyadri college of engineering and management, Mangalore <br>
email id: sanjana.ec23@sahyadri.edu.in <br>
git hub profile: sanjana-ECE-Sahyadri <br>
linkedin profile : Sanjana K L <br>
## Task 1 of the program 
## Task 1 A
A. Installation of RISC-V toolchain and performing simple program using C language in C lab<br>
![WhatsApp Image 2025-01-09 at 16 12 59_cc91d651](https://github.com/user-attachments/assets/be73230a-acfa-4fac-b87e-9bfd9c0dc4bd)
## Task 1 B
B. practice of programs in RISC-V lab
![WhatsApp Image 2025-01-09 at 16 12 59_a1bd10ab](https://github.com/user-attachments/assets/6b0a8c30-760b-4fdc-87a5-3bc4e499d150)
![WhatsApp Image 2025-01-09 at 16 12 59_2aa9adb6](https://github.com/user-attachments/assets/489aa5b8-d951-4584-b2a7-d97a56090b3f)
## Task 2
A. Understanding of spike ( RISC-V complier) , compling of simple C program using RISC-V GCC/SPIKE and debugging the same by providing required commands.
![spike](https://github.com/user-attachments/assets/f1786096-c5b4-4b3c-814d-24a5b5477fd5)
![spike2](https://github.com/user-attachments/assets/9cfab13a-d041-4095-adfd-e61e84950c04)
B. The RISC-V object dump of -Ofast
![ofast](https://github.com/user-attachments/assets/df1ea6fb-49e0-4ab7-8aba-887a424f8b78)
C. The RISC-V object dump of -O1
![o1](https://github.com/user-attachments/assets/1433c293-12df-4327-85c3-5b7d9369c4fd)
## Task 3
From the riscv-objdump of application code , identification of 15 unique RISCV Iinstruction
![Screenshot 2025-01-18 213136](https://github.com/user-attachments/assets/7c13b047-18d6-4e2e-9455-43f25533e203)
## Task 4
creating waveform for the given simulation using verilog netlist from RISC-V core verilog Netlist.
![Screenshot 2025-01-21 225633](https://github.com/user-attachments/assets/a939872d-e946-4b93-a91e-a253c081e50c)
![Screenshot 2025-01-21 225046](https://github.com/user-attachments/assets/a5ead509-1f72-4bbe-8004-be2a531b1675)
## Task 5
## Automatic irrigation system 
### Overview
An Automatic Irrigation System using a RISC-V Board is designed to efficiently manage water supply to plants based on soil moisture levels, reducing water wastage and manual effort. The system uses sensors to monitor soil moisture and environmental conditions, then controls a water pump accordingly. The RISC-V board acts as the central processing unit, processing sensor data and automating irrigation.
### Components required
1. RISC-V Board (e.g., HiFive1, BeagleV, or Sipeed Longan Nano)<br>
2. Soil Moisture Sensor – Detects soil moisture levels <br>
3. Relay Module – Controls the water pump based on sensor data <br>
4. Water Pump – Supplies water when needed<br>
5. Bluetooth Module (HC-05 or HC-06) – Enables wireless communication<br>
6. Power Supply (5V/12V, depending on pump requirements)<br>
7. Resistors, Capacitors, Jumper Wires, and Breadboard – For connections
![IMG-20250203-WA0025](https://github.com/user-attachments/assets/e6dfb9e2-58ff-4015-bd6c-04b5d943b018)
### Pin-by-Pin Explanation of the Circuit
#### 1. Soil Moisture Sensor:
VCC (Power): Connected to the 3.3V or 5V pin of the RISC-V board (depending on the sensor).<br>
GND (Ground): Connected to the GND pin of the RISC-V board.<br>
Analog Output: Connected to an analog input pin (A0) on the RISC-V board to send soil moisture data.<br>
#### 2. RISC-V Board<br>
Acts as the brain of the system. Below are the critical pins used:<br>
A0 (Analog Input): Receives the signal from the soil moisture sensor<br>
Digital Pin 7 (Relay Control): Sends a HIGH/LOW signal to control the relay.<br>
TX Pin (Transmit): Connected to the RX (Receive) pin of the Bluetooth module for communication.<br>
RX Pin (Receive): Connected to the TX (Transmit) pin of the Bluetooth module for communication.<br>
3.3V or 5V Pin: Powers the soil moisture sensor and Bluetooth module.<br>
GND Pin: Common ground for all connected components.<br>
#### 3. HC-05 Bluetooth Module:<br>
VCC (Power): Connected to the 5V pin of the RISC-V board. <br>
GND (Ground): Connected to the GND pin of the RISC-V board. <br>
TX (Transmit): Connected to the RX Pin of the RISC-V board for transmitting data to the board. <br>
RX (Receive): Connected to the TX Pin of the RISC-V board for receiving data from the board.<br>
#### 4. Relay Module:
VCC (Power): Connected to the 5V pin of the RISC-V board.<br>
GND (Ground): Connected to the GND pin of the RISC-V board.<br>
Signal (Control Input): Connected to Digital Pin 7 of the RISC-V board. When this pin is HIGH, the relay is activated.<br>
COM (Common Terminal): Connected to one terminal of the power source for the water pump (230V AC).<br>
NO (Normally Open): Connected to one terminal of the water pump. When the relay is activated, this closes the circuit and powers the pump.<br>
#### 5. Water Pump:
Input Terminal 1: Connected to the NO terminal of the relay.<br>
Input Terminal 2: Connected to the neutral wire of the AC power source (230V, 50Hz).<br>
The pump turns on or off based on the relay’s state.<br>
#### 6. Power Connections:
The RISC-V board, soil sensor, and Bluetooth module use a 5V DC supply.<br>
The relay and water pump are powered by 230V AC (high voltage).<br>
#### Working Explanation
*The soil sensor measures the soil moisture level and sends an analog signal (voltage) to A0 on the RISC-V board.<br>
*The RISC-V board processes the signal:<br>
*If the soil moisture is below the threshold, it sends a HIGH signal to Pin 7, activating the relay and turning on the water pump.<br>
*If the soil moisture is above the threshold, it sends a LOW signal to Pin 7, deactivating the relay and turning off the pump.<br>
*The Bluetooth module (HC-05) enables manual control via a mobile device:<br>
*Sending '1' through Bluetooth will turn the pump ON (activates the relay).<br>
*Sending '0' through Bluetooth will turn the pump OFF (deactivates the relay).<br>
*The relay module acts as a switch, isolating the low-voltage control system (RISC-V) from the high-voltage power supply to the pump.<br>




 








