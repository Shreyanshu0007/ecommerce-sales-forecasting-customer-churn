# E-commerce Sales Forecasting and Customer Churn Prediction

## Project Overview

An end-to-end Data Science project using the Brazilian E-Commerce Public Dataset by Olist. This project explores sales performance, product categories, customer purchasing behaviour, sales forecasting, and customer inactivity using Python and Machine Learning.

## Business Objectives

- Analyze historical e-commerce sales and revenue trends.
- Identify top-performing product categories.
- Understand customer purchasing and repeat-order behaviour.
- Explore customer inactivity over a 180-day prediction window.
- Develop and evaluate baseline machine learning models.
- Generate actionable business recommendations.

## Dataset

**Source:** [Brazilian E-Commerce Public Dataset by Olist — Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

The dataset contains information about customers, orders, products, sellers, payments, reviews, and geolocation.

Currency: Brazilian Real (BRL).

## Dataset Setup

The dataset is not included in this GitHub repository because the raw and processed CSV files are excluded through `.gitignore`.

To run this project locally:

1. Download the [Brazilian E-Commerce Public Dataset by Olist from Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).
2. Extract the downloaded files.
3. Create the following folder structure in the project root:

```text
data/
├── raw/
```

4. Place all nine original CSV files inside `data/raw/`.

The expected files are:

- olist_customers_dataset.csv
- olist_geolocation_dataset.csv
- olist_order_items_dataset.csv
- olist_order_payments_dataset.csv
- olist_order_reviews_dataset.csv
- olist_orders_dataset.csv
- olist_products_dataset.csv
- olist_sellers_dataset.csv
- product_category_name_translation.csv

5. Run the notebook from the `notebooks/` directory or use the paths specified in the notebook.

The cleaned dataset is generated during the data preparation process.

## Technologies Used

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Jupyter Notebook
- Git and GitHub

## Project Structure

```text
Project_1_Ecommerce/
├── data/
│   └── raw/
├── notebooks/
│   └── 01_dataset_exploration.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

## Project Workflow

1. Dataset loading and initial exploration
2. Data cleaning and preparation
3. Exploratory Data Analysis
4. Product and category performance analysis
5. Customer behaviour and retention analysis
6. Sales forecasting
7. Customer churn analysis
8. Feature engineering and dataset preparation
9. Machine learning model development
10. Model evaluation and comparison
11. Business insights and recommendations

## Key Business Findings

- November 2017 recorded the highest monthly revenue at approximately R$987,765.
- Health & Beauty was the highest-revenue product category, generating approximately R$1.26 million.
- Approximately 97% of customers made only one purchase in the historical delivered-sales analysis.
- The repeat buyer rate was approximately 3%.

## Machine Learning

Three classification models were evaluated:

- Dummy Classifier
- Logistic Regression
- Random Forest

The churn analysis used a 180-day prediction window.

**Important:** The target represents no observed purchase during the prediction window, not confirmed permanent churn.

Logistic Regression achieved the highest balanced accuracy among the three evaluated models (0.5432). However, its performance remained weak, particularly for identifying active customers. The model is not deployment-ready.

## Business Recommendations

- Introduce loyalty programs to encourage repeat purchases.
- Use personalized offers to encourage second purchases.
- Focus marketing efforts on high-revenue categories.
- Analyze seasonal sales patterns for campaign planning.
- Improve customer-level features and class-imbalance handling before deploying churn models.

## Installation

Clone the repository:

```bash

git clone https://github.com/Shreyanshu0007/ecommerce-sales-forecasting-customer-churn.git

cd ecommerce-sales-forecasting-customer-churn

```

Install dependencies:

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open `notebooks/01_dataset_exploration.ipynb`.

## Limitations

- The dataset covers a historical period from 2016 to 2018.
- Some calendar years are incomplete.
- Customer inactivity is an analytical proxy, not proof of permanent churn.
- The churn dataset is extremely imbalanced.
- Sales forecasting is based on a relatively short historical time series.

## Conclusion

This project demonstrates an end-to-end Data Science workflow involving data exploration, cleaning, visualization, forecasting, customer analysis, machine learning, and business recommendations.

It also highlights the importance of selecting appropriate evaluation metrics and interpreting machine learning results carefully when dealing with imbalanced datasets.