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
* After that I created  a Logistic Regression Model with the Original Data to evaluate the model’s performance by doing the following:

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

![Confusion Matrix](/Images/confusion_matrix.png")

![Classification report](/Images/calssification_report.png")

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
![Balanced Accuracy Score](/Images/Balanced_accuracy_score.png)

![Confusion Matrix](/Images/confusion_matrix.png")

![Classification report](/Images/calssification_report.png")

## **Summary**

* A lending company might want a model that requires classifying healthy loans and non-healthy loans correctly most of the time: 

    * healthy loans being identified as a non-healthy loan might be more costly for a lending company since it might cause the loss of customers. 
  
    * non-healthy loans being identified as a healthy loan might also be more costly for a lending company due to the loss of funds being provided by the lender.

`The Logistic Regression model fitted with OverSampled data performed much better than the model fitted with Imbalanced data due to the data being balanced and generating a higher accuracy score and a higher recall, indicating that the model will make extremely fewer mistakes when classifying non-healthy loans.`

</br>

`The lending company would most likely want fewer False Positives due to the high possibility of a lender loosing provided funds when classifying non-healthy loans as healthy. The data below is shown in the confusion matrices which indicates how many healthy/non-healthy loans the model predicted correctly/incorrectly.`

* Model fitted with Imbalanced Data: 
  
  * 56 (FALSE POSITIVES) --> The actual value is healthy and the predicted value is non-healthy 


  * 102 (FALSE NEGATIVES) --> The actual value is non-healthy and the predicted value is healthy

</br>

* Model fitted with Balanced Data: 
  
  * 4 (FALSE POSITIVES) --> The actual value is healthy and the predicted value is non-healthy 


  * 116 (FALSE NEGATIVES) --> The actual value is non-healthy and the predicted value is healthy
  
`According to the confusion matrices, the number of False Postives drastically decreases indicating the model will classify healthy & non-healthy loans correctly. Based off of this analysis, I would recommend using Model 2 (Logistic Regression Model fitted with Balanced (oversampled) data.`

---