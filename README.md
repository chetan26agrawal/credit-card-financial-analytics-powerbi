# 💳 Credit Card Financial Analytics | Power BI

## 📌 Project Overview

This project focuses on analyzing **credit card usage, customer behavior, financial performance, and credit risk using Power BI and DAX**.

The objective was to transform credit card transaction and customer data into an interactive analytical dashboard covering **transaction trends, customer utilization, revenue performance, delinquency, satisfaction, loan behavior, and credit risk**.

The project demonstrates practical application of **DAX calculations, KPI development, financial analysis, customer segmentation, and interactive Power BI visualization**.

---

## 🎯 Business Problem

A banking institution needs deeper visibility into credit card customer behavior and financial risk.

The analysis focuses on understanding:

- How credit card transaction activity changes over time.
- How customer utilization affects credit risk.
- Which clients contribute the highest transaction value.
- Which customers show high credit utilization.
- How delinquency impacts customer risk.
- How interest earned compares with revolving balances.
- How income relates to credit limits.
- How customer satisfaction varies by card category.
- How credit limits influence personal loan approval.
- Which customers require immediate risk attention.

---

## 📊 Dataset

The project uses customer-level and credit-card financial data containing information related to:

- Client Transactions
- Credit Limits
- Transaction Amounts
- Revolving Balances
- Utilization Ratios
- Delinquent Accounts
- Interest Earned
- Income
- Personal Loans
- Card Categories
- Customer Satisfaction

### Key Fields

- `Client_Num`
- `Credit_Limit`
- `Total_Trans_Amt`
- `Avg_Utilization_Ratio`
- `Total_Revolving_Bal`
- `Delinquent_Acc`
- `Interest_Earned`
- `Income`
- `Personal_loan`
- `Card_Category`
- `Cust_Satisfaction_Score`

---

## 🛠️ Tools & Technologies

- **Microsoft Power BI**
- **DAX**
- Power Query
- Data Modeling
- Data Transformation
- KPI Development
- Financial Analysis
- Customer Analytics
- Credit Risk Analysis
- Data Visualization
- Interactive Dashboarding

---

# 📈 Transaction Performance Analysis

## 1. Running Total of Credit Card Transactions

Created a DAX-based running total to track cumulative credit card transaction activity over time.

This enables analysis of transaction growth and helps identify changes in customer spending patterns.

---

## 2. Four-Week Moving Average

Calculated a **4-week moving average of Credit Limit for each client** using DAX time-based analysis.

This smooths short-term fluctuations and provides a clearer view of credit-limit trends.

---

## 3. MoM & WoW Growth Analysis

Calculated:

- Month-over-Month transaction growth
- Week-over-Week transaction growth

These metrics help identify changes in transaction activity and monitor short-term and monthly financial trends.

---

# 💰 Financial & Customer Analysis

## 4. Customer Acquisition Cost Analysis

Calculated **Customer Acquisition Cost (CAC) as a ratio of transaction amount** to evaluate acquisition efficiency relative to customer transaction activity.

This provides a financial perspective on customer acquisition performance.

---

## 5. Yearly Average Utilization Ratio

Calculated the yearly average of `Avg_Utilization_Ratio` across all clients.

The metric helps monitor overall credit utilization behavior and identify periods of increasing customer credit usage.

---

## 6. Interest Earned vs Revolving Balance

Calculated the percentage relationship between:

- `Interest_Earned`
- `Total_Revolving_Bal`

This helps evaluate interest generation relative to outstanding revolving balances.

---

# 🏆 Customer Performance Analysis

## 7. Top 5 Clients by Transaction Amount

Identified the **Top 5 clients based on Total Transaction Amount**.

This helps management identify high-value customers and understand their contribution to overall transaction activity.

---

## 8. High Utilization Customers

Identified clients whose:

`Avg_Utilization_Ratio > 80%`

These customers represent a potentially important group for **credit monitoring and risk-management strategies**.

---

# ⚠️ Customer Risk Analysis

## 9. Customer Churn Indicator

Created a KPI to flag customers who have:

`Total_Trans_Amt = 0`

during the **last 6 months**.

This indicator helps identify inactive customers and supports customer retention and re-engagement strategies.

---

## 10. Delinquency Rate

Calculated the percentage of clients with:

`Delinquent_Acc > 0`

This KPI provides a high-level view of delinquency exposure across the customer base.

---

# 🛡️ Credit Risk Score

## 11. Credit Risk Scoring Model

Created a client-level **Credit Risk Score** using three key financial risk factors:

- `Avg_Utilization_Ratio`
- `Delinquent_Acc`
- `Total_Revolving_Bal`

### Scoring Formula

```text
Credit Risk Score =
100 - (
    Utilization Score × 40%
    +
    Delinquency Score × 40%
    +
    Revolving Balance Score × 20%
)
```

The scoring model uses weighted components to evaluate customer credit exposure.

### Risk Categories

```text
75 – 100  → Low Risk
50 – 74   → Medium Risk
0 – 49    → High Risk
```

Higher credit-risk scores represent lower risk exposure.

---

## 📊 Risk Analysis Result

The analyzed dashboard sample contained:

- **11 Total Clients**
- **11 High-Risk Clients**
- **100% High-Risk Classification**
- **0 Low-Risk Clients**
- **0 Medium-Risk Clients**

The dashboard indicates that all clients in the analyzed sample were classified as **High Risk** based on the computed Credit Risk Score. :contentReference[oaicite:2]{index=2}

### Business Implication

The result highlights the importance of:

- Credit monitoring
- Risk mitigation
- Utilization management
- Delinquency control
- Customer engagement

---

# 📊 Income & Credit Analysis

## 12. Income vs Credit Limit Correlation

Analyzed the relationship between:

- Customer Income
- Credit Limit

The correlation analysis helps evaluate whether customers with higher income generally receive higher credit limits.

---

# 😊 Customer Satisfaction Analysis

## 13. Customer Satisfaction by Card Category

Calculated the average `Cust_Satisfaction_Score` by `Card_Category`.

This helps identify differences in customer experience across credit-card categories and supports customer-service improvement initiatives.

---

# 🏦 Loan Approval vs Credit Limit

## 14. Personal Loan Analysis

Compared the average credit limit of customers:

- With personal loans
- Without personal loans

This analysis helps evaluate the relationship between **credit capacity and personal-loan adoption**.

---

# 🚨 High-Risk Customer Flag

## 15. High-Risk Client Identification

Created a high-risk flag for customers whose:

- `Total_Revolving_Bal` exceeds **90% of Credit_Limit**
- `Avg_Utilization_Ratio` is high

This enables management to identify customers requiring **immediate credit-risk monitoring**.

---

# 🧮 DAX Analysis

The project demonstrates practical use of DAX for financial and customer analytics.

### Key DAX Concepts

- CALCULATE
- SUM
- AVERAGE
- DIVIDE
- FILTER
- DISTINCTCOUNT
- DATEADD
- DATESINPERIOD
- TOPN
- RANKX
- IF
- SWITCH
- Variables
- Time Intelligence
- Conditional Logic

---

# 📌 KPI Framework

The dashboard tracks multiple financial and customer KPIs.

### 💳 Transaction KPIs

- Total Transaction Amount
- Running Transaction Total
- MoM Growth
- WoW Growth
- 4-Week Moving Average

### 💰 Financial KPIs

- Credit Limit
- Revolving Balance
- Interest Earned
- Interest-to-Revolving Balance %
- CAC Ratio

### 👥 Customer KPIs

- Active Customers
- Top 5 Clients
- Customer Churn Indicator
- Customer Satisfaction
- Loan Adoption

### ⚠️ Risk KPIs

- Average Utilization Ratio
- Delinquency Rate
- Credit Risk Score
- Risk Category
- High-Risk Client Flag

---

# 💡 Key Insights

The analysis provides visibility into:

- Credit card transaction trends.
- Customer credit utilization.
- High-value customer contribution.
- Customer inactivity and potential churn.
- Delinquency exposure.
- Interest generation relative to revolving balances.
- Income and credit-limit relationships.
- Loan adoption behavior.
- Customer satisfaction across card categories.
- Overall customer credit risk.

The risk-scoring dashboard specifically shows **11 out of 11 analyzed clients classified as High Risk**. :contentReference[oaicite:3]{index=3}

---

# 💼 Business Impact

The analysis can support banking teams in making decisions related to:

### 🛡️ Credit Risk Management

Identify customers with high utilization, delinquency, and revolving-balance exposure.

### 👥 Customer Retention

Detect inactive customers and create targeted re-engagement strategies.

### 💰 Financial Performance

Monitor transaction activity, interest generation, and customer-level financial contribution.

### 🏦 Credit & Loan Strategy

Understand how credit limits relate to personal-loan adoption.

### 😊 Customer Experience

Evaluate satisfaction across different credit-card categories.

### 📊 Management Reporting

Provide senior management with interactive KPIs and financial risk indicators.

---

# 🚀 Project Outcome

Developed a **Power BI credit card analytics solution using DAX** to evaluate financial performance, customer behavior, and credit risk.

The project combines **transaction analysis, time intelligence, customer segmentation, financial KPIs, delinquency monitoring, and a weighted credit-risk scoring model** into a structured analytical framework.

The final analysis provides management with actionable visibility into **customer profitability, utilization behavior, churn indicators, delinquency exposure, and high-risk customers**.

---

# 📚 Key Skills Demonstrated

## 📊 Power BI

- Dashboard Development
- Interactive Visualizations
- KPI Cards
- Data Modeling
- Report Design
- Financial Reporting

## 🧮 DAX

- Time Intelligence
- Running Totals
- Moving Averages
- MoM Growth
- WoW Growth
- Ranking
- Top-N Analysis
- Conditional Measures
- Risk Scoring
- KPI Calculations

## 💳 Financial Analytics

- Transaction Analysis
- Credit Utilization
- Interest Analysis
- Revolving Balance Analysis
- Delinquency Analysis
- Credit Risk Assessment
- Loan Analysis

## 👥 Customer Analytics

- Customer Segmentation
- Customer Churn
- Customer Satisfaction
- High-Value Customer Analysis
- Customer Behavior Analysis

---

# 📂 Repository Structure

```text
Credit-Card-Financial-Analytics/
│
├── Dataset/
│   └── Credit_Card_Dataset.xlsx
│
├── PowerBI/
│   └── Credit_Card_Analytics.pbix
│
├── Screenshots/
│   └── Credit_Risk_Analytics_Dashboard.png
│
└── README.md
```

---

## 👤 Author

**Chetan Agrawal**

**Data Analyst | Excel | SQL | Power BI | Python**

---

## 🏷️ Project Type

**Power BI | DAX | Financial Analytics | Credit Risk Analytics | Customer Analytics**

---

## ⭐ Key Takeaway

This project demonstrates how **Power BI and DAX can transform credit-card data into actionable financial and risk insights** for better customer management and informed banking decisions.
