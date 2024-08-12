# Comparing Classifiers

This project explores and compares the performance of several classification algorithms on a dataset related to the marketing of bank products. The goal is to predict whether a client will subscribe to a term deposit based on various features, using different machine learning models.

## Overview

The dataset used in this project comes from a Portuguese banking institution and is a collection of the results of multiple marketing campaigns. The classification task involves predicting a binary outcome: whether or not a client subscribes to a term deposit.

## Models Compared

The following machine learning models were compared in this project:

1. **Logistic Regression**
2. **K-Nearest Neighbors (KNN)**
3. **Decision Tree**
4. **Support Vector Machine (SVM)**

## Key Steps

1. **Data Preparation**: The data was preprocessed, including handling missing values, encoding categorical variables, and scaling features as needed.
2. **Baseline Model**: A baseline model was established using the majority class for comparison against more complex models.
3. **Model Training**: Each model was trained using default settings and then optimized using hyperparameter tuning.
4. **Model Evaluation**: The models were evaluated based on accuracy, F1-score, and ROC-AUC, with a focus on the impact of class imbalance.

## Findings

- **Logistic Regression**: Achieved a good balance between performance and computational efficiency, making it the preferred model.
- **KNN**: Performed similarly to Logistic Regression but struggled with class imbalance, leading to a lower F1-score.
- **Decision Tree**: Showed potential but required careful tuning to avoid overfitting.
- **SVM**: Performed well but was computationally expensive, making it less practical for larger datasets.

## Interpretation of Statistics

### Descriptive Stats
- **Class Distribution**: Most clients didn't subscribe to a term deposit (`no` ≈ 89%), making our target variable imbalanced. This has a big impact on how our models perform.
- **Feature Correlations**: Some features, like `emp.var.rate`, `euribor3m`, and `nr.employed`, are highly correlated. This might cause redundancy in the model, potentially harming its ability to generalize.

### Inferential Stats
- **Logistic Regression**: Accuracy is solid at 91%, with a strong ROC-AUC of 0.93. However, it struggles to identify the minority class (`yes`), with a recall of just 0.39.
- **KNN**: After tuning, it shows decent accuracy but a low F1-score (0.3666), indicating it's not great at predicting `yes`.
- **Decision Tree**: Hits 90.9% accuracy with tuning, but overfitting is a concern—it aces the training set (100%) but slips on the test set.
- **SVM**: Also good accuracy (90.9%), but it's much slower, which could be a problem with larger datasets.

## Findings & Actionable Insights

1. **Imbalance Issue**: The biggest challenge is the class imbalance. While models like Logistic Regression do well overall, they often miss potential subscribers (`yes`).
2. **Efficiency**:
  - **Logistic Regression** is fast and performs well, making it a top pick.
  - **KNN** is quick but struggles with imbalance.
  - **Decision Tree** looks promising but needs careful tuning.
  - **SVM** is accurate but slow, so maybe not ideal for bigger datasets.
3. **Feature Importance**: Not all features are created equal. Focusing on the most impactful ones could boost model performance.

## Next Steps & Recommendations

1. **Tune Models More**: Keep tweaking hyperparameters, especially for Decision Tree and KNN, to improve minority class predictions.
2. **Tackle Imbalance**: Try SMOTE or class weighting to boost recall for `yes`—reducing false negatives could mean more successful targeting.
3. **Shift Metrics**: Move beyond accuracy to metrics like F1-score, precision, or recall to better reflect your business goals.
4. **Feature Engineering**: Revisit your feature set—consider interactions, drop redundant ones, and explore new features based on your domain knowledge.
5. **Deploy the Best Model**: If Logistic Regression is working well, deploy it, but keep an eye on performance and be ready to update as needed.
6. **Monitor & Iterate**: After deployment, keep track of how the model is doing, especially its ability to identify potential subscribers. Regular updates with new data will help maintain and improve performance.
