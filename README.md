# CA04_Ensemble_Models
Computer Assignment 04 Ensemble Models

CA04 – Ensemble Models

Course: BSAN 6070 – Machine Learning
Student: Sebastian Zapata-Ochoa
Assignment: CA04 – Ensemble Methods

📌 Overview

This project builds and evaluates four ensemble classification models using the U.S. Census Income dataset:

Random Forest

AdaBoost

Gradient Boosting

XGBoost

The goal of this assignment is to analyze how model performance changes as the number of estimators increases and to identify the optimal estimator value within a specified range.

For each model, performance is evaluated using:

Accuracy

AUC (Area Under the ROC Curve)

📊 Dataset

The dataset was obtained from the Census Bureau and includes:

48,842 observations

7 demographic attributes

Binary target variable:

>50K (1)

<=50K (0)

The dataset was loaded using the required path:

https://github.com/ArinB/MSBA-CA-03-Decision-Trees/blob/master/census_data.csv?raw=true

Training and testing data were separated using the provided dataset indicator column.

🧹 Data Preparation

The preprocessing steps mirror those completed in CA03:

Encoding categorical variables using pd.get_dummies

Converting target variable to binary (0/1)

Separating features (X) and target (y)

Splitting into training and testing sets based on dataset flag

No additional data quality assessment (DQA) was required per assignment instructions.

🔬 Model Training Approach

For each model, the hyperparameter n_estimators was varied across:

[50, 100, 150, 200, 250, 300, 350, 400, 450, 500]

All other hyperparameters were left at default values.

For each estimator value:

The model was trained on the training data.

Predictions were generated on the test set.

Accuracy was calculated.

AUC was calculated using predicted probabilities.

Results were plotted:

Accuracy vs. n_estimators

AUC vs. n_estimators

📈 Model Results Summary
Gradient Boosting

Best Accuracy: 0.8485 at 200 estimators

Best AUC: 0.8996 at 350 estimators

AdaBoost

Best Accuracy: 0.8442 at 350 estimators

Best AUC: 0.8967 at 350 estimators

XGBoost

Best Accuracy: 0.8465 at 50 estimators

Best AUC: 0.8976 at 50 estimators

(Random Forest results included in notebook output.)

📊 Performance Comparison

Among the tested models:

Gradient Boosting achieved the highest overall AUC

AdaBoost showed steady improvement with increasing estimators

XGBoost reached peak performance quickly (at lower estimator values)

Boosting methods generally demonstrated stronger discriminative power compared to bagging-based Random Forest

Gradient Boosting provided the strongest overall performance balance between Accuracy and AUC.

🧠 Key Observations

Increasing estimators improves performance up to a plateau.

Beyond optimal points, improvements are marginal.

Boosting models may reach optimal performance with fewer estimators.

AUC often continues improving slightly even when Accuracy plateaus.
