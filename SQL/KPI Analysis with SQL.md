# KPI Analysis with SQL



\---KPI Analysis

SELECT \*

FROM public."Financial\_sales\_data";



\---1. Total Revenue 

SELECT SUM(sales) AS Total\_revenue

FROM public."Financial\_sales\_data";



\---2. Total Orders

SELECT COUNT(DISTINCT order\_id)

FROM public."Financial\_sales\_data";



\---3. Average order value

SELECT SUM(sales)/COUNT(DISTINCT order\_id) AS Average\_Order\_Value

FROM public."Financial\_sales\_data";



