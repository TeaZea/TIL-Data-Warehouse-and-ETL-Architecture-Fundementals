# TIL: Data Warehouse and ETL Architecture

### TLDR;

This is a collection of the basic fundementals of data warehouseing and ELT architecture I've learned. This repo showcases some schema and SCD assignments I've completed as well as a 'cap stone' project I took the initiative of completing. All of the schemas here were made using [draw.io](https://app.diagrams.net/)


## Sales Order Transaction Fact Table Project

[This](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Sales%20Order%20Transactional%20Fact%20Table/Sales%20Order%20Schema-ver1.jpg) is a project I decided to do so I can put the fundementals I learned on display. I decided to do a sales order transaction fact table (within the scope of manufacturing domain) as it reflects something I see day to day. I chose to create a snowflake schema because I work with AS400 quite a bit and I feel like a snowflake schema can better suit this type of program which relies on various methods of reflecting/streaming data, both up and downstream.

Below is the fact table. It's fed from 5 dimension tables and it's purpose is to show the customer, product and other important details that would be included on a business invoice.

![fact table](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Sales%20Order%20Transactional%20Fact%20Table/Sales%20order%20fact.jpg)

### Main Dimensions
- Customer Dim
- Date Dim
- Product Dim
- Freight Dim
- Taxes Dim

All dimensions posess a natural key and a surrogate key. The SKs function as the PK for their own dimension and FK for tables it feeds into.

>[!Note]
>Some dimensions would benefit from record keeping IE: frieght cost (freight dimension) or the price of raw materials for components (product dimension). Those details were not included in this project as I was trying to focus more on the schema as a whole while still including a bit of info like the attributes of the records.

### Challenges
Outside of developing the actual fact table, the entire branch of the product_Dim was the most challenging part.

![product dim](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Sales%20Order%20Transactional%20Fact%20Table/Product%20branch.jpg)

The product dimension (and associated dims) needed to be done from a manufacturing-first point of view. Products don't come from nothing. They are made using various components. Those components are created from their own raw meterials or other components. On top of all of that, all of them have their own list and retail prices, as well as dimensions. While building this portion of the schema out, I had to constantly modify which dims certain records where placed, often finding I had to create a whole new dim for them. Overall, even though this was the most challenging part, it was also the most fun part.

### Beyond The Technical Solution
When designing the schema, I tried to include as many branching dims as possible that would also help facilitate better data driven decisions downstream for multiple departments within an organization. For instance, sales and marketing departments can benefit the most from the shocased dimensions, however, product teams can deep dive into the costing or complexity of components; while the logistics department can monitor fluctiation in freight charges year over year.


## TIL Transaction, Snapshot and Accumulating Snapshot Tables
Below is a basic transaction table for a students meal card spending. I decided to use a star schema as this was fairly straight forward.

![transaction](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Basic%20Transaction%20Table/Basic%20Student%20Meal%20Transaction%20Table.jpg)
-

This is a snapshot fact table to see what papers have been published for members of a university faculty. I decided to try a snowflake schema because to me it made sense that publications would be directly related to their authors (faculty) dim tables.

![snapshot](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Basic%20Snapshot%20Table/Basic%20Faculty%20Papers%20Published%20Snapshot%20Table.jpg)
-

Lastly, this is a basic accumulating snapshot fact table showing when grants were paid to sudents.

![accumulating snapshot](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Accumilating%20Snapshot%20Table/Grants%20Accumulating%20Snapshot%20Fact%20Table.jpg) 


## TIL Warehousing Architecture

Here are two solutions for possible user access layers. The maine warehouse takes data from multiple campuses and displays them 2 ways. The first by campuses and the second by amalgamation of records from all campuses.

![warehouse architecture1](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Data%20Warehouseing%20Architecture/Data%20Warehouse%20Architecture_Sltn1.jpg)

![warehouse architecture2](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Data%20Warehouseing%20Architecture/Data%20Warehouse%20Architecture_Sltn2.jpg)


## TIL ETL Fundementals

Below shows basic knowledge of understanding attributes and the need for consistant data types and governance during the transformation process of an ETL pipeline.

![etl fundementals](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/ETL%20Fundemental/ETL%20Fundemental.jpg)


## TIL Factless Fact Table

![simple factless fact table](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Factless%20Fact%20Table/Basic%20Orientation%20Program%20Registration%20Factless%20Fact%20Table.jpg)


## TIL SCD Types

[This](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/tree/main/Type%201_Type%202%20SCD) is a link to a little assignment I did to demonstrate understanding of Type 1 and 2 SCD. This table shows information of faculty members. 'highest degree' can be changed in place, while a record of a faculty member's 'rank' has to be kept for historical analysis. I used excel as I thought this was the easiest way to showcase changes being made to a table.


