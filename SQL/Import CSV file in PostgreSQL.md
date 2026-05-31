# Import CSV file in PostgreSQL

\---Created database in PostgreSQL

\---Created table named Financial\_sales\_data
CREATE TABLE public."Financial\_sales\_data"(

&#x20;   customer\_id character(10),

&#x20;   first\_name character varying(20),

&#x20;   last\_name character varying(20),

&#x20;   date\_of\_birth date,

&#x20;   sales numeric(10, 2),

&#x20;   outlet\_type character varying(6),

&#x20;   city\_type character varying(7),

&#x20;   category\_of\_goods character varying(50),

&#x20;   region character varying(5),

&#x20;   country character varying(20),

&#x20;   segment character varying(12),

&#x20;   sales\_date date,

&#x20;   order\_id character(10),

&#x20;   order\_date date,

&#x20;   ship\_date date,

&#x20;   state\_of\_country character varying(20),

&#x20;   postal\_code integer,

&#x20;   product\_id character(10),

&#x20;   quantity smallint,

&#x20;   discount real,

&#x20;   profit real

);





\--- Forgot to put 4 columns

\--- Add them in table(ship\_mode, sub\_category, product\_name, sales\_year), reordered the csv file for the process.



\---Verify table, column names, datatypes



select \* 

from public."Financial\_sales\_data";



\---Importing CSV file in sql



COPY public."Financial\_sales\_data"(

customer\_id, 

first\_name,

last\_name, 

date\_of\_birth,

sales,

outlet\_type,

city\_type,

category\_of\_goods,

region,

country,

segment,

sales\_date,

order\_id,

order\_date,

ship\_date,

state\_of\_country,

postal\_code,

product\_id,

quantity,

discount,

profit,

sub\_category,

product\_name,

ship\_mode,

sales\_year

)

FROM 'C:\\Finance Data\\Financial Sales Data.csv'

DELIMITER ','

CSV HEADER;





\---I didn't take help of query to create table, Right-click Financial Sales Data -> Create





