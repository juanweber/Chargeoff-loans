# Chargeoff-loans
Prediction of which loans will be "Fully paid" or "charged off" using the Lending Club 2018 dataset.

This notebook aims to predict which loans will be either “Fully paid” or “Charged off”, taking Lending Club data from 2018. The dataset contains both numerical and categorical data gathered before and after loans are extended, so there is a need identify which features are determined after the fact. Categorical data is encoded into numerical values, and rows with outliers are discarded as well as features with constant, or missing values over 30%. Remaining missing values are replaced with the median of the corresponding feature. After this, the dataset is split into training and test sets. Training set is rebalanced, generating synthetic samples with the SMOTE algorithm, and then a data scaling is performed. PCA is applied with a Random Forest with default hyperparameters, giving 25 principal components, which then are used for running a series of default classifiers for finding the best one, finding that Extra Trees Classifier gives the best results, which is later optimized with RandomizedSearch with 3 Cross-validations for hyperparameter tuning. Final accuracy is 0.9036, but other evaluation criteria are poor. This could be improved with more extensive iterations of RandomizedSearchCV.

The 10 most important features for this classification exercise, according to the default Random Forest Classifier are:

Loan grade
Verification status
Loan sub-grade
Loan Term
Number of credit inquiries in past 6 months
Interest Rate on the loan
Number of open trades in last 6 months
Purpose for the loan provided by the borrower.
Employment length in years
Number of revolving trades opened in past 24 months
