# Project3 - Classification Model
# Problem Statement

Given that 
We work for a Tech News & Media Company 
that writes/talks about Computer Technology update, which usually choose buzzing and popular topics from social media post to write/talks in our news 

Due to high competitiveness in this industry where everyone can become a news reporter and publisher, Business positioning is a must!, we can’t just write random article about this and that just like before

In response, 
Our company is deciding to be more specific and subjective, whether our news is to serve Apple or Windows fanboy for our brand positioning sake!

Mac or Windows, one way or another,
All we need is the tool to skim through posts whether each one is about Windows or Mac so we can choose post from our (yet) chosen label  for upcoming articles/news correctly and conveniently!

# Our plan 

To find
1.Most Precise Classification Model to classify text from social media alike.
2.Recommendation for further studies and Business strategy/execution suggestion


# Exploratory Data Analysis
This gets done by following the order below:

Raw Scrapped Data 
MacOS:   19,312 rows, 4 columns
Windows:   28,209 rows, 4 columns

Data Imputation
(i.e. filling/dropping missing values, duplicates filtering out odd ones)

Duplicated Rows (This one gets dropped)
MacOS: 8,215 rows
Windows 3,265 rows

text includes [removed] [deleted] (This one gets dropped)
MacOS: 9,614 rows
Windows: 5,185 rows

Created New Column
(Message = Topic + Text (Body)

Ready Data for Modelling

MacOS: 10,867 rows, 5 columns
Windows: 10,380 rows, 5 columns

# Modeling
1.Logistic Regression with GridSearch
2.KNN  (K-nearest neighbor) with GridSearch
3.Random Forest with GridSearch
4.Multinomial NB (Naive Bayes) with GridSearch
5.Decision Tree with GridSearch

# Results

## 1.Logistic Regression with GridSearch

True Negatives: 3204
False Positives: 222
False Negatives: 303
True Positives: 3283

              precision    recall  f1-score   support

           0       0.91      0.94      0.92      3426
           1       0.94      0.92      0.93      3586

    accuracy                           0.93      7012
   macro avg       0.93      0.93      0.93      7012
weighted avg       0.93      0.93      0.93      7012

## 2.KNN  (K-nearest neighbor) with GridSearch

True Negatives: 3257
False Positives: 169
False Negatives: 321
True Positives: 3265

              precision    recall  f1-score   support

           0       0.72      0.85      0.78      3426
           1       0.83      0.68      0.75      3586

    accuracy                           0.76      7012
   macro avg       0.77      0.77      0.76      7012
weighted avg       0.77      0.76      0.76      7012

## 3.Random Forest with GridSearch

True Negatives: 3257
False Positives: 169
False Negatives: 321
True Positives: 3265

              precision    recall  f1-score   support

           0       0.91      0.95      0.93      3426
           1       0.95      0.91      0.93      3586

    accuracy                           0.93      7012
   macro avg       0.93      0.93      0.93      7012
weighted avg       0.93      0.93      0.93      7012

## 4.Multinomial NB (Naive Bayes) with GridSearch

True Negatives: 3337
False Positives: 89
False Negatives: 1287
True Positives: 2299

              precision    recall  f1-score   support

           0       0.91      0.96      0.93      3426
           1       0.96      0.91      0.93      3586

    accuracy                           0.93      7012
   macro avg       0.93      0.93      0.93      7012
weighted avg       0.94      0.93      0.93      7012

## 5.Decision Tree with GridSearch

True Negatives: 3337
False Positives: 89
False Negatives: 1287
True Positives: 2299

              precision    recall  f1-score   support

           0       0.72      0.97      0.83      3426
           1       0.96      0.64      0.77      3586

    accuracy                           0.80      7012
   macro avg       0.84      0.81      0.80      7012
weighted avg       0.84      0.80      0.80      7012


# Conclusion

Logistic Regression, Random Forest and Multinomial Naive Bayes  
are among the best model to classify such text with high precision score.
Although we suggest improve these 3 models to be able to classify 3 class labels for more practical utilization. (i.e. given class below)
0: None of 2
1: Mac
2: Windows

As problem statement,
it states that text that will be used to classified will come from all over the place.


# Further Studies Recommendation

We could try these following to improve the model,
Neatly clean our dataset since there are slightly chance of data contamination (mislabelling post)
Mix with text sources from other platform to stimulate our model with environment our unseen data could possibly come from

# Data Dictionary

|column|data type|description|
|:-:|:-:|:-:|
|vote|int|mechanism for user to vote whether they like this post or not similar to Likes on Facebook|
|title|string|topic of the post|
|text|string|body of the post|
|date|datetime|date of post establishing|
|message|string|title and text combined|
|Class|bool|Label for class where 0 is Windows and 1 is Mac|
