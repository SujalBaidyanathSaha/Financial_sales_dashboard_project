# Data Exploration(EDA)



\---Exploratory Data Analysis

SELECT \*

FROM public."Financial\_sales\_data";



\---1. Unique Customers

SELECT COUNT(DISTINCT customer\_id) AS Unique\_customers

FROM public."Financial\_sales\_data";



\---2. Unique Products

SELECT COUNT(DISTINCT sub\_category) AS Unique\_Products

FROM public."Financial\_sales\_data";



\---3. List of Products

SELECT DISTINCT sub\_category AS List\_of\_unique\_Products

FROM public."Financial\_sales\_data"

ORDER BY List\_of\_Products ASC;



\---4. Date Range

SELECT MIN(sales\_date) AS Start\_date, 

&#x20;      MAX(sales\_date) AS End\_date

FROM public."Financial\_sales\_data";



\---5. Total Rows

SELECT COUNT(\*)

FROM public."Financial\_sales\_data";



\---6. List of Unique States

SELECT DISTINCT state\_of\_country AS List\_of\_Unique\_States

FROM public."Financial\_sales\_data";

