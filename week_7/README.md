# CUSTOMER PERSONALITY ANALYSIS

## Project overview
- This project focuses on customer segmentation using a marketing campaign dataset. 
- By applying various clustering algorithms, such as K-means and Hierarchical Clustering, the goal is to uncover meaningful customer groups based on income, spending habits, and engagement with the company's products.

## Dataset
- The dataset used for this analysis is the Marketing Campaign dataset containing customer demographics, product purchases, and campaign interactions.
- Link to the dataset: https://www.kaggle.com/datasets/imakash3011/customer-personality-analysis

## Libraries
- pandas, numpy, seaborn, matplotlib, missingno, datetime, sklearn, scipy

## Basic Exploratory Data Analysis (EDA)
- Data Structure: The dataset’s structure and basic statistics are reviewed.
- Missing Values: Missing data in key columns (e.g., income) is visualized using missingno and handled through KNN imputation.
- Distribution Analysis: Income, recency, and spending features are plotted to understand their distribution. Most spending features are highly right-skewed.

## Feature Engineering
- Age is derived from the customer’s birth year.
- Total money spent is calculated by summing various product purchase columns.
- Feature Scaling: A RobustScaler is used to scale the features due to the presence of outliers and skewed distributions.

## K-means Clustering
- Elbow Method: The optimal number of clusters is determined using the elbow method, resulting in 3 clusters.
- K-means Model: The K-means clustering algorithm is applied to the scaled data, and the clusters are visualized using a scatter plot of income vs. total spent.

## Insights from K-Means Clusters
- Cluster 1 has the highest average income and spending, indicating they are the most profitable.
-  Cluster 0 has the lowest income and spending, showing minimal response to campaigns.
- Cluster 2 tends to make the most purchases through both deals and web (5.08 and 6.39), while Cluster 1 relies heavily on catalog purchases (5.43).
- In terms of store purchases: Highest in Class 1 with Class 0 being significantly lower than the other 2 classes.

## Evaluation Metrics
- Silhouette Score: Measures how similar an object is to its own cluster compared to other clusters. K-means shows a silhouette score of 0.2588.
- Davies-Bouldin Score: Measures cluster separation, with a score of 1.507 for K-means.

## Hierarchical Clustering
- An alternative approach using Hierarchical Clustering is explored, resulting in a better silhouette score (0.6715). - - - However, the resulting clusters were not as meaningful because of the imbalance in the cluster sizes:
               - 2 : 2236
               - 1 : 3
               - 3 : 1

