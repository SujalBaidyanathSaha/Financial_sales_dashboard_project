# Data Quality Report



###### **Data Overview:**

* Total rows: 100001
* Total columns: 25
* Missing Values: 0
* Dataset Cover: 01-01-2019 to 31-12-2023



###### **Data Cleaning Log (Excel and Power Query Editor)**

* CTRL+A = Select all
* ALT+HOA, ALT+HOI = Autofit rows and columns
* Data Tab -> Get data -> From table/ranges -> Open in Power Query Editor
* Fixed data types or each column
* Rename Customer Name to First Name
* Freeze header
* Cleaned data, no duplicates or nulls



###### **Data Dictionary:**

|**Column Name**|**Description**|**Data Type**|
|-|-|-|
|Customer ID|Unique customer identifier|Text|
|First Name|First name of the customer|Text|
|Last Name|Last name of the customer|Text|
|Date Of Birth|Customers Date of Birth|Date|
|Sales|Purchase amount in Indian Rupees (₹)|Currency|
|Year|2019-2023|Whole Number|
|Outlet Type|Large, Medium and Small|Text|
|City Type|Tier 1, Tier 2, or Village|Text|
|Category of goods|Product category (Furniture, Electric Appliances, Fruits \& Vegetables, Household, Dairy, Fast Food)|Text|
|Region|North, South, East, or West|Text|
|Country|India|Text|
|Segment|Customer type (Consumer, Corporate)|text|
|Sales Date|Date of sale|Date|
|Order ID|Unique identifier for each transaction|Text|
|Ship Date|Date when the order was shipped|Date|
|Ship Mode|Shipping method (Standard Class, Second Class, First Class, Same Day)|Text|
|State|Indian state where the purchase was made|Text|
|Postal Code|Postal code for the purchase location|Whole Number|
|Product ID|Unique identifier for each product|Text|
|Sub-Category|Specific subcategories under each category|Text|
|Product name|Randomized product names based on subcategory|Text|
|Quantity|Number of items purchased|Whole number|
|Discount|Discount applied (0% - 50%)|Decimal number|
|Profit|Profit calculated after applying discount|Decimal Number|



