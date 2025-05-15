## Overview of the Analysis

The purpose of this analysis was to evaluate the performance of machine learning models in predicting the likelihood that a loan applicant would default on a loan. The dataset contained historical financial information about loan applicants, including variables such as income, debt-to-income ratio, loan amount, and credit history.

The primary target variable was `loan_status`, which we aimed to classify as:

* `0`: Healthy loan (the applicant repaid the loan)
* `1`: High-risk loan (the applicant defaulted)

Using `value_counts()`, we identified that the dataset was highly imbalanced, with a much higher number of healthy loans (`0`) compared to high-risk loans (`1`), which posed a challenge for prediction accuracy on the minority class.

To address this, we followed a typical supervised machine learning pipeline:

* Data preprocessing and cleaning
* Feature and target variable separation
* Training/testing data split
* Model training using `LogisticRegression`
* Model evaluation using classification metrics (accuracy, precision, recall, and F1-score)

## Results

* **Machine Learning Model 1: Logistic Regression**

  * **Accuracy Score**: 0.99
  * **Precision Score**:

    * Class 0 (healthy loans): 1.00
    * Class 1 (high-risk loans): 0.84
  * **Recall Score**:

    * Class 0: 0.99
    * Class 1: 0.94
  * **F1 Score**:

    * Class 0: 1.00
    * Class 1: 0.89

## Summary

The Logistic Regression model performs exceptionally well in classifying both healthy and high-risk loans, with an overall accuracy of 99%. It predicts healthy loans with near-perfect precision and recall, and high-risk loans with strong recall (94%) and good precision (84%).

Given the business context—minimizing financial risk—it’s more important to correctly identify high-risk loans (`1`). The model’s high recall for this class means it effectively flags risky borrowers, which can help lenders avoid defaults.

**Recommendation**: I recommend using the Logistic Regression model, as it offers a strong balance between overall accuracy and the ability to identify high-risk loans with minimal false negatives. Further enhancements could involve rebalancing the data or testing other algorithms to improve precision for class 1.
