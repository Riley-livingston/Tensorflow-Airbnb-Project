<img src="https://i.imgur.com/OcLOedO.jpg" height = "100%" width="100%" alt = ">Airbnb Analysis for Cleaning Services"/>

<h1>Airbnb Listings Price Predictions with Tensorflow's Keras - Active Directory </h1>
<h2>Key Findings</h2>

The predicted impact of every dirty review on a listing is -0.036 days booked out of 90. At the 95% confidence level, dirty reviews per listing's impact on days booked out of 90 is significant with a p-value of 0.032 and an overall model fit (R²) of 0.126.
 


<h2>Authors</h2>

<a href="https://github.com/Riley-livingston"> @RileyLivingston</a>

<h2>Description</h2>
This project consists of exploritory analysis and a multivariate linear regression of publicly available Airbnb data. This directory will guide you through the steps I took and thought process in determining the relationship between dirty reviews in Airbnb listings and days booked out of 90. Version 1 of the Airbnb Listings Analysis for Cleaning Services project that showcasees SQL and Tableau can be found <a href="https://github.com/Riley-livingston/AirBnb-Listings-Analysis-for-Cleaning-Services"> here. </a>

<br />

<h2>Languages and packages used</h2>

- MySQL
- Python 3.10 | Numpy | Pandas | Sklearn
  

<h2>Environments used </h2>

- VScode
- Jupyter Notebook
- Dbeaver 22.2.2

<h2>Data source</h2>

- <a href="https://drive.google.com/drive/folders/1Q2yFaDajfJ6hALKMCmrQbHnFhsti44bO?usp=sharing"> Airbnb detailed listings and reviews data NYC 09-07-2022</a>
- <a href="https://docs.google.com/spreadsheets/d/1iWCNJcSutYqpULSQHlNyGInUvHg2BoUGoNRIGa6Szc4/edit#gid=1322284596"> Data dictionary</a>

<h2>Methods</h2>

- Exploratory data analysis
- Multivariate linear regression

<h2>Data analysis process</h2>

<p align="left">
 <u>Business task</u>:
 
- Determine if there is a relationship between reviews that indicate uncleanliness of an airbnb listing and days booked out of a 90 day period.
- If that relationship exists, what is the impact of every dirty review on average days booked out of 90 for a listing on Airbnb in NYC's 5 boroughs?
 
  - KEY METRICS
    - p-value, or statistical significance of the beta coefficent of the dirty_review variable/feature on days booked out of 90 for a listing.
 
    - the value of the beta coefficent of the dirty review variable used in the model. A positve coefficent would indicate that dirty reviews have a postive impact on bookings while a negative beta coefficent would indicate a negative impact. A larger or smaller beta coefficents would indicate a larger impact on bookings.

    - R² or overall fit of the model. An R² closer to one would indicate that the model is really good at predicting bookings for the next 90 days.
 
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
  - <a href="https://github.com/Riley-livingston/Airbnb-Listings-Analysis-for-Cleaning-Services-v2/blob/main/dirty_reviews_v2.sql"> SQL script to clean and filter the data.sql</a>
 <br />
  - <a href="https://github.com/Riley-livingston/Airbnb-Listings-Analysis-for-Cleaning-Services-v2/blob/main/clean_and_filtered_airbnb_data_v2.csv"> Cleaned and filtered data.csv</a>
 <br />
 <br />
<img src="https://i.imgur.com/AKSoy6j.png" height = "100%" width="100%" alt = ">SQL select statement with explaination"/>
   - Days a listing is booked out of 90 is calculated by substracting 90 from the availability_90 feature. This calculated feature will be the target variable in this analysis, The feature that is being predicted.
   <br />
   <br />
   - Distinct reviews are counted in the select statement. The impact of review count with the condition of indicating uncleanliness will be the feature of interest in [redicting bookings in this analysis.
 <br />
 <br /> 
 
<img src="https://i.imgur.com/Vhpkstx.png" height = "100%" width="100%" alt = ">SQL Join statement and conditions for dirty reviews with explaination"/>
   - The first part of the where statement includes a list of words that serve as conditions for returning a count of distinct dirty reviews a listing has.
   <br />
   <br />
   - I included the most popular words by usage that indicate uncleanliness. 
   <br />
   <br />
   - Each distinct review will be counted where any one or more of these words listed shows up. Reviews where these words dont show up will not be counted in the dirty review count feature. 
 <br />
 <br />
<img src="https://i.imgur.com/HSBhnqs.png" height = "100%" width="100%" alt = ">SQL more filtering and group by order by conditions with explaination"/>
    - The second part of the where statement includes conditions that only return rows where listings are booked at less than 365 days out of 365. The reasoning behind this was Airbnb doesnt differeienciate between unavailable and fully booked listings. Listings displayed as 365 days booked are extremely likely to be simply unavailable rather than booked for an entire year. THe same logic applies to listings that are booked 0 days in the next 365
 <br />
 <br />
  - Rows are filtered out where price per night is less than $2. a few listings exist in the data where the price is either 2 or 1 dollar. This is innacurate information and excluded from the analysis.
 <br />
 <br />
 - The query is grouped by listing url and listing id to ensure that each row represnts a unique listing.
 <br />
 <br />
 - The query is finally ordered by dirty review count and host_id in order to gain immediate insight into the lsiitngs with the most dirty reviews.
  <br />
  <br />
  
<u>Analysis</u>:  
  <br />
  <a href="https://github.com/Riley-livingston/Airbnb-Listings-Analysis-for-Cleaning-Services-v2/blob/main/airbnb_analysis_for_cleaning_services_v2.ipynb"> Jupyter Notebook Full ipynb File </a>
  <br />
  <br />
 
<u>Key findings</u>:
<br />
<br />
  -At the 95% confidence level, dirty reviews per listing's impact on days booked out of 90 is insignificant with a p-value of 0.138.
<br />
<br />
  -Overall fit of the model to the data (R²) is 0.126.
<br />
<br />
  -The beta coefficent of the dirty reviews feature is -0.21 indicating that every dirty review is expected to decrease average days booked out of 90 by 0.21 days.
<br />
<br />
  
Limitations:
 <br />
 <br />
  -The data and results of the analysis are a snapshot of listings available from Airbnb on and before September 7th 2022. Hosts may remove or add listings at anytime and renters may post or delete reviews at anytime which may impact the results of the analysis. Seasonality bias may be present in the number of reviews that contain 'dirty' words indicating uncleanliness.
<br />
<br />
  -The words used to measure dirty reviews are all weighted the same but each dirty review may differ in the severity of the uncleanliness. This would result in the beta coefficent of dirty reviews to over or understate the impact on bookings.
<br />
<br />
  -A list of words was selected to search for dirty reviews in the communts column of the reviews table. This list may not represnted all of the ways a person would describe uncleanliness and lead to some reviews not being included in the analysis impacting the beta coefficent of the dirty review factor in the model's impact on bookings.
<br/>
<br/>
 Future improvements:
<br/>
<br/>
-To further improve the model in predicting bookings, a backward stepwise regression apporach can be used to determine what features in the model are statistically significant in the overall model fit. An F test can be used to compare models and ultimatly arrive at the model that best fits the population.
<br />
<br />
-Inserting a new column that contains strings of 'dirty' words we want to search for in the comments column. This would improve readability in the sql script as we could use the IN opoerator to search for words in a set of values rather than many OR and LIKE statements.
