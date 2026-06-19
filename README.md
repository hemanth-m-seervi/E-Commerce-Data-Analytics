# 🛒 E-Commerce Data Analytics Pipeline & Relational Insights

An end-to-end Data Engineering and Analytics project that processes raw e-commerce datasets, loads them into a MySQL relational database, and generates business intelligence insights using SQL and Python.

This project demonstrates ETL (Extract, Transform, Load) processes, database normalization, advanced SQL analytics, and data visualization techniques commonly used in real-world retail and marketplace platforms.

---

## 📌 Project Overview

The pipeline ingests multiple CSV datasets representing an e-commerce ecosystem, cleans and transforms the data using Python, stores it in a normalized MySQL database, and performs analytical queries to extract meaningful business insights.

### Key Features

- Automated ETL pipeline using Python
- Data cleaning and preprocessing with Pandas
- MySQL relational database design
- Database normalization and referential integrity
- Advanced SQL queries using joins, aggregations, and window functions
- Business intelligence reporting
- Trend and revenue analysis
- Data visualization using Matplotlib and Seaborn

---

## 🛠️ Tech Stack

| Category | Technologies |
|-----------|-------------|
| Programming Language | Python 3.x |
| Database | MySQL |
| Data Processing | Pandas, NumPy |
| Database Connector | mysql-connector-python |
| Visualization | Matplotlib, Seaborn |
| Development Environment | Jupyter Notebook |

---

## 📂 Dataset Structure

The project uses seven interconnected datasets representing different entities within an e-commerce platform.

### 1. Customers (`customers.csv`)
Contains customer information including:
- Customer ID
- Unique customer identifier
- City
- State
- ZIP code prefix

### 2. Geolocation (`geolocation.csv`)
Contains geographic mapping information:
- ZIP code prefixes
- Latitude
- Longitude
- City
- State

### 3. Orders (`orders.csv`)
Tracks the complete order lifecycle:
- Order ID
- Customer ID
- Order status
- Purchase timestamp
- Approval timestamp
- Delivery timestamps

### 4. Order Items (`order_items.csv`)
Contains transaction-level details:
- Order ID
- Product ID
- Seller ID
- Item price
- Freight charges

### 5. Payments (`payments.csv`)
Stores payment transaction information:
- Payment type
- Installments
- Payment value
- Payment sequence

### 6. Products (`products.csv`)
Contains product catalog information:
- Product ID
- Product category
- Weight
- Dimensions
- Packaging details

### 7. Sellers (`sellers.csv`)
Contains seller information:
- Seller ID
- City
- State
- ZIP code prefix

---

## 🗄️ Database Schema

The relational database follows a normalized structure to maintain data consistency and minimize redundancy.

### Entity Relationship Diagram

```text
Customers
    │
    │ (1:N)
    ▼
Orders
    │
    ├──────────────► Payments
    │                    (1:N)
    │
    ▼
Order_Items ◄──────── Products
    ▲
    │
    │
 Sellers

Geolocation
   ▲
   │
Customers & Sellers
```

### Relationships

#### Customers → Orders
- One customer can place multiple orders.
- Each order belongs to one customer.
- Key: `customer_id`

#### Orders → Order Items
- One order may contain multiple products.
- Each item belongs to one order.
- Key: `order_id`

#### Products → Order Items
- One product can appear in many orders.
- Key: `product_id`

#### Sellers → Order Items
- One seller can sell multiple products.
- Key: `seller_id`

#### Orders → Payments
- One order can have multiple payment transactions.
- Key: `order_id`

#### Geolocation
Used for regional and geospatial analysis through ZIP code mappings.

---

## ⚙️ ETL Workflow

The ETL pipeline performs the following operations:

### 1. Data Extraction
- Reads CSV files using Pandas
- Loads datasets into DataFrames

### 2. Data Cleaning
- Handles missing values
- Converts NaN values to SQL NULL
- Removes inconsistencies
- Standardizes column names

### 3. Data Transformation
- Detects data types automatically
- Converts columns into:
  - INT
  - FLOAT
  - DATETIME
  - TEXT

### 4. Database Loading
- Creates tables automatically if they do not exist
- Performs batch insert operations
- Maintains relational integrity

---

## 📊 Business Intelligence Analysis

### 1. Geographic Distribution Analysis
**Objective:** Identify all unique customer cities.

**SQL Concepts Used:**
- DISTINCT
- Filtering

### 2. Order Volume Analysis (2017)
**Objective:** Calculate total orders placed during 2017.

**SQL Concepts Used:**
- YEAR()
- COUNT()

### 3. Revenue by Product Category
**Objective:** Analyze category-wise revenue generation.

**SQL Concepts Used:**
- SUM()
- GROUP BY
- JOIN

### 4. Installment Payment Analysis
**Objective:** Determine the percentage of transactions using installment payments.

**SQL Concepts Used:**
- CASE
- Aggregations

### 5. Customer Density by State
**Objective:** Identify states with the highest customer concentration.

**Output:**
- State-wise customer distribution
- Visualization charts

### 6. Monthly Order Trends (2018)
**Objective:** Track monthly purchasing behavior.

**Output:**
- Time-series visualizations
- Seasonal trend analysis

### 7. Average Order Size by City
**Objective:** Measure average order item counts across cities.

**SQL Concepts Used:**
- Nested Queries
- JOIN Operations

### 8. Revenue Contribution by Category
**Objective:** Calculate each category's percentage contribution to total revenue.

**SQL Concepts Used:**
- SUM()
- Percentage Calculations

### 9. Price vs Purchase Volume Correlation
**Objective:** Determine the relationship between product pricing and purchase frequency.

**Python Concepts Used:**
```python
numpy.corrcoef()
```

### 10. Year-over-Year (YoY) Revenue Analysis
**Objective:** Measure annual growth and identify top-performing years.

**SQL Concepts Used:**
- Window Functions
- LAG()
- DENSE_RANK()
- SUM() OVER()

---

## 📈 Sample Insights

- Top revenue-generating product categories
- Monthly sales trends
- Customer distribution by state
- Installment payment behavior
- Seller performance metrics
- Year-over-year growth analysis
- Product pricing impact on demand

---

## 🚀 Installation

### Clone the Repository

```bash
git clone https://github.com/yourusername/ecommerce-data-analytics.git
cd ecommerce-data-analytics
```

### Install Dependencies

```bash
pip install pandas numpy mysql-connector-python matplotlib seaborn
```

### Launch Jupyter Notebook

```bash
jupyter notebook
```

### Run the Analysis Notebook

```bash
data_analysis_demo.ipynb
```

---

## 📁 Project Structure

```text
ecommerce-data-analytics/
│
├── customers.csv
├── geolocation.csv
├── orders.csv
├── order_items.csv
├── payments.csv
├── products.csv
├── sellers.csv
│
├── data_analysis_demo.ipynb
├── README.md
│
└── screenshots/
```

---

## 🎯 Learning Outcomes

This project demonstrates practical experience in:

- Data Engineering
- ETL Development
- Database Design
- SQL Analytics
- Data Cleaning
- Business Intelligence
- Data Visualization
- Relational Database Management
- Exploratory Data Analysis (EDA)

---

## 👨‍💻 Author

**Hemanth Sirvi**
