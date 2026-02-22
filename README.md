

---

# 🩺 Intelligent Classification of Fetal Health Conditions Using CTG Features

> Machine Learning based multi-class classification of fetal health conditions using Cardiotocography (CTG) features with K-Fold Cross-Validation and a Novel Adaptive Confidence-Aware XGBoost objective.

---

## 📌 Overview

This repository contains the complete implementation of our research paper:

**"Intelligent Classification of Fetal Health Conditions Using CTG Features"**

The study focuses on automatic classification of fetal health status into:

* 🟢 Normal
* 🟡 Suspect
* 🔴 Pathological

using supervised machine learning algorithms and a proposed modified XGBoost model with a **Custom Adaptive Confidence-Aware Objective Function**.

---

## 📊 Dataset

Dataset used from Kaggle:

🔗 [https://www.kaggle.com/datasets/andrewmvd/fetal-health-classification](https://www.kaggle.com/datasets/andrewmvd/fetal-health-classification)

* Total Samples: 2126
* Features: 21 CTG-based features
* Classes: 3 (Normal, Suspect, Pathological)

---

## ⚙️ Methodology

### 🔹 1. Data Preprocessing

* Duplicate removal
* Correlation analysis
* Feature selection (removal of highly correlated histogram features)
* Label encoding (for XGBoost compatibility)
* Z-score normalization
* Stratified train-test split (80:20)
* SMOTE oversampling for class imbalance handling

---

### 🔹 2. Machine Learning Models Implemented

* Decision Tree
* Random Forest
* Gradient Boosting
* K-Nearest Neighbors
* Standard XGBoost
* ✅ **Proposed Modified XGBoost (Novel Contribution)**

---

### 🔹 3. Novel Contribution

We introduced a:

## 🔥 Adaptive Confidence-Aware Objective Function

Instead of using standard `multi:softprob`, we designed a custom gradient & Hessian update rule:

* Penalizes uncertain predictions
* Dynamically scales gradients based on prediction confidence
* Improves robustness in multi-class classification

Implemented using:

```python
xgb_model.set_params(objective=adaptive_confidence_objective)
```

This introduces methodological novelty in boosting-based fetal health classification.

---

### 🔹 4. Validation Strategy

* 5-Fold Stratified Cross-Validation
* Metrics:

  * Accuracy
  * Precision
  * Recall
  * F1-Score
  * ROC-AUC (OvR)

---

## 📈 Generated Outputs

The pipeline automatically generates:

* Class Distribution Plot
* Correlation Heatmap
* SMOTE Visualization
* Cross-Validation Boxplot
* Accuracy Across Folds Plot
* ROC Curves (Multi-class + Micro Average)
* Confusion Matrix
* F1-Score Visualization
* Feature Importance Plot
* Performance Summary Table
* Saved Trained Model (`xgboost_model.pkl`)

---

## 🧠 Model Performance (Summary)

| Metric    | Cross-Validation | Test Set |
| --------- | ---------------- | -------- |
| Accuracy  | ~99%             | ~99%     |
| Precision | High             | High     |
| Recall    | High             | High     |
| F1-Score  | High             | High     |
| ROC-AUC   | ~0.99+           | ~0.99+   |

(Exact values will depend on random seed and environment.)

---



---

## 🛠️ Installation

```bash
pip install numpy pandas matplotlib seaborn scikit-learn xgboost imbalanced-learn joblib
```

---

## ▶️ How to Run

1. Download dataset from Kaggle.
2. Update dataset path in script:

```python
df = pd.read_csv('path_to_fetal_health.csv')
```

3. Run:

```bash
python fetal_health_classification.py
```

---

## 🔬 Research Highlights

* Robust preprocessing pipeline
* SMOTE for imbalance correction
* Stratified K-Fold validation
* Custom boosting objective (novel gradient update)
* Comprehensive evaluation with visualizations
* High reproducibility (random seed fixed)

---

## 📜 Citation

If you use this work, please cite our paper:

```
Intelligent Classification of Fetal Health Conditions Using CTG Features
```

(Full citation details to be added after publication.)


বললেই আমি তোমার repo টাকে publication-level করে সাজিয়ে দেব।
