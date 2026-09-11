# 🛍️ Customer Shopping Behavior Analysis

### Turning Customer Transaction Data into Actionable Business Insights

> **An end-to-end data analytics project using Python, SQL, and Power BI to analyze customer purchasing behavior, identify valuable customer segments, and support data-driven marketing and business strategies.**

---

## 📌 Project Overview

Understanding **why customers buy, what they buy, and what influences their purchasing decisions** is critical for improving sales, customer satisfaction, and long-term loyalty.

This project analyzes **3,900 customer purchase transactions across 18 attributes** to uncover patterns in:

* 👥 Customer demographics
* 🛒 Product preferences
* 💰 Purchase and spending behavior
* 🎯 Discount usage
* ⭐ Product ratings
* 📦 Shipping preferences
* 🔄 Customer loyalty and repeat purchases
* 💳 Subscription behavior
* 🌦️ Seasonal purchasing patterns

The analysis follows a complete data analytics workflow:

**Raw Data → Data Cleaning → Exploratory Analysis → SQL Analysis → Power BI Dashboard → Business Recommendations**

---

## 🎯 Business Problem

A leading retail company wants to better understand its customers' shopping behavior to improve **sales, customer engagement, satisfaction, and long-term loyalty**.

The key business question addressed in this project is:

> **"How can the company leverage consumer shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?"**

The analysis focuses on understanding the factors that influence customer decisions, including **discounts, product reviews, seasons, payment preferences, demographics, and purchasing behavior**.

---

## 📊 Dataset

The dataset contains:

| Metric               | Details                                 |
| -------------------- | --------------------------------------- |
| **Total Purchases**  | 3,900                                   |
| **Total Columns**    | 18                                      |
| **Data Type**        | Customer shopping transaction data      |
| **Missing Values**   | 37 values in `Review Rating`            |
| **Primary Analysis** | Customer behavior & purchasing patterns |

### Key Features

**Customer Information**

* Age
* Gender
* Location
* Subscription Status

**Purchase Information**

* Item Purchased
* Category
* Purchase Amount
* Season
* Size
* Color

**Shopping Behavior**

* Discount Applied
* Previous Purchases
* Frequency of Purchases
* Review Rating
* Shipping Type

The dataset structure and missing-value information are documented in the project analysis.

---

# 🔄 Project Workflow

```text
                ┌──────────────────────┐
                │      Raw Dataset     │
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │  Python / Pandas     │
                │ Data Cleaning & EDA  │
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │      PostgreSQL      │
                │   SQL Analysis      │
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │      Power BI       │
                │ Interactive Dashboard│
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │ Business Insights &  │
                │ Recommendations      │
                └──────────────────────┘
```

---

# 🐍 1. Data Preparation & Analysis — Python

Python was used for **data cleaning, exploration, transformation, and feature engineering**.

### Key Steps

#### 📥 Data Loading

The raw CSV dataset was imported using **Pandas**.

```python
import pandas as pd

df = pd.read_csv("customer_shopping_behavior.csv")
```

#### 🔍 Exploratory Data Analysis

Initial exploration was performed using:

* `df.info()`
* `df.describe()`
* Null-value analysis
* Data structure inspection

#### 🧹 Missing Value Treatment

The dataset contained **37 missing values in the Review Rating column**.

Missing ratings were imputed using the **median review rating of the corresponding product category**, helping preserve category-level rating behavior.

#### 🏷️ Column Standardization

Column names were standardized to improve readability and maintain consistency throughout the analysis.

#### ⚙️ Feature Engineering

New analytical features were created, including:

* `age_group`
* `purchase_frequency_days`

Age groups were created through age-based binning, while purchase frequency was transformed into a more analysis-friendly format.

#### 🔎 Data Consistency

The relationship between `discount_applied` and `promo_code_used` was examined, and `promo_code_used` was removed due to redundancy.

---

# 🗄️ 2. SQL Business Analysis

The cleaned dataset was integrated into **PostgreSQL** for structured business analysis.

SQL was used to answer **10 key business questions**.

### 🔹 Business Questions

| #  | Business Question                                                                 |
| -- | --------------------------------------------------------------------------------- |
| 01 | What is the total revenue generated by male vs. female customers?                 |
| 02 | Which customers used discounts but still spent above the average purchase amount? |
| 03 | Which are the top 5 products with the highest average review ratings?             |
| 04 | How do average purchase amounts compare between Standard and Express shipping?    |
| 05 | Do subscribed customers spend more than non-subscribers?                          |
| 06 | Which 5 products have the highest percentage of discounted purchases?             |
| 07 | How can customers be segmented into New, Returning, and Loyal groups?             |
| 08 | What are the top 3 most purchased products within each category?                  |
| 09 | Are repeat buyers more likely to subscribe?                                       |
| 10 | What is the revenue contribution of each age group?                               |

These queries use SQL techniques including:

* `GROUP BY`
* `ORDER BY`
* Aggregate functions
* `CASE`
* Subqueries
* `CTE`
* `ROW_NUMBER()`
* Conditional aggregation
* Window functions

## The complete set of business queries is included in the repository.

# 📈 3. Power BI Dashboard

An interactive **Power BI dashboard** was developed to transform the analysis into an easy-to-understand visual format.

The dashboard focuses on:

* Revenue analysis
* Customer demographics
* Product performance
* Shipping behavior
* Subscription impact
* Customer segmentation
* Discount behavior
* Customer purchasing patterns

The dashboard enables stakeholders to explore trends and identify opportunities for **data-driven decision-making**.

### Dashboard Highlights

**💰 Revenue Insights**

Female customers generate slightly higher total revenue than male customers in the analyzed dataset.

**📦 Shipping Behavior**

Customers choosing Express Shipping show a higher average purchase value than Standard Shipping customers.

**💳 Subscription Behavior**

Subscription status shows a meaningful relationship with customer spending and repeat purchasing behavior.

**👥 Customer Segmentation**

Customers are categorized into:

* **New**
* **Returning**
* **Loyal**

This segmentation helps identify opportunities to move customers toward higher-value relationships.

The dashboard analysis reports a distribution of approximately **50% New, 35% Returning, and 15% Loyal customers**.

---

# 💡 Key Business Insights

### 1. 👥 Customer Segmentation

A significant proportion of customers fall into the **New** customer segment, creating an opportunity to improve retention and encourage repeat purchases.

> **Business Opportunity:** Convert New customers → Returning customers → Loyal customers.

---

### 2. 💳 Subscription Opportunity

Subscription behavior is associated with higher customer value and repeat purchasing patterns.

> **Business Opportunity:** Strengthen subscription programs through exclusive benefits and targeted offers.

---

### 3. 🎯 High-Value Discount Customers

The analysis identifies customers who use discounts while still spending above the average purchase amount.

These customers represent a valuable segment because they combine **high spending with promotional responsiveness**.

> **Business Opportunity:** Target high-value discount users with personalized or exclusive offers.

---

### 4. 📦 Express Shipping Customers

The analysis shows that customers using Express Shipping have a higher average purchase amount than Standard Shipping customers.

The dashboard reports approximately:

* **Express Shipping:** $65 average purchase
* **Standard Shipping:** $58 average purchase

This represents approximately **12% higher spending per transaction** for Express Shipping customers.

> **Business Opportunity:** Explore premium shipping as a potential indicator of higher customer value.

---

### 5. ⭐ Product Performance

Top-rated products can be leveraged in marketing campaigns and product positioning strategies.

> **Business Opportunity:** Highlight highly rated and best-selling products to improve product visibility and customer engagement.

---

# 🚀 Business Recommendations

Based on the analysis, the following strategies are recommended:

### 💳 1. Boost Subscription Adoption

Promote exclusive benefits and incentives to encourage customers to subscribe.

### 🔄 2. Strengthen Customer Loyalty

Introduce loyalty programs that reward repeat purchases and help transition customers into the **Loyal** segment.

### 🎯 3. Implement Targeted Marketing

Focus marketing efforts on:

* High-revenue customer segments
* High-value discount users
* Express Shipping customers
* High-revenue age groups

### 🛍️ 4. Improve Product Positioning

Use customer ratings and purchase frequency to identify products that should receive greater promotional visibility.

### 🏷️ 5. Review Discount Strategy

Balance the benefits of discounts in driving purchases against the need to maintain healthy margins.

These recommendations align with the project's documented business recommendations.

---

# 🛠️ Tools & Technologies

### Programming & Analysis

* 🐍 **Python**
* **Pandas**
* **Jupyter Notebook**

### Database & SQL

* 🐘 **PostgreSQL**
* **SQL**
* **SQLAlchemy**

### Data Visualization

* 📊 **Microsoft Power BI**

### Data & Documentation

* CSV
* Jupyter Notebook
* SQL
* Power BI
* PowerPoint

---

# 📁 Repository Structure

```text
Customer-Shopping-Behavior-Analysis/
│
├── 📂 data/
│   └── customer_shopping_behavior.csv
│
├── 📂 python/
│   └── Customer_Shopping_Behavior_Analysis.ipynb
│
├── 📂 sql/
│   └── customer_behavior_sql_queries.sql
│
├── 📂 powerbi/
│   └── customer_behavior_dashboard.pbix
│
├── 📂 presentation/
│   └── Customer-Shopping-Behavior-Analysis.pptx
│
├── 📄 Business Problem.pdf
├── 📄 Customer Shopping Behavior Analysis.pdf
└── 📄 README.md
```

> **Note:** The folder structure above is a recommended GitHub organization. Rename/move files accordingly if your repository currently uses a different structure.

---

# 📌 Project Deliverables

| Deliverable           | Description                              |
| --------------------- | ---------------------------------------- |
| 🐍 Python Notebook    | Data cleaning, EDA & feature engineering |
| 🗄️ SQL Queries       | Business-focused customer analysis       |
| 📊 Power BI Dashboard | Interactive visualization and insights   |
| 📑 Project Report     | Analysis findings and recommendations    |
| 🎤 Presentation       | Visual communication of project insights |
| 💾 Dataset            | Customer shopping transaction data       |

The original project requirements specifically call for Python data preparation, SQL analysis, Power BI visualization, reporting/presentation, and a structured GitHub repository.

---

# 🎓 Skills Demonstrated

This project demonstrates practical experience in:

* Data Cleaning
* Exploratory Data Analysis
* Feature Engineering
* Customer Segmentation
* Business Analytics
* SQL Query Development
* PostgreSQL
* Data Visualization
* Power BI Dashboard Development
* KPI Analysis
* Customer Behavior Analysis
* Business Problem Solving
* Data-Driven Decision Making
* Business Recommendation Development

---

# 📊 End-to-End Analytics Architecture

```text
                  CUSTOMER TRANSACTION DATA
                              │
                              ▼
                     ┌────────────────┐
                     │     Python     │
                     │                │
                     │ • Cleaning     │
                     │ • EDA          │
                     │ • Transformation│
                     │ • Feature Eng. │
                     └───────┬────────┘
                             │
                             ▼
                     ┌────────────────┐
                     │   PostgreSQL   │
                     │                │
                     │ • Data Storage │
                     │ • SQL Queries  │
                     │ • Segmentation │
                     │ • Aggregation  │
                     └───────┬────────┘
                             │
                             ▼
                     ┌────────────────┐
                     │    Power BI    │
                     │                │
                     │ • KPIs         │
                     │ • Dashboard    │
                     │ • Visualization│
                     └───────┬────────┘
                             │
                             ▼
                     ┌────────────────┐
                     │    Business    │
                     │    Insights    │
                     │                │
                     │ • Marketing    │
                     │ • Loyalty      │
                     │ • Products     │
                     │ • Subscriptions│
                     └────────────────┘
```

---

# 📚 Conclusion

This project demonstrates how customer transaction data can be transformed into **actionable business intelligence** through an end-to-end analytics workflow.

By combining **Python for data preparation, SQL for structured business analysis, and Power BI for interactive visualization**, the project identifies meaningful patterns across customer segments, products, discounts, subscriptions, shipping preferences, and purchasing behavior.

The resulting insights can help businesses make more informed decisions around **customer retention, subscription growth, targeted marketing, product positioning, and promotional strategy**.

---

## ⭐ If you found this project useful

Feel free to **star ⭐ the repository** and explore the analysis, SQL queries, notebook, and Power BI dashboard.

---

### 👨‍💻 Project

**Customer Shopping Behavior Analysis**

**Technologies:** Python • Pandas • SQL • PostgreSQL • Power BI • Data Analytics

**Focus:** Customer Analytics • Business Intelligence • Data-Driven Decision Making
