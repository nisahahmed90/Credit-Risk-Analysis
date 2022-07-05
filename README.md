# Credit Risk Analysis

## Overview
In this project, we use Python to build and evaluate several machine learning models to predict credit risk.
We adopted the following procedure:

- oversample the data using the RandomOverSampler and SMOTE algorithms.
- Undersample the data using the ClusterCentroids algorithm.
- Use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm.
- Compare two machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier.

We will evaluate the performance of these models and make a recommendation on whether they should be used to predict credit risk.

## Results (Balanced Accuracy Scores, Confusion Matrixes and Imbalanced Classification Reports)

### RandomOverSampler model

<img width="847" alt="Screen Shot 2022-07-04 at 7 02 36 PM" src="https://user-images.githubusercontent.com/100812308/177223838-83e55afa-038f-4545-9e06-a5b22092fffa.png">

The balanced accuracy score is 65%.
The high_risk precision is about 1% only with 62% sensitivity which makes a F1 of 2% only.
Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 65%.

### SMOTE model

<img width="888" alt="Screen Shot 2022-07-04 at 7 05 52 PM" src="https://user-images.githubusercontent.com/100812308/177224024-f1237b00-06ab-4406-ab56-c2f1f02f47d0.png">

The results are pretty similar to the previous model.
The balanced accuracy score is 64%.
The high_risk precision is about 1% only with 65% sensitivity which makes a F1 of 2% only.
Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 65%.

### ClusterCentroids model

<img width="857" alt="Screen Shot 2022-07-04 at 7 12 19 PM" src="https://user-images.githubusercontent.com/100812308/177246492-10b87d32-30f9-4c91-900a-e51cad35c63e.png">


Here the balanced accuracy score is down to about 51%.
The high_risk precision is still 1% only with 63% sensitivity which makes a F1 of 1%.
Due to the high number of false positives, the low_risk sensitivity is only 44%.

### SMOTEENN model

<img width="894" alt="Screen Shot 2022-07-04 at 7 12 44 PM" src="https://user-images.githubusercontent.com/100812308/177246508-7e918697-7a03-4a42-9e87-0f15136605d2.png">


The balanced accuracy score is about 62%.
The high_risk precision is still 1% only with 70% sensitivity which makes a F1 of only 2%.
Due to the high number of false positives, the low_risk sensitivity is 54%.

### BalancedRandomForestClassifier model

<img width="835" alt="Screen Shot 2022-07-04 at 7 13 27 PM" src="https://user-images.githubusercontent.com/100812308/177246581-9cf7cd6e-179b-4ac5-8990-204818bbe966.png">


The balanced accuracy score improved to about 79%.
The high_risk precision is still low at 4% only with 67% sensitivity which makes a F1 of only 7%.
Due to a lower number of false positives, the low_risk sensitivity is now 91% with 100% presicion.

### EasyEnsembleClassifier model

<img width="836" alt="Screen Shot 2022-07-04 at 7 15 49 PM" src="https://user-images.githubusercontent.com/100812308/177246601-6aa3da7c-7781-47fc-9ff5-4bb244c95056.png">

Now, the balanced accuracy score is high to about 93%.
The high_risk precision is still low at 7% only with 91% sensitivity which makes a F1 of only 14%.
Due to a lower number of false positives, the low_risk sensitivity is now 94% with 100% presicion.

## Summary
All the models used to perform the credit risk analysis show weak precision in determining if a credit risk is high.
The Ensemble models brought a lot more improvment specially on the sensitivity of the high risk credits.
The EasyEnsembleClassifier model shows a recall of 92% so it detects almost all high risk credit. On another hand, with a low precision, a lot of low risk credits are still falsely detected as high risk which would penalize the bank's credit strategy and infer on its revenue by missing those business opportunities.
For those reasons I would not recommend the bank to use any of these models to predict credit risk.
