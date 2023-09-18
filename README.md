# CryptoClustering

Welcome to the CryptoClustering project! In this challenge, I will explore the world of cryptocurrencies and use unsupervised learning techniques to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

## Table of Contents
- [Instructions](#instructions)
- [Preparing the Data](#preparing-the-data)
- [Finding the Best Value for k Using the Original Scaled DataFrame](#finding-the-best-value-for-k-using-the-original-scaled-dataframe)
- [Optimizing Clusters with Principal Component Analysis (PCA)](#optimizing-clusters-with-principal-component-analysis-pca)
- [Finding the Best Value for k Using the PCA Data](#finding-the-best-value-for-k-using-the-pca-data)
- [Cluster Cryptocurrencies with K-means Using the PCA Data](#cluster-cryptocurrencies-with-k-means-using-the-pca-data)

## Instructions

1. **File Renaming**
   - Renamed the `Crypto_Clustering_starter_code.ipynb` file as `Crypto_Clustering.ipynb` for consistency.

2. **Data Loading and Visualization**
   - Loaded the `crypto_market_data.csv` into a DataFrame to prepare for analysis.
   - Obtained summary statistics and create data visualizations to understand the dataset's characteristics before proceeding.

## Preparing the Data

3. **Data Normalization**
   - Used the `StandardScaler()` module from scikit-learn to normalize the data from the CSV file.
   - Created a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

## Finding the Best Value for k Using the Original Scaled DataFrame

4. **Elbow Method**
   - Utilized the elbow method to find the optimal value for k (number of clusters) with the following steps:
     - Created a list with k values ranging from 1 to 11.
     - Initialized an empty list to store inertia values.
     - Ran a loop to compute the inertia for each possible value of k.
     - Created a dictionary with data for plotting the elbow curve.
     - Plotted a line chart displaying all the inertia values calculated for different values of k to visually identify the best value for k.
   - Answered the following question in the notebook: What is the best value for k?

5. **Clustering Cryptocurrencies with K-means**
   - Clustered the cryptocurrencies using the best value for k obtained from the elbow method on the original scaled data with the following steps:
     - Initialized the K-means model with the best value for k.
     - Fitted the K-means model using the original scaled DataFrame.
     - Predicted the clusters to group the cryptocurrencies using the original scaled DataFrame.
     - Created a copy of the original data and add a new column with the predicted clusters.
     - Created a scatter plot using hvPlot, setting "PC1" as the x-axis and "PC2" as the y-axis. Colored the graph points with the labels found using K-means. Included the "coin_id" column in the hover information to identify 
       the cryptocurrency represented by each data point.

## Optimizing Clusters with Principal Component Analysis (PCA)

6. **Principal Component Analysis (PCA)**
   - Performed a PCA on the original scaled DataFrame to reduce the features to three principal components.
   - Retrieved the explained variance to determine how much information each principal component holds.
   - Answered the question in the notebook: What is the total explained variance of the three principal components?

## Finding the Best Value for k Using the PCA Data

7. **Elbow Method on PCA Data**
   - Applied the elbow method to the PCA data to find the optimal value for k with the following steps:
     - Created a list with k values ranging from 1 to 11.
     - Initialized an empty list to store inertia values.
     - Ran a loop to compute the inertia for each possible value of k.
     - Created a dictionary with data for plotting the elbow curve.
     - Plotted a line chart displaying all the inertia values calculated for different values of k to visually identify the best value for k.
   - Answered the following questions in the notebook: What is the best value for k when using the PCA data? Does it differ from the best k value found using the original data?

## Cluster Cryptocurrencies with K-means Using the PCA Data

8. **Clustering with PCA Data**
   - Clustered the cryptocurrencies using the best value for k obtained from the elbow method on the PCA data with the following steps:
     - Initialized the K-means model with the best value for k.
     - Fitted the K-means model using the PCA data.
     - Predicted the clusters to group the cryptocurrencies using the PCA data.
     - Created a scatter plot using hvPlot, setting "price_change_percentage_24h" as the x-axis and "price_change_percentage_7d" as the y-axis.
     - Colored the graph points with the labels found using K-means.
     - Included the "coin_id" column in the hover information to identify the cryptocurrency represented by each data point.
   - Answered the question: What is the impact of using fewer features to cluster the data using K-Means?
