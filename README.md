# Data Science Analysis: Retail Customer & Sales Behaviour

This project investigates retail purchasing behaviour using two publicly available datasets: the BigBasket Customer Analytics dataset and the Supermarket Sales dataset.

The analysis follows a commercial data analytics perspective, focusing on customer purchasing patterns, order behaviour, and the ability of machine learning models to identify high-volume or high-quantity transactions.

## Objectives

- Clean and preprocess two retail datasets.
- Perform exploratory data analysis and visualise purchasing trends.
- Engineer meaningful customer, order, and temporal features.
- Apply machine learning algorithms to identify purchasing patterns.
- Evaluate model performance using appropriate classification metrics.
- Compare model performance against baseline predictions.
- Identify the most influential variables and discuss their commercial relevance.

## Machine Learning Models

### BigBasket
- **Decision Tree Classifier**
- Target: High-volume order
- Evaluation: Accuracy, Precision, Recall, F1-score, and baseline accuracy.

### Supermarket Sales
- **Random Forest Classifier**
- Target: High-quantity transaction
- Evaluation: Accuracy, Precision, Recall, F1-score, and baseline accuracy.

## Key Findings

The BigBasket Decision Tree identified previous average order size as the most influential feature, followed by previous order frequency and ordering time. However, its predictive performance was only marginally better than the baseline.

The Supermarket Sales Random Forest identified unit cost, customer rating, and transaction timing as the most influential features. However, the model performed approximately at baseline level, indicating limited predictive power from the available variables.

Overall, the analysis demonstrates the difference between variables that are useful for understanding purchasing behaviour and variables that provide sufficient information for reliable prediction.
