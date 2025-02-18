Power BI Report: Product Sales and Stock Analysis

Overview

  This Power BI report provides detailed insights into product sales and stock performance. It helps users track inventory levels, 
identify top-selling products, and monitor total sales revenue. The report is powered by PostgreSQL as the database, with queries 
executed to fetch relevant data for visualization and analysis. The visuals are structured to offer a clear view of product performance and inventory management.

Data Connection
  This report is connected to a PostgreSQL database, where SQL queries were executed to retrieve and process data. 
  Key queries include:
    Fetching stock levels and identifying products with low stock.
    Aggregating total sales per product to determine top-selling items.
    Calculating stock distribution across product categories.

Summing total revenue from sales transactions.

Visuals in the Report

  1. Quantity in Stock Per Product with Low Stock

      Visual Type: Bar Chart
      Description: Displays the current stock quantity for each product, highlighting products with low stock (below a threshold of 25) for 
easy identification and timely restocking.
      Data Source: stock table, products table.
      SQL Query Example:
          SELECT p.product_id, p.name, s.quantity
          FROM stock s
          JOIN products p ON s.product_id = p.product_id
          WHERE s.quantity < 25;

  2. Top Products Sold

      Visual Type: Line Chart
      Description: Ranks the top-selling products based on quantity sold, providing insights into sales trends.
      Data Source: sales table, products table.
      Metrics: Total quantity sold per product.
      SQL Query Example:
        SELECT p.name, SUM(s.quantity) AS total_sold
        FROM sales s
        JOIN products p ON s.product_id = p.product_id
        GROUP BY p.name
        ORDER BY total_sold DESC;

  3. Stock Quantity by Category
      Visual Type: Pie Chart
      Description: Displays the stock distribution across various product categories.
      Data Source: stock table, products table, categories table.
      Metrics: Stock quantity per category.
      SQL Query Example:
        SELECT c.category_name, SUM(s.quantity) AS total_stock
        FROM stock s
        JOIN products p ON s.product_id = p.product_id
        JOIN categories c ON p.category_id = c.category_id
        GROUP BY c.category_name;

  4. Total Sales Revenue
      Visual Type: Gauge
      Description: Displays the total revenue from sales transactions, providing a quick summary of overall sales performance.
      Data Source: sales table.
      Metrics: Sum of total_price from sales data.
      SQL Query Example:
        SELECT SUM(total_price) AS total_revenue FROM sales;

 Data Model and Relationships
    Tables Used:
        sales: Contains transaction details (sale_id, product_id, quantity, sale_date, total_price).
        stock: Tracks product stock levels (product_id, quantity, last_updated).
        products: Stores product details (product_id, name, description, price, category_id).
        categories: Defines product categories (category_id, category_name).

  Relationships:
      products table is related to sales via product_id.
      products table is related to stock via product_id.
      products table is related to categories via category_id.

Purpose and Use Cases
  Inventory Management: Identifies low-stock products to facilitate timely restocking.
  Sales Analysis: Provides insights into top-selling products and sales trends.
  Revenue Tracking: Allows stakeholders to monitor overall sales performance.
  Category Distribution: Helps in understanding stock allocation across different categories.

How to Use This Report
  Use the Quantity in Stock Per Product with Low Stock chart to monitor stock levels and identify items needing restocking.
  Refer to the Top Products Sold chart to understand product performance and sales trends.
  Analyze the Stock Quantity by Category pie chart for insights into stock distribution across categories.
  View the Total Sales Revenue card for a quick summary of overall sales performance.

Conclusion
  This Power BI report, integrated with PostgreSQL, provides critical insights into product sales and stock management. 
By leveraging SQL queries to extract and analyze data, it enables   efficient inventory management, sales strategy optimization, and overall business performance monitoring.

