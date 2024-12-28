# Walmart-Analytical-Dashboard

##  Project Overview


The assessment delivers a detailed summary of revenue performance across various dimensions, including customer type, total revenue, 5% total tax, time of day, city, gender, and monthly trends. This part emphasizes how the current results correspond with the set targets.


## Data Source

This dataset, acquired from a mentor, is organized into one sheet

## Tools

Postgres SQL

Microsoft PowerBi


## Data Cleaning

Data was obtained as a clean data set



## Exploratory Data Analysis

Make Report For

i.Total sum of Revenue

ii.Total sum of Tax

iii.Time of the day by Revenue

iv. Product by Quatity

v. Payment method by Revenue

vii. Day by Revenue

viii. Month by Revenue

ix.Product by Revenue

## Queries 


Question : What product line had the largest VAT?

```
SELECT 
MAX (tax)AS Highest_Vat,
Product_line	
FROM
Walmart
GROUP BY Product_line
ORDER BY Highest_Vat DESC;
```


Question :Which branch sold more products than average product sold?
```
SELECT branch, 
SUM(quantity) AS total_products_sold
FROM Walmart
GROUP BY branch
HAVING SUM(quantity) > (SELECT AVG(total) 
 FROM (SELECT SUM(quantity) AS total 
  FROM Walmart
GROUP BY branch) AS branch_totals)
```

Question : What is the most common product line by gender?

```
Select 
Distinct Product_line,
gender
FROM
Walmart
GROUP BY Product_line,gender
Order by gender DESC;
```








## Result/ Findings

i. Total Revenue: $323k

ii.Total Tax : $15K

iii. Revenue by Time of Day: A clear trend emerged, with Evening leading at $138k, Afternoon following at $123k, and Morning generating $62k.

iv. Top-Selling Product Categories by Quantity: Electronic Accessories lead with 971 units sold, followed by Food & Beverages at 952, Sports & Travel at 920, Home & Lifestyle at 911, Fashion Accessories at 902, and Health & Beauty at 854.

v. Revenue by Payment Method: Cash leads with $112.21k (34.74%), followed closely by E-Wallets at $109.99k (34.06%), and Credit Cards at $100.77k (31.2%).

vii. Revenue by Day: Saturday takes the lead with $56.1k, followed by Tuesday at $51.5k, Thursday at $45.3k, Sunday at $44.5k, Friday at $43.9k, Wednesday at $43.7k, and Monday at $37.9k.



























