## Wokwi Architecture

+------------------------------------------------------+
|                  ICU MONITORING UI                   |
|        (Serial Monitor / Virtual Dashboard)          |
|  - Risk Level: LOW / MEDIUM / HIGH                   |
|  - Vital Signs Display                               |
+-------------------------▲----------------------------+
                          |
                          |
+-------------------------|----------------------------+
|              EDGE PROCESSING LAYER                   |
|              (ESP32 / Arduino Nano 33 BLE)           |
|                                                      |
|  - Sensor Data Acquisition                           |
|  - Signal Validation & Thresholding                  |
|  - Feature Packaging                                 |
|  - Sepsis Risk Logic (Rule-based / ML-ready)         |
|                                                      |
+-------------------------▲----------------------------+
                          |
                          |
+-------------------------|----------------------------+
|              SENSOR EMULATION LAYER                  |
|                (Wokwi Virtual Sensors)               |
|                                                      |
|  - Potentiometer → Heart Rate / BP                   |
|  - DHT / Temp Input → Body Temperature               |
|  - Slider / Pot → SpO₂                               |
|  - Digital Input → Respiration Rate                  |
|                                                      |
+------------------------------------------------------+
---
## Data Flow Architecture 

[ Potentiometers / Virtual Sensors ]
                ↓
        [ ESP32 / Arduino ]
                ↓
   [ Feature Processing & Risk Logic ]
                ↓
      [ Serial Output / Status ]
---
