# 🚲 Jenson Bikes SQL Business Analysis

## 📌 Project Overview

This project analyzes the **BikeStores relational database using SQL** to uncover actionable insights across stores, customers, products, categories, inventory, and staff performance.

The objective was to transform transactional bicycle-sales data into meaningful business insights that support **sales optimization, customer retention, inventory planning, pricing strategy, and operational efficiency**.

The project demonstrates practical application of advanced SQL techniques to solve real-world business problems and support data-driven decision-making.

---

## 🎯 Business Objectives

The analysis focuses on five major business areas:

- **Store Performance** — Evaluate store-wise sales and identify top-performing locations.
- **Customer Behavior** — Analyze customer spending, ordering patterns, and loyalty.
- **Product Analysis** — Identify best-selling, premium, and low-performing products.
- **Staff Performance** — Evaluate employee order-handling efficiency.
- **Business Growth** — Extract insights to support strategic decision-making.

---

## 📊 Dataset

The project uses the **BikeStores relational database**, containing interconnected data across sales, customers, products, stores, staff, categories, and orders.

### Key Business Entities

- Customers
- Orders
- Order Items
- Stores
- Staffs
- Products
- Categories
- Brands
- Stocks

---

## 🗄️ Database Architecture

The database follows a **normalized relational structure** with primary and foreign keys maintaining relationships between business entities.

### Core Relationships

```text
Customers
    │
    └── Orders
          │
          ├── Order Items
          │       │
          │       └── Products
          │               │
          │               ├── Categories
          │               └── Brands
          │
          ├── Stores
          └── Staffs

Stores
    │
    └── Stocks
          │
          └── Products
```

The relational structure enables multi-table SQL analysis across sales, customers, products, stores, staff, and inventory.

---

## 🛠️ Tools & Technologies

- **SQL**
- MySQL
- Relational Database Analysis
- JOIN
- GROUP BY
- HAVING
- Subqueries
- Window Functions
- RANK()
- EXISTS / NOT EXISTS
- Aggregate Functions
- ORDER BY
- LIMIT
- Date Analysis
- Cumulative Analysis

---

# 📍 Store Performance Analysis

## Q1. Total Products Sold by Each Store

Calculated the total number of products sold by each store using order and order-item data.

### Result

- **Baldwin Bikes — 4,779 products**
- **Santa Cruz Bikes — 1,516 products**
- **Rowlett Bikes — 1,? products**

Baldwin Bikes emerged as the strongest store by total product quantity sold.

### Business Insight

The analysis highlights the strongest-performing store and helps management compare store-level sales performance for resource allocation and growth planning.

---

# 📈 Cumulative Product Sales Analysis

## Q2. Cumulative Quantity Sold by Product

Calculated the cumulative quantity sold for each product over time using SQL window functions.

### SQL Technique

```sql
SUM(quantity) OVER (
    PARTITION BY product_id
    ORDER BY order_date, order_id
)
```

### Business Insight

The cumulative view helps track how product sales build over time and identify products with consistently increasing demand.

---

# 🏆 Category-Wise Top-Selling Products

## Q3. Highest-Selling Product in Each Category

Identified the highest-performing product in each category based on:

**Quantity × List Price**

### SQL Techniques

- `SUM()`
- `RANK() OVER()`
- `PARTITION BY`
- `ORDER BY`

### Key Results

- Children Bicycles — Electra Boys' 1 (16-inch)
- Cycling Clothing — Forte MT-01 Mountain Bike Socks
- Cycling Components — SHIMANO Ultegra CS-6500 9-Speed Cassette
- Touring Bikes — Raleigh Talus 7.2 - 2016
- Mountain Bikes — Trek Domane SLR 9 - 2018
- Road Bikes — Surly Long Haul Trucker - 2016
- Miscellaneous — Park Tool 106 Repair Stand

### Business Insight

Category-level top sellers provide a strong basis for **inventory planning, promotional focus, and product-level sales strategy**.

---

# 💰 Customer Spending Analysis

## Q4. Highest-Spending Customer

Identified the customer who generated the highest total order value across the database.

### Result

**Pamelia Newman — $3,780,184.00**

### Business Insight

Pamelia Newman represents the highest-value customer based on total spending, highlighting an opportunity for **customer retention, loyalty programs, and personalized offers**.

---

# 💎 Premium Product Analysis

## Q5. Highest-Priced Product in Each Category

Identified the highest-priced product available within every product category.

### SQL Approach

Compared each product's `list_price` against the maximum price within its category using a correlated subquery.

### Key Findings

The analysis identified premium products across **13 category-level results**.

The highest-priced products included:

- Trek Powerfly 8 FS Plus — $499,999
- Trek Fuel EX 9.8 27.5 Plus — $529,999
- Trek Domane SLR 9 Disc — $1,199,999

### Business Insight

Premium product identification supports **pricing strategy, inventory planning, premium product positioning, and merchandising decisions**.

---

# 👥 Customer Engagement Analysis

## Q6. Orders Placed by Each Customer per Store

Calculated the total number of orders placed by each customer across individual stores.

### SQL Techniques

- `JOIN`
- `COUNT()`
- `GROUP BY`
- `ORDER BY`

### Business Insight

This analysis helps identify **high-activity customers within each store** and provides insights into customer engagement and store-level loyalty.

---

# 👨‍💼 Staff Performance Analysis

## Q7. Staff Members Who Have Not Handled Any Orders

Identified staff members who currently have no assigned orders using a `LEFT JOIN`.

### Result

**4 staff members** were identified as having no handled orders.

### Business Insight

This helps management identify potentially underutilized employees and improve **workload distribution and resource allocation**.

---

## Q8. Staff Members Performing Above Average

Identified staff members who handled more orders than the overall average number of orders handled by staff.

### Result

**4 staff members** performed above the average order-handling level.

### Business Insight

These employees represent stronger operational performers and can be recognized for **productivity, workload management, and operational efficiency**.

---

# 🚲 Product Demand Analysis

## Q9. Top 3 Most Sold Products

Identified the three products with the highest total quantity sold.

### Top Products

1. **Electra Cruiser 1 (24-Inch) - 2016 — 296 units**
2. **Electra Townie Original 7D EQ - 2016 — 290 units**
3. **Electra Townie Original 21D - 2016 — 289 units**

### Business Insight

These products represent the strongest quantity-based demand and can be prioritized for **inventory availability, promotions, and sales planning**.

---

# 💵 Product Pricing Analysis

## Q10. Median Product List Price

Calculated the median value of the product price list.

### Result

**Median List Price — $74,999.00**

### Business Insight

The median price provides a reliable representation of the central product-price level while reducing the influence of extremely high or low-priced products.

---

# 📦 Inventory Analysis

## Q11. Products That Have Never Been Ordered

Identified products that have never appeared in the order-item records using `NOT EXISTS`.

### Result

**14 products** were identified as never ordered.

### Business Insight

These products represent potential **slow-moving or inactive inventory**, creating an opportunity for repricing, promotional campaigns, inventory optimization, or catalogue review.

---

# 🚲 Customer Product Category Analysis

## Q12. Customers Who Ordered All Road Bike Products

Identified customers who purchased every available product within the **Road Bikes** category.

### Result

**No customers were found** who had purchased all Road Bikes products.

### Business Insight

The result indicates that no single customer has purchased the complete Road Bikes product range, suggesting opportunities for **cross-selling and targeted product recommendations**.

---

# 🔍 Advanced SQL Techniques

The project demonstrates the practical application of multiple advanced SQL concepts.

### 🔗 JOIN

Used multiple joins to combine:

- Customers
- Orders
- Order Items
- Products
- Stores
- Staffs
- Categories

---

### 📊 GROUP BY & HAVING

Used grouped aggregations to calculate:

- Store sales
- Customer orders
- Staff performance
- Product sales
- Category-level metrics

---

### 🪟 Window Functions

Used window functions for advanced analytical calculations.

Examples:

- Cumulative quantity sold
- Product ranking within categories

---

### 🏅 RANK()

Used `RANK()` with `PARTITION BY` to identify the highest-performing products within individual categories.

---

### 🧩 Subqueries

Used correlated and nested subqueries for:

- Highest-priced products
- Above-average staff performance
- Category comparisons

---

### ✅ EXISTS / NOT EXISTS

Used `NOT EXISTS` to identify products that had **never been ordered**.

---

### 📈 Aggregate Functions

Used:

- `SUM()`
- `COUNT()`
- `AVG()`
- `MAX()`

to generate business-level metrics.

---

# 💡 Key Findings

The SQL analysis generated several important business findings:

- **Baldwin Bikes** emerged as the top-performing store by product quantity sold.
- **Pamelia Newman** was the highest-spending customer at **$3,780,184.00**.
- The top three products sold **296, 290, and 289 units** respectively.
- The median product list price was **$74,999.00**.
- **4 staff members** handled more orders than the overall staff average.
- **4 staff members** had not handled any orders.
- **14 products** had never been ordered.
- No customer had purchased every product within the Road Bikes category.
- Premium products were identified across **13 category-level results**.

---

# 💼 Business Recommendations

Based on the SQL analysis, the following strategic actions can be considered:

### 🏪 Focus on Top-Performing Stores

Prioritize high-performing stores such as Baldwin Bikes to maximize sales opportunities and replicate successful strategies.

### 👥 Retain High-Value Customers

Develop loyalty programs, personalized offers, and targeted promotions for high-spending customers.

### 🚲 Promote High-Demand Products

Maintain adequate inventory of top-selling products and use them in promotional campaigns.

### 💰 Review Pricing Strategy

Use product price distribution and premium-product analysis to support competitive pricing decisions.

### 👨‍💼 Optimize Staff Allocation

Review workload distribution and improve task allocation for underutilized staff members.

### 📦 Optimize Inventory

Review the 14 never-ordered products to identify opportunities for repricing, promotion, or catalogue optimization.

### 📈 Expand in High-Demand Markets

Use store and product performance insights to identify opportunities for future business expansion.

---

# 🚀 Project Outcome

This project transformed raw **BikeStores transactional data into actionable business insights using advanced SQL analysis**.

The analysis evaluated **store performance, customer spending, product demand, pricing, inventory, staff productivity, and category-level performance**.

The project demonstrates how SQL can be used to identify **revenue drivers, high-value customers, operational gaps, and inventory opportunities** to support data-driven business decisions.

---

# 📚 Key Skills Demonstrated

## 💻 SQL

- Advanced SQL Queries
- Complex Joins
- Multi-table Analysis
- Window Functions
- Ranking
- Subqueries
- Correlated Subqueries
- EXISTS / NOT EXISTS
- Aggregate Functions
- GROUP BY
- HAVING
- Date-Based Analysis

## 📊 Data Analytics

- Sales Analysis
- Customer Analytics
- Product Analytics
- Store Performance Analysis
- Staff Performance Analysis
- Pricing Analysis
- Inventory Analysis
- Business Insight Generation

## 💼 Business Analytics

- Revenue Optimization
- Customer Retention
- Product Strategy
- Inventory Optimization
- Pricing Strategy
- Operational Efficiency
- Sales Performance
- Data-Driven Decision Making

---

# 📂 Repository Structure

```text
Jenson-Bikes-SQL-Analysis/
│
├── Dataset/
│   └── BikeStores_Database.sql
│
├── SQL/
│   └── Jenson_Bikes_SQL_Analysis.sql
│
├── Presentation/
│   └── Jenson_Bikes_SQL_Projects.pptx
│
├── Screenshots/
│   └── SQL-query-results
│
└── README.md
```

---

## 👤 Author

**Chetan Agrawal**

**Data Analyst | Excel | SQL | Power BI | Python**

---

## 🏷️ Project Type

**SQL Data Analysis | Sales Analytics | Customer Analytics | Product Analytics | Inventory Analysis**

---

## ⭐ Key Takeaway

This project showcases the power of **SQL in transforming relational sales data into actionable insights** that support better decisions across sales, customers, products, inventory, and operations.
