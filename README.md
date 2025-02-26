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
## Automatic light system 
### Overview
An automatic light system is a setup designed to automatically control the lighting based on the presence or absence of individuals within its detection range. This system will also give the indication of motion detected by blinking the led 3 times.
### Components required
1. VSDSquadron Mini Board
2. IR Sensor
3. LEDs
4. Bread Board
5. USB Cable
6. Jumper Wires
![WhatsApp Image 2025-02-26 at 5 57 05 PM (1)](https://github.com/user-attachments/assets/18cd6a57-8ce9-4863-9dd1-071f0d715b6e)
### Pin Diagram
IR SENSOR, LED	VSD SQUADRON BOARD
VCC OF IR	3.2V
GND OF IR	GND
OUT OF IR	PIN 4
LED	PIN 6
###Working
The IR sensor is strategically placed in a location where it can detect the movement of individuals within its sensing range.
The IR sensor continuously monitors its surroundings for any changes in infrared radiation caused by the movement of individuals.
When someone enters the detection range of the IR sensor, it detects the change in radiation and triggers an output signal.
When the IR sensor detects motion, it sends a signal to the microcontroller which then activates the LED lighting system. The LED lights up, providing illumination and the led will blink 3 times in the area where motion is detected which gives indication of motion detected.
### code
//These include the necessary header files (ch32v00x.h and debug.h) for the CH32V microcontroller and debugging purposes.
#include <ch32v00x.h>
#include <debug.h>
//pin configuration
void GPIO_Config(void)
{
GPIO_InitTypeDef GPIO_InitStructure = {0}; //structure variable GPIO_InitStructure of type GPIO_InitTypeDef which is used for GPIO configuration.

RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE); // to Enable the clock for Port D
//pin 4 OUT PIN FOR IR SENSOR
GPIO_InitStructure.GPIO_Pin = GPIO_Pin_4 ; // Defines which Pin to configure
GPIO_InitStructure.GPIO_Mode = GPIO_Mode_IPU; // Defines Output Type
GPIO_Init(GPIOD, &GPIO_InitStructure);
//pin 6 IS LED PIN
GPIO_InitStructure.GPIO_Pin = GPIO_Pin_6 ; //
GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP; // Defines Output Type
GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz; // Defines speed

GPIO_Init(GPIOD, &GPIO_InitStructure);

}
//main function

int main(void)
{
uint8_t IR = 0;
uint8_t set=1;
uint8_t reset=0;
uint8_t a=0;
NVIC_PriorityGroupConfig(NVIC_PriorityGroup_2);// Configuring NVIC priority group
SystemCoreClockUpdate();// Update System Core Clock
Delay_Init();//Initialize Delay
GPIO_Config();//Call GPIO configuration function

while(1)
{
IR = GPIO_ReadInputDataBit(GPIOD, GPIO_Pin_4);
if (IR==1)//Read state of Pin 4 (IR sensor)
{ // for blinking of led three times upon motion detection
	for(a=0;a<3;a++){
GPIO_WriteBit(GPIOD, GPIO_Pin_6, set);
Delay_Ms(200);
GPIO_WriteBit(GPIOD, GPIO_Pin_6,reset);
Delay_Ms(100);}

}

}
}

