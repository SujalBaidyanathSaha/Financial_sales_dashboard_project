# Customer, Regional, and Time-series Analysis with SQL



\---Customer, Regional and Time-series Analysis 

SELECT \* 

FROM public."Financial\_sales\_data";



\---1. Top 10 Customers

SELECT CONCAT(first\_name,' ',last\_name) AS Customer\_name,

&#x20;      SUM(sales) AS Revenue

FROM public."Financial\_sales\_data"

GROUP BY Customer\_name

ORDER BY Revenue DESC

LIMIT 10;



\---2. Revenue% from top 20% customers

WITH Customer\_Revenue AS (

SELECT customer\_id, 

&#x20;      SUM(sales) AS revenue

FROM public."Financial\_sales\_data"

GROUP BY customer\_id

), 

Ranked\_Customers AS(

SELECT customer\_id, revenue, 

&#x20;      NTILE(5) OVER(ORDER BY revenue DESC) AS customer\_group

FROM Customer\_revenue

)

SELECT  

&#x20;     ROUND(100.0\*SUM(

&#x20;            CASE

&#x09;		   WHEN customer\_group=1 THEN revenue

&#x09;		   ELSE 0

&#x09;		 END

&#x20;                 )/SUM(revenue),2) AS revenue\_pct\_from\_top\_20\_customers

FROM Ranked\_Customers;



\---3. City generating highest revenue

SELECT city\_type,

&#x20;      SUM(sales) AS Revenue

FROM public."Financial\_sales\_data"

GROUP BY city\_type

ORDER BY Revenue DESC;



\---4. Underperforming State

SELECT state\_of\_country, 

&#x20;      SUM(sales) AS Revenue

FROM public."Financial\_sales\_data"

GROUP BY state\_of\_country

ORDER BY Revenue ASC

LIMIT 1;



\---5. Monthly Growth

WITH Monthly\_Sales AS (

&#x20;   SELECT

&#x20;       DATE\_TRUNC('month', order\_date) AS month,

&#x20;       SUM(sales) AS total\_sales

&#x20;   FROM public."Financial\_sales\_data"

&#x20;   GROUP BY DATE\_TRUNC('month', order\_date)

)



SELECT

&#x20;   month,

&#x20;   total\_sales,

&#x20;   LAG(total\_sales) OVER (ORDER BY month) AS previous\_month\_sales,

&#x20;   ROUND(

&#x20;       100.0 \*

&#x20;       (total\_sales - LAG(total\_sales) OVER (ORDER BY month))

&#x20;       / LAG(total\_sales) OVER (ORDER BY month),

&#x20;       2

&#x20;   ) AS growth\_percentage

FROM Monthly\_Sales

ORDER BY month;

