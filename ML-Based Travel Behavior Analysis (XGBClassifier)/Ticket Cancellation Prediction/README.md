# 🚖 Transportation Request Application – ML Prediction

This project implements **machine learning pipelines** for a transportation request platform, focusing on **two key prediction modules**:

1. **Cancellation Prediction** – Predict whether a user will cancel a booking  
2. **Trip Type/Engagement Analysis** – Optional module for analyzing user engagement or trip characteristics

The goal is to train models on historical booking data, evaluate performance, and generate predictions on new requests.

---

## 📂 Dataset Overview

- **Training Data**: `train_data.csv`  
- **Test Data**: `test_data.csv`  
- Columns include booking details, vehicle type, pricing, trip reason, gender, discount usage, and timestamps.  
- Target Columns: 
  - `Cancel` for cancellation module  
  - Other columns (optional) for engagement/analysis module

---

## 🧩 Project Workflow (Common Preprocessing)

1. **Data Cleaning**
   - Drop irrelevant columns (UserID, BillID, Coupon codes, etc.)
   - Fill missing values using **grouped mode** or median  
   - Convert Boolean and categorical columns to numeric  
   - Generate new features:
     - `family` size per BillID
     - `is with family` flag
     - `blit_gap` (days between booking and departure)
     - `has discount` flag
     - `net_price` (Price minus CouponDiscount)

2. **Feature Scaling**
   - Normalize price-related columns using `MinMaxScaler`

3. **Encoding Categorical Variables**
   - Label encoding for `From`, `To`, `Vehicle`

4. **Final Feature Selection**
   - Drop timestamp and ID columns

---

## 1️⃣ Cancellation Prediction Module

**Objective:** Predict whether a booking will be canceled.  

**Model:**  
- Algorithm: `XGBoostClassifier`  
- Parameters:
  - `max_depth = 20`  
  - `learning_rate = 0.1`  
  - `n_estimators = 1000`  
  - `min_child_weight = 1`  
  - `gamma = 1`  

**Workflow:**
- Split training data into train/test sets  
- Fit XGBoost on preprocessed features  
- Evaluate using **F1-score** and confusion matrix  
- Predict cancellations for test dataset

**Performance:**  
- F1-score ≈ 0.943 on validation set

**Output:**  
- DataFrame with predicted `Cancel` column for submission

---

## 2️⃣ Trip Type / Engagement Module (Optional)

- Analyze trip features like `TripReason`, `VehicleClass`, and `family` for additional insights  
- Could use classification or regression models depending on the analysis target  
- Preprocessing and feature engineering are shared with cancellation module

---

## 🛠️ Tools & Technologies

- **Programming Language:** Python  
- **Data Handling:** Pandas, NumPy  
- **Machine Learning:** XGBoost, scikit-learn  
- **Evaluation Metrics:** F1-score, classification report, confusion matrix  
- **Preprocessing:** MinMaxScaler, LabelEncoder, Feature Engineering

---

## 🎯 Conclusion

This project demonstrates a **robust ML workflow** for real-world transportation data, including:

- Data cleaning and preprocessing
- Feature engineering for domain-specific insights
- High-performance model training and evaluation
- Predictions for unseen data  

It can be easily extended to other prediction tasks within the platform.
