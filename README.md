# 🔥 Basic Heater Control System – Embedded Systems Intern Assignment

**Author:** Hiba Fathima P C  
**Date:** July 19, 2025  
**Simulator:** [Wokwi Project Link](https://wokwi.com/projects/436891492894744577)

---

## 📌 Overview

This project implements a **basic heater control system** using an LM35 temperature sensor, an ESP32 microcontroller, and a simulated heating mechanism (Red LED). Built for the upliance.ai Embedded Systems Intern Assignment, it demonstrates temperature-driven state control, overheating protection, and visual/audio feedback features.

---

## 🧰 Components Used

| Component         | Quantity | Role                                  |
|------------------|----------|---------------------------------------|
| ESP32 Dev Module | 1        | Microcontroller                       |
| LM35             | 1        | Temperature sensing                   |
| Red LED          | 1        | Simulated heater                      |
| Green LED        | 1        | Status indicator (safe state)         |
| Buzzer           | 1        | Overheat alarm                        |
| 220Ω Resistors   | 2        | For LEDs                              |
| Breadboard + Wires | —      | For wiring                            |

---

## 📈 System Architecture

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/596ebc3d-2855-4cd8-8cb8-a85192285145" />



### Modules:
- **LM35**: Analog temperature sensor (10mV/°C)
- **ESP32**: Reads sensor, drives logic
- **Red LED**: Heater indicator (ON = Heating)
- **Green LED**: Stable/safe state indicator
- **Buzzer**: Alerts during overheating
- **Serial Monitor**: Logs state and temperature

---

## 🧠 State Machine Logic

| State          | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `IDLE`         | Temp < HEATING_THRESHOLD – system waits                                     |
| `HEATING`      | Temp < TARGET_TEMPERATURE – heater ON                                       |
| `STABILIZING`  | Temp > TARGET_TEMPERATURE – heater OFF, temp settling                       |
| `TARGET_REACHED` | Temp in [STABILIZE_LOWER, STABILIZE_UPPER] – heater OFF                   |
| `OVERHEAT`     | Temp > OVERHEAT_THRESHOLD – heater OFF, buzzer ON                           |

---

## 🚀 How to Run (in Wokwi)

1. Open the project: [Wokwi Link](https://wokwi.com/projects/436891492894744577)
2. Click “Run” to simulate.
3. Adjust LM35 temperature slider to observe state transitions.
4. Watch the Serial Monitor for logs and status updates.

**GPIO Pin Mapping:**

| Pin      | Component        |
|----------|------------------|
| GPIO34   | LM35 Vout (ADC)  |
| GPIO17   | Red LED (Heater) |
| GPIO16   | Green LED (Status) |
| GPIO18   | Buzzer           |

---

## 💡 Features Implemented

✅ Temperature-based state transitions  
✅ Overheating detection with buzzer  
✅ Status LED for safe zones  
✅ Periodic sensor reads (non-blocking)  
✅ Serial logging for debugging

---

## ✨ Future Roadmap

- 🔄 Dual-sensor redundancy
- 🧠 PID temperature control
- 🧊 Adaptive cool-down & manual reset
- 📱 Wi-Fi/BLE + UI for heating profiles
- 🕒 RTC-based scheduling

---

## 📁 Repository Structure


