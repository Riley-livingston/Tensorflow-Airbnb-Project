<h1>Airbnb Listing Price Predictions with Tensorflow's Keras - Active Directory </h1>
<h2>Key Findings</h2>

With a root mean squared error (RMSE) of $67.79/night, a median price/night of $125 and 50% of listings failling between $75 and $200/night in the sample, our model is not very practical in predicting prices/night for Airbnbs in NYC with our chosen features. 

Our model has an R² 0.6532 meaning our features can only account for 65.32% of the variation inthe dataset. Because we are looking for relatively high percision in predicting prices, our overall model fit is not ideal.
 


<h2>Authors</h2>

<a href="https://github.com/Riley-livingston"> @RileyLivingston</a>

<h2>Description</h2>

 I used TensorFlow's Keras API to train a Neural network capable of predicting the price per night of airbnb listings in New York City. The ultimate purpose of this project is to develop and understanding of machiine learning model creation and selection, algorithms, and data analysis skills.

<br />

<h2>Languages and packages used</h2>

- Python 3.10 | Numpy | Pandas | Sklearn | TensorFlow | MatPlotLib | Seaborn
  

<h2>Environments used </h2>

- VScode
- Jupyter Notebooks

<h2>Data source</h2>

- <a href="https://drive.google.com/drive/folders/1Q2yFaDajfJ6hALKMCmrQbHnFhsti44bO?usp=sharing"> Airbnb detailed listings and reviews data NYC 09-07-2022</a>
- <a href="https://docs.google.com/spreadsheets/d/1iWCNJcSutYqpULSQHlNyGInUvHg2BoUGoNRIGa6Szc4/edit#gid=1322284596"> Data dictionary</a>

<h2>Methods</h2>

- Exploratory data analysis
- Feature Engineering
- Multivariate linear regression using Neural Networks

<h2>Data analysis process</h2>

<p align="left">
 <u>Business task</u>:
 
  - Create a Tensorflow Keras API neural network to predict the price per night for Airbnb listings in NYC. The network should be trained on a dataset containing information about Airbnb listings such as listing type, location, ratings, reviews, amenities, etc. 
  
  - The network should be able to predict the price of a listing based on the data it has been trained on. The accuracy of the predictions should be evaluated using a metric such as the Root mean squared error or the coefficient of determination.
 
  - KEY METRICS
    - The percent of variance that can be explained by our model or how well our model fits the data on the test set (R²) or, Explained Variance Score
    - Root mean squared error (RMSE) in $/night compared to the median price per night of a listing * We want to penalize large errors when predicting price per night so RMSE is chosen over the mean absolute error (MAE). We are choosing to use a median and IQR instead of a mean and STD becasue our chosen resposne variable, price/night is heavily skewed to the right. A median will provide us with a more accurate representation of the typical price per night. * 
    - The ratio of loss on the training data to loss on the validation data (loss/val loss).  
    - We want our validation data loss to be around the same as our testing data loss. This would mean that our model is fitted properly, most likely neither under or overfited to the training data. 
 
<br />
<p align="left">
 <u>Data preparation</u>: 
 
  PRIVACY AND ACESSABILITY
 
   - Data for this analysis was scrapped directly from Airbnb's website by third party <a href="https://insideairbnb.com"> insideairbnb</a>.
   - All data present in this repository as well as findings derived from analysis is publicly available information and falls under fair use. No private         information is being used including names, listings, and review details as it is all publicly displayed on Airbnb’s website.
   
 <br/>
  DATA STRUCTURE AND INTEGRITY
 
   - Data used in this analysis is organized in 2 tables (listings and reviews) and columns in csv format. 
   - Integrity of the data source was verfified by choosing 10 random listings urls from the listings table listing_url column and comparing the listing information from the link to the data scraped and organized into columns in the reviews and listings tables.

 
<br />
<br />
<u>Documentation of data processing and cleaning</u>: <br/>
  - 
 <br />
 
<u>Analysis</u>:  
  <br />
  <a href="https://github.com/Riley-livingston/Tensorflow-Airbnb-Project/blob/main/airbnb_keras_linear_regression.ipynb"> Jupyter Notebook Full ipynb File </a>
  <br />
  <br />
 
<u>Key findings</u>:
<br />
<br />
  <img src="https://i.imgur.com/3gN1xds.png" height = "50%" width="50%" alt = ">Validation Loss vs Training Loss"/>
  <img src="https://i.imgur.com/X3EkSPl.png" height = "50%" width="50%" alt = "> Error Distribution"/>
  <img src="https://i.imgur.com/m5wgz2y.png" height = "50%" width="50%" alt = ">Predicted vs Actual Prices"/>
 
  
 Future improvements/Limitations:
<br/>
<br/>
-To further improve the model, The number and type of features to be included in the model should be determined by performing feature selection techniques such as pruning, correlation analysis, univariate analysis, and recursive feature elimination.
<br />
<br />
-Principal Component analysis (PCA) could be used to reduce the number of features in the model down to the most important information. In practice this would be used on much larger sets of data to reduce redundant features and computational cost.
