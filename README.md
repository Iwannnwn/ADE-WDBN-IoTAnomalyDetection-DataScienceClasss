# ADE-WDBN: Adaptive Differential Evolution Weighted Deep Belief Network
### Anomaly Detection for IoT Network Security

## 📌 Overview
This project proposes **ADE-WDBN (Adaptive Differential Evolution – Weighted Deep Belief Network)** for **anomaly detection in IoT network traffic**.  
The model is designed to handle **resource-constrained IoT environments** and **highly imbalanced attack data**, where conventional methods struggle to identify rare but critical cyber attacks.

The system focuses on detecting network anomalies caused by attacks such as **spoofing, DoS, botnet injection, and scanning**.

---

## 🔐 Motivation
IoT devices have significant limitations:
- Limited **memory**, **energy**, and **computational power**
- Inability to run complex security mechanisms
- Network attacks often produce **subtle (fuzzy) patterns**
- Severe **class imbalance** between normal and attack traffic

This motivates the use of a **lightweight yet robust anomaly detection model**.

---

## 🗂 Dataset
- **Data**: IoT network traffic dataset
- **Task**: Binary classification  
  - `0` → Normal traffic  
  - `1` → Anomalous traffic (attack)
- **Data Split**: Train / Test

---

## 🧠 Model Architecture

### ADE-WDBN Framework
The proposed model consists of:
- **Deep Belief Network (DBN)** with stacked **Restricted Boltzmann Machines (RBMs)**
- **Logistic Regression layer** for final classification
- **Weighted loss function** to handle class imbalance

### Optimization Strategy
- **Adaptive Differential Evolution (ADE)** is used to optimize:
  - Learning rate
  - Weight decay
  - RBM epochs
  - Contrastive Divergence (CD-k)
  - Scaling factor

---

## ⚙️ Training Strategy

### Imbalanced Data Handling
- **Class Weighting**
- **Weighted Random Sampler**

These strategies help the model focus on minority (attack) samples.

---

## 🔍 Inference
- Input: Network traffic features
- Output: Binary class prediction  
  - `0` → Normal  
  - `1` → Anomaly

---

## 📊 Evaluation Metrics
Model performance is evaluated using:
- **F1-Score**
- **Recall**
- **Precision**
- **Accuracy**

---

## 📈 Results Comparison

| Model | F1-Score | Recall | Precision | Accuracy |
|------|---------|--------|-----------|----------|
| **ADE-WDBN** | **0.3556** | **0.80** | 0.23 | 0.71 |
| Logistic Regression | 0.2826 | 0.65 | 0.18 | 0.67 |
| XGBoost | 0.1538 | 0.10 | 0.33 | 0.89 |

📌 ADE-WDBN achieves the **highest F1-Score and Recall**, making it more effective in detecting rare IoT attacks despite lower accuracy.

---

## 🛠 Tech Stack
- Python  
- PyTorch  
- Scikit-learn  
- NumPy, Pandas  

---

## 📜 Reference
Zhang, C., Tan, K. C., Li, H., & Hong, G. S. (2019).  
**A cost-sensitive deep belief network for imbalanced classification.**  
IEEE Transactions on Neural Networks and Learning Systems, 30(1), 109–122.
