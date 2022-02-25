# Clustering Cryptocurrencies with K-Means Method
Unsupervised ML techniques to group cryptocurrencies into meaningful clusters.

## Overview
The goal of this project was to identify what cryptocurrencies are on the trading market and how they can be grouped to create a classification system. Unsupervised Machine Learning techniques, such as Principal Component Analysis and K-Means, were used.

## Results
### Preprocessing the Data for PCA
The first steps in the analysis consisted of cleaning and filtering the dataset (retrieve from CryptoCompare (https://min-api.cryptocompare.com/data/all/coinlist)).
Rows were filtered to exclude cryptocurrencies that are not currently being trading, to exclude rows with missing values and to include rows with total number of coins mined greater than zero. The resulting data frame had 532 rows in length.

***Include data frame image

In preparation for Principal Component Analysis (PCA), the categorical variables in the above data frame were transformed into dummy variables and the data was standardized.

### Reducing Data Dimensions Using PCA
In preparation for using the K-means algorithm, the next step was applying PCA to reduce the dimensions to three principal components.

***Include data frame image

### Clustering Cryptocurrencies Using K-means
An elbow curve was created using hvPlot to find the best value for K.

***Include elbow curve plot

Then, the K-means algorithm was executed to predict the K clusters for the cryptocurrencies.

### Visualizing Cryptocurrencies Results
The clusters can be visualized in the following scatterplots below.

***Include scatterplots

## Summary
In sum, 