# Home_Sales

Home Sales Analysis with PySpark

Overview

In this project, we aim to analyze home sales data using PySpark and SparkSQL. The dataset, home_sales_revised.csv, is stored on an AWS S3 bucket, and we will leverage PySpark's SQL functions to answer several questions related to the average price of homes based on specific criteria. Key tasks include reading the data, creating temporary tables, querying data, caching, and partitioning the dataset for improved performance. This analysis will demonstrate how PySpark can be used to handle large datasets efficiently and answer business-critical questions.

Methodology

Renaming the Notebook: The notebook Home_Sales_starter_code.ipynb was renamed to Home_Sales.ipynb to reflect the completion of the analysis.
Data Import: The dataset home_sales_revised.csv was imported from an AWS S3 bucket into a PySpark DataFrame.
Temporary Table Creation: A temporary table named home_sales was created for efficient querying with SparkSQL.
SQL Queries:
Average Price of Four-Bedroom Houses: We calculated the average price of four-bedroom homes sold each year, rounded to two decimal places.
Average Price of Three-Bedroom, Three-Bathroom Homes: We calculated the average price of homes that have three bedrooms and three bathrooms, grouped by the year they were built, rounded to two decimal places.
Average Price of Large Three-Bedroom Homes: We calculated the average price of homes with three bedrooms, three bathrooms, two floors, and a minimum of 2,000 square feet, grouped by the year they were built, rounded to two decimal places.
Average Price per View Rating: We calculated the average price of homes based on their "view" rating for homes with an average price greater than or equal to $350,000. The runtime for this query was also measured.
Caching: The home_sales temporary table was cached to improve query performance. We checked if the table was cached, then ran the average price query to compare the runtime of cached and uncached queries.
Partitioning: The dataset was partitioned by the date_built field and saved in Parquet format. A temporary table was then created for the partitioned data.
Final Query Execution: The same query from Step 4 (average price per "view" rating) was executed on the partitioned data to compare its performance with the uncached runtime.
Uncaching the Table: The home_sales temporary table was uncached, and we verified that it was no longer cached using PySpark.
Repository Upload: The final Home_Sales.ipynb notebook was uploaded to the GitHub repository named "Home_Sales."
Results

The queries successfully calculated the average price of homes based on the different criteria, with results rounded to two decimal places as requested.
Caching the home_sales temporary table resulted in a faster query execution time, which was particularly noticeable in the query that calculates the average price per "view" rating for homes priced over $350,000.
Partitioning the dataset by the date_built field and using the partitioned Parquet format further improved query performance for large datasets.
The performance difference between the cached and uncached queries was clearly observable, with cached queries running significantly faster.

References
ChatGPT
XpertLearning Assistant
The Tutor Fred Logan
