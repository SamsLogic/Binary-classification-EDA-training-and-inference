# Binary-classification-EDA-training-and-inference

This is the colab link to the code - https://colab.research.google.com/drive/1Crag3hX87HamRBvw12mgGKG-nyXv1nvK#scrollTo=BrlOWelQOTCG

## Libraries Used

  1. numpy = 1.19.5
  2. matplotlib = 3.2.2
  3. pandas = 1.1.5
  4. seaborn = 0.11.2
  5. sklearn = 1.0.1
  6. XGBoost = 0.90
  7. LightGBM = 2.2.3

Directly install the above mentioned packages by using the command:

`pip install -r requirements.txt --user`

## Approach

My Approach to work upon the dataset was both data centric. EDA was performed on the data as well as certain requried data processing was performed starting with outlier detection, Null value handling, Data standarization and dimensionality reduction. The thought process for this appraoch was to first understanding the data and perform the data cleaning as per the understanding and then analysing how much the columns were correlated with each other as well as with the target value.

## Files

train.csv - To be used as training and validation set - 3910 records, 57 features, 1 output
test_set.csv - To be used for prediction - 691 records, 57 features
Submission.csv - Model prediction results
EDA, Train and Inference.py - Script for EDA, training and prediction
EDA, Train and Inference.ipynb - Notebook for EDA, training and prediction

## Models

Multi-model approach was used for training on the data where the data was trained over multiple models and the best model was identified by comparison over certain metrics. The models used are:
  1.  Logistic Regression
  2.  Support Vector Classifier
  3.  Random Forest Classifier
  4.  XGBoost
  5.  LightGBM

After the validation results it was identifed that LightGBm performed better than other models.

## Data Validation result

Validation data was selected with a ratio of 4:1 of the training data. Below are some results of the data validation:

### ROC AUC Score:

  Logistic Regression:  0.9145264918148214
  Support vecotr classifier:  0.9316317549727161
  Random Forest Classifier:  0.9372249603942968
  XGBoost:  0.9372381622953705
  LightGBM:  0.9411855307164232

### F1 - Score:

  Logistic Regression:  0.894393741851369
  Support vecotr classifier:  0.9128205128205129
  Random Forest Classifier:  0.9261744966442953
  XGBoost:  0.9226736566186108
  LightGBM:  0.9268929503916449

### Confusion Matrix:

  Logistic Regression
  
          0    1 
      0   554  44
      1   37 343

  Support vecotr classifier
  
          0    1 
      0   554  44
      1   24 356

  Random Forest Classifier

          0    1 
      0   578  20
      1   35 345

  XGBoost

          0    1 
      0   567  31
      1   28 352

   LightGBM

          0    1 
      0   567  31
      1   25 355
 
 ### Classification report:
 
   Logistic Regression
   
                   precision    recall  f1-score   support

               0       0.94      0.93      0.93       598
               1       0.89      0.90      0.89       380

        accuracy                           0.92       978
       macro avg       0.91      0.91      0.91       978
    weighted avg       0.92      0.92      0.92       978


  Support vecotr classifier
  
                   precision    recall  f1-score   support

               0       0.96      0.93      0.94       598
               1       0.89      0.94      0.91       380

        accuracy                           0.93       978
       macro avg       0.92      0.93      0.93       978
    weighted avg       0.93      0.93      0.93       978


  Random Forest Classifier
  
                   precision    recall  f1-score   support

               0       0.94      0.97      0.95       598
               1       0.95      0.91      0.93       380

        accuracy                           0.94       978
       macro avg       0.94      0.94      0.94       978
    weighted avg       0.94      0.94      0.94       978


  XGBoost
  
                   precision    recall  f1-score   support

               0       0.95      0.95      0.95       598
               1       0.92      0.93      0.92       380

        accuracy                           0.94       978
       macro avg       0.94      0.94      0.94       978
    weighted avg       0.94      0.94      0.94       978


  LightGBM

                   precision    recall  f1-score   support

               0       0.96      0.95      0.95       598
               1       0.92      0.93      0.93       380

        accuracy                           0.94       978
       macro avg       0.94      0.94      0.94       978
    weighted avg       0.94      0.94      0.94       978
  
## Test Result

submission.csv can be checked for submission results.

