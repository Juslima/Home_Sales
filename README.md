## Home Sales Analysis with SparkSQL

### Introduction

This GitHub repository documents my analysis of home sales data using Apache Spark and SparkSQL. The project's primary objective was to gain insights into home sales by performing various data operations and answering specific questions about the dataset. This README provides an overview of the project, its tasks, and the results achieved.

### Project Overview

The project encompassed the following key tasks:

1. **Data Ingestion:** I initiated the project by importing the necessary libraries and reading the home sales data from an AWS S3 bucket into a Spark DataFrame. Here's a snippet of the data:

   ```
   +--------------------+----------+----------+------+--------+---------+-----------+--------+------+----------+----+
   |                  id|      date|date_built| price|bedrooms|bathrooms|sqft_living|sqft_lot|floors|waterfront|view|
   +--------------------+----------+----------+------+--------+---------+-----------+--------+------+----------+----+
   |f8a53099-ba1c-47d...|2022-04-08|      2016|936923|       4|        3|       3167|   11733|     2|         1|  76|
   |7530a2d8-1ae3-451...|2021-06-13|      2013|379628|       2|        2|       2235|   14384|     1|         0|  23|
   |43de979c-0bf0-4c9...|2019-04-12|      2014|417866|       2|        2|       2127|   10575|     2|         0|   0|
   |b672c137-b88c-48b...|2019-10-16|      2016|239895|       2|        2|       1631|   11149|     2|         0|   0|
   |e0726d4d-d595-407...|2022-01-08|      2017|424418|       3|        2|       2249|   13878|     2|         0|   4|
   |5aa00529-0533-46b...|2019-01-30|      2017|218712|       2|        3|       1965|   14375|     2|         0|   7|
   ...

2. **Creating Temporary View:** To facilitate SQL-based analysis, I created a temporary view named "home_sales" from the DataFrame.

3. **Analyzing Home Prices:** I executed SQL queries to answer specific questions about home prices and characteristics. Here are some example results:

   - **What is the average price for a four-bedroom house sold in each year rounded to two decimal places?**
     ```
     +----+---------+
     |year|avg_price|
     +----+---------+
     |2019| 300263.7|
     |2020|298353.78|
     |2021|301819.44|
     |2022|296363.88|
     +----+---------+
     ```

   - **What is the average price of a home for each year the home was built that has 3 bedrooms and 3 bathrooms rounded to two decimal places?**
     ```
     +----+---------+
     |year|avg_price|
     +----+---------+
     |2010|292859.62|
     |2011|291117.47|
     |2012|293683.19|
     |2013|295962.27|
     |2014|290852.27|
     |2015| 288770.3|
     |2016|290555.07|
     |2017|292676.79|
     +----+---------+
     ```

   - **What is the average price of a home for each year built that has 3 bedrooms, 3 bathrooms, with two floors, and is greater than or equal to 2,000 square feet rounded to two decimal places?**
     ```
     +----+---------+
     |year|avg_price|
     +----+---------+
     |2010|285010.22|
     |2011|276553.81|
     |2012|307539.97|
     |2013|303676.79|
     |2014|298264.72|
     |2015|297609.97|
     |2016| 293965.1|
     |2017|280317.58|
     +----+---------+
     ```

   - **What is the "view" rating for the average price of a home, rounded to two decimal places, where the homes are greater than or equal to $350,000?**
     - The query executed successfully, and the runtime was negligible (0.0 seconds).

4. **Caching and Performance Analysis:** I explored the caching feature of Spark. I cached the "home_sales" temporary table and verified its cache status. I also ran a query on the cached table and compared its runtime with the uncached version. Both cached and uncached runtimes were negligible (0.0 seconds), likely due to the dataset's size.

5. **Parquet Data and Partitioning:** I wrote the formatted data to Parquet files and partitioned it by the "date_built" field. This demonstrated the ability to work with different data formats and efficiently manage large datasets.

6. **Uncaching Data:** Finally, I uncached the "home_sales" temporary table and verified that it was no longer cached.

### Project Conclusion

This project provided valuable hands-on experience with Apache Spark and SparkSQL for data analysis. I successfully completed a range of tasks, from data ingestion to complex SQL queries and caching. Additionally, I gained insight into Parquet data storage and partitioning, which are essential for managing big data efficiently.

The provided results, along with the detailed code and analysis, can be found in the Jupyter Notebook named "Home_Sales.ipynb" within this repository.

If you have any questions, feedback, or suggestions for improvement, please feel free to reach out. Thank you for exploring this repository and my analysis of home sales data with SparkSQL!

