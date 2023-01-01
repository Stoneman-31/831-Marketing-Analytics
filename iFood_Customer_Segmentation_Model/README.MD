# iFood

### This project is to practice the skills of customer segmentation modeling. 
The data is from a online shopping website from Brazil. We used customer demographic info and shopping info to design customer cluster snapshot with K-means & RandomForest model. 

This project mainly used FRM (frequency, rerency and monetory ) model to evalue customer value. 

### Data cleaning techniques:
none， data does not contain missing value or outliers. 

### Feature engineering techniques used:
 1. Created "Frequency" feature by adding all the store visits through different channels and divided by "Customer_Days". 
 2. standardlize "frequency","income","MntTotal","Recency", so everything can be comparied on a same scale. 

### Hypertuning:
1. Elbow Method: Used Silhouette and Inertia to determine K value ( how many clusters we should use)

### Evaluation:
1. Accuracy
2. AUC
3. F1 SCORE
