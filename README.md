# 831-Marketing-Analytics

Please download the zip file to obtain train and test data sets

The goal of this project is to find the difference between only collecting the info of yes/no (binomial) and multi-level (multinomial) answer.

For example, for the dataset, we could only collect final purchase result as buy or not, or we can collect more info as viewed promo page, viewed home page, buy, or not.


The techniques used at data cleaning:
1. drop columns where data is missing >70%
2. fill the rest missing values with .fillna(value=0) or fillna('Unknown)
3. Replace 'null' with 'Unknown', so all the missing values are representated in same symbol "Unknown", easier for later process. 

The techniques used at feature engineering:
1. use get_dummies to turn string value to numeric values
2. obtain mean value of 'annualsales' and created a new feature base off that
3. Principle Component Analysis (PCA)

Model used:
1. Random forest

Hypertunning method used:
1. GridSearch
2. RandomSearch
