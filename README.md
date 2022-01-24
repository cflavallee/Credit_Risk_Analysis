# Credit_Risk_Analysis

## Overview
The purpose of this analysis was to use 6 different Supervised Machine Learning models to see how they performed on predicting credit risk based on a number of factors.  This was done using Pandas, Jupyter Notebook, Scikit-learn, and imbalanced-learn, among other tools. 

## Results
Because the data was very imbalanced in favor or low risk credit applications, it was necessary to use a variety of tools to improve the Machine Learning training models.  This was done by increasing the high risk data, decreasing the low risk data, using a combination of under and over sampling, and employing ensemble methods.  Despite using various means to account for skewed data, the models still had difficulty recognizing high risk loans, as can be see in the results below. 


### RandomOverSampler
By using the RandomOverSampler algorithm, the goal was to train the model with more high risk data than was in the actual dataset.  Unfortunately, the model was not good at predicting high risk loans, despite the oversampling used to train the model.  This could be due to a number of factors, potentially due to the fine line between low and high risk loans used in the dataset.  Additionally, the model may not have been able to learn the nuance needed to identify a high risk loan.  As seen with almost all of the models, this model erred on the side of predicting a loan to be low risk.  So, while precision was high, recall was very low, thus missing almost all of the high risk loans.  This could be seen as a very negative thing, however, with more low risk loans than high risk ones, the company may not lose much money by determing a loan to be low risk rather than high risk, depending on the amount of the loan. 

![Random Balanced](https://github.com/cflavallee/Credit_Risk_Analysis/blob/main/Images/ROSScore.PNG)
![Random Imbalanced](https://github.com/cflavallee/Credit_Risk_Analysis/blob/main/Images/ROSImbalanced.PNG)

### SMOTE
Similar to the above mode, SMOTE did not do any better in predicting high risk loans, and did about the same with low risk. 

![SMOTE Balanced](https://github.com/cflavallee/Credit_Risk_Analysis/blob/main/Images/SMOTEScore.PNG)
![SMOTE Imbalanced](https://github.com/cflavallee/Credit_Risk_Analysis/blob/main/Images/SMOTEImbalanced.PNG)

### ClusterCentroids
As with the previous models, the one did not fare any better, and in fact, did relatively worse in predicting both low and high risk loans. 

![Centroid Balanced](https://github.com/cflavallee/Credit_Risk_Analysis/blob/main/Images/CentroidScore.PNG)
![Centroid Imbalanced](https://github.com/cflavallee/Credit_Risk_Analysis/blob/main/Images/CentroidImbalanced.PNG)

### SMOTEENN
Even using a combination of over and under sampling the data did not perform much better than the previous three models, at least not to a significant extent. 

![SMOTEENN Balanced](https://github.com/cflavallee/Credit_Risk_Analysis/blob/main/Images/SMOTENNScore.PNG)
![SMOTEENN Imbalanced](https://github.com/cflavallee/Credit_Risk_Analysis/blob/main/Images/SMOTEENNImbalanced.PNG)

### BalancedRandomForestClassifier
The ensemble learning methods did significantly better than the over and under sampling ones, but still did not perform at a level I would be confident using when it comes to credit risk.  

![Forest Balanced](https://github.com/cflavallee/Credit_Risk_Analysis/blob/main/Images/ForestScore.PNG)
![Forest Imbalanced](https://github.com/cflavallee/Credit_Risk_Analysis/blob/main/Images/ForestImbalanced.PNG)

### EasyEnsembleClassifier
Again, the ensemble learning performed better than adjusting the sampling, but probably not to a level that any company would be happy with. 

![Easy Balanced](https://github.com/cflavallee/Credit_Risk_Analysis/blob/main/Images/EnsembleScore.PNG)
![Easy Imbalanced](https://github.com/cflavallee/Credit_Risk_Analysis/blob/main/Images/EnsembleImbalanced.PNG)

## Summary

In conclusion, the models used in their current form may not be the best options to use on credit risk prediction.  While I would not recommend any of these models, there may be adjustments that could improve performance enough to make automating this task worth while.  Additionally, a further inspection of the data could reveal areas of improvement in cleaning or adjusting the data in order to help the Machine Learning models improve performance.  Also, a fiscal analyis of the cost of the current method for determing credit risk versus the fiscal impact of using Machine Learning would provide insight into the efficacy of using one model or the other.  