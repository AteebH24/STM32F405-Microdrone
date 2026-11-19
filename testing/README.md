# Flight Controller Testing and Validation
## Overview

This section documents the hardware bring up, electrical testing, firmware verification, and troubleshooting performed on the custom STM32F405 microdrone flight controller.

## 1. Power System Testing
- Powered the PCB using a regulated bench power supply and a 1S LiPo battery.
- Measured supply voltages using a digital multimeter.
- Verified microcontroller programming and operation through the ST-Link interface.
- Investigated unexpected power behavior and charging circuit heating.

## 2. Motor Driver Testing
- Tested individual brushed DC motors before simultaneous operation.
- Verified motor control through four PWM outputs.
- Confirmed all four motors operated simultaneously.
- Measured approximately 1.5 A total current draw at 3.9 V during full throttle testing.
## 3. PWM Signal Verification
Equipment: Saleae logic analyzer.
- Examined STM32F405 PWM output signals.
- Verified PWM activity on motor control channels.
- Confirmed firmware controlled motor operation.
## 4. Receiver Communication Testing

Communication interface: UART using FlySky iBUS.
- Successfully connected and bound the FlySky firmware.
- Demonstrated wireless throttle control of the four motors.
## 5. Hardware Troubleshooting

### Flyback Diode Orientation

During initial motor testing, abnormal diode heating was observed.

Investigation identified incorrect flyback diode orientation.

The diodes were reinstalled with the Cathodes connected toward the positive motor supply.

Subsequent testing confirmed that the abnormal diode heating was resolved.
