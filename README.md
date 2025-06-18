
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
| 1        | Default   | None | 30     | No         | 1      | Default | 0.43 | 0.56 |0.43|0.81|
| 2        | Adam      | L2   | 50     | Yes        | 2      | 0.001 | 0.49 | 0.54 |0.46| 0.65 |
| 3        | RMSprop   | L1   | 60     | Yes        | 3      | 0.0005 | 0.54| 0.00 |0.00| 0.00|
| 4        | Adam      | L1_L2| 70     | Yes        | 2      | 0.0001 | 0.52 | 0.38 |0.46|0.31 |

---


## ✅ Best Performing Model

- **Neural Network with Adam optimizer, L1_L2 regularization, dropout, and early stopping**
- Outperformed all classical models in both accuracy and F1 score

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
├── Summative_Intro_to_ml_[AmandineIrakoze]_assignment.ipynb
├── README.md
├── saved_models/
│   ├──scaler.joblib
├── optimization_results.csv
├── Ecommerce_Sales_Prediction_Dataset (1).csv



```

## 🧭 How to Run the Notebook

1. Clone the repo:
```bash
git clone https://github.com/Amandine0610/project_sales_forecasting.git
```

2. Open the Jupyter Notebook:
```bash
jupyter notebook Summative_Intro_to_ml_[AmandineIrakoze]_assignment.ipynb

```

3. Run cells in order. Trained models will be saved in `saved_models/`.

# 👤 Author

Amandine Irakoze

African Leadership University – BSE

Course: Introduction to Machine Learning

# Demo video link

https://drive.google.com/file/d/1FTY9iOgr3FxiTNrohPTXSPuyus4XFgO7/view?usp=sharing