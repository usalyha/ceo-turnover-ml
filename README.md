# Why Do CEOs Get Fired?

A machine learning–based empirical study on predicting CEO dismissals using firm- and executive-level data from U.S. public companies between 1992 and 2022.

> This project was developed as a final team assignment for *Data Mining Labs and Methods* (Spring 2025) at Seoul National University.


## Research Question

**Why and when do CEOs get fired?**

We build and interpret classification models to predict CEO forced turnovers based on a rich set of executive and firm financial data. The project focuses on:
- Feature selection and interpretation
- Time and industry heterogeneity
- Practical application for investors, executives, and researchers

---

## Dataset

- **Period**: 1992–2022
- **Data**: 
  - CEO identifiers, age, gender, compensation (bonus, option, salary)
  - Firm-level financial ratios: profitability, growth, and stability
  - 3-year lagged variables for compensation and financials

> Each row represents a CEO-firm-year combination.

We apply **matched case-control sampling** (1:1 and 1:2) to handle class imbalance and avoid bias in forced vs. non-forced turnovers.


## Methods

### Models
- XGBoost (feature importance)
- Decision Tree & Random Forest (full and matched sample)
- Logistic Regression (baseline, Lasso-selected, Boosting-selected)

### Key Techniques
- Permutation Feature Importance
- Stratified Train-Test Split (by forced turnover)
- Industry and Year Dummy Interactions
- Comparison pre/post 2008 Global Financial Crisis


## Key Findings

- **Executive Compensation**: Bonus and option-based pay are highly predictive of forced turnover risk.
- **Firm Profitability**: Pre-tax income and ROA are negatively associated with CEO dismissals.
- **Tenure Effects**: U-shaped relationship — early (2y) and very long (20y+) tenures increase risk.
- **Industry-Specific Trends**: 
  - Oil, Utility: Option-heavy compensation → greater impact
  - Pharma: R&D cutbacks strongly predict dismissal
- **Financial Crisis Aftermath**:
  - Stability metrics (e.g. Quick ratio, Receivables) become more influential
  - Option > Bonus post-2008



## Use Cases

- **For CEOs**: Understand personal risk factors for forced termination.
- **For Investors**: Identify governance-related risk early.
- **For Researchers**: Extend studies on corporate governance, gender dynamics, and performance sensitivity.


## Repository Structure

```bash
ceo-turnover-ml
├── data/                 
├── logistic/              
├── xgboost/                
├── treemodels/                   
└── README.md        
