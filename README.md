# Unsupervised-Machine-Learning-Crypto

**Background**

I created a report that includes what cryptocurrencies are on the trading market and determine whether they can be grouped to create a classification system.

**Data Preparation**

    - Read crypto_data.csv into Pandas. The dataset was obtained from CryptoCompare.

    - Discard all cryptocurrencies that are not being traded. In other words, filter for currencies that are currently being traded. After, drop the IsTrading column from the dataframe.

    - Remove all rows that have at least one null value.

    - Filter for cryptocurrencies that have been mined (Total coins mined should be greater than zero).

    - For the machine learning algorithm, its data should be numeric.  Since the coin names do not contribute to the analysis of the data, delete the CoinName from the original dataframe.

    - Convert the remaining features with text values, Algorithm and ProofType, into numerical data. Used Pandas to create dummy variables. 

    - Standardize your dataset so that columns that contain larger values do not unduly influence the outcome.
    
**Dimensionality Reduction**

Creating dummy variables dramatically increased the number of features in your dataset. Therefore, I completed dimensionality reduction with PCA. Rather than specify the number of principal components when you instantiate the PCA model, I stated the desired explained variance. Using PCA(n_components=0.99) creates a model that will preserve approximately 99% of the explained variance, whether that means reducing the dataset to 80 principal components or 3. For this project, I preserved 90% of the explained variance in dimensionality reduction. 

Next, I further reduced the dataset dimensions with t-SNE and visually inspect the results. In order to accomplish this task, I ran t-SNE on the principal components: the output of the PCA transformation. Then created a scatter plot of the t-SNE output. 

![Screen Shot 2022-03-12 at 3 25 01 PM](https://user-images.githubusercontent.com/87212158/158033831-05e0d703-5427-4c78-967f-7b0370c27798.png)

**Cluster Analysis with k-Means**

I created an elbow plot to identify the best number of clusters. Use a for-loop to determine the inertia for each k between 1 through 10.

Both the t-SNE and an elbow plot using k-means suggest that there are not meaningful clusters found in the dataset.

![Screen Shot 2022-03-12 at 3 24 14 PM](https://user-images.githubusercontent.com/87212158/158033787-e2556a32-fff6-4975-858c-2e6ca782f0b8.png)

![Screen Shot 2022-03-12 at 3 23 53 PM](https://user-images.githubusercontent.com/87212158/158033776-330f50f3-659c-4f46-918e-a0966cadee9b.png)
