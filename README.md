# TIL: Data Warehouse and ETL Architecture

### TLDR + Sales Order Transaction Fact Table Project;
This is a collection of the basic fundementals of data warehouseing and ELT architecture I've learned. This repo showcases some schema and SCD assignments I've completed as well as a 'cap stone' project I took the initiative of completing. All of the schemas here were made using [draw.io](https://app.diagrams.net/)
--
[This](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Sales%20Order%20Transactional%20Fact%20Table/Sales%20Order%20Schema-ver1.jpg) is a project I decided to do so I can put the fundementals I learned on display. I decided to do a sales order transaction fact table (within the scope of manufacturing domain) as it reflects something I see day to day. I chose to create a snowflake schema because I work with AS400 quite a bit and I feel like a snowflake schema can better suit this type of program which relies on various methods of reflecting/streaming data, both up and downstream.

Below is the fact table. It's fed from 5 dimension tables and it's purpose is to show the customer, product and other important details that would be included on a business invoice.

![fact table](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Sales%20Order%20Transactional%20Fact%20Table/Sales%20order%20fact.jpg)

### Main Dimensions
- **Customer Dim**
- **Date Dim**
- **Product Dim**
- **Freight Dim**
- **Taxes Dim**

All dimensions posess a natureal key and a surugate key. The SKs function as the primary key for their own dimension and foreign key for tables it feeds into.

### Challenges
TODO: creating the product dimension


---

### Transaction, Snapshot and Accumulating Snapshot Tables
Below is a basic transaction table for a students meal card spending. I decided to use a star schema as this was fairly straight forward.

![transaction](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Basic%20Transaction%20Table/Basic%20Student%20Meal%20Transaction%20Table.jpg)
-

This is a snapshot fact table to see what papers have been published for members of a university faculty. I decided to try a snowflake schema because to me it made sense that publications would be directly related to their authors (faculty) dim tables.

![snapshot](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Basic%20Snapshot%20Table/Basic%20Faculty%20Papers%20Published%20Snapshot%20Table.jpg)
-

Lastly, this is a basic accumulating snapshot fact table showing when grants were paid to sudents.

![accumulating snapshot](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Accumilating%20Snapshot%20Table/Grants%20Accumulating%20Snapshot%20Fact%20Table.jpg) 

---

### Warehousing Architecture

Here are two solutions for possible user access layers. The maine warehouse takes data from multiple campuses and displays them 2 ways. The first by campuses and the second by amalgamation of records from all campuses.

![warehouse architecture1](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Data%20Warehouseing%20Architecture/Data%20Warehouse%20Architecture_Sltn1.jpg)

![warehouse architecture2](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Data%20Warehouseing%20Architecture/Data%20Warehouse%20Architecture_Sltn2.jpg)

---

### ETL Fundementals

Below shows basic knowledge of understanding attributes and the need for consistant data types and governance during the transformation process of an ETL pipeline.

![etl fundementals](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/ETL%20Fundemental/ETL%20Fundemental.jpg)

---

### Factless Fact Table

![simple factless fact table](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Factless%20Fact%20Table/Basic%20Orientation%20Program%20Registration%20Factless%20Fact%20Table.jpg)

---

### SCD Types

[This](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/tree/main/Type%201_Type%202%20SCD) is a link to a little assignment I did to demonstrate understanding of Type 1 and 2 SCD. This table shows information of faculty members. 'highest degree' can be changed in place, while a record of a faculty member's 'rank' has to be kept for historical analysis. I used excel as I thought this was the easiest way to showcase changes being made to a table.


