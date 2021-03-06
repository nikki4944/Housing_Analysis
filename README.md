# Housing Data Analysis

## Project Overview

For the final project, the team performed an analysis of housing data for Montgomery County, Marland, from January 2016 through September 2021. The data was analyzed to see if any trends could be detected in the data that might have been impacted by the COVID-19 pandemic. Finally, a supervised machine learning model was built to determine if housing prices could be predicted based on the collected real estate information.

The data consisted of a .csv file obatined from the real estate MLS database which provided comprehensive housing information for each home sold in Montgomery County over the past five years. The information in the .csv file was parred down to contain the core elements determined by the group to be most relevant to the analysis.

<img width="326" alt="Screen Shot 2021-09-26 at 5 39 07 PM" src="https://user-images.githubusercontent.com/82982901/134825053-6cb0d9ba-6ae5-490d-a8ab-8c74dbd06e09.png">

## Technology Overview

The team used the Pandas library for cleaning and scraping the data, PostgreSQL to store the dataset, SQLAlchemy to connect the database, and the SciKitLearn library for compiling the machine learning model. Additionally, the dashboard and all visuals for the analysis were created using Tableau.

## Results of Analysis

The analysis found three key areas where the COVID-19 pandemic appears to have impacted the housing market: time to market, total number of homes sold, and average home price.

* First, the biggest impact of the pandemic on the housing market has been the amount of time properties remain on the market. As the following image shows, the average time a property was on the market has been cut in half from it's high of 120 days in April 2016 to less than 60 days in June 2021.
<img width="978" alt="Screen Shot 2021-09-29 at 1 15 03 PM" src="https://user-images.githubusercontent.com/82982901/135317351-90ed4d96-f347-433c-9ef9-f906c5d3e71c.png">

* Second, the total number of homes sold in Montogomery County increased dramatically beginning in Q2 of 2019, a 35% increase from the previous year. Following the on-set of the pandemic in 2020, the usual pattern of busy season for buying has remained the same, with Q1 averaging the least number of sales per year; however, the other three quarters have reported significant increases in sales compared to pre-2019 numbers. The increased volume of sold homes has not returned to pre-2019 levels and is continuing to trend upward.
<img width="864" alt="Screen Shot 2021-09-29 at 1 29 46 PM" src="https://user-images.githubusercontent.com/82982901/135321184-cbf4231b-acaa-4f07-8888-cc15a7049178.png">

* Finally, the average housing price has risen by $100,000 since the pandemic began. However, while this is a significant increase, it is in line with the data from previous years.
<img width="866" alt="Screen Shot 2021-09-29 at 1 17 54 PM" src="https://user-images.githubusercontent.com/82982901/135318451-5506f86e-08e0-493c-9df7-d5c869e1c1db.png">

## Machine Learning Model

### Data Preprocessing

The machine learning models were created using our previously cleaned .csv file of housing information obtained from the real estate MLS database. The original data set contained over 100 columns which were trimmed down to seventeen of the most important as determined by the group.

For the machine learning model, the seventeen columns, or features, were trimmed down further to only contain the following: Sold Price, New Construction YN, Age, InteriorSqFt, Bedrooms, Baths, Garage YN, #ofStories, and Stucture Type. The Sold Price column was further preproccessed by removing the "$" and "," from the number. The final step was to run .get_dummies() on the dataframe to convert all features to numerical values.

### Feature Selection

The model is designed to predict housing prices based on the features provided for analysis. The Sold Price column was designated as the target with the New Construction UN, Age, InteriorSqFt, Bedrooms, Baths, Garage YN, #ofStories, and Structure Type columns used as the features. 

### Training and Testing

The data was split into 20% testing and 80% training sets.

### Model Choice

Two supervised machine learning models were created in order to determine the most accurate model for predicting housing prices using this dataset.

* First, a Multiple Linear Regression model was created which yielded a 56% testing accuracy and a 59% training accuracy.

<img width="715" alt="Screen Shot 2021-09-22 at 9 29 35 PM" src="https://user-images.githubusercontent.com/82982901/134824560-60cd78a9-ac3c-4f9b-95ca-53d15506b3eb.png">

* Second, a Random Forest Regression model was created wich yielded a 96% training accuracy and a 71% testing accuracy.

<img width="720" alt="Screen Shot 2021-09-22 at 9 31 19 PM" src="https://user-images.githubusercontent.com/82982901/134824553-b2f12a50-1669-4b03-934a-4980fe79a1f6.png">

The Random Forest Regression model is preferred for this project as it has better control over overfitting as well as using averages to improve predictive accuracy. Expansion of the features based on the recommendations in the next section are expected to increase the testing accuracy of the Random Forest Regression model.

## Summary

The analysis successfully identified three areas where the pandemic has started to impact the housing market in Montgomery County. Additionally, the machine learning model is able to predict housing prices based on the data with a 71% accuracy.

This analysis is limited as it only takes into account information pertaining directly to the property, location, and features of the house. The analysis would benefit from the inclusion of school district ratings; metro and trasportation statistics, such as proximity to address; demographic information, such as age and salary of buys; and inflation information. 

## Presentation
The Google Slides presentation can be found [here](https://docs.google.com/presentation/d/1-4T5Qp4jW8rH_IEMHoFSeD3qF8_sQpcPtzCkrLryhHk/edit?usp=sharing).

The full Tableau visualizations can be found  [here](https://public.tableau.com/authoring/Dashboard_16320975806010/Story1#1) and [here](https://public.tableau.com/app/profile/adam.paseltiner/viz/FinalProject_16321823013550/MontgomeryCountyHomesPrePostCOVID?publish=yes).
