<div align="center">

# Kamal Bura

**Embedded systems · UAV security research · Data platforms**

</div>

---

I build things that run on constrained hardware and I research how to secure them.
Most of my work sits at the boundary between firmware and the systems it talks to —
flight controllers, sensor networks, ground stations — and increasingly on what happens
when you put modern cryptography and machine learning on a device with a few hundred
kilobytes of RAM and a battery budget.

Three threads run through the repositories here:

**Embedded and hardware.** ESP32 and ESP-IDF, Arduino, Raspberry Pi. Cascaded PID
control and IMU sensor fusion for multirotors, differential-steering RC platforms,
USB HID over TinyUSB, I2S audio pipelines, and assistive devices. Where I can, I
document the hardware as carefully as the code — bill of materials, wiring, and the
failure modes I actually hit.

**Security research.** Post-quantum cryptography on UAV links — ASCON, ML-KEM, ML-DSA,
SPECK, NTRU, Saber — benchmarked for latency, throughput and energy on Raspberry Pi 4
and 5. Alongside that, DDoS detection on the same constrained hardware using XGBoost
and Time Series Transformers, and reinforcement-learning schedulers that trade off
threat level against thermal and battery state. I also take apart consumer hardware:
a recent teardown of an Android projector surfaced preinstalled malware and a
reproducible debloat path.

**Data and ML platforms.** End-to-end pipelines rather than notebooks — ingestion with
watermarked incremental loads, PostgreSQL, Airflow DAGs running on a Raspberry Pi,
model training and forecasting, and a dashboard on top. I care about the boring parts:
idempotent loads, lineage, and knowing when a model has gone stale.

---

## Selected work

### Systems and platforms
| Project | What it is |
|---|---|
| [final_year](https://github.com/Kamalbura/final_year) | Air quality forecasting platform: Open-Meteo ingestion, PostgreSQL with watermarks, per-city Airflow DAGs on a Pi, 7-day forecasting, Next.js dashboard |
| [d-detectetion](https://github.com/Kamalbura/d-detectetion) | Modular DDoS detection for Raspberry Pi — XGBoost or Time Series Transformer over a shared pipeline, with INT8 quantisation |
| [agent-q](https://github.com/Kamalbura/agent-q) | Windows accessibility overlay in WPF/.NET 8 — screen context capture, LLM action planning, validation and safety layer before execution |

### Hardware and firmware
| Project | What it is |
|---|---|
| [DeskMate](https://github.com/Kamalbura/DeskMate) | ESP32-S3 desk companion with an animated expressive face, MPU6050 gesture reactions, idle sleep and OTA updates |
| [RC-cyber-truck](https://github.com/Kamalbura/RC-cyber-truck) | ESP32 RC vehicle: differential steering, interrupt-driven RC decoding, BTS7960 motor control, signal-loss failsafe |
| [tank](https://github.com/Kamalbura/tank) | Arduino Mega tank-steer robot — 10-channel RC, three-mode state machine, seven servos, timer-safe PWM |
| [avhzy-ct3-tcp](https://github.com/Kamalbura/avhzy-ct3-tcp) | Live power measurement streamed off an AVHzY CT-3 meter over TCP — Lua on the meter, Python on the host |

### Reverse engineering
| Project | What it is |
|---|---|
| [orange-box-s40-teardown](https://github.com/Kamalbura/orange-box-s40-teardown) | Full teardown of an Android projector: partition and boot-chain analysis, device tree, preinstalled malware findings, debloat results, custom Linux feasibility |

### Sensing and web
| Project | What it is |
|---|---|
| [Air-quality-monitoring](https://github.com/Kamalbura/Air-quality-monitoring) | ESP32 → ThingSpeak → Node/Express dashboard with a Python analytics pipeline and CSV fallback |
| [pi-nas](https://github.com/Kamalbura/pi-nas) | Raspberry Pi 4B NAS build, documented, with a live status page |
| [portfolio](https://github.com/Kamalbura/portfolio) | Next.js 15 / React 19 portfolio — GSAP, Lenis, Tailwind 4, WCAG 2.1 AA |

---

## Tools

**Languages** C · C++ · Python · JavaScript / TypeScript · C# · SQL · Lua
**Embedded** ESP-IDF · Arduino · FreeRTOS · TinyUSB · MAVLink · I2C / I2S / UART · PlatformIO
**ML** PyTorch · XGBoost · scikit-learn · Optuna · ONNX
**Crypto** liboqs · ASCON · ML-KEM · ML-DSA · mbedTLS
**Data** PostgreSQL · Airflow · dbt · Docker
**Web** Next.js · React · Node / Express · Tailwind

---

<div align="center">

Some of my research lives in private repositories while the work is under review.
Happy to talk about it — reach me at the address on my GitHub profile.

</div>
