# Cryptocurrencies

# Overview and Backbround 

You and Martha have done your research. You understand what unsupervised learning is used for, how to process data, how to cluster, how to reduce your dimensions, and how to reduce the principal components using PCA. It’s time to put all these skills to use by creating an analysis for your clients who are preparing to get into the cryptocurrency market.

Martha is a senior manager for the Advisory Services Team at Accountability Accounting, one of your most important clients. Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they’ve asked you to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data Martha will be working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what Martha is looking for, she has decided to use unsupervised learning. To group the cryptocurrencies, Martha decided on a clustering algorithm. She’ll use data visualizations to share her findings with the board.

What You're Creating
This new assignment consists of four technical analysis deliverables. You will submit the following:

- Deliverable 1: Preprocessing the Data for PCA
- Deliverable 2: Reducing Data Dimensions Using PCA
- Deliverable 3: Clustering Cryptocurrencies Using K-means
- Deliverable 4: Visualizing Cryptocurrencies Results

# Results

## Deliverable 1: Preprocessing the Data for PCA
Instructions: Using your knowledge of Pandas, you’ll preprocess the dataset in order to perform PCA in Deliverable 2.

Follow the instructions below and use the crypto_clustering_starter_code.ipynb file to complete Deliverable 1.

Open the crypto_clustering_starter_code.ipynb file, rename it crypto_clustering.ipynb, and save it to your Cryptocurrencies GitHub folder.

Read in the crypto_data.csv to the Pandas DataFrame named crypto_df.
NOTE
The crypto_data.csv was retrieved from CryptoCompare (Links to an external site.).

Keep all the cryptocurrencies that are being traded.
Drop the IsTrading column.
Remove rows that have at least one null value.
Filter the crypto_df DataFrame so it only has rows where coins have been mined.
Create a new DataFrame that holds only the cryptocurrency names, and use the crypto_df DataFrame index as the index for this new DataFrame.
Remove the CoinName column from the crypto_df DataFrame since it's not going to be used on the clustering algorithm.
Take a moment to check that your crypto_df DataFrame looks like the image below

D1.png



## Deliverable 2: Reducing Data Dimensions Using PCA

Using your knowledge of how to apply the Principal Component Analysis (PCA) algorithm, you’ll reduce the dimensions of the X DataFrame to three principal components and place these dimensions in a new DataFrame.Follow the instructions below and use the information in the crypto_clustering_starter_code.ipynb file to complete Deliverable 2.

Continue using the crypto_clustering.ipynb file from Deliverable 1 where you’ve already performed the preprocessing steps.
Using the information we’ve provided, apply PCA to reduce the dimensions to three principal components.
If you’d like a hint on how to use the PCA algorithm, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

HINT
Create a new DataFrame named pcs_df that includes the following columns, PC 1, PC 2, and PC 3, and uses the index of the crypto_df DataFrame as the index.
Your DataFrame should look like the image below

D2.png

## Deliverable 3: Clustering Cryptocurrencies Using K-means

Using your knowledge of the K-means algorithm, you’ll create an elbow curve using hvPlot to find the best value for K from the pcs_df DataFrame created in Deliverable 2. Then, you’ll run the K-means algorithm to predict the K clusters for the cryptocurrencies’ data.

Follow the instructions below and use the information in the crypto_clustering_starter_code.ipynb file to complete Deliverable 3.

Continue using the crypto_clustering.ipynb file that you used in Deliverable 2 to reduce the dataset to three dimensions.
Using the pcs_df DataFrame, create an elbow curve using hvPlot to find the best value for K.
Next, use the pcs_df DataFrame to run the K-means algorithm to make predictions of the K clusters for the cryptocurrencies’ data.
If you’d like a hint on how to use the K-means algorithm, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

Create a new DataFrame named clustered_df by concatenating the crypto_df and pcs_df DataFrames on the same columns. The index should be the same as the crypto_df DataFrame.
Add the CoinName column that holds the names of the cryptocurrencies, which you created in Step 7 of Deliverable 1, to the clustered_df.
Add another new column to the clustered_df named Class that holds the predictions, i.e., model.labels_, from Step 3.
Your clustered_df DataFrame should look like the image below:

D3.png


## Deliverable 4: Visualizing Cryptocurrencies Results

Using your knowledge of creating scatter plots with Plotly Express and hvplot, you’ll visualize the distinct groups that correspond to the three principal components you created in Deliverable 2, then you’ll create a table with all the currently tradable cryptocurrencies using the hvplot.table() function.

Follow the instructions below and use the information in the crypto_clustering_starter_code.ipynb file to complete Deliverable 4.

Continue using the crypto_clustering.ipynb file from Deliverable 3 where you have predicted the K clusters for the cryptocurrencies’ data.
Create a 3D scatter plot using the Plotly Express scatter_3d() function to plot the three clusters from the clustered_df DataFrame.
Add the CoinName and Algorithm columns to the hover_name and hover_data parameters, respectively, so each data point shows the CoinName and Algorithm on hover.
If you’d like a hint on how to add additional parameters to a Plotly Express 3D scatter plot, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

Create a table with tradable cryptocurrencies using the hvplot.table() function.
If you’d like a hint on how to use the hvplot.table() function, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

Your table should look like the table in the image below:

D4.png



Print the total number of tradable cryptocurrencies in the clustered_df DataFrame.
Use the MinMaxScaler().fit_transform method to scale the TotalCoinSupply and TotalCoinsMined columns between the given range of zero and one.
If you’d like a hint on how to use the MinMaxScaler().fit_transform method to scale the "TotalCoinSupply" and "TotalCoinsMined" columns, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

Create a new DataFrame using the clustered_df DataFrame index that contains the scaled data you created in Step 5.
Add the CoinName column from the clustered_df DataFrame to the new DataFrame.
Add the Class column from the clustered_df DataFrame to the new DataFrame.
Your new DataFrame should look similar to the image below:

D4.1.png

Create an hvplot scatter plot with x="TotalCoinsMined", y="TotalCoinSupply", and by="Class", and have it show the CoinName when you hover over the the data point.
If you’d like a hint on how to add the CoinName column data when you hover over a data point, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

D4.1.2.png


# Summary 

