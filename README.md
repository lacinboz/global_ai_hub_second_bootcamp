# Global AI Hub Project - Machine Learning - 
This repository contains a project I completed during the Aygaz Machine Learning Bootcamp, which was part of the 10MillionAI initiative run by Global AI Hub.

# Airbnb Price Prediction and Clustering Analysis

Dataset: [Kaggle - Airbnb Open Data](https://www.kaggle.com/datasets/arianazmoudeh/airbnbopendata/code)

Project on Kaggle: [My Kaggle Notebook](https://www.kaggle.com/code/lainboz/airbnb-last/notebook)

## Overview

This notebook focuses on predicting Airbnb prices and analyzing clustering based on different features. The workflow includes data exploration, data cleaning, feature engineering, modeling, and evaluation. Below are the steps performed in the notebook along with the results observed in both supervised and unsupervised approaches.

## Steps

### 1. Data Exploration and Preprocessing
- **Exploration:** The dataset was examined using various functions to understand the structure and identify which columns might be important for price estimation.
- **Missing Data Handling:** 
  - Numeric columns were filled with the median.
  - Categorical columns were filled with the mode.
  - The `price` and `service fee` columns, initially in object format, were converted to float.
  - Some rows with missing values were dropped.
- **Dropping Columns:** Several irrelevant columns were dropped during preprocessing.

### 2. Data Visualization
- **Price Distribution:** A plot was created to show the distribution of prices.
- **Count Plots:** Count plots were generated for all categorical columns to visualize their distribution.
- **Relationship with Price:** Graphs were created to show the relationship between each categorical column and price.
- **Top 20 Neighborhoods:** A bar chart showing the average prices of the top 20 neighborhoods by listing count.
- **Construction Year Distribution:** A distribution plot of the construction years was also generated.

### 3. Feature Engineering
- **One-Hot Encoding:** Categorical variables were converted into numerical ones using One-Hot Encoding.

### 4. Scaling and Correlation Heatmap
- Applied feature scaling to normalize the data.
- Generated a heatmap to visualize the correlation between the features.

### 5. Model Training - Regression
- **Model Used:** Linear Regression.
- **Training:** The model was trained to predict the `price` of Airbnb listings based on multiple features, such as room type, neighborhood, and host verification status.

#### Observations:
- The feature importance analysis revealed that only the `service fee` appeared significant in the model, overshadowing all other features. 
- Despite attempts, the issue was unresolved. I suspect that feature scaling might be the cause, as the unscaled features caused `service fee` to dominate in the correlation matrix and the model.
  
  **Outcome:** The model exhibited signs of **overfitting**, heavily relying on the `service fee`, leading to poor generalization on new data.

### 6. Unsupervised Learning - Clustering
- **Clustering Approach:** K-Means clustering was applied to group listings based on their latitude, longitude, and price.
- **Variables Used:** Latitude (`lat`), Longitude (`long`), and Price (`price`).
- **Visualization:** A scatter plot was created to visualize the clusters formed based on location and price, with color-coding for cluster membership. The cluster centers were highlighted using red `x` markers.

#### Cluster Analysis:
- The clustering process resulted in 5 distinct groups based on location and price.
  
- **Cluster Summary:**
  - **Cluster 2 (Average Price: 1085.27 USD):** The cluster with the highest average price, representing the most expensive areas.
  - **Cluster 3 (Average Price: 854.98 USD):** Another high-priced cluster.
  - **Cluster 0 (Average Price: 623.28 USD):** A medium-high priced cluster.
  - **Cluster 4 (Average Price: 395.28 USD):** A medium-priced cluster.
  - **Cluster 1 (Average Price: 164.71 USD):** The cluster with the lowest average price, indicating the most affordable areas.

  **Outcome:** Clustering grouped areas into distinct price segments. High-priced areas were separated from more affordable ones, providing insight into geographical price variation.

## Results and Conclusions
- **Supervised Learning:** The `price` variable was heavily influenced by the `service fee`. Despite attempts, I was unable to resolve this issue. Feature scaling is likely critical in this case, as unscaled data caused this imbalance, leading to overfitting.
- **Unsupervised Learning:** The clustering analysis provided meaningful segmentation, where each cluster had distinct price characteristics, offering insight into how listings are categorized based on pricing.

**Conclusion:** The dataset was suitable for both supervised and unsupervised learning tasks. However, the quality of the data may affect the outcomes of the analysis.


