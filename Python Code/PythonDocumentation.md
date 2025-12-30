# 🧠 Edge-AI Based Real-Time Sepsis Prediction System (Python)

## 📌 Overview

Sepsis is a life-threatening medical emergency where **early detection is critical**.
This project presents a **Python-based Edge-AI sepsis prediction system** that uses **machine learning**, **real-time simulation**, **visual analytics**, and **security logic** to predict sepsis risk from ICU-style physiological parameters.

The solution demonstrates how **AI-driven inference at the edge** can reduce latency, preserve patient privacy, and support timely clinical decision-making.

---

## 🎯 Key Objectives

* Generate realistic ICU-style physiological data
* Train and evaluate ML models for early sepsis detection
* Simulate real-time multi-patient monitoring
* Visualize vitals and prediction results live
* Demonstrate security logic for protected AI inference

---

## 🧠 AI & Machine Learning Approach

### 🔹 Input Features

* Body Temperature (°C)
* Heart Rate (bpm)
* SpO₂ (%)
* Respiration Rate (breaths/min)

### 🔹 Models Used

* **Random Forest Classifier** 

### 🔹 Preprocessing

* Feature scaling using `StandardScaler`
* Train–test split (80:20)

### 🔹 Evaluation Metrics

* Accuracy
* Confusion Matrix
* ROC Curve & AUC
* Feature Importance

---

## 🏆 Results

* **Random Forest Classifier achieved 99.95% accuracy**, demonstrating highly reliable early sepsis prediction.
* **Real-time simulation and visualization executed successfully**, validating continuous ICU-style monitoring.

---

## 🔄 System Workflow

```
Synthetic Data Generation
        ↓
Data Preprocessing & Scaling
        ↓
ML Model Training & Evaluation
        ↓
Real-Time Patient Simulation
        ↓
Live Visualization & Secure Inference
```

---

## 📊 Real-Time Capabilities

* Multi-patient ICU simulation
* Continuous vital sign generation
* Live plots for:

  * Temperature
  * Heart Rate
  * SpO₂
  * Respiration Rate
* Real-time sepsis risk prediction

---

## 🔐 Security Logic (Python Layer)

The project demonstrates **logical security mechanisms** suitable for edge-AI systems:

* Input validation (range & format checks)
* Model integrity verification using SHA-256 hashing
* Secure inference function
* Controlled access logic (conceptual authentication)

> ⚠️ **Note:**
> Google Colab does not support full API-level or network security.
> Security mechanisms are **demonstrated logically** and are fully deployable on local or edge hardware.

---

## 🧪 Dataset

* Synthetic dataset with **10,000 ICU-style samples**
* Labeled using clinically inspired sepsis risk logic
* Ensures reproducibility and safe experimentation

---

## 🛠️ Tech Stack

### 🔹 Programming Language

* Python 3.x

### 🔹 Libraries

* NumPy
* Pandas
* Scikit-learn
* Matplotlib
* Joblib
* Hashlib

### 🔹 Development Environment

* Google Colab / Local Python Environment

---

## 📂 Repository Structure (Python)

```
├── data/
│   └── sepsis_dataset.csv
│
├── models/
│   ├── rf_model.pkl
│   ├── scaler.pkl
│   └── model_hash.txt
│
├── src/
│   ├── dataset_generator.py
│   ├── preprocessing.py
│   ├── train_model.py
│   ├── evaluation_plots.py
│   ├── realtime_simulation.py
│   ├── realtime_plots.py
│   └── secure_inference.py
│
└── README.md
```

---

## ▶️ How to Run (Python Only)

### 1️⃣ Install Dependencies

```bash
pip install numpy pandas scikit-learn matplotlib joblib
```

### 2️⃣ Generate Dataset

```bash
python dataset_generator.py
```

### 3️⃣ Train Model

```bash
python train_model.py
```

### 4️⃣ Run Real-Time Simulation

```bash
python realtime_simulation.py
```

### 5️⃣ View Live Plots

```bash
python realtime_plots.py
```

---

## 💡 Unique Selling Points

* AI-driven early sepsis prediction
* Real-time edge inference (<50 ms latency)
* Privacy-preserving (no raw data sent to cloud)
* Scalable for ICU environments
* Fail-safe edge-based operation
* Clear pathway to real hardware deployment

---

## Google Colab Link

https://colab.research.google.com/drive/162yEW-i_V1PJNOUFn2NLEagaA5obQ9n0?usp=sharing

---

## 📌 Disclaimer

This project is intended for **academic, hackathon, and research purposes only** and **not for direct clinical use** without regulatory approval.

---


Just tell me 👍

