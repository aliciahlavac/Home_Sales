# Home_Sales
Module 22 Challenge

In this project, I performed a series of data analysis tasks using PySpark, which is a powerful framework for handling big data with Apache Spark and Python. The Jupyter Notebook associated with the work done (originally in Google Colab) is [Home_Sales.ipynb](https://github.com/aliciahlavac/Home_Sales/blob/main/Home_Sales.ipynb), and it uses Spark 3.5.0, which is a change from the original starter code.  In this notebook, I imported the necessary PySpark SQL functions that would be essential for my data manipulation and querying tasks.

I started off reading a dataset named home_sales_revised.csv into a Spark DataFrame. This dataset contained information about home sales, and once it was loaded into the DataFrame, I created a temporary table named home_sales in Spark's in-memory storage. This was a crucial step to facilitate efficient SparkSQL queries on the data.

Then, using SparkSQL, I ran several queries:

1. I calculated the average price of four-bedroom houses sold each year. This required grouping the data by year and bedroom count and then calculating the average price.

2. I determined the average price of homes with three bedrooms and three bathrooms for each year they were built. This involved filtering and aggregating the data based on specific home features.

3. I expanded my analysis to calculate the average price of homes that met multiple criteria - three bedrooms, three bathrooms, two floors, and a minimum size of 2,000 square feet - for each year.

4. I analyzed the "view" rating for homes that were priced at $350,000 or more. Additionally, I measured the runtime of this query to understand the performance implications (0.6156942844390869 seconds).

To optimize the performance of my queries, I cached the home_sales temporary table. Caching is a key technique in Spark that speeds up repeated queries by keeping the data in memory.

After caching, I re-ran the query that involved the "view" rating and average price criteria to compare its runtime against the uncached version, thereby demonstrating the effectiveness of caching in improving query performance (runtime now 0.8942062854766846 seconds).

Furthermore, I partitioned the data by the "date_built" field and saved it in the Parquet format, which is known for its efficiency. I created a new temporary table for this partitioned data to run the same "view" rating query, allowing me to compare the runtime performance in different scenarios.

Finally, I uncached the home_sales temporary table and verified its uncaching status using PySpark. 
