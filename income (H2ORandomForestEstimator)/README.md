# 💰 Income Prediction Using H2O Random Forest

This project implements a **supervised machine learning pipeline** for predicting individual income categories (`<=50K` or `>50K`) using the **H2O Random Forest** algorithm.  
The objective is to train a robust model on census data, evaluate its performance using F1-score, and generate predictions for unseen test data.

---

## 📂 Dataset Overview

- **Training Data**: `train.csv`  
  - Contains demographic and economic features such as age, education, occupation, and hours worked per week  
  - Target column: `income` (binary classification)
- **Test Data**: `test.csv`  
  - Same features as training data (without target)  
- **Task**: Binary classification (`<=50K` vs `>50K`)

---

## 🧩 Project Workflow

1. **Data Loading & Inspection**  
   - Load CSV datasets using **Pandas**  
   - Explore data distribution and feature types

2. **Data Preprocessing**  
   - Handle categorical features (H2O automatically encodes factors)  
   - Split training data into training and validation sets

3. **H2O Initialization & Model Setup**  
   - Initialize H2O cluster  
   - Convert datasets to `H2OFrame`  
   - Configure **H2ORandomForestEstimator** with:
     - `ntrees = 100`  
     - `sample_rate = 0.7`

4. **Model Training**  
   - Train on the training H2OFrame  
   - Monitor progress and convergence

5. **Model Evaluation**  
   - Generate predictions on validation set  
   - Convert predictions to numeric labels (`0` for `<=50K`, `1` for `>50K`)  
   - Evaluate using **F1-score** for balanced performance assessment

6. **Test Data Prediction**  
   - Apply the trained model on unseen test data  
   - Generate structured DataFrame ready for submission or further analysis

---

## 🛠️ Tools & Technologies

- **Programming Language**: Python  
- **Data Handling**: Pandas, NumPy  
- **Machine Learning**: H2O.ai, H2ORandomForestEstimator  
- **Evaluation Metrics**: F1-score (weighted/binary)

---

## 📊 Key Insights

- Random Forests handle **categorical and numerical features** effectively  
- Using H2O allows **distributed and efficient training** for large datasets  
- Model achieved **F1-score ≈ 0.725** on validation set, demonstrating balanced precision and recall  

---

## 🎯 Conclusion

This project provides a **complete end-to-end workflow** for income prediction from census data:  
from preprocessing, H2O-based model training, evaluation, to test data prediction.  
It demonstrates practical usage of **H2O Random Forest** for scalable, high-performance classification tasks with tabular data.
