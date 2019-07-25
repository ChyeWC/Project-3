# Project-3
Project 3 submission

Problem Statement
----
Develop a classification model that can distinguish which of two subreddits, ([r/wow](https://www.reddit.com/r/wow) or [r/Overwatch](https://www.reddit.com/r/Overwatch/.json)), a particular post belongs to. Overwatch and World of Warcraft(wow) are two games produced by Blizzard.

## Executive Summary
The project is divided into 2 notebooks.
The first notebook Main contains the data collection and basic modeling. The results of the data collection are saved into data.csv file that will be used for modeling for the main and gridsearch notebook.
The secnd notebook Gridsearch uses gridsearch to get the best parameters.

1 feature (title) from the post is used for the prediction. Count, Hash and Tfidf Vectorizing are used separately to engineer this feature. Logistic Regression, KNN and Multinomial NB models are used in this notebook. 

#### Conclusions and Recommendations

The Multinomial Naive Bayes model performed the best. By using gridsearch, it was determined that the best parameters being , alpha= 1 and fit_prior= true. The accuracy score on the training data was 99.2%. The score for the test data is 89.5%. This means our model is probably overfitting on the test data. 

The gridsearch does not return the best parameters for the vectorizer. GridSearchCV needs a metric to optimize. As a vectorizer do not return a score, gridsearch could not optimize on the vectorize method.
As a result, based on the parameters provided from gridsearch, the features are increased to 11836. This makes the model very complex and prone to overfitting. The parameters for the vectorizer can be fined tuned further to improve the performance of the model.

References:

https://www.quora.com/Can-we-use-GridSearchCV-on-CountVectorizer-when-using-scikit-learn-models-on-text-data-or-can-grid-search-only-be-run-on-the-predictive-models
