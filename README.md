# GradientBoostingCovid19
Code repository for the paper "A hybrid machine learning/deep learning COVID-19 severity predictive model from CT images and clinical data".

Due to the European Data Protection Law (GDPR16, European Union 2016-05-04) patients dataset is not in this repository. Data can be made available from the corresponding author on reasonable requests upon ethical comittee approval.
Our predictive model is composed of the following steps:

**(In notebook CT_Covid.ipynb)**
1. CT image preprocessing
2. lungs extraction
3. CNN classifier training (evaluated on the validation set)

**(In notebook Feature_extraction_from_CT.ipynb)**

4. Feature extraction
5. Principal Component Analysis of the extracted features

**(In notebook Hybrid CatBoost Covid-19.ipynb)**

6) CatBoost preliminary classifier from clinical data and image extracted features 
7) Bayesian hyperparameter optimization with Optuna of the preliminary CatBoost classifier (on the training set)
8) Feature selection with a voting BorutaSHAP (Boruta with Shapley values) based procedure with the CatBoost preliminary classifier (on the training set)
9) CatBoost classifier on the reduced feature space
10) Bayesian hyperparameter optimization with Optuna to create a shortlist of CatBoost models (on the training set)
11) Choice of the best performing CatBoost model with overfitting detector (evaluated on the validation set)
12) Retraining the best CatBoost model on joined training+evaluation set and evaluation on the testset.  

