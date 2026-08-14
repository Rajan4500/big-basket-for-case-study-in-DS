# BigBasket Customer Analytics

## Overview

This project analyses customer purchasing behaviour using the **BigBasket Customer Analytics** dataset. The analysis is conducted from a commercial data analytics perspective, with a focus on understanding customer ordering patterns and determining whether historical purchasing behaviour can help identify high-volume orders.

The project includes data cleaning, feature engineering, exploratory data analysis, visualisation, machine learning, and model evaluation.

## Dataset

**Dataset:** BigBasket Customer Analytics

**Source:** Kaggle — BigBasket Customer Analytics

The dataset contains approximately 62,000 product-level transaction records covering multiple years of customer purchasing activity.

Key characteristics include:

* 62,141 transaction records
* 106 unique customers
* 8,387 unique orders
* 1,732 unique products/SKUs
* 216 unique product descriptions
* Customer, order, product and transaction-date information

## Data Preprocessing

The dataset was inspected for data quality before modelling.

The preprocessing included:

* Checking for missing values
* Checking for duplicate records
* Converting the `Created On` variable from Excel-style serial numbers and text dates into a standard datetime format
* Creating temporal features such as:

  * Year
  * Month
  * Day of week
  * Hour
* Aggregating product-level transactions into order-level observations
* Creating historical customer behaviour features
* Removing first customer orders when previous purchasing history was unavailable
* Preventing data leakage by ensuring historical features were calculated using only information from previous orders

## Machine Learning Problem

The analysis investigates:

> **Can historical customer purchasing behaviour help predict whether an order will be high-volume?**

An order was classified as a **high-volume order** when its number of items was above the median order size.

The target variable was:

`high_volume_order`

where:

* `0` = Low-volume order
* `1` = High-volume order

## Machine Learning Model

### Decision Tree Classifier

A Decision Tree Classifier was used to identify relationships between previous customer behaviour, ordering frequency, time-related variables, and order volume.

The main predictor variables included:

* Previous number of orders
* Previous average order size
* Days since previous order
* Month
* Day of week
* Hour
* Year

## Model Evaluation

The model was evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion matrix
* Majority-class baseline accuracy

### Results

| Metric            | Result |
| ----------------- | -----: |
| Accuracy          | 59.57% |
| Precision         | 50.88% |
| Recall            | 50.59% |
| F1-score          | 50.74% |
| Baseline Accuracy | 58.84% |

The Decision Tree improved upon the baseline by approximately **0.72 percentage points**.

## Feature Importance

The most influential features identified by the Decision Tree were:

1. Previous average order size — 35.53%
2. Previous number of orders — 17.85%
3. Hour — 13.60%
4. Days since previous order — 13.51%
5. Month — 9.14%

These results suggest that historical customer purchasing behaviour was more informative than the general calendar variables.

## Exploratory Analysis

The project also investigates purchasing behaviour through visualisations, including:

* Monthly order trends
* Orders by hour
* Customer order frequency
* Previous average order size versus current order size
* Average order size over time

These visualisations provide descriptive insights into customer behaviour beyond the predictive modelling results.

## Key Findings

The analysis suggests that previous customer purchasing behaviour, particularly historical average order size, provides the strongest signal for identifying high-volume orders.

However, the Decision Tree achieved only a small improvement over the majority-class baseline. This indicates that the available variables provide useful descriptive information but have limited predictive power.

Additional commercial variables such as promotions, discounts, product categories, customer demographics, loyalty behaviour, and marketing interactions could potentially improve predictive performance.

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Jupyter Notebook

## Project Structure

```text
BigBasket-Customer-Analytics/
│
├── bigBasket.csv
├── BigBasket_Analysis.ipynb
└── README.md
```
