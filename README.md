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
![1000235946 (1)](https://github.com/user-attachments/assets/f3fe2d4d-a1e5-4ee2-988d-8a009f0e48d1)
![1000235948](https://github.com/user-attachments/assets/52ae017a-b78d-437e-8c73-6fc06776ab11)

## Task 4
creating waveform for the given simulation using verilog netlist from RISC-V core verilog Netlist.
![Screenshot 2025-01-21 225633](https://github.com/user-attachments/assets/a939872d-e946-4b93-a91e-a253c081e50c)
![Screenshot 2025-01-21 225046](https://github.com/user-attachments/assets/a5ead509-1f72-4bbe-8004-be2a531b1675)
## Task 5
## LED Blinking Project using VSDSquadron Mini (RISC-V Board)
### Overview
This project demonstrates how to blink an LED using the VSDSquadron Mini, a RISC-V-based development board. The LED will turn ON and OFF at regular intervals, controlled by a simple delay loop in the firmware.
### Components required
VSDSquadron Mini	
LED	
Resistor (330Ω)	
Breadboard	
Jumper Wires	
USB Type-C Cable
![task66](https://github.com/user-attachments/assets/622c5075-5c99-480b-bc4f-da5fbd54c255)
### Pin Diagram
VSDSquadron Mini Pin	Connected To
PA0 (GPIO Pin 0)	LED Anode (+)
GND	LED Cathode (-) through 330Ω resistor
Explanation: The PA0 pin is configured as an output to control the LED. The resistor prevents excessive current flow.
### Working
The VSDSquadron Mini initializes the PA0 pin as an output.
The program sets PA0 HIGH to turn the LED ON.
A small delay is added.
The program then sets PA0 LOW to turn the LED OFF.
Another delay is added.
This cycle repeats indefinitely, creating a blinking effect.
### C code  
#include <stdint.h>
#include "vsd_delay.h"
#include "vsd_gpio.h"

#define LED_PIN 13 // Change this pin number based on your board's LED connection

void main() {
    // Configure LED pin as output
    GPIO_SetMode(LED_PIN, GPIO_MODE_OUTPUT);

    while (1) {
        GPIO_Write(LED_PIN, 1); // Turn LED ON
        delay_ms(500); // Wait for 500ms

        GPIO_Write(LED_PIN, 0); // Turn LED OFF
        delay_ms(500); // Wait for 500ms
    }
}
## Task 6
Demostration of LED BLINKING PROJECT USING VSDSUADRON MINI BOARD

https://github.com/user-attachments/assets/ca00b111-d894-4038-9bae-aeb23f9b984e





