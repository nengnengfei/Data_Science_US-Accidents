# US Accidents from February 2016 to Dec 2021: Project Overview
* Created a tool that estimates data science salaries (MAE ~ $ 11K) to help data scientists negotiate their income when they get a job.
* Scraped over 1000 job descriptions from glassdoor using python and selenium
* Engineered features from the text of each job description to quantify the value companies put on python, excel, aws, and spark. 
* Optimized Linear, Lasso, and Random Forest Regressors using GridsearchCV to reach the best model. 
* Built a client facing API using flask 

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

## Model Building 

First, I transformed the categorical variables into dummy variables. I also split the data into train and tests sets with a test size of 20%.   

I tried three different models and evaluated them using Mean Absolute Error. I chose MAE because it is relatively easy to interpret and outliers aren’t particularly bad in for this type of model.   

I tried three different models:
*	**Multiple Linear Regression** – Baseline for the model
*	**Lasso Regression** – Because of the sparse data from the many categorical variables, I thought a normalized regression like lasso would be effective.
*	**Random Forest** – Again, with the sparsity associated with the data, I thought that this would be a good fit. 

## Model performance
The Random Forest model far outperformed the other approaches on the test and validation sets. 
*	**Random Forest** : MAE = 11.22
*	**Linear Regression**: MAE = 18.86
*	**Ridge Regression**: MAE = 19.67

## Productionization 
In this step, I built a flask API endpoint that was hosted on a local webserver by following along with the TDS tutorial in the reference section above. The API endpoint takes in a request with a list of values from a job listing and returns an estimated salary.
