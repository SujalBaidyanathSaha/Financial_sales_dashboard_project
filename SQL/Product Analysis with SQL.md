# Product Analysis with SQL



\---Product Analysis

SELECT \*

FROM public."Financial\_sales\_data";



\---1. Top Products

SELECT DISTINCT sub\_category,

&#x20;      SUM(sales) AS Total\_revenue

FROM public."Financial\_sales\_data"

GROUP BY sub\_category

ORDER BY Total\_revenue DESC;



\---2. Top 3 Product contributing most revenue

SELECT DISTINCT sub\_category,

&#x20;      SUM(sales) AS Total\_revenue

FROM public."Financial\_sales\_data"

GROUP BY sub\_category

ORDER BY Total\_revenue DESC

LIMIT 3;



WITH Product\_revenue AS (

SELECT sub\_category,

&#x20;      SUM(sales) AS Total\_revenue

FROM public."Financial\_sales\_data"

GROUP BY sub\_category

)

SELECT sub\_category, Total\_revenue

FROM(

SELECT sub\_category, Total\_revenue, 

&#x20;      DENSE\_RANK() OVER(ORDER BY total\_revenue DESC) AS Revenue\_rank

FROM Product\_revenue)ranked

ORDER BY Total\_revenue DESC

LIMIT 3;



\---3. Products Performing more than Average

WITH Product\_Revenue AS (

&#x20;SELECT sub\_category, SUM(sales) AS total\_revenue

&#x20;FROM public."Financial\_sales\_data"

&#x20;GROUP BY sub\_category

)

SELECT sub\_category, total\_revenue

FROM Product\_Revenue

WHERE total\_revenue > (

&#x20;       SELECT AVG(total\_revenue)

&#x20;       FROM Product\_revenue

)

ORDER BY total\_revenue DESC;



\---4. Products performing less than average

WITH Product\_Revenue AS (

&#x20;SELECT sub\_category, SUM(sales) AS total\_revenue

&#x20;FROM public."Financial\_sales\_data"

&#x20;GROUP BY sub\_category

)

SELECT sub\_category, total\_revenue

FROM Product\_Revenue

WHERE total\_revenue < (

&#x20;       SELECT AVG(total\_revenue)

&#x20;       FROM Product\_revenue

)

ORDER BY total\_revenue DESC;

