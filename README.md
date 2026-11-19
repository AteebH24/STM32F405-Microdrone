# STM32F405 Microdrone Flight Controller

## Project Overview

This project focuses on the design and development of a custom STM32F405-based flight controller for a four-motor brushed microdrone. The system integrates embedded firmware, PCB design, power management, wireless receiver communication, inertial sensing, and motor control into a compact aerial platform.

The flight controller was designed around an STM32F405 microcontroller and manufactured as a custom two-layer PCB. The board interfaces with a BMI270 inertial measurement unit (IMU), FlySky radio receiver, and four MOSFET-driven brushed DC motors.

The project covers the complete hardware development process, including schematic capture, PCB layout, PCB assembly, firmware development, electrical debugging, and system integration.

## Key Features

- Custom two-layer STM32F405 flight-controller PCB
- BMI270 six-axis IMU interfacing over SPI
- Complementary-filter attitude estimation and PID stabilization firmware
- Four-channel PWM brushed DC motor control
- FlySky iBUS receiver communication using UART DMA
- 1S LiPo battery power architecture
- USB-C charging circuitry
- SWD programming and debugging
- Custom 3D-printed microdrone frame
## Hardware Architecture

The flight controller integrates several subsystems:

**Microcontroller:** STM32F405 operating with an external 8 MHz crystal and a configured 168 MHz system clock.

**Power Management:** Single-cell LiPo battery input, BQ24074 battery charging circuitry, TPS61023 boost converter, and regulated supply rails.

**Motor Control:** Four independent MOSFET switching channels controlled through STM32 timer-generated PWM signals.

**Inertial Sensing:** BMI270 accelerometer and gyroscope connected through SPI for attitude estimation.

**Wireless Communication:** FlySky receiver connected through UART for remote throttle and flight-control commands.

**Programming and Debugging:** SWD interface for firmware programming and hardware debugging.

## Firmware Architecture

The embedded firmware was developed in C using STM32CubeIDE and STM32 HAL.

Major firmware modules include:

- Clock configuration and peripheral initialization
- Four-channel PWM generation using TIM3
- FlySky iBUS packet reception and decoding through UART DMA
- BMI270 initialization and accelerometer/gyroscope data processing
- Complementary-filter roll and pitch estimation
- PID-based attitude stabilization logic
- Receiver arming and communication-loss failsafe handling
## Hardware Development and Testing

The custom PCB was assembled and tested using a bench power supply, multimeter, ST-Link programmer, and Saleae logic analyzer.

Testing activities included:

- Verifying regulated power rails
- Programming the STM32 through SWD
- Measuring PWM signals at the motor-control outputs
- Debugging flyback diode polarity and motor-drive circuitry
- Verifying FlySky receiver communication
- Testing simultaneous four-motor throttle response
- Evaluating motor current consumption and available thrust
  
During bench testing, the four-motor system drew approximately 1.5 A at a 4.1 V supply under full-throttle conditions.

## Development Status

The flight-controller PCB has been assembled, programmed, and electrically tested. Four-channel motor control and receiver throttle response have been demonstrated.

The firmware includes IMU interfacing, attitude estimation, and PID stabilization logic. Closed-loop stabilization and controlled flight testing remain to be validated following propulsion improvements.

## Engineering Challenges and Improvements

Several issues were identified during hardware bring-up and system integration:

- **Flyback diode polarity:** Corrected diode orientation to resolve abnormal heating during motor operation.
- **Motor thrust:** Identified insufficient thrust from the initial brushed motors, requiring a propulsion upgrade.
- **Connector reliability:** Identified loose motor-wire crimps and planned improved connector assemblies.
- **Power management:** Investigating charger operation and unintended power-rail behavior.
- **Mechanical weight:** Identified opportunities to reduce PCB and airframe mass.
## Engineering Tools

**PCB Design:** KiCad, schematic capture, PCB layout, Gerber generation

**Embedded Development:** STM32CubeIDE, Embedded C, STM32 HAL

**Communication and Control:** SPI, UART DMA, PWM, PID control

**Testing and Debugging:** ST-Link, Saleae logic analyzer, bench power supply, digital multimeter, soldering and hot-air rework

**Mechanical Design:** SolidWorks, FDM 3D printing

## Repository Contents

- hardware/ — Schematic, PCB layout, Gerbers, and bill of materials
- firmware/ — STM32 firmware source code and configuration
- mechanical/ — 3D-printed frame models and CAD files
- testing/ — Hardware measurements, troubleshooting, and validation
- media/ — PCB photographs, assembly images, and demonstration videos
## Future Improvements

- Complete closed-loop attitude stabilization and flight validation
- Upgrade motors to improve thrust-to-weight ratio
- Reduce PCB size and overall system weight
- Improve motor connector reliability
- Resolve charging and power-switching issues
- Develop a revised PCB incorporating lessons learned from the first prototype
