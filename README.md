# 🧬 Breast Cancer Prediction System

![Python](https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge&logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.0+-orange?style=for-the-badge&logo=scikit-learn)
![XGBoost](https://img.shields.io/badge/XGBoost-latest-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-green?style=for-the-badge)

A machine learning system that predicts whether a breast tumor is **Malignant (Cancerous)** or **Benign (Non-cancerous)** using the Wisconsin Breast Cancer Dataset. Multiple ML algorithms were trained, compared, and combined using ensemble methods for maximum accuracy.

---

## 📌 Table of Contents
- [About the Project](#about-the-project)
- [Dataset](#dataset)
- [Models Used](#models-used)
- [Project Workflow](#project-workflow)
- [Results](#results)
- [How to Run](#how-to-run)
- [Project Structure](#project-structure)
- [Tech Stack](#tech-stack)

---

## 🔍 About the Project

Cancer diagnosis is one of the most critical medical decisions. This project uses machine learning to assist in classifying tumors as **Malignant (M)** or **Benign (B)** based on cell nucleus measurements extracted from digitized images of fine needle aspirates (FNA).

Key highlights:
- **7 ML models** trained and compared
- **SMOTE** used to handle class imbalance
- **GridSearchCV** for hyperparameter tuning
- **Voting + Stacking Classifiers** for ensemble predictions
- Full pipeline saved with **Pickle** for deployment

---

## 📊 Dataset

**Wisconsin Breast Cancer Dataset** (`data.csv`)

| Feature | Details |
|---|---|
| Source | UCI Machine Learning Repository |
| Samples | 569 |
| Features | 30 numeric features |
| Target | Diagnosis — M (Malignant) / B (Benign) |
| Class Split | ~37% Malignant, ~63% Benign |

Features include measurements like:
- `radius_mean`, `texture_mean`, `perimeter_mean`
- `area_mean`, `smoothness_mean`, `compactness_mean`
- `concavity_mean`, `concave points_mean`, etc.

---

## 🤖 Models Used

| Model | Description |
|---|---|
| Logistic Regression | Baseline linear classifier |
| K-Nearest Neighbors | Distance-based classifier |
| Naive Bayes | Probabilistic classifier |
| Support Vector Machine | Margin-based classifier with RBF kernel |
| Random Forest | Ensemble of decision trees |
| XGBoost | Gradient boosting |
| LightGBM | Fast gradient boosting |
| **Voting Classifier** | Combines top 3 models (soft voting) |
| **Stacking Classifier** | Top 3 models + Logistic Regression as meta-learner |

---

## 🔄 Project Workflow

```
1. Data Loading & Exploration
        ↓
2. Data Cleaning
   - Removed unnecessary columns (id, Unnamed: 32)
   - Label Encoding (M=1, B=0)
        ↓
3. Exploratory Data Analysis
   - Correlation Heatmap
   - Class Distribution (Bar + Pie)
   - Feature Boxplots
        ↓
4. Preprocessing
   - StandardScaler (feature normalization)
   - Train-Test Split (80/20, stratified)
   - SMOTE (class imbalance handling)
        ↓
5. Model Training
   - 7 individual models with GridSearchCV
   - Cross-validation (5-fold)
        ↓
6. Ensemble Methods
   - Voting Classifier (top 3 models)
   - Stacking Classifier
        ↓
7. Evaluation
   - Accuracy, Precision, Recall, F1-Score, ROC-AUC
        ↓
8. Model Saving (Pickle)
```

---

## 📈 Results

Evaluation metrics tracked for all models:

| Metric | Description |
|---|---|
| **Accuracy** | Overall correct predictions |
| **Precision** | Of predicted malignant, how many were actually malignant |
| **Recall** | Of actual malignant cases, how many were caught |
| **F1-Score** | Balance between Precision and Recall |
| **ROC-AUC** | Area under the ROC curve |

> ⚠️ In medical diagnosis, **Recall is prioritized** over Accuracy — missing a malignant tumor (false negative) is far more dangerous than a false alarm.

---

## 🚀 How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/YOUR_USERNAME/cancer-prediction.git
cd cancer-prediction
```

### 2. Install Dependencies
```bash
pip install numpy pandas scikit-learn xgboost lightgbm imbalanced-learn matplotlib seaborn
```

### 3. Run Training Notebook
```bash
jupyter notebook PRJ_Cancer_Prediction_Training.ipynb
```

### 4. Run Testing / Prediction
```bash
jupyter notebook PRJ_Cancer_Prediction_Testing.ipynb
```

---

## 📁 Project Structure

```
cancer-prediction/
│
├── data.csv                              # Dataset
├── PRJ_Cancer_Prediction_Training.ipynb  # Training notebook
├── PRJ_Cancer_Prediction_Testing.ipynb   # Testing & prediction notebook
│
├── models/
│   ├── best_model_*.pkl                  # Best individual model
│   ├── voting_classifier.pkl             # Voting ensemble model
│   ├── stacking_classifier.pkl           # Stacking ensemble model
│   ├── scaler.pkl                        # StandardScaler
│   ├── label_encoder.pkl                 # Label Encoder
│   └── feature_names.pkl                 # Feature names list
│
└── README.md
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python | Core programming language |
| Pandas / NumPy | Data manipulation |
| Scikit-learn | ML models, preprocessing, evaluation |
| XGBoost / LightGBM | Advanced gradient boosting |
| imbalanced-learn | SMOTE for class imbalance |
| Matplotlib / Seaborn | Data visualization |
| Pickle | Model serialization |
| Jupyter Notebook | Development environment |

---

## 👤 Author

**Momin Saad Asrar**  
B.E. CSE (AI-ML) — Anjuman-I-Islam's Kalsekar Technical Campus  
📧 saadizhan123@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/saad-momin-9a88542bb)

---

> ⭐ If you found this project helpful, please give it a star!
