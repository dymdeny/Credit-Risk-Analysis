# Module 12 Report Template

## Overview of the Analysis

* What is credit risk ?Credit risk is associated with the possibility of a client failing to meet contractual obligations, such as mortgages, credit card debts, and other types of loans.
Minimizing the risk of default is a major concern for financial institutions. For this reason, commercial and investment banks, venture capital funds, asset management companies and insurance firms,  are increasingly relying on technology to predict which clients are more prone to stop honoring their debts.
* In this assignment,I will try to determine which loans are healthy (low-risk) or non-healthy (high-risk) based on the loan status provided by the lending company by using machine learning model.

## In Step 3 I am using the value_counts function to check the balance of the labels variable (y) to see the numbers of healthy loans [0] and non-healthy loans [1]:

```
# code
y.value_counts()

# output
0    75036
1     2500
Name: loan_status, dtype: int64
```
* After that I created  a Logistic Regression Model with the Original Data to evaluate the model performance by doing the following:

- Calculate the accuracy score of the model.

- Generate a confusion matrix.

- Print the classification report.

`Based on the confusion matrix, I have got following results:`

- 18,765 loan status that are healthy (low-risk), the model predicted 18,663 as 
   healthy correctly and 102 as healthy incorrectly. 

- 619 loan status that are non-healthy (high-risk), the model 
   predicted 563 as non-healthy correctly and 56 as non-healthy incorrectly.

- With balanced accuracy score 0.95 or 95%

 ![Balanced Accuracy Score](/Images/Balanced_accuracy_score.png)


 ![Confusion Matrix](/main/Images/confusion_matrix.png")


 ![Classification report](/main/Images/classification_report.png")

* To obtain better accuracy score and to improve  classification of  all type of loans, I used the LogisticRegression classifier and the resampled data to fit the model and make predictions.
```
# code
y_resampled.value_counts()
# output
0    56271
1    56271
Name: loan_status, dtype: int64
```
* Based on confusin matrix, I have got the next results:
- From 18,765 loan status that are healthy (low-risk), the model predicted 18,649 as 
   healthy correctly and 116 as healthy incorrectly. 

- From 619 loan status that are non-healthy (high-risk), the model 
   predicted 615 as non-healthy correctly and 4 as non-healthy incorrectly.
- With hight balanced accuracy score of 99%

 ![Oversampled Balanced Accuracy Score](/main/Images/balanced accuracy score.png)

 ![Oversampled Confusion Matrix](/main/Images/confusion matrix.png")

 ![Oversampled Classification report](/main/Images/classification_report_imbalanced.png")

## Summary
- The main goal for this analysis is to find out the model which will be correctly classifying  healthy  and non-healthy loans.

    
- The Logistic Regression model with OverSampled data showing better performance than  model which has been fitted with Original data.Superiority of this  can be seen in  higher accuracy score and a higher recall numbers.Also, model mantioned above make less mistakes when classifying non-healthy loans.

* Based off this analysis, I would recommend Model 2.
