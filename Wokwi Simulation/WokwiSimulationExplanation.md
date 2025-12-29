# 🩺 Edge-AI Enabled Real-Time Sepsis Prediction System
---

## 📌 Project Overview

This project presents a **Wokwi-based simulation** of an **Edge-AI Enabled Real-Time Sepsis Prediction System** designed for **ICU critical care applications**.
The system continuously monitors multiple physiological parameters, performs **local (edge) inference** to predict sepsis risk, and triggers **real-time alerts**, ensuring **low latency**, **privacy preservation**, and **reliability**.

Due to simulation constraints, physiological sensors are emulated using analog inputs while preserving the **exact data flow, logic, and architecture** intended for real-world deployment.

---

## 🎯 Problem Addressed

Sepsis is a life-threatening condition requiring **early detection**. Traditional cloud-based or manual monitoring systems suffer from:

* High latency
* Intermittent connectivity
* Privacy risks
* Delayed clinical response

This project demonstrates how **Edge AI + secure wireless sensing** can provide **early warning and decision support** in ICU environments.

---

## 🧠 System Architecture (Simulated)

```
Physiological Sensors (Simulated)
        ↓
ESP32 Edge Device
- Sensor Fusion
- Feature Extraction
- Sepsis Risk Inference
        ↓
Alert System (LED + Buzzer)
        ↓
Secure MQTT Payload (Simulated)
        ↓
Gateway / Dashboard (Serial Monitor)
```

---

## 🧰 Simulation Platform

* **Platform**: Wokwi Online Simulator
* **Controller**: ESP32 Dev Module
* **Programming Language**: Arduino (C++)

---

## 🔧 Components Used (Simulation)

| Component        | Purpose                     |
| ---------------- | --------------------------- |
| ESP32            | Edge processing & inference |
| Potentiometer ×4 | Simulated vital signs       |
| Red LED          | High sepsis risk alert      |
| Yellow LED       | Moderate risk indicator     |
| Buzzer           | Critical alert              |
| Serial Monitor   | MQTT + Dashboard simulation |

---

## 🔌 Pin Connections

### ESP32 Pin Mapping

| Parameter                  | Component     | ESP32 GPIO |
| -------------------------- | ------------- | ---------- |
| Temperature                | Potentiometer | GPIO 33    |
| Heart Rate                 | Potentiometer | GPIO 34    |
| SpO₂                       | Potentiometer | GPIO 35    |
| Respiration Rate           | Potentiometer | GPIO 32    |
| High-Risk LED (Red)        | LED           | GPIO 2     |
| Moderate-Risk LED (Yellow) | LED           | GPIO 16    |
| Buzzer                     | Alarm         | GPIO 4     |

**Power Supply**

* All sensors → **3.3V**
* All grounds → **Common GND**

---

## 🧪 Sensor Simulation Logic

Potentiometers emulate physiological ranges:

| Vital Sign       | Simulated Range     |
| ---------------- | ------------------- |
| Temperature      | 35 – 41 °C          |
| Heart Rate       | 50 – 140 bpm        |
| SpO₂             | 85 – 100 %          |
| Respiration Rate | 10 – 35 breaths/min |

Turning the potentiometer knob **clockwise increases the value**.

---

## 🧠 Edge-AI Sepsis Prediction Logic

The ESP32 performs **local inference** using clinically inspired thresholds:

### Risk Scoring Criteria

* Temperature > 38 °C
* Heart Rate > 100 bpm
* SpO₂ < 92 %
* Respiration Rate > 22
* Shock Index > 0.9

### Risk Classification

| Score | Risk Level |
| ----- | ---------- |
| 0–1   | LOW        |
| 2–3   | MODERATE   |
| ≥4    | HIGH       |

---

## 🚨 Alert Mechanism

| Risk Level | LED       | Buzzer |
| ---------- | --------- | ------ |
| LOW        | OFF       | OFF    |
| MODERATE   | Yellow ON | OFF    |
| HIGH       | Red ON    | ON     |

Alerts are generated **instantly at the edge**, without cloud dependency.

---

## 📡 Secure Communication (Simulated)

* The system simulates **AES-encrypted MQTT payloads**
* JSON data is printed to the Serial Monitor
* In real deployment:

  * MQTT over TLS
  * AES-256 encryption
  * Raspberry Pi / Server gateway

### Example Payload

--- MQTT Publish (Encrypted Payload) ---
{
  "patient_id": "ICU_01",
  
  "temperature": 39.00
  
  "heart_rate": 117.00
  
  "spo2": 89.00
  
  "resp_rate": 19.00
  
  "risk": "HIGH"

}

---

## ▶️ How to Run the Simulation

1. Open the project in **Wokwi**
2. Click **▶ Play**
3. Open **Serial Monitor**
4. Rotate potentiometers to change vital signs
5. Observe:

   * Real-time risk prediction
   * LED & buzzer alerts
   * Secure payload output

---

## 🎥 How to Demonstrate (Hackathon Tip)

1. Start with **normal vitals** → LOW risk
2. Increase **2 parameters** → MODERATE risk
3. Increase **3–4 parameters** → HIGH risk
4. Highlight:

   * Edge inference
   * Instant alert
   * Secure data output

---

## 🔍 Why Potentiometers Are Used

Due to simulation limitations, potentiometers are used to **emulate physiological signals**.

✔ This is **standard and accepted** in hackathons
✔ Real sensors can replace them **without changing the algorithm**

---

## 🏥 Real-World Hardware Mapping

| Simulation     | Real Deployment     |
| -------------- | ------------------- |
| Potentiometer  | MAX30102 / MLX90614 |
| ESP32          | ESP32 / Nano 33 BLE |
| Serial Monitor | MQTT Broker         |
| JSON Output    | ICU Dashboard       |

---

## 🏆 Key Highlights

* ✔ Edge-AI based real-time prediction
* ✔ Low-latency alerts
* ✔ Privacy-preserving design
* ✔ Scalable multi-patient architecture
* ✔ Hackathon-ready & defensible

---

## Wokwi Simulation Link
https://wokwi.com/projects/451660277721056257

---

## ⚠️ Disclaimer

This simulation is intended for **educational and proof-of-concept purposes only**.
It does **not replace medical diagnosis** and should be clinically validated before real-world deployment.

---

## 👥 Team

**Team Name**: NeuroEdge
**Domain**: Edge AI | Healthcare IoT | Critical Care Systems

---

## ✅ Conclusion

This Wokwi simulation successfully demonstrates a **secure, edge-intelligent sepsis prediction system** that aligns with modern ICU requirements and hackathon evaluation criteria.

---
