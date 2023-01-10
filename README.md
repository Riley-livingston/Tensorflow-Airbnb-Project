<h1>Airbnb Listing Price Predictions with Tensorflow's Keras - Active Directory </h1>
<h2>Key Findings</h2>

Key Findings Here
 


<h2>Authors</h2>

<a href="https://github.com/Riley-livingston"> @RileyLivingston</a>

<h2>Description</h2>

Description Here

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
 
  - Business task here
  - Business task here
 
  - KEY METRICS
    - The percent of varaince that can be explained by our model or how well our model fits the data on the test set (R²) or, Explained Variance Score
    - Root mean squared error (RMSE) * We want to penalize large errors when predicting price per night so RMSE is chosen over the mean absolute error (MAE) * 

    - 
 
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
  <a href="https://github.com/Riley-livingston/Airbnb-Listings-Analysis-for-Cleaning-Services-v2/blob/main/airbnb_analysis_for_cleaning_services_v2.ipynb"> Jupyter Notebook Full ipynb File </a>
  <br />
  <br />
 
<u>Key findings</u>:
<br />
<br />
  -
  
Limitations:
 <br />
 <br />
  -
<br/>
<br/>
 Future improvements:
<br/>
<br/>
-To further improve the model in predicting bookings, a backward stepwise regression apporach can be used to determine what features in the model are statistically significant in the overall model fit. An F test can be used to compare models and ultimatly arrive at the model that best fits the population.
<br />
<br />
-
