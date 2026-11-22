# Task:02 Customer Cohort & Churn Analytics

##  Project Overview
This project analyzes telecom/SaaS customer retention behavior using the **IBM Telco Customer Churn** dataset. Customers are segmented by subscription vintage (tenure cohorts), contract types, service tiers, and payment methods to compute retention curves, identify high-risk churn drivers, and propose actionable retention strategies.

##  Objectives
- Calculate the baseline customer churn rate.
- Segment customers into tenure-based cohorts (`0–12` to `61–72` months) across contract types (`Month-to-month`, `One year`, `Two year`).
- Visualize customer retention via a **Cohort Retention Matrix Heatmap** and a **Tenure Retention Curve**.
- Identify high-risk churn segments based on internet service, tech support, and payment methods.
- Provide data-driven strategic recommendations to reduce churn.

##  Tools & Technologies Used
- **Python 3** (Google Colab / Jupyter Notebook)
- **Pandas & NumPy:** Data cleaning, preprocessing, and cohort aggregation
- **Matplotlib & Seaborn:** Cohort retention matrix heatmap visualization
- **Plotly Express:** Interactive retention curve visualization


## Key Findings & Results

### 1. Baseline Metric
- **Overall Churn Rate:** **26.58%** (across 7,032 valid customer records)

### 2. Cohort & Contract Retention Insights
- **First-Year Vulnerability (`0–12 Months`):** Month-to-month customers in their first year show the lowest retention rate at **48.65%** (a **51.35%** churn rate). Retention steadily improves with tenure, reaching **77.78%** for customers in the `61–72 Months` cohort.
- **Contract Stability:** Long-term contracts drastically reduce churn. `Two-year` contracts maintain **100%** retention during the first 24 months and stay above **96%** across all tenure cohorts.

### 3. Top High-Risk Churn Segments
| Internet Service | Tech Support | Payment Method | Customer Count | Churn Rate (%) |
| :--- | :--- | :--- | :---: | :---: |
| Fiber optic | No | Electronic check | 1,288 | **58.07%** |
| Fiber optic | No | Mailed check | 185 | **49.73%** |
| DSL | No | Electronic check | 442 | **38.91%** |
| Fiber optic | No | Bank transfer (automatic) | 400 | **36.50%** |
| Fiber optic | Yes | Electronic check | 307 | **32.90%** |

> **Key Takeaway:** Adding **Tech Support** to Fiber Optic + Electronic Check users drops their churn rate from **58.07%** down to **32.90%** (~25% reduction).

##  Strategic Retention Recommendations
1. **First-Year Onboarding & Contract Upgrade Incentives:** Target `0–12 Month` month-to-month subscribers with a 10–15% discount or a free service month after Month 3 to encourage migration to 1-year contracts.
2. **Bundled Tech Support for Fiber Optic Plans:** Include 6 months of complimentary Tech Support for new Fiber Optic subscribers to address early service friction.
3. **Auto-Pay Migration Campaign:** Offer a $5/month bill credit to customers using Electronic Checks to incentivize switching to automatic bank transfers or credit card auto-pay.



## Repository Structure
```text
├── telco_customer_churn.csv         # Cleaned IBM Telco Churn dataset
├── Customer_Cohort_Churn.ipynb      # Python analysis & visualization notebook
├── cohort_retention_matrix.png      # Heatmap of retention rates by tenure & contract
├── retention_curve.png              # Retention rate progression over tenure months
├── Churn_Analysis_Report.pdf        # Executive summary report & recommendations
└── README.md                        # Project documentation
