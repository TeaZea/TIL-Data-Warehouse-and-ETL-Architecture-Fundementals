# TIL: Data Warehouse and ETL Architecture

### TLDR;
This is a collection of the basic fundementals of data warehouseing and ELT architecture I've learned. This repo showcases some schema and SCD assignments I've completed as well as a 'cap stone' project I took the initiative of completing.

---

### Transaction, Snapshot and Accumulating Snapshot Tables
[Here](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Basic%20Transaction%20Table/Basic%20Student%20Meal%20Transaction%20Table.jpg) is a basic transaction table for a students meal card spending. I decided to use a star schema as this was fairly straight forward.

[This](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Basic%20Snapshot%20Table/Basic%20Faculty%20Papers%20Published%20Snapshot%20Table.jpg) is a snapshot fact table to see what papers have been published for members of a university faculty. I decided to try a snowflake schema because to me it made sense that publications would be directly related to their authors (faculty) dim tables.

[This](https://github.com/TeaZea/Data-Warehouse-and-ETL-Architecture-Fundementals/blob/main/Accumilating%20Snapshot%20Table/Grants%20Accumulating%20Snapshot%20Fact%20Table.jpg) is a basic accumulating snapshot fact table showing when grants were paid to sudents.
