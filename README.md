# 🛍️ Retail Sales Prediction — End-to-End Machine Learning Pipeline

A complete end-to-end machine learning project that predicts the total purchase amount of retail transactions using customer demographics and product information. Built as part of a data science capstone, this project covers everything from raw data cleaning to a live interactive web application.

---

## 📌 Project Overview

Retail businesses deal with thousands of transactions daily. Understanding what drives purchase value can help with inventory planning, pricing strategies, and customer targeting. In this project, I built a machine learning pipeline that takes in transaction details and predicts how much a customer is likely to spend.

The target variable is **Total Amount** — the total value of a retail transaction.

---

## 📂 Project Structure

```
retail-sales-ml/
│
├── Capstone_Retail_Sales_Prediction.ipynb   # Main notebook (all phases)
├── retail_sales_dataset.csv                 # Dataset
└── README.md                                # You are here
```

---

## 🗂️ Dataset

The dataset contains **1,000 retail transactions** with the following features:

| Column | Description |
|---|---|
| Transaction ID | Unique identifier for each transaction |
| Date | Date of purchase |
| Customer ID | Unique customer identifier |
| Gender | Customer gender (Male/Female) |
| Age | Customer age |
| Product Category | Type of product (Beauty, Clothing, Electronics) |
| Quantity | Number of items purchased |
| Price per Unit | Price of a single item |
| Total Amount | Total transaction value *(target variable)* |

---

## 🔧 Project Pipeline

### Phase 1 — Data Loading & Cleaning
- Loaded the dataset using Pandas
- Converted the `Date` column to datetime format
- Extracted `Month` and `Day of Week` as new features
- Checked for and confirmed zero missing values and duplicates
- Stripped whitespace from categorical columns

### Phase 2 — Exploratory Data Analysis (EDA)
Generated 5 visualizations to understand the data:

- **Average spend by Product Category** — Electronics had the highest average transaction value
- **Revenue by Gender** — fairly balanced split between male and female customers
- **Monthly Revenue Trend** — visible peaks suggesting seasonal demand
- **Age Distribution** — customers range from 18–64 with an even spread
- **Correlation Heatmap** — Price per Unit and Quantity showed the strongest correlation with Total Amount

### Phase 3 — Feature Engineering & Preprocessing
- Applied **Label Encoding** to Gender and Product Category
- Defined feature matrix **X** (7 features) and target **y** (Total Amount)
- Split the data: **80% training / 20% testing**

### Phase 4 — Model Training & Evaluation
Trained and compared two regression models:

| Model | MAE | R² |
|---|---|---|
| Linear Regression | Higher | Lower |
| Random Forest Regressor | Lower ✅ | Higher ✅ |

**Random Forest** was selected as the best model.

Feature importance analysis showed:
- `Price per Unit` — most influential predictor
- `Quantity` — second most influential
- `Age`, `Gender`, `Month` — minimal impact

### Phase 5 — Interactive Web App (Gradio)
Deployed the trained Random Forest model into a **live Gradio web app** that allows users to:
- Input customer age, gender, product category, quantity, price, month, and day of week
- Get a real-time predicted Total Amount instantly

---

## 🚀 How to Run

### Option 1 — Google Colab (Recommended)
1. Open the notebook in [Google Colab](https://colab.research.google.com/)
2. Upload `retail_sales_dataset.csv` to the Colab files panel
3. Run all cells from top to bottom
4. The Gradio app will launch automatically at the end

### Option 2 — Local
1. Clone the repo
```bash
git clone https://github.com/nike750/retail-sales-ml.git
cd retail-sales-ml
```

2. Install dependencies
```bash
pip install pandas numpy scikit-learn matplotlib seaborn gradio
```

3. Launch Jupyter and open the notebook
```bash
jupyter notebook Capstone_Retail_Sales_Prediction.ipynb
```

---

## 🛠️ Tools & Libraries

| Tool | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | Data loading and manipulation |
| NumPy | Numerical computations |
| Scikit-learn | Model training, encoding, evaluation |
| Matplotlib & Seaborn | Data visualization |
| Gradio | Interactive web app |

---

## 📊 Key Findings

- **Price per Unit and Quantity** are the strongest drivers of Total Amount — which makes sense since Total Amount = Quantity × Price per Unit
- **Random Forest significantly outperformed** Linear Regression, capturing non-linear relationships in the data
- **Customer demographics** (age, gender) had very little influence on how much someone spends
- **Seasonality** shows some effect — certain months had noticeably higher sales

---

## 👩‍💻 About

Built by **Olanike Olaniyi** — AI/ML Engineer & Data Science student.  
Part of an end-to-end ML capstone project.

[![GitHub](https://img.shields.io/badge/GitHub-nike750-181717?style=flat&logo=github)](https://github.com/nike750)
