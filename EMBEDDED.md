# Embedded systems and robotics

[← Profile overview](./README.md) · [AI & Software →](./AI_SOFTWARE.md)

I build embedded systems where behaviour must remain understandable when a
sensor fails, a radio packet is lost, or the higher-level computer stops
responding. My work combines microcontrollers, Linux edge systems, sensors,
motor control, and wireless communication.

## Selected work

| Project | Focus |
|---|---|
| [**Smart Car**](https://github.com/Kamalbura/smart_car) | Raspberry Pi voice and vision system with an MCU responsible for obstacle stopping and motor-status telemetry. |
| [**ESP32 RC Race Car**](https://github.com/Kamalbura/esp32-rc-race-car) | Custom ESP32-S3 transmitter and receiver using ESP-NOW, CRC-checked packets, a 120 ms failsafe, yaw assistance, and speed-aware steering. |
| [**DeskMate**](https://github.com/Kamalbura/DeskMate) | ESP32-S3 desk companion with an expressive display, gesture reactions, idle behaviour, and OTA updates. |
| [**RC Rover Arm**](https://github.com/Kamalbura/rc-rover-arm) | Arduino Mega rover with tank steering, a seven-servo arm, ten-channel RC input, and distinct rover, arm, and precision modes. |
| [**ESP32 Car**](https://github.com/Kamalbura/esp32-car) | Sensor robot developed from a Pi-tethered platform into a Wi-Fi dashboard and Android-controlled system. |

## Areas of focus

- ESP32, STM32, Arduino, FreeRTOS, and embedded Linux
- Motor control, PWM, sensor integration, and safety interlocks
- UART, SPI, I²C, I²S, ESP-NOW, and wireless control links
- Linux edge services, serial protocols, observability, and fault handling
- Hardware validation: current limits, timing, thermal behaviour, and safe
  bench testing

## Engineering approach

The hardware layer should retain authority over safety-critical actions. Higher
levels can request behaviour; they should not be able to bypass a local stop,
timeout, or sensor fault.
