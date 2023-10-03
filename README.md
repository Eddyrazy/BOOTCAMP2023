# BOOTCAMP2023
QUESTION:Let’s say you’re a Product Data Scientist at Instagram. How would you measure the success of the Instagram TV product?"
In this role I will evaluate metrics such as viewership,watchtime and viewer retetion to measure the success of Instagram TV product.
I will use data obtained from Instagram users to measure this as follows:
#importing libraries
import pandas as pd
import xgboost as xgb
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score, classification_report

#loading data from source
Data=pd.read_csv(r'C:\Users\ADAM\Downloads\MOCK_DATA.csv')
# 1. Handling Missing Values
# Drop rows with missing values
data = data.dropna()
