# GradientBoostingCovid19
Repository for the paper "Gradient boosting classification of COVID-19 severity from deep learning extracted CT features and non-imaging data in patients from a northern Italy hospital"
Due to the European Data Protection Law (GDPR16, European Union 2016-05-04) we can not condivide patients data.
Our predictive model is composed of the following steps:
1) CT image preprocessing
2) lungs extraction
3) CNN classifier training (evaluated on the validation set)
4) feature extraction
5) Principal Component Analysis of the extracted features
6) CatBoost preliminary classifier from clinical data and image extracted features 
7) Bayesian hyperparameter optimization with Optuna of the preliminary CatBoost classifier (on the training set)
8) Feature selection with a voting BorutaSHAP (Boruta with Shapley values) based procedure with the CatBoost preliminary classifier (on the training set)
9) CatBoost classifier on the reduced feature space
10) Bayesian hyperparameter optimization with Optuna to create a shortlist of CatBoost models (on the training set)
11) Choice of the best performing CatBoost model with overfitting detector (evaluated on the validation set)
12) Retraining the best CatBoost model on joined training+evaluation set and evaluation on the testset.  
The machine learning part of the model is in a Jupyter notebook.



)
