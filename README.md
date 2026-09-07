# HR Employee Attrition Analysis

Predicting which employees are at risk of leaving, and identifying the key drivers of attrition, using the IBM HR Analytics dataset.

## 🎯 Project Overview

Employee turnover is expensive — lost productivity, hiring costs, and training time. This project analyzes HR data for 1,470 employees to:

1. **Understand why employees leave** through exploratory data analysis and a metrics dashboard
2. **Predict who might resign soon** using a simple, explainable classification model
3. **Translate findings into actionable HR recommendations**

## 📊 Dataset

- **Source:** [IBM HR Analytics Employee Attrition & Performance](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset) (Kaggle)
- **Size:** 1,470 employees, 35 attributes
- **Note:** This is a fictional dataset created by IBM data scientists for analytics practice — no real employee data is involved.

## 🔑 Key Findings

- Overall attrition rate: **~16%** (roughly 1 in 6 employees)
- **Overtime** is the single strongest driver of attrition — employees working overtime leave at a much higher rate
- **Early-tenure employees** (0–2 years) are at the highest flight risk
- **Frequent business travel** and **low job satisfaction / poor work-life balance** are strongly associated with leaving
- **Sales Representatives** show disproportionately high attrition compared to other roles
- Model performance: **Logistic Regression, ROC-AUC ≈ 0.80** on held-out test data

## 🛠️ Approach & Tools

| Step | Technique |
|---|---|
| EDA / Dashboard | Matplotlib, Seaborn — 9 charts covering department, role, overtime, age, income, satisfaction, tenure |
| Feature Engineering | Dropped constant/ID columns, label-encoded categoricals, engineered a tenure-bucket feature |
| Modeling | Logistic Regression (`class_weight="balanced"`) — chosen for interpretability over accuracy gains from black-box models |
| Evaluation | Accuracy, Precision, Recall, F1, ROC-AUC, Confusion Matrix (accuracy alone is misleading on this imbalanced dataset) |

**Why Logistic Regression instead of a more complex model?** For an HR use case, a model that stakeholders can interpret and trust is more valuable than a marginal accuracy improvement from a black box. The coefficients directly show which factors raise or lower attrition risk, which supports real conversations with HR teams rather than an opaque score.

## 📁 Repository Structure

```
├── HR_Attrition_Analysis.ipynb          # Main notebook (fully executed)
├── WA_Fn-UseC_-HR-Employee-Attrition.csv # Dataset
├── charts/                               # Saved chart images
└── README.md
```

## 🚀 How to Run

1. Clone this repo
2. Install dependencies: `pip install pandas numpy matplotlib seaborn scikit-learn`
3. Open `HR_Attrition_Analysis.ipynb` in Jupyter or Google Colab (keep the CSV in the same folder)
4. Run all cells

## ⚠️ Limitations

- Correlational, not causal — the model highlights associations, not proven causes
- Categorical features are label-encoded, so raw coefficient signs for those features should be read alongside the dashboard charts, not in isolation
- Dataset is relatively small (1,470 rows) and fictional, so findings are illustrative of technique rather than a real company's actual attrition patterns

## 📬 Contact

Feel free to reach out if you'd like to discuss this project or HR analytics in general.
