# Sales Data Analysis using Python and SQLite

## Objective
Analyze sales data using SQL queries inside Python, and visualize results using simple bar and pie charts.  
The goal is to calculate total quantity sold, total revenue, top customers, and highest-selling products.

## Tools
- **Python**: sqlite3, pandas, matplotlib  
- **SQLite**: Embedded database  
- **Jupyter Notebook** 

## Database
- Database file: `sales_data.db`
- 
- Table: `sales`  
- Columns:
  - `id` (Primary Key)  
  - `customer_name`  
  - `product`  
  - `product_id`  
  - `quantity`  
  - `price_per_each`  
  - `total_price`  

- **Dataset**: 50 sample rows of customers buying different products (electronics, appliances, accessories, etc.)

## SQL Queries Used
1.#Total sales quantity & revenue per product
SELECT product, 
       SUM(quantity) AS total_qty, 
       SUM(total_price) AS revenue
FROM sales
GROUP BY product
ORDER BY revenue DESC;

# Top 5 customers by total spending
SELECT customer_name, SUM(total_price) AS total_spent
FROM sales
GROUP BY customer_name
ORDER BY total_spent DESC
LIMIT 5;

# Total revenue by product category
SELECT product, SUM(total_price) AS revenue
FROM sales
GROUP BY product
ORDER BY revenue DESC;


# Highest-selling product by quantity
SELECT product, SUM(quantity) AS total_qty
FROM sales
GROUP BY product
ORDER BY total_qty DESC
LIMIT 1

## Visualizations
- Bar chart: Revenue by product.
- 
- Pie chart: Revenue contribution by product.

## Insights
- Laptops & TVs generated the highest revenue.
- 
- Top customer spent over ₹1,00,000.
- 
- Chargers and headphones were high in volume but low in revenue.
- 
- This analysis shows how combining SQL and Python can quickly generate insights from sales data.

# How to Run

Open the project in Jupyter Notebook or Python IDE.

Ensure sales_data.db is in the same folder as the script.

Run the notebook cells.

Check console output for query results and view generated charts.
