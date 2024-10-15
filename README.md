# TIL: Data Warehouse and ETL Architecture

### TLDR + Sales Order Transaction Fact Table;
This is a collection of the basic fundementals of data warehouseing and ELT architecture I've learned. This repo showcases some schema and SCD assignments I've completed as well as a 'cap stone' project I took the initiative of completing.

[This](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Sales%20Order%20Transactional%20Fact%20Table/Sales%20Order%20Schema-ver1.jpg) is a project I decided to do so I can put the fundementals I learned on display.

(TODO detailed views of each branch of the snowflake + reasoning)

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

TODO

---

### SCD Types

TODO


