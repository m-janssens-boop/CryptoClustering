# CryptoClustering
Background
---------
This Repository uses Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.
### Objectives
## Prepare the Data
- Use the `StandardScaler()` module from `scikit-learn` to normalize the data from the CSV file.
- Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
## Find the Best Value for k Using the Original Scaled DataFrame
- Use the elbow method to find the best value for `k` by:
  - Create a list with the number of `k` values from 1 to 11.
  - Create an empty list to store the inertia values.
  - Create a for loop to compute the inertia with each possible value of `k`.
  - Create a dictionary with the data to plot the elbow curve.
  - Plot a line chart with all the inertia values computed with the different values of `k` to visually identify the optimal value for `k`.
## Cluster Cryptocurrencies with K-means Using the Original Scaled Data
- cluster the cryptocurrencies for the best value for `k` on the original scaled data by:
  - Initialize the K-means model with the best value for `k`.
  - Fit the K-means model using the original scaled DataFrame.
  - Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
  - Create a copy of the original data and add a new column with the predicted clusters.
  - Create a scatter plot using hvPlot as follows:
    - Set the x-axis as "PC1" and the y-axis as "PC2".
    - Color the graph points with the labels found using K-means.
    - Add the "coin_id" column in the `hover_cols` parameter to identify the cryptocurrency represented by each data point.
## Optimize Clusters with Principal Component Analysis
- Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.
- Retrieve the explained variance to determine how much information can be attributed to each principal component.
- Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
## Find the Best Value for k Using the PCA Data
- Use the elbow method on the PCA data to find the best value for `k`.
## Cluster Cryptocurrencies with K-means Using the PCA Data
-  cluster the cryptocurrencies for the best value for `k` on the PCA data.
## Compare both methods using the plots created to highlight key differences
<img width="707" alt="Screenshot 2023-08-03 at 1 04 00 PM" src="https://github.com/m-janssens-boop/CryptoClustering/assets/127706155/09dc2586-438d-41ef-8c10-546dff335878">

<img width="708" alt="Screenshot 2023-08-03 at 1 03 48 PM" src="https://github.com/m-janssens-boop/CryptoClustering/assets/127706155/4d71e50a-aa34-4dae-a6de-058643d99076">
