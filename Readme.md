# ❤️ Heart Disease Prediction
### AI/ML Engineering Internship — Task 3 | DevelopersHub Corporation

---

## 📌 Task Objective
Build a binary classification model to predict whether a person is at risk of heart disease based on clinical health data. This project covers the full ML pipeline — from data cleaning and EDA to model training, evaluation, and feature analysis.

---

## 📂 Dataset
- **Name:** Heart Disease UCI Dataset (Cleveland)
- **Source:** Kaggle — Heart Disease UCI
- **Samples:** 920 rows
- **Original Features:** 16 columns (id, age, sex, dataset, cp, trestbps, chol, fbs, restecg, thalch, exang, oldpeak, slope, ca, thal, num)
- **Target Column:** `num` → binarized to 0 (No Disease) and 1 (Heart Disease)

---

## ⚙️ Preprocessing Steps
- Dropped irrelevant columns: `id`, `dataset`
- Binarized target: `num` values 1/2/3/4 → 1 (disease present)
- Encoded binary text columns: `sex` (Male/Female → 1/0), `fbs` and `exang` (TRUE/FALSE → 1/0)
- One-hot encoded multi-category columns: `cp`, `restecg`, `thal`, `slope`
- Filled remaining missing values with column median
- Applied `StandardScaler` for feature normalization
- Final feature count: **22 features** after encoding

---

## 🤖 Models Applied
| Model | Description |
|-------|-------------|
| Logistic Regression | Linear classification with L2 regularization |
| Decision Tree | Non-linear tree-based classifier (max_depth=5) |

---

## 📊 Key Results

| Metric | Logistic Regression | Decision Tree |
|--------|-------------------|---------------|
| Test Accuracy | **83.70%** | ~80% |
| ROC-AUC Score | **0.9032** | ~0.85 |
| CV Accuracy (5-Fold) | ~83% | ~79% |

> **Best Model: Logistic Regression** with 83.70% accuracy and 0.9032 ROC-AUC

---

## 🔍 Key Findings

1. **ROC-AUC of 0.9032** places this model in the "Excellent" range (>0.9), well above the 0.5 random baseline
2. **Top 5 predictive features:**
   - `cp_asymptomatic` — Asymptomatic chest pain is a strong silent indicator
   - `chol` — High cholesterol correlates with disease risk
   - `age` — Risk increases significantly with age
   - `oldpeak` — ST depression induced by exercise
   - `thalch` — Maximum heart rate achieved
3. Categorical encoding of chest pain type (`cp`) significantly improved model performance
4. Logistic Regression outperformed Decision Tree — suggesting the decision boundary is relatively linear in this feature space

---

## 📈 Visualizations Generated
- Target class distribution (bar + pie chart)
- Age distribution by disease status
- Box plots: numerical features vs target
- Sex vs heart disease rate
- Full correlation heatmap
- Feature-target correlation ranking
- Confusion matrices (both models)
- ROC curves comparison
- Decision Tree feature importance
- Logistic Regression coefficients
- Model performance comparison chart

---

## 🛠️ Tech Stack
- **Language:** Python 3.10
- **Libraries:** pandas, numpy, matplotlib, seaborn, scikit-learn
- **Environment:** VS Code + Jupyter Notebook

---

## 🚀 How to Run
```bash
# 1. Clone the repository
git clone https://github.com/Dev-ZishanKhan/heart-disease-prediction.git

# 2. Navigate into the folder
cd heart-disease-prediction

# 3. Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

# 4. Launch the notebook
jupyter notebook heart_disease_prediction.ipynb
```

---

## 📁 Repository Structure
```
heart-disease-prediction/
│
├── heart_disease_prediction.ipynb   # Main Jupyter notebook
├── heart.csv                        # Dataset
├── README.md                        # Project documentation
└── images/                          # Generated plot outputs
    ├── 01_target_distribution.png
    ├── 02_age_distribution.png
    ├── 03_boxplots_vs_target.png
    ├── 04_sex_vs_disease.png
    ├── 05_correlation_heatmap.png
    ├── 06_feature_target_correlation.png
    ├── 07_confusion_matrices.png
    ├── 08_roc_curves.png
    ├── 09_feature_importance.png
    ├── 10_lr_coefficients.png
    └── 11_model_comparison.png
```

---

*DevelopersHub Corporation — AI/ML Engineering Internship 2026*