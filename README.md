# lita-Capstone-project(SALES DATA)
## PROJECT OVERVIEW
---
This project is based on analyzing sales data to identify trends, top-selling products, revenue, units sold, by comparing regions, transaction categories and some other Metrics for business decision-making. 
In this project, I will be making use of large sales dataset to extract valuable insights. To explore sales trends over time, identify the best-selling products, calculate revenue metrics such as total sales and Total Revenue, and create visualizations and present my findings effectively. This will also enable me make data-driven recommendations for optimizing sales strategies.

### DATA INFORMATION
---
The data set was retrieved from an open source. It shows the record of sales data of a set of product over a period of time, it comprises of columns and rows. The columns names are: Customer ID, Product,Region, Quantity Ordered, Unit Price and Order Date.

#### DATA CLEANING AND TOOLS USED
---
The cleaning process was one of the most important aspect of this project as it eliminated duplicate that could bring inadequacies or errors into my analysis.
   
    *Microsoft Excel
I ensure the data was cleaned by checking for duplicate rows by selecting the table, navigating to the data tab and clicking on “Remove Duplicates”, to remove duplicates.
I created additional columns by multiplying Quantity by Unit price, which will help in carrying out a proper and detailed analysis. all these were done to make the data clean and ready for analysis.
   
    *  POWER BI
I loaded the Clean Data Set into PowerBI for the further analysis and Visualization in order to answer business questions and meet up with objectives.

    *SQL(STRUCTURED QUERY LANGUAGE)
 I used this tool to query the database in a number of ways, using English-like statements. i also used it to store and manage data in Relational
Database Management System (RDBMS).

    *GITHUB
    This is used as a tool for portfolio building.

##### EXPLORATORY DATA ANALYSIS
---
I used this in exploring the Sales data set, in order to answer some underlying questions such as
   
      *What are the top performing products?
      *What is the Total Sales, Total revenue by months or year?
      *Who are the "Top 5" Customers?
      *Which product has the lowest number of sales?

###### DATA ANALYSIS
---
I used some basic lines of code, queries, Dax functions in the course of this Analysis. Some of which are;

```SQL

......TOTAL SALES FROM EACH PRODUCT CATEGORY.....
SELECT PRODUCT,SUM(SALES) as Totalsales
from[dbo].[LITA CAPSTONE SALES DATA]
Group by Product
Table 1.1
PRODUCTS   TOTAL SALES
Shoes	   3087500
Jacket	1050000
Hat	   1587500
Socks	   912500
Shirt	   2450000
Gloves	1500000

From the table above , i was able to calculate the total sales made from each product category. a total sales of #3,087,500 was made from Shoes, #1,050,000 from Jacket, #1,587500 from Hat, #912,500 from socks, #,2450,000 from Shirt and #1,500,000

.........number of sales transactions in each region......
SELECT Region,
COUNT(product) as sales_transactions_number 
from [dbo].[LITA CAPSTONE SALES DATA]
GROUP BY REGION

Table 1.2
Region	sales_transactions_number
North	12500
East	12500
South	12500
West	12500

SELECT Region,SUM(SALES) as Totalsales
from[dbo].[LITA CAPSTONE SALES DATA]
Group by Region

Table 1.3
Region	Totalsales
North	1950000
East	2450000
South	4675000
West	1512500

..highest  selling product.......
select (product)from[dbo].[LITA CAPSTONE SALES DATA]


SELECT PRODUCT, 
SUM(sales) as total_Revenue
from[dbo].[LITA CAPSTONE SALES DATA]
group by product

Table 1.4
PRODUCT	total_Revenue
Shoes	 3087500
Jacket 1050000
Hat	 1587500
Socks	 912500
Shirt	2450000
Gloves 1500000


........monthly sales totals for the current year......
select orderdate,[revenue] as total_sales
from [dbo].[LITA CAPSTONE SALES DATA]
where year (OrderDate) in (2024)


  
