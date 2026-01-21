# Elderly Fall Detection using Machine Learning and Deep Learning

A comparative study of **classical machine learning**, **fully connected deep neural networks**, and **sequence-based deep learning models (LSTM)** for elderly fall detection using wearable sensor data.

This project analyzes how different modeling approaches perform on **time-series accelerometer data** from the **MobiFall Dataset** and highlights the importance of temporal modeling for fall detection.

---

## 📌 Project Overview

Falls are one of the major health risks for elderly individuals. Wearable sensors generate time-series data that can be used to automatically recognize activities and detect falls.

In this project, we compare three approaches:

1. Feature Engineering + Classical Machine Learning  
2. Fully Connected Deep Neural Network (FC-DNN)  
3. Sequence-Based Deep Learning (LSTM)

The goal is to identify which approach performs best for fall detection and understand their strengths and limitations.

---

## 👩‍💻 Contributors

- **Alina Idrees**
- **Khadija tul Kubra**

---

## 📂 Dataset Information

- **Dataset Name:** MobiFall Dataset v2.0  
- **Source:** Kaggle (Original smartphone-based sensor dataset)  
- **Subject Used:** `sub10`  
- **Sensor:** 3-axis Accelerometer (X, Y, Z)  
- **Data Type:** Time-series sensor data  

### Activity Classes (6)

- Standing  
- Walking  
- Sitting  
- Back Sitting Chair  
- Fall Forward Lying  
- Sideward Lying  

---

## ⚙️ Data Preprocessing

The following preprocessing steps were applied:

- Removal of metadata and headers from raw `.txt` files  
- Parsing and cleaning of sensor readings  
- Non-overlapping fixed-length window segmentation  
- Label encoding  
- Z-score normalization  
- Train-test split (80% training, 20% testing)

For sequence-based models:
- **Sequence length:** 200 time steps

---

## 🧠 Modeling Approaches

### 1️⃣ Feature Engineering + Classical ML

Statistical features were extracted from each window:
- Mean
- Standard deviation
- Minimum
- Maximum

Models used:
- Logistic Regression
- Support Vector Machine (SVM)
- Decision Tree
- Random Forest / XGBoost

---

### 2️⃣ Fully Connected Deep Neural Network (FC-DNN)

- Multilayer Perceptron trained on raw normalized sensor data
- Treats each sample independently
- No explicit temporal modeling

---

### 3️⃣ Sequence-Based Deep Learning (LSTM)

- Raw accelerometer signals segmented into sequences
- Temporal order preserved
- LSTM learns motion dynamics over time

---

## 📊 Results Summary

| Approach | Model | Accuracy | Macro F1-Score |
|--------|------|----------|---------------|
| Feature Engineering + ML | Random Forest | **98.31%** | **0.9626** |
| Fully Connected DNN | FC-DNN (Raw Data) | 90.05% | 0.73 |
| Sequence-Based Model | LSTM | 96.48% | 0.9165 |

---

## 📈 Key Observations

- Classical ML models perform well with engineered features but require domain expertise.
- Fully connected neural networks reduce feature engineering effort but ignore temporal dependencies.
- LSTM significantly outperforms other approaches in terms of balanced performance due to effective temporal modeling.
- Macro F1-score is critical due to class imbalance between daily activities and fall events.

---

## ⚠️ Challenges Faced

- Class imbalance in fall vs non-fall activities  
- Parsing raw sensor files with inconsistent formats  
- Selecting appropriate window and sequence lengths  
- Improving macro F1-score instead of only accuracy  

---

## 🔮 Future Work

- Use overlapping sliding windows  
- Train models on multiple subjects  
- Explore GRU, Attention, and Transformer-based models  
- Optimize models for real-time fall detection systems  
- Deploy on edge or mobile devices  

---

## 🛠️ Technologies Used

- Python  
- NumPy, Pandas  
- Scikit-learn  
- TensorFlow / Keras  
- Matplotlib  

---

## 📄 License

This project is for **academic and educational purposes** only.

---

## ⭐ Acknowledgment

We acknowledge the creators of the **MobiFall Dataset** for providing open access to sensor data used in this study.

---

Feel free to ⭐ this repository if you find it helpful!
