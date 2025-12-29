## DataFlow Diagram Architecture

[ Potentiometers / Virtual Sensors ]
                ↓
        [ ESP32 / Arduino ]
                ↓
   [ Feature Processing & Risk Logic ]
                ↓
      [ Serial Output / Status ]

---

## Wokwi Diagram Architecture

Step 1: 
**SENSOR EMULATION LAYER**

(Wokwi Virtual Sensors)                                   
 - Potentiometer → Heart Rate / BP  
 - DHT / Temperature Input → Body Temperature        
 - Slider / Potentiometer → SpO₂                 
 - Digital Input / Pot → Respiration Rate

Step 2:
**EDGE PROCESSING LAYER**

(ESP32 / Arduino Nano 33 BLE)  
 - Sensor Data Acquisition
 - Signal Validation & Thresholding
 - Feature Packaging
 - Sepsis Risk Logic (Rule-based / ML-ready) 
     
Step 3:
**ICU MONITORING UI** 
(Serial Monitor / Virtual Dashboard)
- Risk Level: LOW / MEDIUM / HIGH
- Real-time Vital Signs Display   

