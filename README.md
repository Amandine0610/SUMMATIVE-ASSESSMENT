
# 🏷️ Project Title
**Optimizing Neural Networks for Predicting Premium Sports Product Sales**

## 📌 Problem Statement
Premium sporting goods companies lose 15–25% in turnover due to inaccurate sales forecasting. This project aims to develop a machine learning model to classify whether a product will have high sales performance based on features such as price, discount, and marketing spend.

## 📊 Dataset Overview

- **Type**: Real-word dataset
- **Size**: 365 records (1 year of sales data)
- **Source**: Actual e-commerce transactions
- **Features**:
  - `date`-Sales transaction 

  - `product_category`-Categories include Sports, Toys, Home Decor, Fashion, Electronics

  - `price` – Ranges from $14.59 (lowest) to $996.91 (highest)

  - `discount` – Percentage discount, spanning 0% to 49.92%

  - `marketing_spend` –Investment in marketing per product, varying from $106.47 to $9972.66

  - `units_sold` - Sales volume, ranging from 5 to 57 units per product



The dataset was split into:
- **Training Set**: ~70% (256 records)
- **Validation Set**: ~15%(54 records)
- **Test Set**: ~15%(55 records)

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


### 3. Classical ML Results Summary:

| Model | Accuracy | F1 Score | Recall | Precision | ROC AUC | 
| Logistic Regression | 0.5067 | 0.5316 | 0.6087 | 0.4719 | 0.5182 | 
| XGBoost | 0.5267 | 0.4892 | 0.4928 | 0.4857 | 0.5804 | 

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

- Neural Network (Adam + L2 Regularization, Early Stopping) provided competitive results compared to classical ML models but did not strongly outperform Logistic Regression across all evaluation metrics.
- If recall (correctly identifying high-sales products) is the key priority, then Logistic Regression is the better-performing model.
- If robustness across multiple metrics is preferred, Adam + L2 Regularization with early stopping remains the best NN model.


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