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
##### DATA VISUALISATION

![image](https://github.com/user-attachments/assets/78467103-02ee-4e7f-bbc2-fe1faefb68af)

The table above showcase the summary of the sales data with the  use of a Pivot Table in Excel.
From the analysis, we were able to summarise the Total sales generated from each product. 
The product that recorded the highest sales is Shoes with a Total of #613,380.
The use of Pivot Table also enabled us get a record of Total Sales generated monthly for the year 2023 and 2024.
It was also recorded that  29.19% of the total sales was gotten from shoes, 23.11% from shirt, 15.055 from Hat, 14.135 from Gloves,9.91% from Jacket and 8.60% from soc


![image](https://github.com/user-attachments/assets/340c47bd-5da4-40c6-9377-28b29f48a22c)

The table above is a pictoral summary of the Sales Report, with the aid  of Charts. 
Monthly Sales was summarised, where the Sales activities rose steadily from january through february, seen in January through. it was deduced that the sales dropped in March and started picking up in April through June. the peak of the Sales activities began in th month of June and dropped in August.

![image](https://github.com/user-attachments/assets/6d4a1e8f-b24d-47fd-885d-4acdd8352243)




###### DATA ANALYSIS
---
I used some basic lines of code, queries, Dax functions in the course of this Analysis. Some of which are;

```SQL

......TOTAL SALES FROM EACH PRODUCT CATEGORY.....
SELECT PRODUCT,SUM(SALES) as Totalsales
from[dbo].[LITA CAPSTONE SALES DATA]
Group by Product
---
####** SQL QUERIES FOR SALES DATA PROJECT**************


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

........NUMBER OF SALES TRANSACTION IN EACH REGION......

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


.........THE HIGHEST SELLING PRODUCT BY TOTAL SALES VALUE.........

SELECT Region,SUM(SALES) as Totalsales
from[dbo].[LITA CAPSTONE SALES DATA]
Group by Region

Table 1.3
Region	Totalsales
North	1950000
East	2450000
South	4675000
West	1512500

..HIGHEST SELLING PRODUCT......
select (product)from[dbo].[LITA CAPSTONE SALES DATA]

........TOTAL REVENUE PER PRODUCT
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


........MONTHLY SALES TOTAL FOR THE CURRENT YEAR......
select orderdate,[revenue] as total_sales
from [dbo].[LITA CAPSTONE SALES DATA]
where year (OrderDate) in (2024)

.............TOP 5 CUSTOMERS.......
select top 5 customer_id,SUM(quantity)
from[dbo].[LITA CAPSTONE SALES DATA]
group by customer_id

TABLE 1.5
customer_id	(No column name)
Cus1431	      711
Cus1249	      567
Cus1302	      723
Cus1115	      715
Cus1005	      588

select Region, SUM(Sales) as Region_Sales,
COUNT(Sales)*100.0/SUM(count(Sales))
over() as percentage from[dbo].[LITA CAPSTONE SALES DATA]
group by region

Table 1.6
Region	Region_Sales	percentage
North	   1950000	         25
East	   2450000	         25
South	   4675000	         25
West	   1512500	         25


...........PRODUCT WITH NO SALES IN THE LAST QUATER..............

select PRODUCT, SUM(QUANTITY) AS SALES 
from[dbo].[LITA CAPSTONE SALES DATA]
 WHERE MONTH (ORDERDATE) BETWEEN 10 AND 12 -- MONTHS 10, 11 AND 12
 GROUP BY PRODUCT
 HAVING SUM(QUANTITY) = 0

TABLE 1.7
PRODUCT	SALES

---


##### DATA VISUALISATION

![image](https://github.com/user-attachments/assets/b6f4182c-e33f-49d8-8dc3-6e5400efef3c)






  
