# prediction-of-cirrhosis-outcomes

This project aims to predict cirrhosis outcomes using various machine learning algorithms. The dataset includes health-related variables associated with patients' conditions. Models evaluated include Logistic Regression, Random Forest, SVM, AdaBoost, XGBoost, Gradient Boosting, Neural Network, and KNN.

# Model Evaluation Summary

1. Logistic Regression:
Accuracy: 80.33%
Log Loss: 0.51
Cannot identify class 1.

2. Random Forest:
Accuracy: 82.16%
Log Loss: 0.48
Poor detection of class 1 (15%).

3. SVM:
Accuracy: 81.59%
Log Loss: 0.50
Similar issues as Logistic Regression.

4.AdaBoost:
Accuracy: 81.15%
Log Loss: 1.05
Struggles with class 1 detection.


5. XGBoost:
Accuracy: 84.31%
Log Loss: 0.51
Best overall performance.
Gradient Boosting:

Accuracy: 82.92%
Log Loss: 0.45
Issues with class 1.

6. Neural Network:
Accuracy: 77.99%
Log Loss: 0.85
Lowest performance.

7. KNN:
Accuracy: 79.57%
Log Loss: 2.80
Struggles with class 1.

# Hyperparameter Tuning for XGBoost
The tuning process for the XGBoost model was performed using both Grid Search and Randomized Search techniques:

1. Grid Search:
Best Parameters:
colsample_bytree: 0.6
gamma: 0
learning_rate: 0.1
max_depth: 3
min_child_weight: 3
n_estimators: 200
subsample: 0.8
Best Cross-Validation Score: 82.75%

2.Randomized Search:
Best Parameters:
subsample: 0.8
n_estimators: 300
min_child_weight: 7
max_depth: 9
learning_rate: 0.02
gamma: 0.3
colsample_bytree: 0.5

> Best Cross-Validation Score: 82.69%
Although the tuned models showed improved performance compared to the default parameters, the baseline XGBoost model yielded an accuracy of 84.31% and a log loss of 0.51. This indicates that the initial configuration of the XGBoost model already provided strong predictive power, making it a viable option without further tuning.

# Conclusion
XGBoost performed best for predicting cirrhosis outcomes, followed by Gradient Boosting and Random Forest. All models struggled to identify class 1, indicating a need for improved handling of class imbalance.

# Clinical Relevance
Accurate prediction of cirrhosis outcomes is crucial for effective patient management and treatment planning. Misclassifying patients, particularly those in class 1, can lead to inadequate care and increased risk of severe complications. Enhancing model performance in identifying all classes can help clinicians make informed decisions, allocate resources efficiently, and improve patient prognoses. Addressing class imbalance in the dataset should be prioritized to ensure better diagnostic accuracy and patient outcomes.

# Feature Importance
The top three features contributing to the model's predictions are:

1. Bilirubin-Albumin Ratio: This feature is critical as it reflects liver function and the severity of liver disease. Higher ratios may indicate worsening liver function, helping to predict patient outcomes.

2. Prothrombin Category: Prothrombin time is an essential measure of blood clotting. Abnormal levels can signify liver dysfunction, making this feature vital for assessing cirrhosis severity and prognosis.

3. Hepatomegaly: The presence of liver enlargement is a significant indicator of liver disease severity. This feature aids in evaluating the physical state of the liver, contributing to accurate outcome predictions.

Incorporating these features effectively in the model can enhance its predictive power, leading to better clinical decisions and patient management.
