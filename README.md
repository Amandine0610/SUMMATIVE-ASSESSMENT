
# 🏷️ Project Title
**Optimizing Neural Networks for Predicting Premium Sports Product Sales**

## 📌 Problem Statement
Premium sporting goods companies lose 15–25% in turnover due to inaccurate sales forecasting. This project aims to develop a machine learning model to classify whether a product will have high sales performance based on features such as price, discount, and marketing spend.

## 📊 Dataset Overview
A synthetic dataset was generated with the following features:
- `price`: Product price (range: 100–1000)
- `discount`: Discount percentage (range: 0–50%)
- `marketing_spend`: Budget allocated for marketing (range: 0–10,000)
- `high_sales`: Target binary variable (1 = high sales, 0 = low sales)

The dataset contains 2000 samples and was split into training, validation, and test sets using stratified sampling.

## 🧠 Model Implementations

### 1. Baseline Neural Network (No Optimization)
- One hidden layer with 8 ReLU units
- Sigmoid output
- No dropout, no early stopping, no learning rate adjustments

### 2. Optimized Neural Network Models
Several models were trained using different combinations of:
- Optimizers: Adam, RMSprop
- Regularization: L1, L2
- Dropout
- Early stopping
- Learning rate tuning

### 3. Classical ML Models
- Logistic Regression (with hyperparameter tuning)
- SVM
- XGBoost

## 📋 Optimization Results Summary

| Instance | Optimizer | Reg. | Epochs | Early Stopping | Layers | LR | Accuracy | F1 Score | Recall | Precision |
|----------|-----------|------|--------|----------------|--------|----|----------|----------|--------|-----------|
| 1 (Base) | Default   | None | 30     | No             | 1      | Default | 0.82 | 0.81 | 0.84 | 0.78 |
| 2        | Adam      | L2   | 50     | Yes            | 2      | 0.001 | 0.86 | 0.85 | 0.88 | 0.83 |
| 3        | RMSprop   | L1   | 60     | Yes            | 3      | 0.0005 | 0.88 | 0.87 | 0.89 | 0.85 |
| 4        | Adam      | L1_L2| 70     | Yes            | 2      | 0.0001 | 0.89 | 0.88 | 0.91 | 0.86 |

> 📌 *Note: The table above summarizes training performance from different combinations of optimization techniques.*

## ✅ Best Performing Model
- Optimized Neural Network with Adam optimizer + L1_L2 regularization + early stopping
- Highest accuracy and F1-score
- Outperformed all classical ML models on validation/test sets

## 🤖 ML Algorithm Comparison

| Model              | Tuned Hyperparameters        | Accuracy | F1 Score |
|-------------------|------------------------------|----------|----------|
| Logistic Regression | C=1.0, penalty='l2'          | 0.81     | 0.80     |
| SVM               | kernel='rbf', C=10            | 0.83     | 0.82     |
| XGBoost           | max_depth=3, learning_rate=0.1| 0.86     | 0.85     |
| Optimized NN      | Adam, dropout, reg., early stop| **0.89** | **0.88** |

## 📈 Visualizations & Error Analysis
- Confusion Matrix
- ROC Curve & AUC
- Precision-Recall Curve
- Loss & Accuracy curves

## 🧪 Prediction
The final saved model was loaded and used to make predictions on unseen test data.

## 📦 Project Structure

```
project_sales_forecasting/
├── notebook.ipynb
├── README.md
├── saved_models/
│   ├── base_model.h5
│   ├── model_adam_l2.h5
│   ├── model_rmsprop_l1.h5
│   ├── model_adam_l1l2_dropout.h5
│   └── logistic_regression_model.pkl
```

## 🧭 How to Run the Notebook

1. Clone the repo:
```bash
git clone https://github.com/yourusername/project_sales_forecasting.git
```

2. Open the Jupyter Notebook:
```bash
jupyter notebook notebook.ipynb
```

3. Run cells in order. Trained models will be saved in `saved_models/`.

