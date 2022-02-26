# Clustering Cryptocurrencies with K-Means Method
Using unsupervised ML techniques to group cryptocurrencies into meaningful clusters.

## Overview
The goal of this project was to identify what cryptocurrencies are currently available on the trading market and how they can be grouped to create a classification system. Unsupervised Machine Learning techniques, such as Principal Component Analysis and K-Means, were used.

## Results
### Preprocessing the Data for PCA
The first steps in the analysis consisted of cleaning and filtering the dataset (retrieve from CryptoCompare(https://min-api.cryptocompare.com/data/all/coinlist)).
Rows were filtered to exclude cryptocurrencies that are not currently being traded, to exclude rows with missing values and to include rows with total number of coins mined greater than zero. The resulting data frame had 532 rows in length.

![Screen Shot 2022-02-25 at 11 32 10 AM](https://user-images.githubusercontent.com/89421440/155828740-da8cff18-ba41-4249-848e-501568ac707b.png)

In preparation for the model analysis, the categorical variables, "Algorithm" and "ProofType", were transformed into dummy variables and the data was standardized. The process of creating dummy variables increased the number of variables from 4 to 98. Principal Component Analysis was then needed to reduce the dimensionality of the dataset.

### Reducing Data Dimensions Using PCA
In preparation for using the K-means algorithm, the next step was applying PCA to reduce the dataset dimensions from 98 to 3 principal components.

![Screen Shot 2022-02-25 at 11 39 28 AM](https://user-images.githubusercontent.com/89421440/155828942-ecf07e88-fdb2-4fbc-bae0-66eaaba0d264.png)

### Clustering Cryptocurrencies Using K-means
The next step was creating an elbow curve plot using hvPlot to find the best value for K, as the number of distinct clusters to group the dataset.

![ElbowCurve_plot](https://user-images.githubusercontent.com/89421440/155829274-b228ae27-992c-4fa1-8143-706cefe526e0.png)

The elbow curve plot above shows a clear change in the 4 mark, so K was set to 4. Then, the K-means algorithm was executed to predict the 4 distinct clusters for the cryptocurrencies.

### Visualizing Cryptocurrencies Results
The 4 distinct clusters can be visualized in the following scatterplots.

![3D_Scatter_plot](https://user-images.githubusercontent.com/89421440/155829433-b5b03a33-0dd5-438f-bbb8-75e50a61efd1.png)

The 3-D scatter plot above shows that two clusters (Classes 0 and 1) gather the majority of cases, 525 out of 532. Class 3 gathers only a small group of 6 data points. While class 2 has a single data point, BitTorrent, that could be treated as a potential outlier.

![Scatter_plot](https://user-images.githubusercontent.com/89421440/155829439-480c9a1b-9820-4fc7-9552-0114c54cbe26.png)

The 2-D scatter plot above adds more meaning to the clusters. BitTorrent seems to be the only cryptocurrency in high demand and high supply in the dataset. Turtle Coin in Class 1 can also be treated as a potential outlier, as it's the only cryptocurrency with high sypply and low demand. Most of the other data points are in low demand and low supply. Class 1 appears to lean towards low to moderate demand and supply.

## Summary
In sum, cryptocurrencies data was analyzed using an unsupervised machine learning model. Specifically, cryptocurrencies were gathered in 4 different clusters using the K-means algorithm. Overall, the model generated meaningful classification. Still, some further factors might need to be considered for model improvement. The first factor is the presence of potential outliers, in particular BitTorrent and Turtle Coin. The second factor is that reducing the dimensionality of the data to 3 dimensions might need to be reevaluated as 3 dimension only accounted for 7% of the variance in the dataset. Finally, Inertia in the K-means algorithm might need to be minimized as the value for this model was 501.998

