# Retail Supply Chain Sales Analysis

## 1. Project Overview

This project focuses on analyzing sales data from a global online store to better understand the factors that influence revenue, profit, and business performance.

The project aims to identify key factors that influence business performance, evaluate sales performance across different markets and customer segments, and propose actionable strategies to optimize revenue, reduce costs, and grow in the long term.

## 2. Data

The dataset used is the Excel file `[C] Retail-Supply-Chain-Sales-Analysis.xlsx`, which contains detailed information about sales transactions, including:

- **Order Information**: Identifier, Order Date, Shipping Method.

- **Customer information**: Customer code, name, segment (Consumer, Corporate, Home Office).

- **Geographic information**: Country, city, region.

- **Product information**: Product code, category, subcategory.

- **Financial information**: Sales, Quantity, Discount, Profit.

## 3. Analysis problems

The project solves 3 main analysis problems, corresponding to 3 notebooks in the `src/` folder:

### 3.1. Analysis of revenue and profit trends (`1.ipynb`)

- **Objective**: Understand the change and growth of revenue/profit over time, identify trends and periods of sudden fluctuations.

- **Method**:
- Summarize sales data by month.

- Apply the **Linear Regression** model to identify and quantify growth trends.

- Use Z-score on the residuals of the model to detect anomalies.

### 3.2. Analyze performance by customer segment (`2.ipynb`)

- **Objective**: Identify the highest value customer segments to focus marketing and sales resources.
- **Method**:
- **Feature Engineering**: Create a comprehensive set of features for each customer, including RFM (Recency, Frequency, Monetary) metrics and other behavioral metrics such as profit margin, average order value, return rate.
- **Clustering**: Use the **K-Means** algorithm to group customers based on the built features. The optimal number of clusters (k) is determined using the Elbow and Silhouette method.

- **Visualization**: Use PCA to reduce the dimensionality of the data and visualize customer clusters on a 2D space.

### 3.3. Analyze the impact of shipping modes (`3.ipynb`)

- **Objective**: Understand the impact of different shipping modes (`Ship Mode`) on the store's revenue and costs.

- **Method**:
- **Model Estimation (MLE)**: Use the **Ordinary Least Squares (OLS)** model, a case of MLE with the assumption that the noise follows a normal distribution.

- **Data Transformation**: Apply log transformation (`log1p`) to the variables `Sales` and `Cost` to stabilize the variance and reduce bias.

- **Controlled Model**: Build a multivariate regression model to estimate the impact of `Ship Mode` after adjusting for other factors such as `Region` and `Category`.

## 4. Directory Structure

```
Project/
├── [DATASET C] Retail Supply Chain Sales Analysis/
│ └── [C] Retail-Supply-Chain-Sales-Analysis.xlsx
├── src/
│ ├── 1.ipynb
│ ├── 2.ipynb
│ └── 3.ipynb
└── README.md
```

## 5. Installation and Usage Instructions

1. **Clone repository (if any):**
```bash
git clone <your-repo-url>
cd <your-repo-folder>
```

2. **Install required libraries setup:**
```bash
pip install pandas numpy matplotlib scikit-learn statsmodels openpyxl jupyter
```

1. **Running the notebooks:**
```bash
jupyter notebook
```