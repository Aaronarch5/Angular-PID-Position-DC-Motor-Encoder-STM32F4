# STM32F4 PID DC Motor Position Controller

This guide explains how to set up a PID position controller using an L298D module and a Pololu 25D DC motor with encoder, using C and STM32FCubeIDE.

## Software Needed
- **STM32CubeIDE**
 
## Components Needed
- **Microcontroller** (e.g., STM32F411CEUx)
- **L298D Motor Driver Module**
- **Pololu 25D DC Motor with Encoder**
- **Power Supply**
- **Connecting Wires**
![STM32F446RE](images/blackpill.png)
![L298D](images/HBridge.jpg)
![Pololu25D](images/Pololu25D.jpg)
## Connections

### 1. Microcontroller to L298D Module

#### Power Supply
- Connect the 5V and GND pins of the microcontroller to the 5V and GND pins of the L298D module.

#### Control Pins
- Connect the control pins (IN1, IN2, IN3, IN4) of the L298D to the digital output pins of the microcontroller. For example:
  - IN1 to microcontroller pin (e.g., PB0)
  - IN2 to microcontroller pin (e.g., PB1)

#### Enable Pins
- Connect the enable pins (ENA, ENB) of the L298D to PWM-capable pins on the microcontroller to control the speed of the motors. For example:
  - ENA to microcontroller PWM pin (e.g., PA6-TIM3_CH1)


### 2. L298D Module to DC Motor

#### Motor Connections
- Connect the output pins of the L298D (OUT1, OUT2, OUT3, OUT4) to the terminals of the DC motor. For example:
  - OUT1 and OUT2 to Motor A terminals

### 3. Encoder Connections

#### Power Supply
- Connect the VCC and GND pins of the encoder to the 5V and GND pins of the microcontroller.

#### Signal Pins
- Connect the encoder signal pins (A and B) to the digital input pins of the microcontroller. For example:
  - Encoder A to microcontroller pin (e.g., PB6)
  - Encoder B to microcontroller pin (e.g., PB7)

## Additional Steps

### Power Supply
- Ensure the L298D module is connected to an appropriate power supply that matches the voltage requirements of your DC motor.

### PID Tuning
- Implement the PID control algorithm in your microcontroller’s firmware to adjust the motor’s position based on the encoder feedback.
