# Marketing-Analytics

Please download the zip file to obtain train and test data sets

The goal of this project is to find the difference between only collecting the info of yes/no (binomial) and multi-level (multinomial) answer.

For example, for the dataset, we could only collect final purchase result as buy or not, or we can collect more info as viewed promo page, viewed home page, buy, or not.


The techniques used at data cleaning:
1. Drop columns where data is missing >70%
2. Fill the rest missing values with .fillna(value=0) or fillna('Unknown)
3. Replace 'null' with 'Unknown', so all the missing values are representated in same symbol "Unknown", easier for later process. 

The techniques used at feature engineering:
1. Use get_dummies to turn string value to numeric values
2. Obtain mean value of 'annualsales' and created a new feature base off that
3. Principle Component Analysis (PCA)

Model used:
1. Random forest

Hypertunning method used:
1. GridSearch
2. RandomSearch


p

# Business Question

## Question 1: In Kiran’s meeting with Parag Chitalia what was the overarching problem they were looking to address?  

 

The overarching problem Kiran and Parag were looking to address was to better target current and potential customers (B2B, B2C), by structuring their marketing efforts through a propensity model to predict the next “action” (target) that these customers would make. Further, by developing a multinomial model to classify this prediction, they would be better able to support the marketing team at VMware to target (personalized e-mails) these customers in their e-mail campaigns.  

 

Once they were able to determine the “Propensity to Respond” model, they would be better equipped to understand what current customers/potential customers are more likely to respond to. 

 

## Question 2: Briefly explain the type of online and offline data available to Kiran’s team?  

The types of data that Kiran had available were online data such as detailed product and event wise data (such as web analytics – page views, unique users, webinar page views et al), referral data, search engine (product searches made on Google for example), UX data such as browser data points, and marketing channel data.  

Additional online data also included targeted digital action data, which was sourced/derived from the VMware website such as Hands on Learning registrations, downloads of a white paper etc. 

They also had offline data such as CRM data (features of the client firm), booking history for each product, responses to campaigns, days since last purchase, and channel-based data to name a few. 

An area of concern was the imbalance of these datasets as the multi-class target variables may have a lot of sparse data. Additionally, the sheer number of features (variables) available amounted to 700+. This meant that starting from the entire dataset and doing dimension reduction would be the prudent course of action. Further, since the dataset is imbalanced and the model to be used has to perform/solve for a multinomial classification problem, algorithms that can perform against both of these factors are important.  

 

 

 

 

## Question 3: How is the propensity to respond model different from the traditional propensity to buy model? 

The propensity to respond model is different than a traditional propensity to buy model because the former is a multinomial classification problem versus the traditional binomial classification problem of a “yes” or “no” when trying to classify if the target is looking to buy. Additionally, a propensity to buy model is applied if we want to identify buying propensity. However, here we would need a propensity to respond, as target customers may be at different stages of buying and propensity to respond would be more effective here. Additionally, propensity to buy will be affected by different decision-makers from the customer organisation. Hence, building a propensity to buy may not lead to desirable results here. 

 

## Question 4: How does B2B personalized marketing differ from B2C marketing? 

B2B marketing is different to B2C marketing due to the complexity of the relationship between winning a contract with an organization versus an individual. With a larger company/organization, there may be many individuals involved in the decision-making process. This could include program sponsors, project managers, analysts, end users etc. With this comes differing responses to marketing efforts as individuals may be more receptive towards one campaign versus another.  

For example, when looking at a specific Software-Defined Data Center (SDDC) products, the evaluation of these products requires more than a tertiary screen. There may be rigorous testing and evaluation of the product features and functionality prior to make the purchase. 

Finally, as a team of individuals evaluates a product, each individual may be at a different stage of the purchase funnel. For example, a curious “Power User”, say an infrastructure engineer (in one subsidiary of the company) may peruse the VMware website for information on the product, meanwhile, a project sponsor (at a strategic level) along with his team who is conducting an RFP may already be at the decision-making stage of purchasing a solution. 

 

## Question 5: VMW has identified more than 600 predictor variables. Do you think that techniques such as logistic regression can be applied when the number of variables is large? What variable reduction techniques can be used to make the model more efficient? 

Techniques such as principal component analysis (PCA) could help to reduce the number of variables to make the model more efficient. Further, imputation could help where a feature that is deemed of some significance has missing data. Additionally, ensuring that redundant data, testing for heteroskedasticity and collinearity would be additional things you could do.  

Due to the imbalance of the dataset (predictor variables) and a lot of classification variables, it is best not to use a logistic regression for this assignment. While we hot encode all classifiers, the notion of predicting an action versus no action is only half the story. The multiple values of actions would leave the logistic regression unfit to adequately predict the multiple actions on the VMWare website. 

 

## Question 6: The data is also highly imbalanced; What problems do we face when classes are not adequately represented and how can these be mitigated? Are certain classification techniques better suited to handle imbalanced data than others? 

When a dataset is imbalanced, one must consider statistical significance with respect to how the data is distributed via certain classes of data. It may be wise to consider grouping (binning) certain classes where data may be sparse. Further, hot encoding and scaling would also lend well to ensure that the dataset could be handled by the random forest model we have built. 

When considering the model to address this imbalance, perhaps an ensemble approach by utilizing bagging or boosting techniques may be able to better arrive a better F1 score or other measure of model performance. Additionally, applying cross-validation (e.g. K-Fold) to ensure that the model is robust in its predictive ability via sampling and resampling. 
