# Meta Data Analyst Pet Store Task
Task from the Meta Deta Analyst professional certification on Coursera.

### Project Overview
This data analysis project consists of cleaning, exploring and analyzing product sales data for a pet-food business, later generating an informative dashboard in Tableau to visualize sales data for different product line, and categories.

### Data Sources
The dataset used for this analysis is the provided "transactions-pet_store_small" file, containing 300 entries of detailed sales data.

Example Rows of Data:
|Date|Order_Number|Customer_ID|Product_Name|SKU|Price|Size|Quantity|Product_Category|Product_Line|
|---|---|---|---|---|---|---|---|---|---|
|6/4/2020|SBT-7370-4009-6368|7f5111f6-53c9-4316-b134-dd8c3b6b29f7|New Dish|NYW2F6CPBY|17.16|large|3|food|dog|
|12/6/2019|LXL-2026-1169-6850|37dbbf1c-40a9-4a9f-8318-51d1d29319bc|Reddy Beddy|I2GQUNYDXW|36.3|medium|2|bedding|dog|
|5/16/2020|DH0-5008-7799-0110|e881497a-9232-4c23-89a0-7f2cfe20ce1b|Foozy Mouse|8PYSMLYINS|10.8|N/A|2|toy|cat|

### Tools:
- Google Sheets - Data Cleaning
- SQL queries in Google Sheets - Data Exploration
- Tableau - Creating Dynamic Dashboard


### Data Cleaning/Preparation
In the initial data preparation phase, I performed the following tasks:
1. Data loading and inspection.
2. Handing missing values.
3. Data cleaning and formatting.

### Exploratory Data Analysis
In the exploratory phase of the data analysis, I asked questions such as:

- What are the total sales for the pet store?
- Which product line (cat, dog) sees the higher sales?
- How do total sales look when seperated into each product category?
- What are the peak sales periods?

### Data Analysis
(Include Code)
-- coding done with 3 backticks as brackets --
```sql
SELECT * FROM tablename
```

### Results/Findings
The summary of the results of the analysis are:

### Recommendations
(increase marketing or run promotions for certain categories during peak sales)

### References 
[Data Analysis with Spreadsheets and SQL](https://www.coursera.org/learn/data-analysis-with-spreadsheets-and-sql)


