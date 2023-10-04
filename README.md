# BOOTCAMP2023
QUESTION:Let’s say you’re a Product Data Scientist at Instagram. How would you measure the success of the Instagram TV product?"
In this role I will evaluate metrics such as viewership,watchtime and viewer retetion to measure the success of Instagram TV product.
I will use data obtained from Instagram users to measure this as follows:
**(i) Viewership:**
	
The viewership metric for IGTV measures the total number of times your IGTV videos have been viewed by users on Instagram. It provides valuable insights into the reach and engagement of your video content. Viewership can be expressed as a cumulative count across all your IGTV videos or as an average view count per video.
**Formulae for Calculating Viewership Metric:**
Total View Count (Cumulative):
The total view count represents the sum of views for all your IGTV videos.
    > **Formula: Total View Count = View Count of Video 1 + View Count of Video 2 + ... + View Count of Video x**
**(ii) Watch Time:** 
Watch time is an essential metric for evaluating the engagement and retention of your IGTV video content. It quantifies the cumulative amount of time viewers have dedicated to watching your videos. This metric helps you assess the overall impact and effectiveness of your video content strategy.
**Formula for Calculating Watch Time Metric:**
The formula for calculating the watch time metric on IGTV is straightforward. It involves summing up the total duration of time users have spent watching your videos:
    > **Watch Time (in seconds) = Duration of Video 1 (in seconds) + Duration of Video 2 (in seconds) + ... + Duration of Video x (in seconds)**
**(iii) User Retention:**
User retention, often expressed as a percentage, measures the proportion of viewers who watch a significant portion of your IGTV video content without dropping off. It helps assess the quality of your content and its ability to keep viewers engaged throughout the video's duration.
Let’s say that a successful threshold for User Retention for Instagram TV is 80%, this would act as a benchmark to gauge its success.
**Formula for Calculating User Retention Metric:**
The formula for calculating user retention on IGTV involves determining the percentage of viewers who watched a specific portion of the video (e.g., from the beginning to a specified time point). The formula is as follows:
   > User Retention (%) = (Number of Viewers at Time T / Total Views) x 100 (expressed as a percentage).
**Here's the process I would take to solve this question:**
**1. Collect Data:** Gather data related to your IGTV content, such as video duration, content category, post date, and any other relevant features. Also, include the user engagement metric you want to predict, such as user retention.
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

# 2. Removing Duplicates
data = data.drop_duplicates()

# Separate features (X) and target variable (y)
X = data.drop("videos", axis=1)
y = data["videos"
         
# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Initialize and train the XGBoost model
model = xgb.XGBClassifier()
model.fit(X_train, y_train)

# Make predictions on the test set
y_pred = model.predict(X_test)

# Evaluate the model's accuracy
accuracy = accuracy_score(y_test, y_pred)
print(f"The accuracy of this model is: {accuracy:.2f}")

# Generate a classification report for detailed metrics
report = classification_report(y_test, y_pred)
print("Classification Report:\n", report)]
This will provide you with metrics like the accuracy of the model, precision, and F1-score to gauge the performance of your model.
**#Interpret the results**
I interpreted the results and came to the conclusion that IGTV is a success according to the user engagement metric.
