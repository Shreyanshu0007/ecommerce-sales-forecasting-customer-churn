# Brazilian E-commerce Analysis and Customer Churn Prediction

## Project Overview

An exploratory data analysis and introductory machine-learning project using the Brazilian E-Commerce Public Dataset by Olist.

The project explores sales performance, product categories, and customer purchasing behaviour, then builds a Logistic Regression model to classify customer inactivity over a defined 180-day observation window.

The notebook demonstrates a foundational workflow using Python, Pandas, NumPy, Matplotlib, Seaborn, and Scikit-learn.

## Project Objectives

- Explore and prepare the Olist e-commerce datasets.
- Analyze historical revenue trends and product-category performance.
- Understand customer purchasing and repeat-order behaviour.
- Define customer inactivity using a 180-day prediction window.
- Prepare customer-level features and a target variable.
- Compare a simple Dummy Classifier baseline with Logistic Regression.
- Evaluate the models using a confusion matrix, precision, recall, and F1-score.
- Summarize findings and practical business recommendations.

## Dataset

**Source:** [Brazilian E-Commerce Public Dataset by Olist — Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

The dataset contains information about customers, orders, order items, payments, reviews, products, sellers, and geolocation.

- Currency: Brazilian Real (BRL).
- Historical coverage: 2016–2018.
- The project uses the nine original CSV files listed below.

### Dataset Setup

The raw dataset is not included in this repository. Download it from Kaggle and place the nine CSV files in `data/raw/`.

Expected files:

- `olist_customers_dataset.csv`
- `olist_geolocation_dataset.csv`
- `olist_order_items_dataset.csv`
- `olist_order_payments_dataset.csv`
- `olist_order_reviews_dataset.csv`
- `olist_orders_dataset.csv`
- `olist_products_dataset.csv`
- `olist_sellers_dataset.csv`
- `product_category_name_translation.csv`

Expected folder structure:

```text
project/
├── data/
│   └── raw/
│       ├── olist_customers_dataset.csv
│       ├── olist_geolocation_dataset.csv
│       ├── olist_order_items_dataset.csv
│       ├── olist_order_payments_dataset.csv
│       ├── olist_order_reviews_dataset.csv
│       ├── olist_orders_dataset.csv
│       ├── olist_products_dataset.csv
│       ├── olist_sellers_dataset.csv
│       └── product_category_name_translation.csv
├── notebooks/
│   └── 01_dataset_exploration.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

## Technologies and Concepts

- **Python**
- **Pandas and NumPy** — data loading, cleaning, grouping, and feature preparation
- **Matplotlib and Seaborn** — exploratory data visualization
- **Scikit-learn** — train-test split, Dummy Classifier, Logistic Regression, feature scaling, and classification metrics
- **Jupyter Notebook**
- **Git and GitHub**

## Notebook Workflow

1. Dataset loading and initial exploration
2. Data cleaning and preparation
3. Exploratory Data Analysis
4. Product and category performance
5. Customer behaviour and repeat-purchase analysis
6. Historical monthly revenue trend analysis
7. Customer inactivity definition and churn dataset preparation
8. Feature and target selection
9. Stratified 80/20 train-test split
10. Dummy Classifier baseline
11. Logistic Regression classification
12. Model evaluation and business interpretation

## Customer Inactivity Definition

For this notebook, a customer is labelled:

- `1` — no order observed during the 180-day prediction window (treated as inactive/churn for this analysis).
- `0` — at least one order observed during the 180-day prediction window (treated as active).

The feature cutoff is **1 April 2018**. Customer features are based on historical activity before the cutoff, and the target is based on activity in the following 180 days.

This is an analytical definition of inactivity for the available dataset. It does not prove that a customer has permanently churned.

## Machine Learning Results

The executed notebook contains **62,299 customers**:

- Inactive / churn label (`1`): **61,688 (99.02%)**
- Active label (`0`): **611 (0.98%)**

The test set contains 12,460 customers. The class distribution is highly imbalanced, so accuracy alone is misleading.

| Model | Accuracy | Inactive (1) Recall | Active (0) Recall |
|---|---:|---:|---:|
| Dummy Classifier | 0.9902 | 1.0000 | 0.0000 |
| Logistic Regression | 0.5774 | 0.5781 | 0.5082 |

Logistic Regression identifies some customers in both classes, while the Dummy Classifier predicts every customer as inactive. However, Logistic Regression's active-class precision is only **0.0118** and active-class F1-score is **0.0230**.

**Interpretation:** The current model has weak practical performance, especially when identifying active customers. The high baseline accuracy is caused by the extreme class imbalance. This is a learning project, not a deployment-ready churn system.

## Key Exploratory Findings

The notebook explores:

- Monthly product revenue and historical revenue changes.
- Product-category revenue performance.
- One-time versus repeat purchasing behaviour.
- Customer activity over the defined observation window.

The notebook outputs should be used as the source of the exact descriptive findings; the figures can change if the dataset or analysis is changed.

## Business Recommendations

Based on the descriptive analysis, possible actions include:

- Test loyalty initiatives that encourage a second purchase.
- Review category-level performance when planning merchandising and promotions.
- Examine customer communication and follow-up strategies.
- Improve the customer-level dataset and evaluate additional approaches before using inactivity predictions for business decisions.

These are recommendations for further investigation, not proven causal effects.

## Installation and Execution

Clone the repository:

```bash
git clone https://github.com/Shreyanshu0007/ecommerce-sales-forecasting-customer-churn.git
cd ecommerce-sales-forecasting-customer-churn
```

Create and activate a virtual environment if desired, then install the dependencies:

```bash
pip install -r requirements.txt
```

Start Jupyter:

```bash
jupyter notebook
```

Open `notebooks/01_dataset_exploration.ipynb` and run the cells in order. Make sure the nine CSV files are in `data/raw/` before running the notebook.

## Limitations

- The dataset is historical and covers 2016–2018.
- The analysis uses one defined feature cutoff and a 180-day observation window.
- No purchase during the observation window is a proxy for inactivity, not proof of permanent churn.
- The target classes are highly imbalanced (99.02% inactive and 0.98% active in the constructed cohort).
- Logistic Regression has weak active-class precision and F1-score.
- The notebook focuses on foundational EDA and classification concepts; it does not include advanced imbalance-handling or model-tuning methods.

## Conclusion

This project demonstrates a practical beginner-level data science workflow: loading and cleaning real-world data, exploring business patterns, preparing customer-level features, training a baseline and Logistic Regression classifier, and interpreting evaluation metrics.

The model results are reported with their limitations rather than presenting the classifier as production-ready.
