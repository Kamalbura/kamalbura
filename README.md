<div align="center">

### K A M A L &nbsp;&nbsp; B U R A

**Embedded systems · robotics · security**

</div>

---

I build machines that have to keep working when something goes wrong.

Most of what I do sits on the boundary between software that can be uncertain and
hardware that cannot — a language model asking a robot to move, a control loop that
must not miss its deadline, a radio link that has to fail closed rather than open.
The interesting part is rarely the happy path. It is what happens when the network
stalls, the sensor is unplugged, the packet is corrupt, or the controller stops
responding entirely.

---

## What I'm building

**A voice-controlled ground robot** on a Raspberry Pi 4 — wakeword to speech-to-text to
an LLM to speech, and when the answer involves moving, a navigation command crosses a
serial line to a microcontroller that owns the motors and is allowed to refuse.

The base system runs end to end on hardware. Its MCU stops the robot when an obstacle is
detected and publishes status telemetry to the Pi; both behaviours are verified on the
physical robot.

Current work focuses on completing the framed UART motion-lease path and enforcing TLS
for app-to-Pi traffic. The running Pi bridge still uses the legacy ASCII protocol, so the
additional cable-loss guarantees of the framed path are not claimed until both ends are
deployed and verified together.

The protocol and safety logic are tested in Python and C. The project documents both the
working system and the remaining verification work.

---

## Selected work

### Robotics and control

| | |
|---|---|
| **[smart_car](https://github.com/Kamalbura/smart_car)** | Voice-controlled Raspberry Pi ground robot with an MCU safety layer. It combines Python services over ZeroMQ, on-device vision, obstacle stopping, and status telemetry verified on hardware. |
| **[esp32-rc-race-car](https://github.com/Kamalbura/esp32-rc-race-car)** | An RC car where **both ends of the radio link are mine** — a handheld ESP32-S3 transmitter and a receiver on the car over encrypted ESP-NOW at 100 Hz, with CRC-checked packets, a 120 ms failsafe, MPU6050 yaw assist and speed-dependent steering authority. Two generations documented, including why the second one uses *slower* motors. |
| **[DeskMate](https://github.com/Kamalbura/DeskMate)** | ESP32-S3 desk companion with an animated expressive face, gesture reactions, idle sleep and OTA updates |
| **[rc-rover-arm](https://github.com/Kamalbura/rc-rover-arm)** | Arduino Mega tank-steer rover with a seven-servo arm — 10-channel RC, three-mode state machine, counter-rotation turns, timer-safe PWM |
| **[esp32-car](https://github.com/Kamalbura/esp32-car)** | Sensor robot across four stages: Pi-tethered, full sensor suite, Wi-Fi dashboard with autonomous mode, then an Android app over Bluetooth |

### Systems and platforms

| | |
|---|---|
| **[air-quality-forecasting](https://github.com/Kamalbura/air-quality-forecasting)** | End-to-end forecasting platform — Open-Meteo ingestion, PostgreSQL with watermarked incremental loads, per-city Airflow DAGs running on a Raspberry Pi, a nine-model zoo behind a factory with Optuna tuning, and a Next.js dashboard |
| **[agent-q](https://github.com/Kamalbura/agent-q)** | Windows accessibility overlay in WPF/.NET 8 — captures screen context, plans actions through an LLM adapter, and validates them behind a safety layer before execution |

### Sensing and instrumentation

| | |
|---|---|
| **[Air-quality-monitoring](https://github.com/Kamalbura/Air-quality-monitoring)** | ESP32 to ThingSpeak to a Node/Express dashboard, with a Python analytics pipeline and local CSV fallback |
| **[avhzy-ct3-tcp](https://github.com/Kamalbura/avhzy-ct3-tcp)** | Live voltage, current and power streamed off an AVHzY CT-3 meter over TCP — Lua on the meter, Python on the host |

### Security

| | |
|---|---|
| **[orange-box-s40-teardown](https://github.com/Kamalbura/orange-box-s40-teardown)** | Full teardown of an Android projector: partition and boot-chain analysis, device tree, driver and kernel module inventory — and preinstalled malware, with a reproducible debloat path and a custom-Linux feasibility assessment |

---

## Tools

**Languages** &nbsp; C · C++ · Python · JavaScript / TypeScript · C# · SQL · Lua

**Embedded** &nbsp; ESP-IDF · Arduino · FreeRTOS · ESP-NOW · TinyUSB · I²C / I²S / SPI / UART

**Robotics** &nbsp; ZeroMQ · ONNX Runtime · YOLO · MPU6050 sensor fusion · PID and slew-rate control

**ML** &nbsp; PyTorch · XGBoost · scikit-learn · Optuna

**Data** &nbsp; PostgreSQL · Airflow · dbt · Docker

**Web** &nbsp; Next.js · React · Node / Express · Tailwind

---

<div align="center">

I try to document what is *actually* true of a system, including the parts that
are not finished yet — a README that overstates what works costs more than one
that admits a gap.

</div>
