# Meta Data Analyst Pet Store Task
Task from the Meta Deta Analyst professional certification on Coursera. The purpose of the exercise is to demonstrate proficiency in cleaning a small dataset, and to build a simple dashboard in Tableau to be used by the business.

### Project Overview
This data analysis project consists of cleaning, exploring and analyzing product sales data for a small pet store, later generating an informative dashboard in Tableau to visualize sales data for different product line, and categories. 

### Data Sources
The dataset used for this analysis is the provided "transactions-pet_store_small" file, containing 300 entries of detailed sales data. This dataset has been renamed to "PetBusinessDataRaw.csv" in the files.

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

When inspecting the data, there are many missing values in columns such as 'Product_Name', 'Size', 'Product_Category', 'Customer_ID' and 'Product_Line'. I began my process of data cleaning by attempting to fill in the missing values wherever possible. This was easily done for many of the columns because of the SKU column having no missing values. SKU (Stock Keeping Unit) is a unique identifier retailers assign to different products, which also changes for differences in the same product such as size and coloring of the product. Since we have the SKU for every product, and there seems to be no errors in this column, we can look up the SKU for every product and fill in missing values such as Product_Name, Size, Product_Category and Product_Line. For example in the raw dataset, one row contains these missing values:

|Date|Order_Number|Customer_ID|Product_Name|SKU|Price|Size|Quantity|Product_Category|Product_Line|
|---|---|---|---|---|---|---|---|---|---|
|3/31/2019|5ZR-4930-9569-1000|e2b695c8-bf79-46d5-9455-f53f68562af2|N/A|RKAPY3I1TP|39.55|N/A|2|N/A|N/A|

All of these fields are solvable through the SKU of the product. This SKU appears 17 times in the dataset, and has filled in values for all of these fields in the vast majority of those instances. Here's a row that features the same SKU as the row we're trying to solve for missing values in, but which has all values filled in correctly:

|Date|Order_Number|Customer_ID|Product_Name|SKU|Price|Size|Quantity|Product_Category|Product_Line|
|---|---|---|---|---|---|---|---|---|---|
|6/10/2020|58M-9760-8722-9405|47f4ea70-2ebc-4090-94af-2a974c1c2f6f|Feline Fix Mix|RKAPY3I1TP|39.55|N/A|1|treat|cat|

We can see that the 'Size' column is still missing it's value, but this is correct for the product in question as we can see that it's a cat treat named 'Feline Fix Mix', we can thus reasonably assume that this is a product that does not come in different sizes. Looking over the dataset, there seems to only be three products that have any data filled in on the 'Size' column, namely 'Reddy Beddy', 'New Dish' and 'Whole Chemistry Recipe'.

All values in the 'Price' column were formatted to USD to avoid any confusion when it comes to calculating sales figures, as the business was described as an american company that only ships domestically.

Once I had filled in all the missing values possible, I checked for duplicate records, which I found none of. At this point I was happy with the final dataset to be used for subsequent analysis. This dataset can be found in the files titled 'PetBusinessDataClean.csv'.


### Exploratory Data Analysis
In the exploratory phase of the data analysis, I asked questions such as:

- What are the total sales for the pet store?
- Which product line (cat, dog) sees the higher sales?
- How do total sales look when seperated into each product category?
- What are the peak sales periods?

I created an additional column titled 'Sales' which contained the simple formula (Price * Quantity) for every row, in order to show the transaction price for every product.

### Data Analysis
(Include Code)
-- coding done with 3 backticks as brackets --
```sql
SELECT * FROM tablename
```

### Results/Findings
The summary of the results of the analysis are:

### Recommendations
The primary purpose of the dashboard is to provide employees with a very easy way to find sales data, through easy filtering to answer questions such as "what were our sales for dog bedding during Q4 2020?". This can easily be answered through selecting the product line and category in question, as well as the months of interest on the line graph as demonstrated here. As we can see the answer is $354,96.
![image](https://github.com/user-attachments/assets/f09e8c2b-ca78-4698-8688-3e9bd7a4d4c6)


Sales have been going down over time, some change in marketing efforts could be explored in order to try to boost sales. The trend line is not statistically significant enough to be reliably used for any modelling, instead it should be revisited and monitored when the business has been operational for longer. 

Treat is the least sold product category for Dogs, yet it's the highest sold category for Cats. Focus marketing efforts in the treat category for cats. Marketing for the Dogs product line should be focused for bedding products. Toy seems to be popular for both pets, so marketing for toys can include both animals.

Small sample size in regards to months of high sales for the different product type, so use advice sparingly but dog products has seen very strong sales uptick in November both years, while cat products has seen very weak figures both of the past novembers, so run a dog-campaign there. Cat products has seen very strong sales in July the past two years, so consider a promotion for that product line in July.

### References 
[Data Analysis with Spreadsheets and SQL](https://www.coursera.org/learn/data-analysis-with-spreadsheets-and-sql)


