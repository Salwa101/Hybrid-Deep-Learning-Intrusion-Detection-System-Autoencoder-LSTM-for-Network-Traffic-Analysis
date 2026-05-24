# 🔐 Hybrid Deep Learning Intrusion Detection System

A machine learning–based Intrusion Detection System (IDS) that combines an **Autoencoder for feature learning** and an **LSTM network for sequential analysis** to detect malicious network activity using the KDDCup99 dataset.

This project also includes a simulated **Security Operations Center (SOC)** real-time monitoring dashboard.

---

## 🚀 Project Overview

Cybersecurity threats are increasing in complexity, making traditional rule-based IDS ineffective. This project builds a **hybrid deep learning approach** to detect anomalies in network traffic using:

- 🧠 Autoencoder → Learns compressed feature representations
- 🔁 LSTM → Captures sequential patterns in network traffic
- 📊 Evaluation → Accuracy, Precision, Recall, F1-score, ROC-AUC
- 🔴 SOC Simulation → Real-time risk monitoring system

---

## 📂 Dataset

We use the **KDDCup99 (SA subset)** dataset from `sklearn.datasets`.

It contains network connection records labeled as:
- Normal traffic
- Attack traffic (DoS, Probe, R2L, U2R)

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Label encoding for categorical features
- MinMax scaling for normalization
- Sequence generation for time-series modeling

### 2. Autoencoder (Feature Learning)
- Compresses input features into lower-dimensional representation
- Learns meaningful patterns in network behavior

### 3. LSTM Model (Attack Detection)
- Processes sequential data
- Classifies network traffic as normal or malicious

### 4. Real-Time SOC Simulation
- Streams test data as packets
- Computes risk score for each packet
- Triggers alerts for suspicious activity

---

## 🧠 Model Architecture

### Autoencoder

Input → Dense(32) → Dense(16) → Dense(8) → Dense(16) → Dense(32) → Output


### LSTM Classifier

LSTM(64, return_sequences=True)
LSTM(32)
Dense(1, sigmoid)


---

## 📊 Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC Curve
- Confusion Matrix

---

## 🔴 SOC Simulation

The system simulates real-time monitoring:


Packet 1 | Risk Score: 0.12 | 🟢 NORMAL
Packet 2 | Risk Score: 0.87 | ⚠️ ATTACK


A risk threshold (0.5) is used to classify events.

---

## 🛠️ Technologies Used

- Python 🐍
- TensorFlow / Keras
- Scikit-learn
- NumPy
- Matplotlib & Seaborn

---

## 📈 Results

The model evaluates network traffic and produces:
- Confusion matrix visualization
- ROC curve with AUC score
- Real-time risk trend graph

> Note: This project uses simplified labels for demonstration purposes.

---

## ⚠️ Limitations

- Uses simplified preprocessing for categorical features
- Labels may not represent real-world imbalance handling
- SOC simulation is not production-grade streaming architecture
- Requires improvement for real deployment use cases

---

## 🔮 Future Improvements

- Use UNSW-NB15 or CICIDS2017 dataset
- Replace LSTM with Transformer-based model
- Add real streaming data pipeline (Kafka / Flink)
- Deploy as Flask/FastAPI security dashboard
- Improve anomaly detection using reconstruction error

---


## 📜 License

This project is for educational and research purposes only.
