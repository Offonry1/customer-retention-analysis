# Customer Churn Analysis
A data analysis project examining why customers leave a telecom company and what can be done to keep them. Built using 7,043 real customer records covering demographics, services, billing and churn status.

## Dataset
- Source: IBM Telco Customer Churn Dataset (via Kaggle)
- Records: 7,043 customers
- Columns: 21 fields covering customer demographics, account tenure, services subscribed, billing method and charges
- Target variable: `Churn` (Yes/No)

## Business Questions Answered
1. What is the overall customer churn rate?
2. What does a typical churning customer look like?
3. What data cleaning was done and why?
4. Does contract type affect churn rate?
5. Does internet service type affect churn rate?
6. Does payment method affect churn rate?
7. Does customer tenure affect churn rate?

## Project Phases
**Phase 1 — Data Loading & Understanding**
Loaded the dataset, explored column types, checked for missing values and duplicates, and answered the first two business questions.

**Phase 2 — Data Cleaning & Transformation**
Fixed TotalCharges (stored as text instead of number), filled 11 blank entries for new customers with 0, dropped the customerID column, and created three new columns — Churn_Flag, Tenure_Band and SeniorCitizen_Label.

**Phase 3 — Exploratory Data Analysis**
Ran univariate and bivariate analysis across all key variables. Cross tabulations compared contract type, internet service, payment method and tenure band against churn status.

**Phase 4 — Data Visualization**
Built five charts showing churn rate by contract type, internet service, tenure band and monthly charges — all with written interpretations.

**Phase 5 — Statistical Testing & Recommendations**
Ran two independent t-tests (monthly charges and tenure) and one chi-square test (contract type). All three returned p-values essentially equal to zero — confirming the patterns are real and not random.

## Key Findings
- Overall churn rate is **26.54%** — more than 1 in 4 customers left
- Month-to-month customers churn at **42.71%** vs just **2.83%** for two-year contracts
- Customers in their first 12 months churn at **47.44%** — the highest risk period
- Fiber optic customers churn at **41.89%** despite paying premium prices
- Electronic check users churn at **45.29%** — much higher than automatic payment users
- Churned customers had shorter tenure and higher monthly charges than retained customers

## Statistical Test Results
| Test | Variables | Result |
|---|---|---|
| T-Test | Monthly Charges vs Churn | Significant — p ≈ 0.00 |
| T-Test | Tenure vs Churn | Significant — p ≈ 0.00 |
| Chi-Square | Contract Type vs Churn | Significant — χ² = 1,184.60, p ≈ 0.00 |

## Top 3 Recommendations
1. **Convert month-to-month customers** to annual or two-year contracts through discounts and loyalty incentives
2. **Invest in the first 12 months** — onboarding programs, check-in calls and early rewards reduce new customer churn significantly
3. **Investigate fiber optic quality and pricing** — premium customers churning at 41.89% suggests the service is not meeting expectations

## Project Structure
Customer_Churn_Project/
data/
WA_Fn-UseC_-Telco-Customer-Churn.csv
notebooks/
churn_analysis.ipynb
outputs/
viz1_churn_rate.png
viz2_contract_churn.png
viz3_boxplots.png
viz4_internet_churn.png
viz5_tenure_churn.png
presentation/
Customer_Churn_Analysis_Presentation.pptx
sql/
customer_churn_analysis.sql
.gitignore
README.md
requirements.txt

## Tools Used
Python | pandas | numpy | matplotlib | seaborn | scipy | Jupyter Notebook

## How to Run
1. Clone or download the repository
2. Install dependencies: `pip install -r requirements.txt`
3. Open `notebooks/churn_analysis.ipynb` in Jupyter
4. Run **Kernel → Restart & Run All**

---
*Prepared by Mandela Offonry — Junior Data Analyst*