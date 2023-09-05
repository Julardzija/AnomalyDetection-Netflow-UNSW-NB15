# AnomalyDetection-Netflow-UNSW-NB15
These two notebooks were a part of my master thesis on anomaly detection within network data. I was able to use feature selection techniques on a large and labelled netflow-based dataset in order to detect anomalies in the dataset.

### NOTE 
This code runs on a small subset (24347 rows) of full dataset (1.6 million rows). The full dataset is available and can be found online. 

## Objective for each notebook

[![Open in Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Julardzija/AnomalyDetection-Netflow-UNSW-NB15/blob/main//CleanData.ipynb)
**Notebook 1: Cleaning data** 

* Initial cleaning of the data
* Simple exploration of the data
* Outputs a new csv file with the data ready for preprocessing

[![Open in Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Julardzija/AnomalyDetection-Netflow-UNSW-NB15/blob/main//PrepareAndModel.ipynb)
**Notebook 2: Preparation and modeling** 

This notebook is the primary part which includes several steps outlined below 
* Basic analysis of the numerical and categorical features
* Splitting of the data into training and test sets
* Testing for normality for numerical values
* Preprocessing which got separated into three methods as we have three feature type categories
    - Numerical features: Preprocessed with Robust Scaling
    - Categorical features with low cardinality (50 or below): Preprocessed with One Hot Encoding
    - Categorical features with high cardinality (above 50): Preprocessed with Target Encoding
* Feature selection using
    - ANOVA
    - Chi Squared
    - Mutual Information
    - RFE (DecisionTreeClassifier as the estimator, and random forest as the model)
* Machine learning modeling (shallow models only)
    -  KNeighbors
    -  KMeans
    -  Random Forest
    -  XGBoost
    -  Isolation Forest
    -  Local Outlier Factor
* Model comparison where i look at
    - Recall
    - Precision
    - F1-Score
    - time to train model
    - time to predict
    - total time
