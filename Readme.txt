Power BI Report: Product Sales and Stock Analysis


Overview:
This Power BI report provides comprehensive insights into the sales and stock performance of products. It is designed to help users track inventory levels, identify top-selling products, and monitor total sales revenue. The visuals are structured to provide a clear view of product performance and stock management.

Visuals in the Report:

1. Quantity in Stock Per Product with Low Stock:
Visual Type: Bar Chart
Description: This visualization displays the current stock quantity for each product. Products with low stock (below a defined threshold of 25) are highlighted for quick identification, helping the team to manage inventory and re-order products in a timely manner.
Data Source: stock table and products table.

2. Top Products Sold:
Visual Type: Line Chart
Description: This visual shows the top-selling products based on quantity sold. The products with the highest sales volume are ranked, providing a clear view of which items are driving sales.
Data Source: sales table and products table.
Metrics: Total quantity sold per product.

3. Stock Quantity by Category:
Visual Type: Pie Chart
Description: This visualization breaks down the stock quantity by product category. It helps to understand the distribution of stock across various categories and identify which categories have more or less stock.
Data Source: stock table, products table, and categories table.
Metrics: Stock quantity for each category.

4. Total Sales Revenue:
Visual Type: Gauge
Description: This metric card shows the total sales revenue from all transactions, providing a quick summary of overall performance.
Data Source: sales table.
Metrics: Total sum of total_price from the sales data.


Data Model and Relationships:
Tables Used:
sales: Contains transaction details, including sale_id, product_id, quantity, sale_date, and total_price.
stock: Tracks product stock levels with product_id, quantity, and last_updated timestamps.
products: Contains product details such as product_id, name, description, price, and category_id.
categories: Defines product categories, including category_id and category_name.
Relationships:
products table is related to sales via product_id.
products table is related to stock via product_id.
products table is related to categories via category_id.

Purpose and Use Cases:
Inventory Management: Helps identify products with low stock levels to enable timely restocking decisions.
Sales Analysis: Provides insights into the most popular products based on sales volume, helping to optimize product offerings.
Revenue Tracking: Allows stakeholders to track the overall sales performance by displaying total sales revenue.
Category Distribution: Provides visibility into stock distribution by category to understand product mix and demand.

How to Use This Report:
Use the Quantity in Stock Per Product with Low Stock bar chart to monitor stock levels across products and identify which items need restocking.
Refer to the Top Products Sold chart to understand which products are performing well in terms of sales.
Use the Stock Quantity by Category pie chart to gain insights into stock distribution across categories.
View the Total Sales Revenue card to get a quick overview of overall sales performance.


Conclusion:
This Power BI report provides key insights into sales and stock performance, enabling better decision-making for inventory management, sales strategy, and overall product performance monitoring.