# FYP-25-26
# Multivariate Regression Model for Steel Property Prediction

This repository contains the implementation of a machine learning framework for the prediction of key mechanical properties of scrap-derived steel, namely:

- Yield Strength (YS)
- Ultimate Tensile Strength (UTS)
- Elongation at Fracture (EL%)

The project leverages industrial-scale data to model the relationship between **chemical composition, processing parameters, and mechanical performance**, with a focus on improving predictability in scrap-based steel production.

---

## 📌 Project Overview

Scrap-based steel production introduces significant variability in chemical composition, making it challenging to consistently achieve target mechanical properties. This project applies machine learning techniques to:

- Predict **YS, UTS, and EL% simultaneously** (multi-output regression)
- Capture **non-linear composition–property relationships**
- Provide **interpretable insights** using SHAP (Shapley Additive Explanations)

The dataset used is based on the work of **Guo et al. (2019)**, comprising over **63,000 industrial steel samples**.

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Removed missing values (~2,000 samples)
- Final dataset: ~63,000 samples
- 26 input features:
  - Chemical composition (e.g. Ceq, Pcm, Nb, Ti, etc.)
  - Processing parameters (e.g. Furnace Temp, Annealing Temp)
- Train-test split: **80/20**
- Feature scaling applied to SVR, ANN, and linear models

---

### 2. Models Implemented

The following regression models were trained and evaluated:

- XGBoost (best performing)
- Random Forest
- Support Vector Regressor (SVR)
- Artificial Neural Network (ANN)
- K-Nearest Neighbours (KNN)
- Ridge Regression
- Regressor Chain (multi-output)

---

### 3. Hyperparameter Tuning

- Performed using **RandomizedSearchCV**
- 5-fold cross-validation
- Optimised for **RMSE and R² performance**

---

### 4. Model Explainability (SHAP)

SHAP (Shapley Additive Explanations) was applied to:

- XGBoost (TreeExplainer)
- Random Forest (TreeExplainer)
- SVR (PermutationExplainer)

This enables:
- Feature importance ranking
- Interpretation of model predictions
- Validation against metallurgical theory

---

## 📊 Key Results

| Model        | Avg R² |
|-------------|--------|
| XGBoost     | ~0.912 |
| Random Forest | ~0.908 |
| SVR / ANN   | ~0.899 |
| Ridge       | ~0.849 |

### Key Findings:
- **Ceq (Carbon Equivalent)** is the dominant predictor for strength
- **Nb and Ti** significantly influence both strength and ductility
- Clear **strength–ductility trade-off captured by SHAP**
- **UTS > YS > EL%** in prediction accuracy

---

## 🧠 Insights

- Strength properties (YS, UTS) are strongly composition-driven
- Ductility (EL%) is less predictable due to missing microstructural features
- Machine learning can act as a **decision-support tool for scrap blending**

---

## 📁 Repository Structure


---

## 🛠️ Tech Stack

- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- SHAP
- Matplotlib / Seaborn

---

## 🚀 Applications

- Scrap steel composition optimisation
- Predictive quality control in steel manufacturing
- Decision-support systems for material design

---

## 📚 Reference

Guo, S. et al. (2019).  
*A predicting model for properties of steel using industrial big data.*

---

## 👤 Author

Abdul Qayyum Zaki  
Nanyang Technological University (NTU)  
Materials Science & Engineering

---

## ⚠️ Disclaimer

This project was developed for academic purposes.  
All modelling, results, and analysis were independently conducted by the author.
