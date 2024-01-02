# Version-3.3-of-the-Tabular-Ensemble-with-XGBoost-LightGBM-scheduled-for-December-2023
Version 3.3 of the Tabular Ensemble with XGBoost/LightGBM, scheduled for December 2023
Version 3.3 of the Tabular Ensemble with XGBoost/LightGBM, scheduled for December 2023.
# Task Overview 
Task: In this synthetic dataset based off of a real dataset funded by the Mayo Clinic, each dataset row/example represents both general and survival information about a patient that has liver cirrhosis, a condition involving prolonged liver damage. The goal is to train a machine learning model that can predict the patient's current survival status based on the data features. 

Approach v1: Our approach will be to train a Logistic Regression model using sklearn to be used as a baseilne model and to then train a performance-focused model using XGBoost as a learning exercise.

Approach v2: After a few days of initial work, we realized that it was feasible within the competition timeframe to improve on Approach 1 by training an Ensemble of models so we changed our approach to training multiple Logistic Regression, Random Forest, and XGBoost models and then combining them into an ensemble.

Approach v3: After manual hyperparameter tuning all the models, we realized that the current Logistic Regression and Random Forest models were too weak to be included in the final Ensemble model. Instead we decided to add a LGBM classifier and create an Ensemble model with a LGBM classifier + XGBoost classifier. We also implemented k-fold cross validation for hyperparameter tuning to reduce variance in the results compared to the validation set approach. We also added the original dataset to the synthetic dataset which improved our results significantly. 

Version History
1. v1.0-1.3 - Implemented dataset loading and dataset pre-processing. Added explanations and comments for each step. 
2. v1.4 - Added Logistic Regression model training and Kaggle submission formatting
3. v2.0 - Added Random Forest and XGBoost model training and prediction.
4. v2.1 - Added log-loss calculations for each model on the validation set. 
5. v2.2 - Added initial hyperparameter tuning for Logistic Regression, Random Forest, and XGBoost models. 
6. v3.0 - Added LGBM Classifier and did hyperparameter tuning for the LGBM Classifier. Added explanations for model training / tuning
7. v3.1 - Combined the tuned LGBM Classifier and XGBoost classifer into an Ensemble model. 
8. v3.2 - Switched to K-Fold Cross Validation approach for all hyperparameter tuning. 
9. v3.3 - Combined original dataset with the synthetic dataset for training and updated log-loss scores accordingly. Did further hyperparameter tuning. 

Log-Loss Score Logs (Validation Scores using Synthetic Dataset only)
1. Default/Tuned Logistic Regression - 0.525 / 0.525
2. Default/Tuned Random Forest - 0.550 / 0.482
3. Default/Tuned XGBoost - 0.515 / 0.437 
4. Default/Tuned LGBM - 0.472 / 0.425
5. Tuned XGBoost / LGBM Ensemble Model - 0.431

Log-Loss Score Logs (Validation Scores using Both the Synthetic Dataset and Original Dataset)
1. Tuned Logistic Regression - 0.53
2. Tuned Random Forest - 0.507
3. Tuned XGBoost - 0.414
4. Tuned LGBM - 0.409
5. Tuned XGBoost / LGBM Ensemble Model - 0.409
