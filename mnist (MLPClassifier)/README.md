# 🤖 Handwritten Digit Classification Using MLP (MNIST Dataset)

This project implements a **supervised machine learning pipeline** for **handwritten digit recognition** using the **Multi-Layer Perceptron (MLP) Classifier** from `scikit-learn`.  
The objective is to build a robust model capable of classifying digits (0–9) from pixel-based features, evaluate its performance, and generate predictions for unseen test data.

---

## 📂 Dataset Overview

- **Training Data**: `mnist_train.csv`  
  - 784 features representing 28x28 grayscale images (flattened)  
  - 1 `label` column indicating the digit class
- **Test Data**: `mnist_test.csv`  
  - 784 features (no labels)
- **Task**: 10-class classification (digits 0–9)
- **Data Source**: [GitHub Release](https://github.com/Aminzarrabi/Ml-Featured-Projects/releases/download/Mnist_train_data/mnist_train.csv)  
  *(The dataset is not included directly due to its size.)*

---

## 🧩 Project Workflow

The project follows a standard **machine learning pipeline**:

1. **Data Loading & Inspection**  
   - Load CSV datasets using **Pandas**  
   - Inspect missing values, data types, and basic statistics

2. **Data Preprocessing & Scaling**  
   - Normalize pixel values  
   - Ensure consistent input format for the neural network

3. **Train-Test Split**  
   - Separate training data into training and validation sets for performance evaluation

4. **Model Training (MLPClassifier)**  
   - Configure MLP with hidden layers, activation function, and solver  
   - Train using the training subset  
   - Hyperparameters tuned for stable convergence

5. **Performance Evaluation**  
   - Generate predictions on the validation set  
   - Evaluate using **weighted F1-score**, precision, recall, and classification report  
   - Visualize performance metrics (optional)

6. **Test Data Prediction**  
   - Apply trained MLP to unseen test data  
   - Generate structured prediction output for submission or further analysis

---

## 🛠️ Tools & Technologies

- **Programming Language**: Python  
- **Libraries**: Pandas, NumPy, Matplotlib, scikit-learn  
- **Model**: MLPClassifier (multi-layer perceptron neural network)  
- **Evaluation Metrics**: Weighted F1-score, classification report, confusion matrix

---

## 📊 Key Insights

- MLP can effectively capture complex non-linear relationships in pixel data  
- Proper feature scaling significantly improves convergence and model stability  
- Weighted F1-score provides a balanced evaluation across all digit classes  

---

## 🎯 Conclusion

This project provides a **complete end-to-end workflow** for handwritten digit recognition:  
from raw CSV data to preprocessing, model training, evaluation, and test data prediction.  
It demonstrates the application of neural networks on tabular image data using scikit-learn and emphasizes **reproducibility, clean code structure, and robust evaluation practices**.
