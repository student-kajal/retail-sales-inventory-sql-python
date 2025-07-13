# 🛍️ Retail Sales & Inventory Analytics Dashboard (Python + SQL)

📌 **Project Overview**  
This project simulates end-to-end e-commerce retail operations — from synthetic data generation to SQL-based insights — using Python, SQLite, and Pandas. It helps analyze regional sales, seasonal trends, and return-heavy products, ideal for business decision-making in retail.

---

## 🎯 Objective

- Simulate realistic sales, returns, and inventory data.
- Store the data in both CSV and SQLite formats.
- Run advanced SQL queries to extract business insights.
- Build a foundation for further dashboarding in Excel/Power BI.

---

## 🛠️ Tools & Technologies

- **Python** – data simulation and processing (`pandas`, `numpy`)
- **SQLite** – embedded database for querying
- **SQL** – business logic queries (aggregation, filtering)
- *(Optional add-on: Power BI or Excel for dashboard)*

---

## 📦 Dataset (Synthetic, Generated in Code)

Columns:
- `ProductID` — Product identifier
- `Region` — Region of transaction (`North`, `South`, `East`, `West`)
- `Sales` — Sale value in ₹
- `Returns` — Returned amount
- `Inventory` — Available stock
- `Date` — Transaction date

> Data is generated with 1,000 rows covering multiple products, regions, and dates in 2023.

---

## 📊 Sample Queries and Insights

### 1. Total Sales by Region
```sql
SELECT Region, ROUND(SUM(Sales), 2) AS TotalSales
FROM sales_inventory
GROUP BY Region; 

2. Monthly Sales Trend
SELECT strftime('%Y-%m', Date) AS Month, ROUND(SUM(Sales), 2) AS MonthlySales
FROM sales_inventory
GROUP BY Month
ORDER BY Month;

3. Top 5 Products by Return %
SELECT ProductID,
       ROUND(SUM(Returns)*100.0/SUM(Sales), 2) AS ReturnPct
FROM sales_inventory
GROUP BY ProductID
HAVING SUM(Sales) > 0
ORDER BY ReturnPct DESC
LIMIT 5;
```
| File/Folder                | Description                                  |
| -------------------------- | -------------------------------------------- |
| `retail.ipynb`             | Main notebook – full code and SQL queries    |
| `retail-checkpoint.ipynb`  | Jupyter auto-saved version                   |
| `sales_inventory_data.csv` | Exported synthetic dataset                   |
| `retail.db`                | SQLite database with `sales_inventory` table |
| `README.md`                | You're reading it 😉                         |

🚀 How to Run
1. Clone the repo
git clone https://github.com/student-kajal/retail-analytics-sql
cd retail-analytics-sql
2. Run the Jupyter Notebook
Make sure Python is installed with required libraries:
pip install pandas numpy
3. Explore SQL Queries
You can explore or modify the queries in retail.ipynb or use DB Browser for SQLite.

💼 Business Impact
📍 Geographic Strategy – Understand which regions are driving the most revenue.

📈 Sales Forecasting – Identify monthly trends to align inventory planning.

🔁 Return Analysis – Detect high-return products for quality checks or policy improvement.

🧠 Operational Readiness – Practice for SQL interviews and dashboards.
📷 Sample Output 

👩‍💻 Author
## Kajal
Data Analyst & Business Problem Solver

📜 License
This repository is for educational and portfolio purposes only.
