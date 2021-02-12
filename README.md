# ChurnPrediction

## Introduction
I wanted to leverage this dataset of credit card customers (https://www.kaggle.com/sakshigoyal7/credit-card-customers) from Kaggle to analyze what features contribute to churn, and then use a Random Forest classifier to predict which customers will churn. 

## Data Exploration and Analysis
The dataset had a variety of features including gender, age, marital status and account level information. First, I explored the distribution of the features related to customer profiles understand what the customers look like, and what the attrition rates of the dataset look like. I also wanted to see if any particular features appeared to be correlated with attrited customers vs. existing customers.

When layering age and attirtion, there didn't seem to be any striking trend between age and attrtion rates. Tenure, or months on book, didn't have a particular impact on attrition rates either; although there appeared to be a lot of customers who had a tenure of 36 months (3 years). In this particular dataset, other factors like education level, gender, marital status and product type didn't seem to impact attrition rates either. Overall, this initial exploratory analysis showed that demographic or profile features of the customers didn't have a significant correlation with attrition.

I also looked at the distribution of continuous vairables, and layered attrited and existing customers to visualize any relationships between the features and attrition. It's clear that account-specific metrics, such as transaction amount and transaction count, have a relationship with attrition. Customers who transact less on their credit card are more likely to attrite. This makes sense intuitively, as customers who use a product more regurlarly are more engaged and less likely to attrite. Revolving balance has an interesting relationship; the group with with $0 of revolving balance are evenly split by attrited and existing customers; this is likely because a good portion of customers who actively use their credit card also pay it down regularly.

## Data Preparation and Preprocessing
Since I wanted to train the data with a a Random Forest classifier, I had to take the categorical variables and one-hot-encode them to create numerical variables that could feed into the classifier. I also had to scale the features since I was interested in exploring feature importance. Then, I split the data into test and train sets (using a 20/80 split), and leveraged the Random Forest Classifier from the scikit-learn library to score the results.

## Model Results
The model did a pretty good job with correctly classifying customers who will churn. I also compared the model performance on the training set and testing set to understand overfitting. Although the test set performed quite well, the training set performed better, indicating that the model did overfit the training data.

## Feature Importance
To understand the business implications of this data set and the churn model, it's important to understand how much each feature contributes to customer churn. I leveraged two methods for this; one using the classifier's feature importance function. This showed that the account-related metrics, such as utilization, revolving balance, and transaction were the most important features. This supports the data exploration, which showed that there was a more direct relationship between account-related factors like transaction counts/amounts and attrition. These insights could be leveraged to explore ways to engage customers by promoting credit card usage through messaging and incentives.

