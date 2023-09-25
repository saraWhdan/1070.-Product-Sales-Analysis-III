# 1070. Product Sales Analysis III
### Problem Link & Description : [ Product Sales Analysis III](https://leetcode.com/problems/product-sales-analysis-iii/description/?envType=study-plan-v2&envId=top-sql-50)
## Solution
```sql
SELECT s.product_id, s.year AS first_year, s.quantity, s.price
from Sales s 
INNER JOIN (
    SELECT product_id, MIN(year) AS first_year
    FROM Sales
    GROUP BY product_id
) first_year_sales ON s.product_id = first_year_sales.product_id AND s.year = first_year_sales.first_year;
