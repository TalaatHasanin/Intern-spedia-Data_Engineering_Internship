# Data Warehouse & ETL System:

## Overview:
In this project I built a complete Data Warehouse system using Snowflake Virtual Warehouse and built an ETL system to transfer data from the local machine to Snowflake Warehouse.

---
## project outlines:
### Part-1: users, roles, and database.
First, I created Virtual Warehouse on Snowflake (adhoc_wh) and then created three users with three roles and grant each role to its own user, and grant default roles (Accountadmin, Securityadmin …etc.) to custom roles (project_manager ...etc.)
Users: Project_manager_01, Data_engineer_01, Analyst_01.
Custom Roles: Project_Manager, Data_engineer, Analyst.
After that, I used the role of Project Manager to create a Warehouse, a database, schema and two tables to transfer the data.

### Part-2: data loading, stages, and file format.
I loaded the data to snowflake using snowflake UI from my local machine because I couldn’t use AWS although the use of AWS cloud provider and using S3 as a storage service would have helped on create a continuous data pipeline.
Before loading the data, I create a file format to assign the type of the data in CSV format, then create an internal stage to load data files from my local machine to snowflake’s respective table, then I test the data in tables by writing a select statement.
In the end of this part, I granted some privileges to custom roles I have created in the first part to use it for transformations in tables in part 3.

### Part-3: Tasks, Transformations, and Query the new tables.
I used tasks in this part to make some transformations in tables, I wrote a SQL statement to choose the data from tables (Customer_details_table & Sales_details_table) without NULL then assign each query to a task.
First, I created a new table with the same structure of respective tables then start the tasks and check it using a SQL query.
In the end I used the user “Analyst” to query the new tables using the SELECT clause only because it is the only one that the user “Analyst” is allowed to use.

---
## Tools: SQL - Snowflake
