# STM32F405 Firmware

Embedded C firmware developed using STM32CubeIDE and STM32 HAL for the custom microdrone flight controller.
## Main Functions
- STM32F405 clock and peripheral initialization
- Four-channel PWM motor control using TIM3
- FlySky iBUS receiver communication through UART DMA
- BMI270 accelerometer and gyroscope interfacing over SPI
- Complementary filter attitude estimation
- PID stabilization logic
- Receiver arming and failsafe handling
