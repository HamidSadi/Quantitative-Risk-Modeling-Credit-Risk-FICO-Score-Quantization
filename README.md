📘 Quantitative Risk Modeling — Credit Risk & FICO Score QuantizationJPMC Quantitative Research Virtual Experience ProgramThis repository contains my completed solutions for Task 3 and Task 4 of the JPMorgan Chase Quantitative Research Virtual Experience Program, focused on credit risk modeling, probability of default (PD) estimation, and FICO credit score quantization techniques used in retail banking and risk analytics.📌 OverviewThe project consists of two major components:🔹 Task 3 — Credit Risk Analysis & PD Modeling🎯 Objective:Build a predictive model that estimates the Probability of Default (PD) for each borrower based on their financial characteristics.📊 Features used:IncomeTotal loans outstandingFICO scoreLoan-to-income ratioPast default historyOther customer-level features🤖 Models Implemented:Logistic RegressionRandom Forest ClassifierGradient Boosting ClassifierXGBoost (if available)📈 Analysis Performed:Feature distributionsCorrelation heatmapsROC & AUC comparisonPD calibrationError analysisExpected Loss computation:$$EL = PD \times LGD \times EAD$$LGD (Loss Given Default): 90% (10% recovery rate)EAD (Exposure At Default): Loan amount✅ Output:A clean function to predict loss:def predict_expected_loss(borrower_features):
    """
    Returns the expected monetary loss for a given borrower.
    Formula: PD * LGD * EAD
    """
    return expected_loss
🔹 Task 4 — Optimal FICO Score Quantization🎯 Objective:FICO scores must be converted into categorical risk buckets for modeling architectures that require discrete labels.☑ Methods Implemented:1️⃣ K-Means Quantization (Primary Method)Fast and stableMinimizes mean squared error (MSE)Uses AIC/BIC to choose optimal number of bucketsProduces continuous-to-categorical mappingProvides clean and interpretable boundariesVisuals included:FICO distribution histogramSmoothed PD vs. FICO plotAIC/BIC/MSE model selection curvesBucket boundary visualization2️⃣ Dynamic Programming Log-Likelihood Optimization (Theory Section)Dynamic programming gives globally optimal buckets by maximizing:$$LL = \sum_{i=1}^{B} \left[ k_i \ln(p_i) + (n_i - k_i)\ln(1 - p_i) \right]$$Constraints:Complexity is $O(N^2)$ to $O(N^3)$Not feasible for large datasetsNot expected to be computed fully in this program, but included for theoretical completeness.Included in the notebook:Full explanation of DP formulationOptimized pseudocodeA tiny runnable DP demo (20 rows) to illustrate the logic🧠 Key Insights⭐ From Task 3:Income, past defaults, and loan-to-income are critical PD predictors.Ensemble models generally outperform simple linear models in capturing non-linear risk factors.Expected loss estimation ties PD directly to financial risk.⭐ From Task 4:K-Means is the most practical quantization method for large datasets.DP is theoretically optimal but computationally heavy.Final bucket boundaries must be monotonic and risk-aligned to be useful for business rules.📂 Repository Structure├── Task3_Credit_Risk_Modeling.ipynb
├── Task4_FICO_Quantization.ipynb
├── data/
│   └── Task 3 and 4_Loan_Data.csv
├── README.md
└── outputs/
    ├── PD_model.pkl
    ├── kmeans_bucket_map.csv
    └── evaluation_plots/
🚀 How to Run1️⃣ Install Requirementspip install numpy pandas scikit-learn seaborn matplotlib xgboost
2️⃣ Launch Jupyter Notebookjupyter notebook
3️⃣ Run All CellsOpen and run:Task3_Credit_Risk_Modeling.ipynbTask4_FICO_Quantization.ipynb🏆 About the ProgramThis work was completed as part of the
