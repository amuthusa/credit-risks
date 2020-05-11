# Credit risks

## Overview:
     
  Analyze the loan application and predict the credit risks of the application. The was data collected by LendingClub, a peer-to-peer lending services company. The data is imbalanced since there are lots of good loan applications compared to less bad ones. This project will compare credit risks using different machine learning algorithm and it will find if there is any model which could be used in the future for predicting the bad loan application.

## Comparison of different models:

  Since the loan application we have from LendingClub is imbalanced we are using different Oversampling models to find the accuracy, precision, recall, F1 score. 

  |Model Name                |   Bal. Accuracy Score  |   Precision         | Recall/Sensitivity | F1 Score
  |--------------------------|:--------------------------:|:--------------------:|:-------------------:|:-------------|
  |Naive RandomOverSampling  |     68%      | high risk - 1%   | high risk - 71%    | high risk - 2%    |      
  |                          |              | low risk - 100%  |  low risk  - 64%   | low risk - 78%    |
  |SMOTE OverSampling        |     68%      | high risk - 1%   | high risk - 68%    | high risk - 2%    |
  |                          |              | low risk - 100%  |  low risk  - 68%   | low risk  - 81%   |
  |Cluster centroid Undersampling |     56% | high risk - 1%   | high risk - 69%    | high risk - 1%    |
  |                               |         | low risk - 100%  |  low risk  - 45%   | low risk -  62%   |
  |SMOTEENN Combination      |     68%      | high risk - 1%   | high risk - 79%    | high risk - 2%    |
  |                          |              | low risk - 100%  |  low risk  - 59%   | low risk - 74%    |
  
   Looking at the Balanced Accuracy score Naive RandomOverSampling, SMOTE OverSampling, and SMOTEENN Combination model stood out with 68% accuracy in predicting risky loans. Further comparing the Recall (percentage of total risky loans)  is low for low-risk loan applications using SMOTEENN Model so dropping it we are left with Naive RandomOverSampling or SMOTE Oversampling. But precision ( percentage of risky loans) identified is pretty low for high-risk loans even though the precision is good for low-risk loans. Falling back on F1-score which is harmonic mean of Precision and Recall which is also pretty low for high-risk loans which brings us to a conclusion none of the models might be the right candidate for predicting the high-risk loans. 
   
## Recommendation:
  
  None of the Oversampling, Undersampling, or Combination models stood out in our comparison, either we should compare a different set of data or get more loan application data before figuring out which model might be our choice for predictions. For Predicting low-risk loans we could think of using SMOTE Oversampling which will be handy.


## Extension:

  Below table shows the accuracy score, precision, recall or sensitivity of the credit risk using the following models BalancedRandomForestClassifier, EasyEnsembleClassifier
  
  |Model Name                |   Bal. Accuracy Score  |   Precision         | Recall/Sensitivity | F1 Score
  |--------------------------|:--------------------------:|:--------------------:|:-------------------:|:-------------|
  |BalancedRandomForest Classifier  |     77%      | high risk - 3%   | high risk - 66%    | high risk - 6%    |      
  |                          |              | low risk - 100%  |  low risk  - 90%   | low risk - 94%    |
  |EasyEnsemble Classifier   |     92%      | high risk - 7%   | high risk - 91%    | high risk - 13%    |
  |                          |              | low risk - 100%  |  low risk  - 93%   | low risk  - 97%   |
  
  Looking at the classifiers precision and F1 score for high risk loans which is pretty low in 7% and 13% respectively makes me to feel these classifiers may not be good for predicting the high risk loans. Also the Recall seems to be high for high risk so we might see lot of false positive in the predictions which will decrease the loan approval rate and the confidence of the applicant.

## Recommendation:

   None of the classifier is good for high risks loans based on unblanaced loan application data. 
  
