# Football-Score-Predictor
## Overview
This project contains a script for training machine learning classifiers to predict the outcome of football matches based on historical data. The script uses data from the English Premier League, Spanish La Liga, French Ligue 1, German Bundesliga, and Italian Serie A.

## Prerequisites
Python 3.x
pandas, numpy, scikit-learn, joblib, and related dependencies
## Data
The data for this project is stored in compressed folders for each league, with one CSV file per season. The CSV files contain columns for the home team, away team, and various match statistics, as well as the final result (Home Win, Away Win, or Draw).

The data is filtered to only include the following columns:

home_encoded: Encoded home team name
away_encoded: Encoded away team name
HTHG: Half-time home team goals
HTAG: Half-time away team goals
HS: Home team shots
AS: Away team shots
HST: Home team shots on target
AST: Away team shots on target
HR: Home team corners
AR: Away team corners
FTR: Full-time result (Home Win, Away Win, or Draw)
The script uses label encoding to convert the home team and away team names to numerical values. The mapping between the numerical values and the team names is saved to a JSON file when the model is exported.

## Classifiers
The script trains and evaluates the following classifiers:

+ Logistic Regression one vs All Classifier
  - This type of statistical model (also known as logit model) is often used for classification and predictive analytics.
  - Logistic regression estimates the probability of an event occurring, such as voted or didn’t vote, based on a given dataset of independent variables. Since the outcome       is a probability, the dependent variable is bounded between 0 and 1. In logistic regression, a logit transformation is applied on the odds—that is, the probability of        success divided by the probability of failure.
  - Within machine learning, logistic regression belongs to the family of supervised machine learning models. It is also considered a discriminative model, which means that      it attempts to distinguish between classes (or categories). 
+ Gaussian Naive Bayes Classifier
  - Gaussian Naive Bayes is a machine learning classification technique based on a probablistic approach that assumes each class follows a normal distribution.
  - It assumes each parameter has an independent capacity of predicting the output variable.
  - It is able to predict the probability of a dependent variable to be classified in each group.
  - But in practice, there are quite a few real-world use cases of this type of classifier, namely document classification and spam-filtering among many others.
+ Random Forest Classifier
  - Random Forest is a popular machine learning algorithm that belongs to the supervised learning technique. It can be used for both Classification and Regression problems       in ML.
  - It is based on the concept of ensemble learning, which is a process of combining multiple classifiers to solve a complex problem and to improve the performance of the        model.
  - Random Forest is a classifier that contains a number of decision trees on various subsets of the given dataset and takes the average to improve the predictive accuracy       of that dataset.
The classifiers are trained and evaluated using 80% of the data for training and 20% for testing. The training and testing metrics for each classifier are printed to the console.

## Exporting the Model
If the user inputs y when prompted, the trained models and metadata are exported to a directory called exportedModels. The metadata includes the mapping between the numerical values and the team names.
