# Data-Analyst-Projects.
-- Query to find Top 5 Customers by Total Spend
-- Demonstrates: JOINs, GROUP BY, and Aggregate Functions
SELECT 
    c.customer_id, 
    c.customer_name, 
    SUM(o.order_amount) AS total_revenue
FROM customers c
JOIN orders o ON c.customer_id = o.customer_id
WHERE o.order_date >= '2025-01-01'
GROUP BY c.customer_id, c.customer_name
ORDER BY total_revenue DESC
LIMIT 5;
