<img src="https://i.imgur.com/UrPo5Fk.png" height = "100%" width="100%" alt = ">Airbnb Analysis for Cleaning Services"/>

<h1>Airbnb Listing Price Predictions with Tensorflow's Keras - Active Directory </h1>
<h2>Key Findings</h2>

With a root mean squared error (RMSE) of $66.22/night, a median price/night of $143, and 50% of listings falling between $85 and $230/night in the data, our model is currently not accurate enough in predicting prices/night for Airbnbs in NYC with our chosen features. 

Our model has an R² 0.6845 meaning our features can only account for 68.45% of the variation in the dataset. 

Because we are looking for relatively high percision in predicting prices, our model would benefit from more data and explanatory features of high priced listings to decrease the root mean squared errors.
 


<h2>Authors</h2>

<a href="https://github.com/Riley-livingston"> @RileyLivingston</a>

<h2>Description</h2>

 I used TensorFlow's Keras API to train a Neural network capable of predicting the price per night of Airbnb listings in New York City. The ultimate purpose of this project is to expand my machine learning toolset when analyzing data, and formulating models to solve business problems and making predictions.
<br />
<h2>Languages and Packages Used</h2>

- Python 3.10 | Numpy | Pandas | Sklearn | TensorFlow | MatPlotLib | Seaborn
  

<h2>Environments Used </h2>

- VScode
- Jupyter Notebooks

<h2>Data Source</h2>

- <a href="http://insideairbnb.com/get-the-data"> Airbnb detailed listings data NYC 09-07-2022</a>
- <a href="https://docs.google.com/spreadsheets/d/1iWCNJcSutYqpULSQHlNyGInUvHg2BoUGoNRIGa6Szc4/edit#gid=1322284596"> Data dictionary</a>

<h2>Methods</h2>

- Exploratory data analysis
- Feature Engineering
- Multivariate linear regression using neural networks

<h2>Data Analysis Process</h2>

<p align="left">
 <u>Business task</u>:
 
  - Create a TensorFlow Keras API neural network to predict the price per night for Airbnb listings in NYC. The network should be trained on a dataset containing information about Airbnb listings such as listing type, location, ratings, reviews, amenities, etc. 
  
  - The network should be able to predict the price of a listing based on the data it has been trained on. The accuracy of the predictions should be evaluated using a metric such as the Root mean squared error or the coefficient of determination.
 
  - KEY METRICS
    - The percent of variance that can be explained by our model or how well our model fits the data on the test set (R²).
    - Root mean squared error (RMSE) in $/night compared to the median price per night of a listing * We want to penalize large errors when predicting price per night so RMSE is chosen over the mean absolute error (MAE). We are choosing to use a median and IQR instead of a mean and STD becasue our chosen resposne variable, price/night is heavily skewed to the right. A median will provide us with a more accurate representation of the typical price per night. * 
    - The ratio of loss on the training data to loss on the validation data (loss/val loss).  
    - We want our validation data loss to be around the same as our testing data loss. This would mean that our model is fitted properly, most likely neither under or overfited to the training data. 
 
<br />
<p align="left">
 <u>Data preparation</u>: 
 
  Privacy and Accessability
 
   - Data for this analysis was scraped directly from Airbnb's website by third party <a href="https://insideairbnb.com"> insideairbnb</a>.
   - All data present in this repository as well as findings derived from analysis is publicly available information and falls under fair use. No private information is being used including names, listings, and review details as it is all publicly displayed on Airbnb’s website.
   
 
  Data Structure and Integrity
 
   - Data used in this analysis is organized in 1 table, listings, and columns in csv format. 
   - Integrity of the data source was verfified by choosing 10 random listings urls from the listings table listing_url column and comparing the listing information from the link to the data scraped and organized into columns in the dataset.
 <br />
 
<u>Analysis</u>:  
  <br />
  <a href="https://github.com/Riley-livingston/Tensorflow-Airbnb-Project/blob/main/airbnb_keras_linear_regression.ipynb"> Full Jupyter Notebook </a>
  <br />
  <br />
 
<u>Key findings</u>:
<br />
<br />
  <img src="https://i.imgur.com/WQtBLyJ.png" height = "50%" width="50%" alt = ">Validation Loss vs Training Loss"/>
 <br />
 <ul>
 
  <li> Our validation data converges with our training data and reaches an asymptote after about 200 epochs. Based on this metric, the model with our selected features and parameters isn't overfitting or underfitting the dataset and we can use it to generalize or make predictions on listings outside of our dataset. </li>
 <br />
 <li> However, we still have relatively high amount of error which indicates that our features don't explain enough of the variance in our dataset for it to be reliably useful in prdicting price per night which would require relatively high percision. </li>
 <br />
 <li> After about $300 per night, our model tends to underprdict listing prices. This could be due to features in the error term that are highly positivley correlated with exlusively high priced listings.</li>
 </ul>
 <br />
 <br />
  <img src="https://i.imgur.com/S9muXMN.png" height = "50%" width="50%" alt = "> Error Distribution"/>
 <br />
 <ul>
 <li>The error, or the actual prices in the testing data set - what our model predicted is normally distrbuted with a root mean squared error (RMSE) of about $76.75. With a mean price per night of $160 and a standard deviation of $114, I wouldn't recommend deploying the model with these features to predict prices of Airbnb Listings.</li>
 </ul>
 <br/>
 <br/>
  <img src="https://i.imgur.com/n6RyY48.png" height = "50%" width="50%" alt = ">Predicted vs Actual Prices"/>
 <br />
 <ul>
 <li> About 70% of the variance in the dataset can be explained by our model. It appears that the predictive power of our features decreases as the price of a listing increases (The size of the error tends to get larger as prices increase).</li>
 <br />
 <li> This could indicate that there is some feature in the error term present in high price listings we arent capturing in the model causing us to systematically  underpredict prices over ~$350 per night.</li>
 </ul>
 <br/>
 <br/>
 Future improvements/limitations:
<br/>
<ul>
<li> To further improve the model, the number and type of features to be included in the model should be determined by performing more advanced feature selection techniques such as correlation analysis, univariate analysis, and recursive feature elimination.</li>
<li> More feature engineering should be done in future iteration of this model, particularly on the amenitites column. We could transform this column by turning each word that appears into a dummy variable and then use feature elimination techniques to determine which specific amenities are most positively and negatively correlated with price per night.</li>
</ul>
