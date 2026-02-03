## 🚖 Transportation Request Application – Trip Reason Prediction

This module focuses on predicting the **purpose of the trip** for each booking in the transportation request platform.  
The target is to classify trips as either **Work** or **Int (International/Other)** based on historical booking data and features.

---

## 📂 Dataset Overview

- **Training Data**: `train_data.csv`  
- **Test Data**: `test_data.csv`  
- Features include booking details, vehicle class, pricing, gender, discounts, timestamps, and family/group flags.  
- **Target Column**: `TripReason` (`Work` = 1, `Int` = 0)

---

## 🧩 Project Workflow

### 1️⃣ Data Cleaning & Feature Engineering
- Fill missing values for `VehicleType` and `VehicleClass` using **grouped mode**
- Generate new features:
  - Month and hour of `DepartureTime` and `Created`
- Convert Boolean fields (`Male`, `VehicleClass`) to numeric  
- Scale price-related columns (`CouponDiscount`, `Price`) using **MinMaxScaler**  
- One-hot encode categorical variables (`Vehicle`)  
- Drop irrelevant columns (`UserID`, `BillID`, timestamps, location columns)

### 2️⃣ Train-Test Split
- Split data into 80% training and 20% validation sets  
- Stratified split ensures balanced class distribution  

### 3️⃣ Model Training
- **Algorithm:** XGBoost Classifier  
- **Key Parameters:**  
  - `max_depth=7`  
  - `learning_rate=0.2`  
  - `n_estimators=200`  
  - `subsample=0.8`  
  - `min_child_weight=1`  
  - `gamma=1`  

### 4️⃣ Model Evaluation
- Use **F1-score** to evaluate performance  
- Classification report and confusion matrix can be generated for deeper insights  
- Validation F1-score ≈ 0.806

### 5️⃣ Test Data Prediction
- Apply trained model to unseen test data  
- Output predictions in structured **DataFrame**  
- Replace numeric labels with original strings (`1 → Work`, `0 → Int`) for clarity

---

## 🛠️ Tools & Technologies

- **Programming Language:** Python  
- **Data Handling:** Pandas, NumPy  
- **Machine Learning:** XGBoost, scikit-learn  
- **Preprocessing:** MinMaxScaler, LabelEncoder, Feature Engineering  
- **Evaluation Metrics:** F1-score, Classification Report, Confusion Matrix

---

## 🎯 Conclusion

This module demonstrates an **end-to-end classification workflow** for predicting trip purpose:  

- Comprehensive data cleaning and preprocessing  
- Feature engineering for temporal and categorical attributes  
- High-performance model training using XGBoost  
- Evaluation and prediction for unseen data  

It can be integrated seamlessly with the **Cancellation Prediction Module** to provide a complete ML-based decision support system for the transportation platform.
