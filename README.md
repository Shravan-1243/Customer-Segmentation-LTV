# Customer Segmentation & LTV Analysis
This project aims to segment e-commerce customers based on their purchasing behavior and estimate their lifetime value (LTV) to enable targeted marketing strategies and improve business profitability.
---
## Dataset
The dataset used in this project is available on Kaggle:  
[Online Retail E-Commerce Data](https://kaggle.com/datasets/1fdb257f95302f345850b066d9587aed8b19ad653217ababb3af21aca25a76de)
It includes online transactional data for a UK-based and registered non-store online retail company.
---
## Project Overview
- Customer Segmentation using **RFM (Recency, Frequency, Monetary)** analysis
- Application of **K-Means Clustering** for grouping similar customer profiles
- Calculation of **Customer Lifetime Value (LTV)**
- Conducting a **Profitability Analysis** by segment
- Visualizing customer behavior and deriving **actionable insights**

 Business Use Case:
- Identify loyal/high-value customers for loyalty rewards

- Spot inactive customers for re-engagement campaigns

- Allocate marketing budget effectively

- Predict future customer value for strategic planning
---
## Methodology
1. **Data Cleaning & Preprocessing**
  - Removed missing values, invalid entries, and canceled transactions
  - Parsed and filtered for valid `CustomerID`, `Invoice`, `InvoiceDate`, `TotalPrice`

2. **RFM Feature Engineering**
  - **Recency**: Days since last purchase
  - **Frequency**: Number of unique invoices
  - **Monetary**: Total spend per customer

3. **RFM Scoring**
   - Each customer scored on a scale from 1 (lowest) to 5 (highest)
   - Combined into an `RFM_Score`

4. **K-Means Clustering**
   - Elbow method used to identify optimal K (K = 4)
   - Customers grouped into 4 clusters

5. **Customer LTV Estimation**
  - LTV calculated using:
    - Average Order Value (AOV)
    - Purchase Frequency
    - Churn Rate
    - Expected number of repeat cycles (1 / Churn Rate)

7. **Profitability Segmentation**
   - Segments analyzed based on LTV and total profit contribution

8. **Data Visualization**
   - Histograms, Boxplots, and Scatter Plots used to explore segment patterns
---
## Key Results
**Top 20% of customers contribute to 80%+ of revenue**
- **4 Customer Clusters** identified:
  - High-value, loyal customers
  - New or inactive customers
  - Mid-tier profitable customers
  - Low-spending customers

- **LTV Distribution**:
  - Wide gap in lifetime value across clusters
  - Top 20% of customers contribute to 80%+ of revenue
---
## Tools & Technologies

- Python (Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn
- Kaggle Notebook
- GitHub for version control & project sharing
---
## Insights & Applications

- Helps in **targeted marketing** and **loyalty programs**
- Provides clarity on **which customers drive revenue**
- Supports decisions on **where to focus promotional efforts**
- Enables data-driven **retention strategies**
---
## Repository Structure
├── ltv-model-project.ipynb # Kaggle Notebook with full analysis
├── Project-Data.ipynb # Initial data exploration
├── IPR-Updated.docx # Interim Project Report
├── Customer_Segmentation_Gantt.pdf # Timeline plan
├── README.md # Project summary and documentation
---
## Conclusion
Through RFM-based segmentation and LTV modeling, this project identifies valuable customer cohorts that significantly influence revenue. It supports data-driven marketing and retention strategies in e-commerce
---
## Acknowledgements

Thanks to Kaggle for the dataset and the open-source Python community for powerful data tools.
---
