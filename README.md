# Telecom Customer Churn Prediction

## Project Overview
Interconnect, a telecommunications company, wants to improve customer retention by identifying clients who are likely to cancel their services. The objective of this project is to build a machine learning model that estimates customer churn risk and provides actionable information for targeted retention strategies.

## Business Objective
The model is designed to help the Marketing team prioritize customers with a higher probability of churn instead of applying retention campaigns to the entire customer base.

The initial performance target was a ROC-AUC of at least **0.75**, with a goal of achieving performance above **0.88**.

## Data
The project combines four datasets containing information about:

- Customer contracts
- Personal information
- Internet services
- Phone services

After integration, the dataset contains **7,043 customers**.

The target variable is `Churn`:
- `0` — active customer
- `1` — customer who cancelled the service

Class distribution:
- Active customers: **5,174**
- Churned customers: **1,869**

## Project Workflow
1. Data quality review and preprocessing
2. Integration of multiple datasets
3. Target variable creation
4. Exploratory data analysis
5. Feature preparation
6. Stratified train/validation/test split
7. One-hot encoding of categorical variables
8. Standardization of numerical variables
9. Training and comparison of machine learning models
10. Hyperparameter tuning
11. Final evaluation on an independent test set
12. Business recommendations

## Models Evaluated
The project compares:

- Logistic Regression
- Random Forest
- Balanced Random Forest
- CatBoost

Model performance was evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC

## Final Model
The selected model was a tuned **CatBoost Classifier**.

### Test Results

| Metric | Score |
|---|---:|
| Accuracy | 0.8581 |
| Precision | 0.8021 |
| Recall | 0.6176 |
| F1-score | 0.6979 |
| ROC-AUC | **0.8985** |

The validation ROC-AUC was **0.9056**, while the final test ROC-AUC was **0.8985**, showing reasonably stable performance on unseen data.

## Business Impact
The model can be used as an early-warning system to identify customers with a higher probability of cancellation.

With approximately **62% recall**, the model identifies a meaningful share of customers who eventually churn. Its approximately **80% precision** also means that most customers flagged as high risk actually belong to the churn class, helping Marketing focus retention resources more efficiently.

A practical implementation could segment customers into high-, medium-, and low-risk groups based on predicted churn probability. Retention actions and decision thresholds should then be adjusted according to the financial cost of an incentive compared with the cost of losing a customer.

## Limitations and Next Steps
Before production deployment, the company should:

- Select the classification threshold according to business costs
- Monitor model performance over time
- Retrain the model when customer behavior changes
- Consider cross-validation or systematic hyperparameter search for more robust model selection
- Evaluate the financial impact of retention campaigns

The model should support business decisions rather than replace them, since not every future cancellation will be detected.

## Technologies
- Python
- Pandas
- NumPy
- Scikit-learn
- CatBoost
- Matplotlib
- Data preprocessing
- Machine Learning
- Classification
- Hyperparameter tuning
- Model evaluation

## Repository Structure

```text
telecom-customer-churn/
├── README.md
├── telecom_customer_churn_portfolio.ipynb
└── requirements.txt
```

## Author
**Jesús Adrián Jiménez Vázquez**

Senior Geologist transitioning into Data Science and Data Analytics.
