# Capstone Project: Customer Segmentation and Conversion Prediction

## Project Overview

This project is part of the Udacity Data Science Nanodegree's capstone, in collaboration with Arvato Bertelsmann, a mail-order sales company in Germany. The goal of the project is to analyze demographics data and identify customer segments using unsupervised learning techniques. We aim to compare these customer segments against demographics information for the general population. Finally, we build a supervised learning model to predict which individuals from a marketing campaign are most likely to convert into customers for Arvato.

## Datasets

**Udacity_AZDIAS_052018.csv:** Demographics data for the general population of Germany (891,211 rows, 366 columns).
**Udacity_CUSTOMERS_052018.csv:** Demographics data for Arvato customers (191,652 rows, 369 columns).
**Udacity_MAILOUT_052018_TRAIN.csv:** Marketing campaign data, including the RESPONSE column indicating customer conversion (42,982 rows, 367 columns).
**Udacity_MAILOUT_052018_TEST.csv:** Similar to the TRAIN dataset, but without the RESPONSE column for model evaluation (42,833 rows, 366 columns).
Each row in the datasets represents one individual, with features including household, building, and neighborhood information.

## Project Structure

### 1. Data Preprocessing

**Missing Values Handling:** Removed columns and rows with excessive missing values and imputed the remaining missing values.

**Feature Engineering:**

- Applied one-hot encoding for categorical variables.
- Standardized and scaled numerical features.

**Dimensionality Reduction:**

Used PCA (Principal Component Analysis) to reduce the feature space.

**Clustering:**

Implemented K-Means clustering to segment the general population.

## 2. Customer Segmentation

**K-Means Clustering:** Segmented the general population into distinct clusters.

**Customer Comparison:** Identified clusters that were over-represented in the customer dataset compared to the general population.

## 3. Supervised Learning

Built a classification model to predict customer conversion using the marketing campaign data.
Implemented various models including Logistic Regression, Random Forest, and XGBoost.
Hyperparameter Tuning: Used GridSearchCV to optimize the model’s parameters.
Dealing with Class Imbalance:
The marketing dataset was highly imbalanced (98.7% negative class).
Applied under-sampling and considered other techniques like SMOTE.
Evaluated model performance using ROC-AUC score and classification metrics.
4. Model Evaluation
Used the validation set for evaluation.
Achieved an improved ROC-AUC score post-tuning and under-sampling techniques.
Results
Customer Segmentation: Clustering identified customer groups that were more likely to convert. These over-represented clusters were targeted in the marketing campaign.
Predictive Model: After addressing class imbalance and fine-tuning, our best model achieved a ROC-AUC score of 0.61 on the validation set.
How to Run
Install dependencies:
bash
Copy code
pip install -r requirements.txt
Run the Jupyter Notebook:
bash
Copy code
jupyter notebook capstone_project.ipynb
Files Included
capstone_project.ipynb: Main notebook with the full analysis, including data preprocessing, clustering, and supervised learning.
requirements.txt: List of all dependencies and libraries required to run the notebook.
data/: Folder containing the datasets.
images/: Folder containing images and visualizations generated during analysis.
Future Work
Model Improvement: Further experiments with techniques like SMOTE or advanced ensemble models to handle class imbalance more effectively.
Feature Engineering: Explore additional feature selection or engineering to enhance model interpretability and performance.
Additional Data: Incorporating external data sources (if available) to better understand the demographic features and improve customer segmentation.
