---
bg: "tools.jpg"
layout: post
title: Project Predict Credit Card Approvals-Python
crawlertitle: Python Project
summary: Description for this article
date:   2021-08-10
categories: posts
tags: ['Python']
author: Irene Y.
bg: "african-penguins.jpg"
---
1. Credit card applications

Commercial banks receive a lot of applications for credit cards. Many of them get rejected for many reasons, like high loan balances, low income levels, or too many inquiries on an individual's credit report, for example. Manually analyzing these applications is mundane, error-prone, and time-consuming (and time is money!). Luckily, this task can be automated with the power of machine learning and pretty much every commercial bank does so nowadays. In this notebook, we will build an automatic credit card approval predictor using machine learning techniques, just like the real banks do.

Use the Credit Card Approval dataset from the UCI Machine Learning Repository. The structure of this notebook is as follows:

First, start off by loading and viewing the dataset.
The dataset has a mixture of both numerical and non-numerical features, that it contains values from different ranges, plus that it contains a number of missing entries. 
Preprocess the dataset to ensure the machine learning model we choose can make good predictions.
After our data is in good shape, we will do some exploratory data analysis to build our intuitions.
Finally, we will build a machine learning model that can predict if an individual's application for a credit card will be accepted.
First, loading and viewing the dataset. We find that since this data is confidential, the contributor of the dataset has anonymized the feature names.

cc_apps = ...

2. Inspecting the applications
The output may appear a bit confusing at its first sight, but let's try to figure out the most important features of a credit card application. The features of this dataset have been anonymized to protect the privacy, but this blog gives us a pretty good overview of the probable features. The probable features in a typical credit card application are Gender, Age, Debt, Married, BankCustomer, EducationLevel, Ethnicity, YearsEmployed, PriorDefault, Employed, CreditScore, DriversLicense, Citizen, ZipCode, Income and finally the ApprovalStatus. This gives us a pretty good starting point, and we can map these features with respect to the columns in the output.

As we can see from our first glance at the data, the dataset has a mixture of numerical and non-numerical features. This can be fixed with some preprocessing, but before we do that, let's learn about the dataset a bit more to see if there are other dataset issues that need to be fixed.

cc_apps_description = ...
print(cc_apps_description)

print('\n')

cc_apps_info = ...
print(cc_apps_info)

print('\n')

3. Splitting the dataset into train and test sets
Now, we will split our data into train set and test set to prepare our data for two different phases of machine learning modeling: training and testing. Ideally, no information from the test data should be used to preprocess the training data or should be used to direct the training process of a machine learning model. Hence, we first split the data and then preprocess it.

Also, features like DriversLicense and ZipCode are not as important as the other features in the dataset for predicting credit card approvals. To get a better sense, we can measure their statistical correlation to the labels of the dataset. But this is out of scope for this project. We should drop them to design our machine learning model with the best set of features. In Data Science literature, this is often referred to as feature selection.

cc_apps = ...

cc_apps_train, cc_apps_test = train_test_split(..., test_size=0.33, random_state=42)

4. Handling the missing values (part i)
Now we've split our data, we can handle some of the issues we identified when inspecting the DataFrame, including:

Our dataset contains both numeric and non-numeric data (specifically data that are of float64, int64 and object types). Specifically, the features 2, 7, 10 and 14 contain numeric values (of types float64, float64, int64 and int64 respectively) and all the other features contain non-numeric values.
The dataset also contains values from several ranges. Some features have a value range of 0 - 28, some have a range of 2 - 67, and some have a range of 1017 - 100000. Apart from these, we can get useful statistical information (like mean, max, and min) about the features that have numerical values.
Finally, the dataset has missing values, which we'll take care of in this task. The missing values in the dataset are labeled with '?', which can be seen in the last cell's output of the second task.
Now, let's temporarily replace these missing value question marks with NaN.

cc_apps_train = cc_apps_train.replace(...)
cc_apps_test = cc_apps_test.replace(...)

5. Handling the missing values (part ii)

We replaced all the question marks with NaNs. This is going to help us in the next missing value treatment that we are going to perform.

An important question that gets raised here is why are we giving so much importance to missing values? Can't they be just ignored? Ignoring missing values can affect the performance of a machine learning model heavily. While ignoring the missing values our machine learning model may miss out on information about the dataset that may be useful for its training. Then, there are many models which cannot handle missing values implicitly such as Linear Discriminant Analysis (LDA).

So, to avoid this problem, we are going to impute the missing values with a strategy called mean imputation.

cc_apps_train.fillna(..., inplace=True)
cc_apps_test.fillna(..., inplace=True)

6. Handling the missing values (part iii)
We have successfully taken care of the missing values present in the numeric columns. There are still some missing values to be imputed for columns 0, 1, 3, 4, 5, 6 and 13. All of these columns contain non-numeric data and this is why the mean imputation strategy would not work here. This needs a different treatment.

We are going to impute these missing values with the most frequent values as present in the respective columns. This is good practice when it comes to imputing missing values for categorical data in general.

for col in ...:
    # Check if the column is of object type
    if ... == 'object':
        # Impute with the most frequent value
        cc_apps_train = cc_apps_train.fillna(...)
        cc_apps_test = cc_apps_test.fillna(...)

7. Preprocessing the data (part i)
The missing values are now successfully handled.

There is still some minor but essential data preprocessing needed before we proceed towards building our machine learning model. We are going to divide these remaining preprocessing steps into two main tasks:

Convert the non-numeric data into numeric.
Scale the feature values to a uniform range.
First, we will be converting all the non-numeric values into numeric ones. We do this because not only it results in a faster computation but also many machine learning models (like XGBoost) (and especially the ones developed using scikit-learn) require the data to be in a strictly numeric format. We will do this by using the get_dummies() method from pandas.

cc_apps_train = ...
cc_apps_test = ...

cc_apps_test = cc_apps_test.reindex(columns=..., fill_value=...)
8. Preprocessing the data (part ii)
Now, we are only left with one final preprocessing step of scaling before we can fit a machine learning model to the data.

Now, let's try to understand what these scaled values mean in the real world. Let's use CreditScore as an example. The credit score of a person is their creditworthiness based on their credit history. The higher this number, the more financially trustworthy a person is considered to be. So, a CreditScore of 1 is the highest since we're rescaling all the values to the range of 0-1.

X_train, y_train = cc_apps_train.iloc[...].values, cc_apps_train.iloc[...].values
X_test, y_test = cc_apps_test.iloc[...].values, cc_apps_test.iloc[...].values

scaler = MinMaxScaler(...)
rescaledX_train = scaler.fit_transform(...)
rescaledX_test = scaler.transform(...)

9. Fitting a logistic regression model to the train set
Essentially, predicting if a credit card application will be approved or not is a classification task. According to UCI, our dataset contains more instances that correspond to "Denied" status than instances corresponding to "Approved" status. Specifically, out of 690 instances, there are 383 (55.5%) applications that got denied and 307 (44.5%) applications that got approved.

This gives us a benchmark. A good machine learning model should be able to accurately predict the status of the applications with respect to these statistics.

Which model should we pick? A question to ask is: are the features that affect the credit card approval decision process correlated with each other? Although we can measure correlation, that is outside the scope of this notebook, so we'll rely on our intuition that they indeed are correlated for now. Because of this correlation, we'll take advantage of the fact that generalized linear models perform well in these cases. Let's start our machine learning modeling with a Logistic Regression model (a generalized linear model).

logreg = ...

10. Making predictions and evaluating performance
But how well does our model perform?

We will now evaluate our model on the test set with respect to classification accuracy. But we will also take a look the model's confusion matrix. In the case of predicting credit card applications, it is important to see if our machine learning model is equally capable of predicting approved and denied status, in line with the frequency of these labels in our original dataset. If our model is not performing well in this aspect, then it might end up approving the application that should have been approved. The confusion matrix helps us to view our model's performance from these aspects.

y_pred = logreg.predict(...)

print("Accuracy of logistic regression classifier: ", ...)

11. Grid searching and making the model perform better
Our model was pretty good! In fact it was able to yield an accuracy score of 100%.

For the confusion matrix, the first element of the of the first row of the confusion matrix denotes the true negatives meaning the number of negative instances (denied applications) predicted by the model correctly. And the last element of the second row of the confusion matrix denotes the true positives meaning the number of positive instances (approved applications) predicted by the model correctly.

But if we hadn't got a perfect score what's to be done?. We can perform a grid search of the model parameters to improve the model's ability to predict credit card approvals.

scikit-learn's implementation of logistic regression consists of different hyperparameters but we will grid search over the following two:

tol
max_iter

tol = ...
max_iter = ...
param_grid = dict(..., ...)

12. Finding the best performing model
We have defined the grid of hyperparameter values and converted them into a single dictionary format which GridSearchCV() expects as one of its parameters. Now, we will begin the grid search to see which values perform best.

We will instantiate GridSearchCV() with our earlier logreg model with all the data we have. We will also instruct GridSearchCV() to perform a cross-validation of five folds.

We'll end the notebook by storing the best-achieved score and the respective best parameters.

While building this credit card predictor, we tackled some of the most widely-known preprocessing steps such as scaling, label encoding, and missing value imputation. We finished with some machine learning to predict if a person's application for a credit card would get approved or not given some information about that person.

grid_model = GridSearchCV(estimator=..., param_grid=..., cv=...)

grid_model_result = grid_model.fit(...)

best_score, best_params = grid_model_result...., grid_model_result....
print("Best: %f using %s" % (...))

best_model = ...
print("Accuracy of logistic regression classifier: ", ...)
