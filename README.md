# Amazon_Vine_Analysisv2

##Purpose
As the data analyst assigned I will be able to
 
   •	Define big data and describe the challenges associated with it.

  •	Define Hadoop and name the main elements of its ecosystem.

  •	Explain how MapReduce processes data.

  •	Define Spark and explain how it processes data.

  •	Describe how NLP collects and analyzes text data.

  •	Explain how to use AWS Simple Storage Service (S3) and relational databases for basic cloud storage.

  •	Complete an analysis of an Amazon customer review.



##Deliverable 1: Perform ETL on Amazon Product Reviews (40 points)

##Deliverable 2: Determine Bias of Vine Reviews (40 points)

##Deliverable 3: A Written Report on the Analysis (20 points)
.
.
.
.

##Deliverable 1: Perform ETL on Amazon Product Reviews (40 points)

2.	Create a new database with Amazon RDS just as you did in this module.

3.	In pgAdmin, create a new database in your Amazon RDS server that you just create.

![image](https://user-images.githubusercontent.com/117233641/232491344-f6ebbc9e-46fa-4073-8d8e-773dc2c7f490.png)

4.	Download the challenge_schema.sql file to your computer.

5.	In pgAdmin, run a new query to create the tables for your new database using the code from the challenge_schema.sql file.
   o	After you run the query, you should have the following four tables in your database: customers_table, products_table, review_id_table, and vine_table.

![image](https://user-images.githubusercontent.com/117233641/232491611-b143a11d-fb8a-487b-81a4-29351a962160.png)

7.	Download the Amazon_Reviews_ETL_starter_code.ipynb file, then upload the file as a Google Colab Notebook, and rename it Amazon_Reviews_ETL.


8.	First extract one of the review datasets, then create a new DataFrame.

![image](https://user-images.githubusercontent.com/117233641/232491692-adb20561-eedc-451e-944e-a6b44030fd33.png)

Next, follow the steps below to transform the dataset into four DataFrames that will match the schema in the pgAdmin tables:
![image](https://user-images.githubusercontent.com/117233641/232492051-828f6f45-c79d-49df-98ba-57bc1e854637.png)

![image](https://user-images.githubusercontent.com/117233641/232492095-35aac716-2920-473a-b572-7d66c0db0a76.png)


##The customers_table DataFrame

To create the customers_table, use the code in the Amazon_Reviews_ETL_starter_code.ipynb file and follow the steps below to aggregate the reviews by customer_id.

 •	Use the groupby() function on the customer_id column of the DataFrame you created in Step 7.

 •	Count all the customer ids using the agg() function by chaining it to the groupby() function. After you use this function, a new column will be created, count(customer_id).

 •	Rename the count(customer_id) column using the withColumnRenamed() function so it matches the schema for the customers_table in pgAdmin.

 •	The final customers_table DataFrame should look like this:
![image](https://user-images.githubusercontent.com/117233641/232493012-3df57187-6768-45b3-ab8c-bcd02c01e535.png)


The products_table DataFrame
To create the products_table, use the select() function to select the product_id and product_title, then drop duplicates with the drop_duplicates() function to retrieve only unique product_ids. Refer to the code snippet provided in the Amazon_Reviews_ETL_starter_code.ipynb file for assistance.
The final products_table DataFrame should look like this:

![image](https://user-images.githubusercontent.com/117233641/232493948-f5e5879a-28f3-43f0-8fe1-c187b2c96cdd.png)


The review_id_table DataFrame
To create the review_id_table, use the select() function to select the columns that are in the review_id_table in pgAdmin (as shown in the following image), and convert the review_date column to a date using the code snippet provided in the Amazon_Reviews_ETL_starter_code.ipynb file.
The final review_id_table DataFrame should look like this:
 
The vine_table DataFrame
To create the vine_table, use the select() function to select only the columns that are in the vine_table in pgAdmin (as shown in the following image).
The final vine_table DataFrame should look like this:
 
 ![image](https://user-images.githubusercontent.com/117233641/232518943-fab3c947-5a9d-4b1d-891f-b85b35bf08e9.png)

Load the DataFrames into pgAdmin
1.	Make the connection to your AWS RDS instance.
2.	Load the DataFrames that correspond to tables in pgAdmin.

![image](https://user-images.githubusercontent.com/117233641/232626552-1b212aeb-7162-45f8-a66f-abd7505810ae.png)


3.	In pgAdmin, run a query to check that the tables have been populated.
![image](https://user-images.githubusercontent.com/117233641/232627074-96b0e6a3-af98-466e-b785-1b7441712ac2.png)


![image](https://user-images.githubusercontent.com/117233641/232626980-3272c615-305b-4202-ac31-2f4f7925199d.png)


![image](https://user-images.githubusercontent.com/117233641/232626894-962304a0-6c4c-4190-b2b7-b3bd10282fe8.png)


