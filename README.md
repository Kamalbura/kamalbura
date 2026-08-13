<div align="center">

### K A M A L &nbsp;&nbsp; B U R A

**Embedded systems · robotics · UAV security research**

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

**A voice-controlled ground robot** on a Raspberry Pi 4 — wakeword to speech-to-text
to an LLM to speech, and when the answer involves moving, a navigation command crosses
a serial line to a microcontroller that owns the motors and is allowed to refuse.
Eight Python services over ZeroMQ, on-device YOLO11n vision, and a safety layer where
motion is a **lease rather than a latch**: the MCU brakes within 300 ms unless the Pi
keeps renewing permission, so a crashed process or an unplugged cable stops the robot
without depending on the Pi behaving correctly. Sensors fail closed. The firmware's
protocol and safety logic are tested twice, once in Python and once in C.

**Post-quantum cryptography on UAV links** — ASCON, ML-KEM, ML-DSA, SPECK, NTRU and
Saber benchmarked for latency, throughput and energy on Raspberry Pi 4 and 5, alongside
DDoS detection on the same constrained hardware and reinforcement-learning schedulers
that trade threat level against thermal and battery headroom. Most of this lives in
private repositories while the work is under review.

---

## Selected work

### Robotics and control

| | |
|---|---|
| **[esp32-rc-race-car](https://github.com/Kamalbura/esp32-rc-race-car)** | An RC car where **both ends of the radio link are mine** — a handheld ESP32-S3 transmitter and a receiver on the car over encrypted ESP-NOW at 100 Hz, with CRC-checked packets, a 120 ms failsafe, MPU6050 yaw assist and speed-dependent steering authority. Two generations documented, including why the second one uses *slower* motors. |
| **[tank](https://github.com/Kamalbura/tank)** | Arduino Mega tank-steer robot — 10-channel RC, three-mode state machine, seven servos, timer-safe PWM |
| **[esp32-car](https://github.com/Kamalbura/esp32-car)** | Sensor robot across four stages: Pi-tethered, full sensor suite, Wi-Fi dashboard with autonomous mode, then an Android app over Bluetooth |
| **[DeskMate](https://github.com/Kamalbura/DeskMate)** | ESP32-S3 desk companion with an animated expressive face, gesture reactions, idle sleep and OTA updates |

### Systems and platforms

| | |
|---|---|
| **[final_year](https://github.com/Kamalbura/final_year)** | Air quality forecasting platform — Open-Meteo ingestion, PostgreSQL with watermarked incremental loads, per-city Airflow DAGs running on a Raspberry Pi, a nine-model zoo behind a factory with Optuna tuning, and a Next.js dashboard |
| **[d-detectetion](https://github.com/Kamalbura/d-detectetion)** | Modular DDoS detection for Raspberry Pi — XGBoost or a Time Series Transformer over a shared pipeline, with INT8 quantisation |
| **[agent-q](https://github.com/Kamalbura/agent-q)** | Windows accessibility overlay in WPF/.NET 8 — captures screen context, plans actions through an LLM adapter, and validates them behind a safety layer before execution |

### Security and reverse engineering

| | |
|---|---|
| **[orange-box-s40-teardown](https://github.com/Kamalbura/orange-box-s40-teardown)** | Full teardown of an Android projector: partition and boot-chain analysis, device tree, driver and kernel module inventory — and preinstalled malware, with a reproducible debloat path and a custom-Linux feasibility assessment |

### Sensing and instrumentation

| | |
|---|---|
| **[Air-quality-monitoring](https://github.com/Kamalbura/Air-quality-monitoring)** | ESP32 to ThingSpeak to a Node/Express dashboard, with a Python analytics pipeline and local CSV fallback |
| **[avhzy-ct3-tcp](https://github.com/Kamalbura/avhzy-ct3-tcp)** | Live voltage, current and power streamed off an AVHzY CT-3 meter over TCP — Lua on the meter, Python on the host |
| **[pi-nas](https://github.com/Kamalbura/pi-nas)** | Raspberry Pi 4B NAS build, documented, with a live status page |

---

## Tools

**Languages** &nbsp; C · C++ · Python · JavaScript / TypeScript · C# · SQL · Lua

**Embedded** &nbsp; ESP-IDF · Arduino · FreeRTOS · ESP-NOW · TinyUSB · MAVLink · I²C / I²S / SPI / UART

**Robotics** &nbsp; ZeroMQ · ONNX Runtime · YOLO · MPU6050 sensor fusion · PID and slew-rate control

**ML** &nbsp; PyTorch · XGBoost · scikit-learn · Optuna

**Crypto** &nbsp; liboqs · ASCON · ML-KEM · ML-DSA · mbedTLS

**Data** &nbsp; PostgreSQL · Airflow · dbt · Docker

**Web** &nbsp; Next.js · React · Node / Express · Tailwind

---

<div align="center">

I try to document what is *actually* true of a system, including the parts that
are not finished yet — a README that overstates what works costs more than one
that admits a gap.

</div>
