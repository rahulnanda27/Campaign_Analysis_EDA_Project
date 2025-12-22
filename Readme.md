# Digital Marketing Campaign Performance Analysis (EDA)

## Executive Summary
This project presents an end-to-end **exploratory and diagnostic analysis** of digital marketing campaign data with the objective of evaluating **conversion efficiency, channel performance, and revenue impact**.

The analysis emphasizes **data quality validation, metric definition, and business-driven insights**, mirroring how a Senior Data Analyst would approach real-world marketing and growth analytics problems.

---

## Tools & Environment
- **Language:** Python  
- **Libraries:** pandas, numpy, matplotlib  
- **Development Environment:** VS Code  
- **Analysis Type:** Exploratory & Diagnostic Analytics  

---

## Data Sources & Structure
├── raw_data_files/
│ ├── campaigns.csv
│ ├── customers.csv
│ ├── events.csv
│ ├── products.csv
│ └── transactions.csv
│
├── EDA_code.ipynb
├── README.md


### Dataset Overview
- **Campaigns:** Channel, objective, target segment, campaign duration  
- **Customers:** User identifiers and metadata  
- **Events:** User interaction data used to construct funnels  
- **Products:** Product catalog and pricing  
- **Transactions:** Revenue, discounts, and refunds  

---

## Data Quality Assessment & Preparation
A structured data validation process was conducted prior to analysis:

### 1. Temporal Data Normalization
- Timestamp and date fields were originally stored as strings
- Converted all relevant columns to `datetime` to enable:
  - Accurate time-series aggregation
  - Campaign duration calculations
  - Daily revenue normalization

### 2. Categorical Standardization
- Identified inconsistent capitalization in `traffic_source`
- Standardized values to ensure:
  - Accurate aggregations
  - Elimination of duplicate category inflation
  - Reliable channel-level comparisons

### 3. Revenue Metric Engineering
- Transaction-level revenue required adjustment for:
  - Discounts
  - Refunded transactions
- **Net revenue** was explicitly derived to reflect true business impact

---

## Analytical Approach
The EDA followed a structured framework:

1. **Univariate Analysis**
   - Distribution of events, users, campaigns, and revenue

2. **Funnel Construction**
   - Event-level aggregation to assess drop-off and conversion efficiency

3. **Channel Performance Evaluation**
   - Conversion rate analysis by traffic source
   - Benchmarking against expected marketing behavior

4. **Campaign Profitability Analysis**
   - Net revenue aggregation at the campaign level
   - Normalization by campaign duration (daily net revenue)

---

## Business Questions & Insights

### 1️⃣ Which Traffic Sources Drive the Highest Conversion?

| Traffic Source | Conversion Rate |
|----------------|------------------|
| **Email** | **17.7%** |
| Paid Search | 16.7% |
| Social | 14.3% |
| Direct | 3.9% |
| Organic | 3.9% |

#### Insight
- **Email consistently outperforms all other channels**, indicating strong intent alignment and targeting efficiency.
- **Direct and Organic traffic materially underperform**, contradicting typical expectations and signaling potential issues in:
  - Landing page experience
  - Audience quality

#### Recommendation
- Prioritize incremental investment in **Email and Paid Search**
- Conduct deeper analysis on **Direct and Organic** traffic to identify friction points

---

### 2️⃣ Which Campaigns Generate the Highest Net Revenue Impact?

Net revenue was calculated after adjusting for discounts and refunds. Normalization was done by campaign duration for campaigns.

| Campaign ID | Channel | Objective | Target Segment | Campaign Period | Net Revenue | Daily Net Revenue |
|------------|--------|-----------|----------------|----------------|------------|------------------|
| 5 | Social | Acquisition | New Customers | 82 days | 191,588.20 | 2,336.44 |
| 18 | Affiliate | Retention | All | 59 days | 191,126.03 | 3,239.42 |
| 29 | Email | Acquisition | New Customers | 62 days | 186,213.14 | 3,003.44 |
| 44 | Affiliate | Reactivation | All | 76 days | 183,494.01 | 2,414.39 |
| 7 | Paid Search | Cross-sell | High Value | 39 days | 176,805.78 | 4,533.48 |


#### Recommendation
- Scale high-performing Paid Search and Email campaigns
- Use daily net revenue as a primary metric for future campaign evaluation

---

## Key Takeaways
- Conversion rate alone is insufficient; **revenue efficiency provides stronger decision support**
- Email remains the most reliable high-intent channel
- Paid Search excels in monetization when targeted effectively
- Data normalization materially impacts analytical accuracy

---

## Limitations & Assumptions
- Attribution modeled at the traffic source level (no multi-touch attribution)
- Conversion defined using available event taxonomy
- Revenue timing aligned to transaction timestamps

---

## Author
**Rahul Nanda**  
 Marketing & Growth Analytics | Aspiring Data Scientist  

📌 *This project demonstrates applied analytics, business reasoning and metric-driven decision making suitable for senior-level roles.*

