# Predicting Customer Lifetime Value (CLV) Using Machine Learning: A Comparative Study
## Master's Project | University of Hertfordshire
This project aims to segment e-commerce customers based on their purchasing behavior and estimate their lifetime value (LTV) to enable targeted marketing strategies and improve business profitability.
---
## Project Overview

Welcome to my Master's project repository! This project dives deep into the fascinating world of Customer Lifetime Value (CLV) prediction, a critical metric for businesses aiming to optimize their customer retention strategies, marketing efficiency, and overall profitability.

The core objective was to investigate and compare the effectiveness of two powerful ensemble machine learning models – **Random Forest** and **XGBoost** – in predicting CLV. What makes this study unique is the integration of **behavioral clustering** (using K-means) alongside traditional **Recency, Frequency, and Monetary (RFM) analysis** to enhance predictive accuracy.

This repository contains the full code, analysis, and report for the project.

 Business Use Case:
- Identify loyal/high-value customers for loyalty rewards
- Spot inactive customers for re-engagement campaigns
- Allocate marketing budget effectively
- Predict future customer value for strategic planning
---
## Dataset

This project utilizes the publicly available **Online Retail II Dataset**, which can be accessed on Kaggle:

* [**Online Retail E-Commerce Data**](https://www.kaggle.com/datasets/1fdb257f95302f345850b066d9587aed8b19ad653217ababb3af21aca25a76de)

It comprises comprehensive transactional data from a UK-based and registered non-store online retail company, providing a rich foundation for CLV prediction.
---
## Key Features & Methodology

Here's a breakdown of the key steps and techniques employed in this project:

1.  **Data Cleaning & Preprocessing:**
    * Handled missing values, invalid entries, and canceled transactions.
    * Parsed and filtered for valid `CustomerID`, `Invoice`, `InvoiceDate`, and `TotalPrice` to ensure data quality.

2.  **RFM Feature Engineering:**
    * Derived essential features for customer analysis:
        * **Recency:** Days since the customer's last purchase.
        * **Frequency:** Total number of unique invoices/purchases made by the customer.
        * **Monetary:** Total monetary value spent by the customer.

3.  **RFM Scoring:**
    * Each customer was scored on a scale from 1 (lowest) to 5 (highest) for Recency, Frequency, and Monetary values.
    * These scores were combined to create a comprehensive `RFM_Score`.

4.  **Behavioral Clustering (K-Means):**
    * The Elbow method was used to identify the optimal number of clusters, leading to **K = 4**.
    * Customers were then grouped into these 4 distinct behavioral clusters based on their RFM characteristics.

5.  **Customer Lifetime Value (CLV) Prediction using Machine Learning:**
    * **Random Forest Regressor** and **XGBoost Regressor** models were trained on features derived from RFM analysis, *augmented with the newly created cluster labels*.
    * Models were evaluated using **RMSE**, **MAE**, and **R² score**. (Note: We'll put the specific scores in 'Results').

6.  **CLV Segmentation & Revenue Analysis:**
    * Predicted CLV values were segmented into four quantiles: Low, Medium, High, and Very High.
    * Analyzed customer count and total revenue contribution by these CLV segments.
    * Cross-tabulated CLV segments with customer clusters (e.g., using heatmaps) to understand segment distribution.

7.  **Profitability Segmentation:**
    * Customer segments were further analyzed based on their predicted CLV and their total profit contribution.

8.  **Data Visualization:**
    * Extensive use of histograms, boxplots, and scatter plots to explore customer behavior patterns and segment characteristics.
---
## Results & Insights

This project yielded several significant findings:

* **Predictive Performance:**
    * **Random Forest Regressor:**
        * RMSE: 50527.50
        * MAE: 2377.41
        * **R² Score: 0.9864** (Demonstrates strong predictive accuracy, with predictions closely aligning with actual CLV values.)
    * **XGBoost Regressor:**
        * RMSE: 122411.74
        * MAE: 7954.32
        * **R² Score: 0.9205** (While performing well, Random Forest showed superior precision for this dataset.)

* **Customer Segmentation:** Identified **4 distinct customer clusters** based on RFM behavior, categorized as:
    * High-value, loyal customers
    * New or potentially inactive customers
    * Mid-tier profitable customers
    * Lower-spending customers

* **Pareto Principle in Action:** Consistently observed that the **top 20% of customers contributed to 80%+ of total revenue**, highlighting the importance of high-value customer identification.
* **Key Drivers of CLV:** Monetary value and the assigned Cluster ID were the most influential features in predicting Customer Lifetime Value, as determined by feature importance analysis.
* **High-Value Clusters:** Cluster 0 (or a specific cluster if you renamed it) consistently showed a significant concentration of 'Very High LTV' customers, affirming the effectiveness of behavioral clustering in isolating high-value segments.
* **Strategic Prioritization:** CLV segmentation allowed for clear revenue attribution and enabled the prioritization of customers for targeted strategies.
---
## Technologies & Tools Used

* **Python** (Primary programming language)
* **Key Libraries:**
    * `pandas` & `numpy` (for data manipulation and numerical operations)
    * `matplotlib` & `seaborn` (for comprehensive data visualization)
    * `scikit-learn` (for K-Means clustering, preprocessing, and Random Forest Regressor)
    * `xgboost` (for XGBoost Regressor)
    * `datetime`
* **Development Environment:** Kaggle Notebook
* **Version Control:** GitHub
---
## 📈 Insights & Business Applications

The insights derived from this project have direct applicability in e-commerce and beyond:

* **Targeted Marketing:** Identify loyal/high-value customers for exclusive loyalty rewards and personalized campaigns.
* **Re-engagement Strategies:** Pinpoint inactive or at-risk customers for tailored re-engagement campaigns.
* **Budget Allocation:** Effectively allocate marketing and retention budgets by focusing resources on high-potential segments.
* **Strategic Planning:** Predict future customer value for robust strategic planning and resource forecasting.
* **Profitability Optimization:** Gain clarity on which customer segments truly drive revenue and profit, enabling optimized business decisions.
---
## Repository Structure

* `ltv-model-project.ipynb`: The main Jupyter Notebook containing the full analysis, from data preprocessing and RFM analysis to K-means clustering, model training (Random Forest & XGBoost), and final evaluations.
* `ltv-model-project.pdf`: A convenient PDF export of the main Jupyter Notebook for quick review.
* `23035825-Shravan-Somashekar-Kanamadi-FPR.docx`: The Final Project Report document, detailing the theoretical background, methodology, results, discussion, and conclusion of the project.
* `Customer_Segmentation_Gantt.pdf`: (Optional - include if you want to show planning) Project timeline and planning document.
* `images/` (Optional - create this folder): Contains key plots and visualizations generated during the analysis (e.g., customer distribution heatmap, predicted vs. actual CLV plots).
---
## Getting Started

To run this project locally:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/Shravan-1243/Customer-Segmentation-LTV.git](https://github.com/Shravan-1243/Customer-Segmentation-LTV.git)
    cd Customer-Segmentation-LTV
    ```
2.  **Install necessary libraries:**
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn xgboost jupyter
    ```
3.  **Download the dataset:**
    The project uses the "Online Retail II" dataset. Download it from the Kaggle link provided in the Dataset section and place it in a `data/` subdirectory within this project's root, or update the file path in the `ltv-model-project.ipynb` accordingly.
4.  **Open the Jupyter Notebook:**
    ```bash
    jupyter notebook ltv-model-project.ipynb
    ```
    Then, run the cells sequentially to reproduce the analysis.
---
## XGBoost Model for LTV Prediction
Used XGBoost Regression to predict Customer Lifetime Value (LTV) based on RFM features and cluster segments.

Model Metrics:
**RMSE: 122411.74
MAE: 7954.32
R² Score: 0.9205**

## Random Forest Model for LTV Prediction
Used Random Forest Regression to predict Customer Lifetime Value (LTV) based on RFM features and cluster segments.

Model Metrics:
**RMSE: 50527.50
MAE: 2377.41
R² Score: 0.9864**

---
## Conclusion

This Master's project successfully demonstrated the power of combining RFM-based segmentation with advanced machine learning models for accurate Customer Lifetime Value prediction. By identifying valuable customer cohorts that significantly influence revenue, this work provides a robust framework to support data-driven marketing and customer retention strategies in the e-commerce domain.
---
## Acknowledgements

I'd like to express my sincere gratitude to my supervisor, **Dr. Julia Goncharenko**, for her invaluable guidance, support, and insights throughout this Master's project. This work was conducted as part of the MSc Data Science and Analytics program at the **University of Hertfordshire**.

Special thanks also to Kaggle for providing the dataset and to the wider open-source Python community for the powerful tools that made this research possible.
---
## Contact

Feel free to reach out if you have any questions or would like to discuss this project further!

* **Name:** Shravan Somashekar Kanamadi
* **LinkedIn:** [https://www.linkedin.com/in/shravan-kanamadi-338715178/]
* **Email:** [https://mail.google.com/mail/u/0/?tab=rm&ogbl#inbox]
---
