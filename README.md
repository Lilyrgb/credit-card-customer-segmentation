# Credit Card Customer Segmentation

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Lilyrgb/credit-card-customer-segmentation/blob/main/credit-card-customer-segmentation.ipynb)

## Overview

This project applies an end-to-end data science workflow to segment credit card customers according to their financial behavior. It combines exploratory analysis, data-quality remediation, feature engineering, preprocessing, K-Means clustering, cluster interpretation, and targeted marketing recommendations.

## Business Objective

Customer segmentation helps financial institutions understand different usage patterns, identify high-value and at-risk groups, and design more relevant retention, engagement, credit, and cross-selling strategies.

## Repository Contents

| File | Description |
| --- | --- |
| `credit-card-customer-segmentation.ipynb` | Clean English Google Colab notebook containing the complete analysis and segmentation workflow. |

## Analysis Workflow

### 1. Exploratory Data Analysis

- Review data types, missing values, duplicates, and descriptive statistics.
- Visualize monetary and behavioral-frequency distributions.
- Identify skewed variables and structural anomalies.

### 2. Data Quality Remediation

The notebook checks and corrects issues such as out-of-range frequency values, inconsistent purchase totals, and conflicting transaction counters. It also creates two business-relevant features:

- `OVER_LIMIT_FLAG` — indicates when the balance exceeds the credit limit.
- `PAYMENT_RATIO` — compares actual payments with minimum payments.

### 3. Preprocessing

- Impute missing `MINIMUM_PAYMENTS` and `CREDIT_LIMIT` values with their medians.
- Remove the unique `CUST_ID` identifier.
- Standardize numerical variables with `StandardScaler`.

### 4. Cluster Selection and Modeling

- Compare candidate values of k with the Elbow Method.
- Evaluate clustering quality with Silhouette Scores.
- Fit a four-cluster K-Means model using `n_init=10` and `random_state=42`.

The notebook records a higher Silhouette Score at k=3 than at k=4, while k=4 is retained for a more detailed and business-interpretable segmentation.

## Customer Segments

| Cluster | Segment | Approx. size | Main behavior |
| ---: | --- | ---: | --- |
| 1 | High Spenders / Responsible Payers | 4.7% | High purchases, high credit limits, and strong payment behavior |
| 2 | Low Users | 44.7% | Limited activity, low purchases, and low engagement |
| 3 | Cash Advance Users / Minimum Payers | 13.4% | Frequent cash advances, high balances, and greater repayment risk |
| 4 | Consistent Installment Buyers | 37.2% | Frequent installment purchases and reliable payment behavior |

## Business Applications

- Retain high-value customers through premium rewards and cross-selling.
- Reactivate low-usage customers with onboarding and engagement campaigns.
- Support higher-risk customers with repayment and debt-management offers.
- Increase installment-customer value through merchant partnerships and targeted promotions.

## Technologies

- Python 3
- Google Colab
- pandas and NumPy
- Matplotlib and Seaborn
- scikit-learn
- K-Means clustering
- Elbow Method and Silhouette Score

## Dataset

The notebook automatically loads the credit-card customer dataset from a public CSV source. The analysis covers 8,950 customers and behavioral variables related to balances, purchases, cash advances, payment patterns, credit limits, and transaction frequency.

## How to Run

1. Click the **Open in Colab** badge above.
2. Run the notebook cells in order.
3. Review the data-quality checks and transformations.
4. Inspect the Elbow Method and Silhouette Score charts.
5. Explore the final cluster profiles, visualizations, and marketing recommendations.

## Publication Notes

- Saved execution outputs and personal notebook metadata were removed for a clean repository version.
- Python syntax was validated across all code cells.
- Cluster labels were aligned with the final reported cluster results.
