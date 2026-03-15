# Loan-prediction-approval
# 🏦 Loan Approval Prediction

> A Machine Learning classification project to predict whether a loan application will be approved or rejected — built as an End Term Project for **INT-254 (Machine Learning)** at Lovely Professional University.

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python) ![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?logo=scikit-learn) ![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter) ![Accuracy](https://img.shields.io/badge/Accuracy-83.24%25-brightgreen)

---

## 📌 Problem Statement

**Dream Housing Finance** company wants to automate their loan eligibility process in real-time. Based on customer details submitted during the online application — such as income, credit history, loan amount, and property area — the model predicts whether the loan should be **approved (Y)** or **rejected (N)**.

This is a **Binary Classification** problem.

---

## 📊 Dataset

| Feature | Description |
|---|---|
| Gender | Male / Female |
| Married | Applicant married (Y/N) |
| Dependents | Number of dependents (0, 1, 2, 3+) |
| Education | Graduate / Under Graduate |
| Self_Employed | Self employed (Y/N) |
| ApplicantIncome | Applicant income |
| CoapplicantIncome | Co-applicant income |
| LoanAmount | Loan amount (in thousands) |
| Loan_Amount_Term | Term of loan (in months) |
| Credit_History | Credit history meets guidelines (Y/N) |
| Property_Area | Urban / Semi-Urban / Rural |
| **Loan_Status** | **Target — Loan approved (Y/N)** |

- **Training set:** 614 rows × 13 columns
- **Test set:** 367 rows × 12 columns

---

## ⚙️ Project Workflow

```
1. Data Loading          →  Load train/test CSV files
2. Data Preprocessing    →  Handle missing values (Mode + Iterative Imputer)
3. Feature Encoding      →  Map categorical variables to integers
4. EDA                   →  Univariate & Bivariate analysis (Seaborn/Matplotlib)
5. Feature Engineering   →  Create 8 new features (EMI, TotalIncome, bins, etc.)
6. Model Building        →  Train multiple ML models
7. Hyperparameter Tuning →  GridSearchCV on best model
8. Prediction            →  Predict on test data & prepare submission
```

---

## 🔧 Feature Engineering

Created **8 new features** to improve model performance:

- `TotalIncome` = ApplicantIncome + CoapplicantIncome
- `EMI` = Monthly loan installment (calculated at 10% interest rate)
- `LoanAmount_per_TotalIncome` = Loan burden ratio
- `Loan_Amount_Term_per_TotalIncome` = Term-to-income ratio
- `EMI_per_Loan_Amount_Term` = EMI efficiency
- `EMI_per_LoanAmount` = EMI-to-loan ratio
- `Credit_History_Income_Sum` = Credit history grouped income sum
- `Dependents_LoanAmount_Sum` = Dependents grouped loan sum
- Bin features using `KBinsDiscretizer` (quantile strategy)

---

## 🤖 Models Compared

| Model | Accuracy |
|---|---|
| Decision Tree | Lower |
| SVC | Lower |
| XGBoost Regressor | Lower |
| Random Forest | Lower |
| **Logistic Regression** | **82.7%** ✅ |
| **Logistic Regression + GridSearchCV** | **83.24%** 🏆 |

**Best Model:** Logistic Regression with hyperparameter tuning via GridSearchCV

**Best Parameters:**
```python
{'C': 0.001, 'max_iter': 100, 'penalty': 'l1', 'solver': 'liblinear'}
```

**Train/Test Split:** 70:30

---

## 📈 Results

| Metric | Score |
|---|---|
| Validation Accuracy | **83.24%** |
| Cross-validation (cv=3) | ~80% avg |
| Final Test Submission | **78%** |

> Feature engineering significantly contributed to improved accuracy.

---

## 🛠️ Tech Stack

- **Language:** Python 3.x
- **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn
- **Models:** Logistic Regression, Random Forest, Decision Tree, SVC, XGBoost
- **Tools:** Jupyter Notebook, Google Colab, GridSearchCV, KBinsDiscretizer, IterativeImputer

---

## 📁 Project Structure

```
Loan-prediction-approval/
│
├── loan_prediction.ipynb     # Main Jupyter Notebook
├── train.csv                 # Training dataset
├── test.csv                  # Test dataset
├── final38.csv               # Final submission predictions
└── README.md                 # Project documentation
```

---

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/nallishiva/Loan-prediction-approval.git

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn xgboost

# 3. Open the notebook
jupyter notebook loan_prediction.ipynb
```

---

## 👥 Team

| Name | Roll No | Contribution |
|---|---|---|
| **Nalli Shiva** | RKM098A19 | Project code, Dataset, Implementation |
| Gatadi Varshith | RKM098A21 | Project code, Dataset research, Report |

**Supervisor:** Dr. Dhanpratap Singh
**Course:** INT-254 — Machine Learning
**University:** Lovely Professional University, Jalandhar
**Submitted:** November 2022

---

## 📬 Connect

**Nalli Shiva** — [LinkedIn](https://www.linkedin.com/in/nallishiva) | [GitHub](https://github.com/nallishiva)

---
*Built with ❤️ at LPU as part of the B.Tech CSE — Machine Learning curriculum*
