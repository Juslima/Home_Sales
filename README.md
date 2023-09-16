## Home Sales SparkSQL Project

### Introduction

In this project, I used Apache Spark and SparkSQL to analyze home sales data and calculate key metrics. The goal was to perform various operations on the data, such as filtering, aggregation, and caching, to answer specific questions about home sales. This repository contains the code and files related to the project.

### Project Overview

The project involved the following main tasks:

1. **Data Ingestion:** I read the home sales data from a provided CSV file into a Spark DataFrame.

2. **Creating Temporary View:** I created a temporary view of the DataFrame named "home_sales" to perform SQL operations.

3. **Analyzing Home Prices:** I used SparkSQL to answer several questions, including calculating the average price of four-bedroom houses each year, finding the average price of homes based on their characteristics, and filtering homes with specific criteria.

4. **Caching and Performance Analysis:** I cached the "home_sales" temporary table and measured query runtimes with and without caching to observe performance improvements.

5. **Parquet Data and Partitioning:** I wrote the formatted data to Parquet files and created a temporary table for Parquet data, demonstrating the ability to work with different data formats.

6. **Uncaching Data:** Finally, I uncached the "home_sales" temporary table and verified that it was no longer cached.

### Results

The project results are available in the Jupyter Notebook named "Home_Sales.ipynb" within this repository. You can review the code, queries, and their outcomes for a detailed understanding of the analysis.

### Conclusion

This project provided hands-on experience with Apache Spark and SparkSQL for data analysis. It covered a range of operations from data ingestion to caching, and it allowed me to explore the performance benefits of caching in Spark. Overall, it was an insightful project for gaining practical experience with big data analysis using Spark.

If you have any questions or feedback, please feel free to reach out. 

Thank you for visiting this repository!
