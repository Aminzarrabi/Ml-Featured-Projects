# 🚀 Machine Learning Featured Projects

This repository contains multiple **practical machine learning projects** tackling real-world tasks.  
Projects include **handwritten digit classification (MNIST)**, **income prediction**, and **transportation-related predictions** (ticket cancellation and trip purpose).

---

## 📂 Projects Overview

### 1️⃣ Handwritten Digit Classification – MNIST

**Objective:** Classify handwritten digits (0–9) from 28x28 grayscale images.

**Dataset:**
- `mnist_train.csv` (784 pixel columns + label)
- `mnist_test.csv` (784 pixel columns)

**Workflow:**
- Load and inspect data
- Train-test split
- MLPClassifier training (scikit-learn)
- Performance evaluation using **weighted F1-score**
- Test data predictions for submission

**Tools & Libraries:** Python, Pandas, NumPy, scikit-learn, Matplotlib

---

### 2️⃣ Income Prediction

**Objective:** Predict whether an individual earns `<=50K` or `>50K`.

**Dataset:** `train.csv`, `test.csv`

**Workflow:**
- Data preprocessing and feature handling
- Model training using **H2O Random Forest**
- Evaluation using **F1-score** (~0.725)
- Prediction on unseen test data

**Tools & Libraries:** Python, Pandas, NumPy, H2O.ai, scikit-learn

---

### 3️⃣ Transportation Prediction

This project contains **two prediction tasks**:

#### a) Cancel Prediction

- **Goal:** Predict ticket cancellations
- **Features:** Vehicle info, pricing, discount usage, family/group flags
- **Model:** XGBoost Classifier
- **Evaluation:** F1-score ≈ 0.943
- **Output:** Submission-ready predictions for test bookings

#### b) Trip Reason Prediction

- **Goal:** Predict trip purpose (`Work` or `Int`)
- **Features:** Vehicle type/class, temporal features (month/hour), demographics
- **Model:** XGBoost Classifier
- **Evaluation:** F1-score ≈ 0.806
- **Output:** Test data predictions

**Tools & Libraries:** Python, Pandas, NumPy, scikit-learn, XGBoost

---

## 🛠️ Tools & Technologies

- Python 3.x
- Data manipulation: Pandas, NumPy
- Machine learning: scikit-learn, XGBoost, H2O.ai
- Data preprocessing: MinMaxScaler, LabelEncoder, One-Hot Encoding
- Evaluation metrics: F1-score, classification report, confusion matrix

---

## 🎯 Learning Outcomes

- End-to-end ML pipelines for multiple tasks
- Handling missing values and feature engineering for structured data
- Scaling and encoding for numeric and categorical features
- Training and evaluating models on tabular and image data
- Prediction on unseen datasets with reproducible workflows
