
# 🏷️ Project Title
**Optimizing Neural Networks for Predicting Premium Sports Product Sales**

## 📌 Problem Statement
Premium sporting goods companies lose 15–25% in turnover due to inaccurate sales forecasting. This project aims to develop a machine learning model to classify whether a product will have high sales performance based on features such as price, discount, and marketing spend.

## 📊 Dataset Overview

- **Type**: Synthetic dataset generated using NumPy
- **Size**: 2,000 records
- **Features**:
  - `price` – Range: 100–1000
  - `discount` – Range: 0–50%
  - `marketing_spend` – Range: 0–10,000
  - `high_sales` – Binary target variable (0 = low, 1 = high)

The dataset was split into:
- **Training Set**: ~70%
- **Validation Set**: ~15%
- **Test Set**: ~15%

---

## 🧠 Model Implementations

### 1. Baseline Neural Network (No Optimization)
- Single hidden layer (8 ReLU units)
- Output layer with sigmoid activation
- No early stopping, regularization, or learning rate tuning

### 2. Optimized Neural Network Models
Implemented with 3–4 different combinations of:
- Optimizers (Adam, RMSprop)
- Regularization (L1, L2,L1_L2)
- Dropout layers
- EarlyStopping and LearningRateScheduler
- Epoch and layer adjustments


### 3. Classical ML Models

- Logistic Regression
- SVM
- XGBoost
(All tuned with `GridSearchCV` or direct hyperparameter setting)

---

## 📋 Optimization Results Summary

| Instance | Optimizer | Reg. | Epochs | Early Stop | Layers | LR | Accuracy | F1 | Precision | Recall |
|----------|-----------|------|--------|------------|--------|----|----------|----|-----------|--------|
| 1        | Default   | None | 30     | No         | 1      | Default | 0.82 | 0.80 | 0.81 | 0.79 |
| 2        | Adam      | L2   | 50     | Yes        | 2      | 0.001 | 0.87 | 0.86 | 0.88 | 0.84 |
| 3        | RMSprop   | L1   | 60     | Yes        | 3      | 0.0005 | 0.89 | 0.88 | 0.87 | 0.89 |
| 4        | Adam      | L1_L2| 70     | Yes        | 2      | 0.0001 | 0.90 | 0.89 | 0.90 | 0.88 |

---


## ✅ Best Performing Model

- **Neural Network with Adam optimizer, L1_L2 regularization, dropout, and early stopping**
- Outperformed all classical models in both accuracy and F1 score

---

## 🤖 ML Algorithm Comparison

| Model              | Tuned Params               | Accuracy | F1 Score |
|-------------------|----------------------------|----------|----------|
| Logistic Regression | C=1.0, penalty='l2'        | 0.81     | 0.80     |
| SVM               | kernel='rbf', C=10          | 0.84     | 0.83     |
| XGBoost           | max_depth=3, lr=0.1         | 0.88     | 0.87     |
| **Best NN Model** | Adam, L1_L2, dropout, early stop | **0.90** | **0.89** |

---

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

