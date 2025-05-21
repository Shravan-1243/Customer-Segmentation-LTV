# Predicting Customer Lifetime Value (CLV) Using Machine Learning  
### MSc Data Science Final Project – University of Hertfordshire  

This project explores the use of ensemble machine learning models to predict **Customer Lifetime Value (CLV)** by combining **RFM analysis** with **K-Means behavioural clustering**. The aim is to help businesses identify high-value customers, optimize marketing spend, and improve customer retention strategies.

---

## Project Summary

The primary objective of this study was to compare the predictive performance of **Random Forest** and **XGBoost** regressors using features derived from:

- **Recency, Frequency, and Monetary (RFM)** values  
- **Customer segments created through K-Means clustering**

The analysis was conducted on the **Online Retail II dataset**, which provides transactional data from a UK-based online retailer.

---

## Business Use Cases

- Identify high-value and loyal customers for retention programs
- Re-engage dormant customers using personalized campaigns
- Strategically allocate marketing budgets
- Forecast customer value for long-term planning

---

## Methodology Overview

### Data Cleaning & Preprocessing
- Removed missing and invalid entries
- Filtered returns and duplicates
- Created `TotalPrice` from `Quantity × Price`

### RFM Feature Engineering
- **Recency**: Days since last purchase  
- **Frequency**: Number of unique transactions  
- **Monetary**: Total amount spent  

### Behavioural Clustering (K-Means)
- Used Elbow Method to determine `k = 4`  
- Segmented customers into 4 behavioural groups  

### CLV Prediction Models
- Trained both **Random Forest** and **XGBoost** regressors  
- Included cluster labels as additional predictive features  
- Evaluated using **R² Score**, **RMSE**, and **MAE**

---

## Model Results

| Model             | R² Score | RMSE        | MAE        |
|------------------|----------|-------------|------------|
| Random Forest     | 0.9864   | 50,527.50   | 2,377.41   |
| XGBoost           | 0.9205   | 122,411.74  | 7,954.32   |

- **Random Forest** demonstrated significantly higher accuracy and lower error.
- **Cluster labels** and **Monetary value** were top predictors in feature importance analysis.

---

## Insights & Visualizations

- Applied quantile-based segmentation to group customers into **Low**, **Medium**, **High**, and **Very High** CLV segments  
- Pareto Principle observed: Top 20% of customers contributed over 80% of revenue  
- Heatmaps showed a clear correlation between high-value clusters and very high LTV groups  
- Plots included: histograms, boxplots, scatter plots, predicted vs actual CLV

---

## Technologies Used

- **Language**: Python  
- **Libraries**:  
  - `pandas`, `numpy` – data manipulation  
  - `scikit-learn`, `xgboost` – ML models & clustering  
  - `matplotlib`, `seaborn` – visualizations  
- **Notebook Environment**: Kaggle  
- **Version Control**: GitHub  

---

## Repository Structure

├── ltv-model-project.ipynb # Jupyter Notebook with full analysis
├── ltv-model-project.pdf # PDF version of the notebook
├── 23035825-Shravan-FPR.docx # Final Project Report
├── Customer_Segmentation_Gantt.pdf # (Optional) Project timeline
├── images/ # Visualizations (e.g., heatmaps, feature plots)

---

## How to Run This Project

1. **Clone the repository:**
```bash
git clone https://github.com/Shravan-1243/Customer-Segmentation-LTV.git
cd Customer-Segmentation-LTV
```
2. **Install required packages:**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost
```
3. Download the dataset:
From Kaggle: Online Retail II Dataset
Place it in a data/ folder or update the file path in the notebook.

4. Run the notebook:
```bash
jupyter notebook ltv-model-project.ipynb
```

## Conclusion
This MSc project showcased how combining RFM segmentation with behavioural clustering can significantly enhance CLV prediction. The insights from this work provide a strong foundation for developing personalized marketing strategies and revenue optimization frameworks in real-world e-commerce applications.

## Acknowledgements
Special thanks to my supervisor *Dr. Julia Goncharenko* for her guidance and support, and to the open-source community for the tools that made this project possible.

## Contact Me
Name: Shravan Somashekar Kanamadi

LinkedIn: linkedin.com/in/shravan-kanamadi-338715178

Email: shravankanamadi12@gmail.com

---

Let me know if you'd like a `short pinned post` to go on top of this repo or your LinkedIn profile too!
