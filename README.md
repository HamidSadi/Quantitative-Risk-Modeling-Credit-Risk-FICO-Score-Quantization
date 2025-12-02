# 🧮 Task 3 — Credit Risk Modeling & Expected Loss Prediction  
### JPMorgan Chase Quantitative Research Virtual Experience Program  

---

This repository contains my solution to **Task 3**, focused on building a predictive model to estimate **Probability of Default (PD)** and compute **Expected Loss (EL)** for retail borrowers using real-world credit risk modeling techniques.

---

# 🎯 Objective

The goal is to build a machine learning model that:

1. Predicts the **Probability of Default (PD)** for a borrower  
2. Calculates the **Expected Loss (EL)** using:
   
\[
EL = PD \times LGD \times EAD
\]

Where:

- **LGD** = 90% (assuming 10% recovery)
- **EAD** = loan amount

This allows the risk team to properly estimate loss allowances and capital requirements.

---

# 📊 Dataset

The dataset includes borrower details such as:

- Income  
- FICO score  
- Total outstanding loans  
- Loan-to-income ratio  
- Previous defaults  
- Loan amount  
- Other numerical indicators  

---

# 🤖 Models Implemented

A full comparative analysis was performed:

### ✔ Logistic Regression  
### ✔ Random Forest Classifier  
### ✔ Gradient Boosting Classifier  
### ✔ XGBoost Classifier (optional if installed)

These models were evaluated using:

- ROC Curves  
- AUC Score  
- Confusion Matrix  
- PD Calibration Plots  
- Feature Importance  

---

# 📈 Visual Analysis

The notebook also includes:

- Correlation heatmap  
- Borrower distribution visualizations  
- PD distribution  
- Feature pair plots  
- Model comparison charts  

---


---

# 📄 **TASK 4 README **

```markdown
# 🏦 Task 4 — FICO Score Quantization & Risk Bucketing  
### JPMorgan Chase Quantitative Research Virtual Experience Program  

---

This repository contains my solution to **Task 4**, focused on converting continuous **FICO credit scores** into **risk buckets** for downstream machine learning models in retail credit risk.

---

# 🎯 Objective

Machine learning models often require categorical labels rather than continuous credit scores. Therefore, this task aims to:

- Derive optimal **bucket boundaries** for FICO scores  
- Maintain **monotonicity** with respect to default risk  
- Minimize predictive error or maximize likelihood  
- Provide a reusable bucket mapping method  

---

# 🔍 Methods Implemented

## 1️⃣ **K-Means Quantization (Primary Method)**  
A practical and efficient approach used in real-world scorecard modeling.

### ✔ Minimizes Mean Squared Error (MSE)  
### ✔ AIC/BIC used to determine optimal number of buckets  
### ✔ Automatically extracts bucket boundaries  
### ✔ Produces interpretable risk categories  

### Visuals Included:
- FICO histogram  
- Smoothed PD vs. FICO  
- MSE / AIC / BIC charts  
- Bucket boundary overlay  

---

## 2️⃣ **Dynamic Programming Log-Likelihood Method — Theory Only**

DP produces the *optimal* bucket boundaries by maximizing:

\[
LL = \sum_{i=1}^{B} [ k_i \ln(p_i) + (n_i - k_i)\ln(1 - p_i) ]
\]

However:

- Complexity is **O(N²–N³)**
- Not feasible for large datasets
- Not required for the final result  

The notebook includes:

### ✔ Full derivation  
### ✔ Explanation of computational limits  
### ✔ Optimized pseudocode  
### ✔ A tiny DP demo on a small sample (20 rows)  

---

# 📦 Final Deliverables

### ✔ K-Means Boundary Extraction  
### ✔ Bucket Mapping Function  
### ✔ PD distribution per bucket  
### ✔ Comparison of quantization methods  
### ✔ Complete documentation  

---

# 🚀 How to Run

Install dependencies:

```bash
pip install numpy pandas scikit-learn seaborn matplotlib
