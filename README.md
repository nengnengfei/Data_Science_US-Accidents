# US Accidents from February 2016 to Dec 2021: Project Overview
* Kaggle
* Information about accidents
* Can be useful to prevent accidents
* Mention that this dataset does not contain data about New York

## Code and Resources Used 
**Python Version:** 3.9  
**Packages:** pandas, Numpy, seaborn, folium  
**Dataset Kaggle:** https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents 

## Data Cleaning
After uploading the data, I needed to analyze and clean it up so that it was usable for our model. I looked at the information about the data and the columns:

*	Read the dataset to check how many rows and colums it contains
*	Checked the name and datatype of columns which present in the dataset
*	Calculated the aggregate statistics of DataFrame
*	Counted the number of numerical columns
*	Checked if there any missing value and presented as percentage of total 

## EDA
I looked at the distributions of the data and the value counts for the various categorical variables. Below are a few highlights from the analysis. 

![alt text](https://github.com/nengnengfei/Data_Science_US-Accidents/blob/main/accidents_by_city.png "Accidents by City")
![alt text](https://github.com/nengnengfei/Data_Science_US-Accidents/blob/main/occurrence_of_accidents_by_hour%20.png "Occurrence of Accidents by Hour")
![alt text](https://github.com/nengnengfei/Data_Science_US-Accidents/blob/main/occurrence_of_accidents_by_hour_Sunday%20.png "Occurrence of Accidents by Hour on Sundays")
![alt text](https://github.com/nengnengfei/Data_Science_US-Accidents/blob/main/occurrence_of_accidents_by_dayofweek.png "Occurrence of Accidents by Day of Week")
![alt text](https://github.com/nengnengfei/Data_Science_US-Accidents/blob/main/accidents_HeatMap.png "Accidents HeatMap")

## Summary 

Insights:
*	No data from New York
*	Less than 5% of cities have more than 1000 accidents
*	Over 1,100 cities have reported just 1 accident
*	Most accidents occurred during weekdays
