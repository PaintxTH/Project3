# Project3 - Classification Model
# Problem Statement

Given that 
We work for a Tech News & Media Company 
that writes/talks about Computer Technology update mostly for Mac and Windows, With short in manpower, Our Editors usually choose variety of IT buzzing and popular topics from social media post to write/talks in our news sometime just paraphrasing.

Tech News company needs to think like a tech company,
Our CEO trying to find a tool to effectively help our editors get more productivity and focus more in quality content without getting more headcount by creating tool to auto-categorize our news articles on our website whether it is Windows or Mac. So our editors don’t have to input it manually and have time to focus more on quality of content.  We are in charge of this project!


# Our plan 

To find
1.Find Most Precise Classification Model to help categorize text into ‘Mac’ or ‘Windows’
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

Multinomial Naive Bayes,  Logistic Regression, Random Forest are among 
the best models to classify such text with high accuracy score and ready to deploy its first trial.

Although, we suggest improve these 3 models to multi-classification, 
So they will to be able to classify more than 2 classes. 

Because we could expand our topics to write more than just Mac or Windows because mobile
operating systems are rising its popularity these day! And this could be new business opportunity.
That way, also can auto-categorize more categories and get broader topics of interests to write/talk
more about on our news article.


# Further Studies Recommendation

We could try these following to improve the model,
Neatly clean our dataset since there are slightly chance of data contamination (mislabelling post)
Mix with text sources from other platform to stimulate our model with various environment for our unseen data could possibly based on and get more generalizable.


# Data Dictionary

|column|data type|description|
|:-:|:-:|:-:|
|vote|int|mechanism for user to vote whether they like this post or not similar to Likes on Facebook|
|title|string|topic of the post|
|text|string|body of the post|
|date|datetime|date of post establishing|
|message|string|title and text combined|
|Class|bool|Label for class where 0 is Windows and 1 is Mac|
