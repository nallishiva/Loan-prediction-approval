# 🏦 Loan Approval Prediction

> A Machine Learning classification project to predict whether a loan application will be approved or rejected.  
> Built as part of **INT-254 (Machine Learning)** at Lovely Professional University — November 2022.

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?logo=scikit-learn)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![Best Accuracy](https://img.shields.io/badge/Best%20Accuracy-82.5%25-brightgreen)

---

## 📌 Problem Statement

A housing finance company wants to automate their loan eligibility process in real-time. Based on customer details submitted during the online application — Gender, Marital Status, Education, Income, Loan Amount, Credit History, and others — the model predicts whether a loan should be **approved (Y)** or **rejected (N)**.

This is a **Binary Classification** problem.

---

## 📊 Dataset — `LoanApprovalPrediction.csv`

| Feature | Description |
|---|---|
| Gender | Male / Female |
| Married | Applicant married (Y/N) |
| Dependents | Number of dependents |
| Education | Graduate / Under Graduate |
| Self_Employed | Self employed (Y/N) |
| ApplicantIncome | Applicant income |
| CoapplicantIncome | Co-applicant income |
| LoanAmount | Loan amount (in thousands) |
| Loan_Amount_Term | Term of loan (in months) |
| Credit_History | Credit history meets guidelines |
| Property_Area | Urban / Semi-Urban / Rural |
| **Loan_Status** | **Target — Loan approved (Y/N)** |

- **Total features:** 12 (after dropping Loan_ID)
- **Categorical variables:** 7
- **Train/Test split:** 60:40 (random_state=1)

---

## ⚙️ Project Workflow

```
1. Load Data              →  Read LoanApprovalPrediction.csv using Pandas
2. Explore Data           →  Check categorical variables, visualise distributions
3. Label Encoding         →  Encode all 7 categorical columns using LabelEncoder
4. Handle Missing Values  →  Fill nulls with column mean
5. Visualisation          →  Correlation heatmap (Seaborn) + bar plots
6. Train/Test Split       →  60:40 split using train_test_split
7. Model Training         →  Train 4 ML models on training set
8. Model Evaluation       →  Compare accuracy on test set
```

---

## 🤖 Model Results

### Training Accuracy
| Model | Training Accuracy |
|---|---|
| 🏆 Random Forest Classifier | **98.04%** |
| Logistic Regression | 80.16% |
| KNN (k=3) | 78.49% |
| SVC | 68.71% |

### Test Accuracy
| Model | Test Accuracy |
|---|---|
| 🏆 Random Forest Classifier | **82.5%** |
| Logistic Regression | 80.83% |
| SVC | 69.16% |
| KNN (k=3) | 63.75% |

**Best Model: Random Forest Classifier**
- `n_estimators = 7`
- `criterion = 'entropy'`
- `random_state = 7`

---

## 🛠️ Tech Stack

| Tool | Usage |
|---|---|
| Python | Core language |
| Pandas | Data loading & manipulation |
| NumPy | Numerical operations |
| Matplotlib & Seaborn | Data visualisation |
| Scikit-learn | Label encoding, model training, evaluation |
| Jupyter Notebook (Anaconda) | Development environment |

---

## 📁 Project Structure

```
Loan-prediction-approval/
│
├── Loan_approval_Prediction.ipynb   # Main Jupyter Notebook
├── LoanApprovalPrediction.csv       # Dataset
└── README.md                        # Project documentation
```

---

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/nallishiva/Loan-prediction-approval.git

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn

# 3. Open the notebook
jupyter notebook Loan_approval_Prediction.ipynb
```

---

## 👤 Author

**Nalli Shiva** — B.Tech CSE, Lovely Professional University (2024)  
[LinkedIn](https://www.linkedin.com/in/nallishiva) · [GitHub](https://github.com/nallishiva)

---
*Built with ❤️ at LPU as part of the B.Tech CSE — Machine Learning curriculum*
