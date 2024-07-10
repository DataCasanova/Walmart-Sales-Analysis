# Optimizing Sales Performance: A Comprehensive Data Analysis for Walmart

## Executive Summary
As a newly hired data analyst at Walmart, my primary task was to analyze our sales data to provide actionable insights that can drive business growth and improve operational efficiency. This report presents a detailed analysis of the sales data, focusing on the importance of data matrices in understanding our business performance. The analysis covers various dimensions such as sales, customer segmentation, shipping details, and product categories.

## Introduction
In my role as a data analyst, I utilized data matrices to organize and analyze sales data, which is crucial for making informed decisions. This report demonstrates how structured data analysis can help Walmart understand its market performance, optimize strategies, and enhance profitability.

## Data Overview
The dataset includes the following key variables:

- Order Details: Row ID, Order ID, Order Date, Ship Date, Ship Mode
- Customer Information: Customer ID, Customer Name, Segment, Country, City, State, Postal Code, Region, Retail Sales People
- Product Information: Product ID, Category, Sub-Category, Product Name
- Sales Metrics: Returned, Sales, Quantity, Discount, Profit

## Tools and Methodology
Tools Used
- Microsoft Excel: For data organization, analysis, and visualization.
- PPower BI: To summarize data and create data matrices for deeper analysis.
- Dax: To calculate totals, averages, and other key metrics.

## Key Findings
## 1. Sales Performance by Region

 Sales Performance by Region         |           Central Region
:-----------------------------------:|:------------------------:
                                        Top Performing Product: Xerox 1915 (Office Supplies - Paper)
                                        Sales: $209.70
                                        Profit: $100.66
                                        Retail Sales Person: Kelly Williams              

 Sales Performance by Region         |           East Region
:-----------------------------------:|:------------------------:
                                        Top Performing Product: Bush Westfield Collection Bookcases (Furniture - Bookcases)
                                        Sales: $323.14
                                        Profit: $12.12
                                        Retail Sales Person: Chuck Magee              

 Sales Performance by Region         |           West Region
:-----------------------------------:|:------------------------:
                                        Top Performing Product: Adjustable Depth Letter/Legal Cart (Office Supplies - Storage)
                                        Sales: $725.84
                                        Profit: $210.49
                                        Retail Sales Person: Anna Andreadi    


## 2. Customer Segmentation

 Corporate                           |       Segment 
:-----------------------------------:|:------------------------:
                                        High Sales: Erica Bern ($34.62)
                                        Regions: West
                                        Key Products: Binders, Storage
                                        Consumer Segment
                                        High Sales: Jennifer Ferguson ($134.52)
                                        Regions: East
                                        Key Products: Labels, Binders, Phones


3. Product Category Analysis

 Product                             |      Category Analysis
:-----------------------------------:|:------------------------:
                                        Office Supplies: Highest volume with products like binders and fasteners showing consistent sales across regions.
                                        Technology: Includes niche products like phone cases and headsets, moderate sales.
                                        Furniture: High-ticket items with significant contributions to sales but varied profit margins.

4. Return Analysis

 Return                              |       Analysis
:-----------------------------------:|:------------------------:
                                        Products with high return rates include binders, highlighting potential quality issues or customer dissatisfaction.

5. Shipping Mode Impact
Standard Class: Predominantly used shipping mode, suggesting cost efficiency.
Second Class: Limited use, potentially for urgent deliveries or high-value items.
Conclusion
Key Findings
Regional Performance: The West region, particularly San Francisco, shows high sales and profit margins, suggesting a strong market presence.
Customer Segmentation: The consumer segment drives high sales volumes, especially in the East region, necessitating targeted marketing strategies.
Product Categories: Office supplies dominate sales, but a focus on reducing return rates and enhancing product quality could further boost profits.
Recommendations
Targeted Marketing: Focus on high-performing regions and customer segments with tailored promotions and advertising.
Product Quality Improvement: Address the return rates for specific products like binders to enhance customer satisfaction.
Optimize Shipping: Evaluate the cost-effectiveness of shipping modes to ensure timely and cost-efficient deliveries.
Importance of Data Matrices
The use of data matrices in this analysis was crucial. By organizing data into structured formats, it becomes easier to extract meaningful insights, identify trends, and make data-driven decisions. This structured approach is essential for large organizations like Walmart to maintain competitive advantage and drive business growth.

Conclusion
By leveraging Excel, pivot tables, and relevant formulas, I was able to provide Walmart with comprehensive insights into sales performance, customer segmentation, and regional trends. This structured approach ensures data-driven decision-making, leading to improved business strategies and growth. As a data analyst, my role is to continue refining these analyses, helping Walmart enhance its market presence and profitability.



**Power BI Concepts applied:**
- DAX Concepts:
                Calculated column,
                Custom Column,
                Year(),
                IF().
- Data Modelling: Star Schema (*:1)

----
## Problem Statement
- How long on average does an order take before delivery?
- What is the total sales made yearly since 2012? Has sales been on the increase since over the yers?
- Which of our customers are most important?
- Which of our products make the greatest profit and which products run the store into loss?
- Any other relevant data-driven insight into our sales. 
## Data Sourcing
Not until I came up with the above mentioned questions did I went ahead to get the data. I then downloaded the csv file, and extracted it into Power BI for clening, analysis and visualization.

It contains 3 sheets/tables:
1. ORDERS with 51,291 rows and 24 columns
2. PEOPLE with 24 rows and 2 columns
3. RETURNS with 1079 rows and 3 columns
----
## Data Transformation/Cleaning:
Data was efficiently cleaned and transformed with the Power Query Editor of Power BI.
[a screenshot of the applied steps]
Some of the applied steps included 

- Making first row as headers in the PEOPle and RETURN tables.
- Analytical transformation of the 'order table';
To have an idea of how long it takes on average for orders to be dilevered, [delivery days] need to be calculated.
 Using "custom columns", 
`delivery days = [shipped date] - [order date]`
- created new column for year of order date and named: [Order Year]
- ADDING conditional column to the 'Returns Table' to assign a numeric value to the Return response of YES and NO. If YES, then 1, else 0.
`Return Orders = IF(Returns[Returned] = "Yes", 1, 0)`
- Datatype then chnged from 'TEXT' TO 'WHOLE NUMBER'.

## DATA MODELLING
Power BI automatically connected related tables resulting in a star schema model.
The 'Order' table is the fact table of the model.
The remaining two dimension tables; 'Return' table and 'People' table are connected to the 'Order' table via the common columns: 'order ID' and Region respectively.
![](model.png)

## Data Analysis and Visuals
![](dashboard.png)
1. From the dashboard, it is observed that it takes 4 days on average to deliver each product on every order.
2. Total sales made in 2012= 2.26M, 2013=2.68M ,2014=3.41M ,2015=4.30M.
3. Sales is highest in the Western Europe region with almost 450k dollars.

![](top10.png)

 Tamara Chand is the most valuable costumer by sales.
 
 ## conclusions & Recommendations
- An order takes 4days on average before delivery.
- There has been a gradual increase in the yearly sales since 2012 at the rate of approximately 19%.
- Different customers topped the profit list for each year.
- **Tamara Chand** has made the highest sales overall since 2012 to 2015. 
 However, on a yearly basis,
**Sanjit Chand** made the highest sale in 2012 with over 5.7k dollars while Tamara Chand could not make the top 10 sales for that year. 

In 2013;
 **Mike Gokenbach** made the higest sales with 4.8k dollars.

In 2014;
**Tamara chand** purchased products worth 8.5k.

In 2015;
**Raymond Buch** purchsed products worth $7.4k.

- **Canon Image (Class 2200) advance copier** made the highest profit in both 2014 and 2015.
Other Insights:
- The consumer segment has made more than 50% of the total sales. 
- Asia Pacific is the region with the highest sales.
