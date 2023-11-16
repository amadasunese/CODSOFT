
Credit Card Fraud Detection Model Development Report

The goal of this project was to build a machine learning model capable of identifying fraudulent credit card transactions. Given a dataset of credit card transactions, the model aims to classify each transaction as either fraudulent or genuine.

Dataset Overview

The dataset contains transactions with features labeled V1 through V28, a result of Principal Component Analysis (PCA) for anonymization and dimensionality reduction. Other features include 'Time' (seconds elapsed between each transaction and the first transaction in the dataset) and 'Amount' (transaction amount). The target variable 'Class' indicates whether a transaction is fraudulent (1) or genuine (0).

Data Preprocessing

•	Loading Data: The dataset was loaded into a Pandas DataFrame for analysis and processing.
•	Handling Missing Values: We checked for missing values and found none, simplifying the preprocessing.
•	Feature Normalization: The 'Amount' feature was normalized using a standard scaler to ensure consistency with the PCA-transformed features.
•	Feature Selection: The 'Time' feature was dropped, as it was deemed not relevant for fraud detection.
•	Data Splitting: The data was split into training and testing sets, with 80% for training and 20% for testing, while maintaining the class distribution in both.
•	Handling Class Imbalance

The dataset exhibited a significant class imbalance, with the majority being genuine transactions. Various strategies were considered to address this:

•	Class Weight Adjustment: The model was trained with class weights inversely proportional to class frequencies.
•	SMOTE: Synthetic Minority Over-sampling Technique was considered but not implemented due to library constraints.
•	Anomaly Detection Algorithms: An alternative approach discussed but not pursued in this instance.

Model Development
A Random Forest classifier was chosen for its robustness and suitability for handling imbalanced data. The model was trained with the following settings:

•	Random Forest Parameters: Default parameters with class_weight='balanced' to adjust for class imbalance.
•	Training: The model was trained on the preprocessed training set.

