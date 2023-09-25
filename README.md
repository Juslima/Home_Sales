## Home Sales Analysis with SparkSQL

### Introduction

This GitHub repository documents my analysis of home sales data using Apache Spark and SparkSQL. The project's primary objective was to gain insights into home sales by performing various data operations and answering specific questions about the dataset. This README provides an overview of the project, its tasks, and the results achieved.

### Project Overview

The project encompassed the following key tasks:

### Data Ingestion: I initiated the project by importing the necessary libraries and reading the home sales data from an AWS S3 bucket into a Spark DataFrame. Here's a snippet of the data:

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

