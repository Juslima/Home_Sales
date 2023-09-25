## Home Sales Analysis with SparkSQL

### Introduction

This GitHub repository documents my analysis of home sales data using Apache Spark and SparkSQL. The project's primary objective was to gain insights into home sales by performing various data operations and answering specific questions about the dataset. This README provides an overview of the project, its tasks, and the results achieved.

### Project Overview

The project encompassed the following key tasks:

**Data Ingestion:** I initiated the project by importing the necessary libraries and reading the home sales data from an AWS S3 bucket into a Spark DataFrame. Here's a snippet of the data:

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

**Creating Temporary View:** To facilitate SQL-based analysis, I created a temporary view named "home_sales" from the DataFrame.

**Analyzing Home Prices:** I executed SQL queries to answer specific questions about home prices and characteristics. Here are some example results:

 ## Queries and Answers

Certainly! Here are the answers to the queries along with their corresponding results:

3. **Average Price for Four-Bedroom Houses by Year:**
   - Query: Calculate the average price for four-bedroom houses sold in each year, rounded to two decimal places.
   - Result:
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

4. **Average Price of Three-Bedroom, Three-Bathroom Homes by Year Built:**
   - Query: Calculate the average price of homes with three bedrooms and three bathrooms for each year the home was built, rounded to two decimal places.
   - Result:
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

5. **Average Price of Three-Bedroom, Three-Bathroom, Two-Floor Homes with at least 2,000 Sq. Ft.:**
   - Query: Calculate the average price of homes with three bedrooms, three bathrooms, two floors, and a living area of at least 2,000 square feet for each year they were built, rounded to two decimal places.
   - Result:
     ```
     +----+---------+
     |year|avg_price|
     +----+---------+
     |2017|280317.58|
     |2016| 293965.1|
     |2015|297609.97|
     |2014|298264.72|
     |2013|303676.79|
     |2012|307539.97|
     |2011|276553.81|
     |2010|285010.22|
     +----+---------+
     ```

6. **Average Price of Homes with a View (View Rating) and Price >= $350,000:**
   - Query: Calculate the average price of homes for each distinct view rating where the average price is greater than or equal to $350,000.
   - Result (partial, due to the large number of view ratings):
     ```
     +----+----------+
     |view| avg_price|
     +----+----------+
     |  99|1061201.42|
     |  98|1053739.33|
     |  97|1129040.15|
     |  96|1017815.92|
     |  95| 1054325.6|
     |  94| 1033536.2|
     |  93|1026006.06|
     |  92| 970402.55|
     |  91|1137372.73|
     |  90|1062654.16|
     |  89|1107839.15|
     |  88|1031719.35|
     |  87| 1072285.2|
     |  86|1070444.25|
     |  85|1056336.74|
     |  84|1117233.13|
     |  83|1033965.93|
     |  82| 1063498.0|
     |  81|1053472.79|
     |  80| 991767.38|
     +----+----------+
     ```

   - Runtime: Approximately 0.73 seconds

## Observations:

In Query 9 (Uncached), the query runtime was approximately 1.18 seconds.
In Query 13 (Parquet Data), the query runtime was significantly faster, at approximately 0.50 seconds.
In both queries, we aimed to identify view ratings associated with average home prices greater than or equal to $350,000. The results are displayed in descending order of view ratings.

The results show the view ratings (on the x-axis) and their corresponding average prices (on the y-axis). We can make the following observations:

The average prices generally increase as view ratings improve, which is expected.
View ratings 90 to 99 have notably higher average prices, indicating that properties with these views tend to command premium prices.
The runtime improvement in Query 13 demonstrates the benefits of storing data in Parquet format and utilizing partitioning, making data retrieval more efficient.


### Project Conclusion

This project provided valuable hands-on experience with Apache Spark and SparkSQL for data analysis. I successfully completed a range of tasks, from data ingestion to complex SQL queries and caching. Additionally, I gained insight into Parquet data storage and partitioning, which are essential for managing big data efficiently.

The provided results, along with the detailed code and analysis, can be found in the Jupyter Notebook named "Home_Sales.ipynb" within this repository.

If you have any questions, feedback, or suggestions for improvement, please feel free to reach out. Thank you for exploring this repository and my analysis of home sales data with SparkSQL!
