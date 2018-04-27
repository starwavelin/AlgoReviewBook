## SQL Interview Questions

#### What is a join?  
A keyword used to query data from more tables based on the relationship between
the fields of the tables. Keys play a major role when JOINs are used.

#### What are the types of join and explain each?
There are various types of join which can be used to retrieve data and it
depends on the relationship between tables.

**Inner Join**

Inner join return rows when there is at least one match of rows between the tables.

**Right Join**

Right join return rows which are common between the tables and all rows of Right
hand side table. Simply, it returns all the rows from the right hand side table
even though there are no matches in the left hand side table.

**Left Join**

Left join return rows which are common between the tables and all rows of Left
hand side table. Simply, it returns all the rows from Left hand side table even
though there are no matches in the Right hand side table.

**Full (Outer) Join**

Return all records when there is a match in either
left (table1) or right (table2) table records.
Matched records are returned once and non-matched records will be kept.

#### What is normalization?
The process of minimizing redundancy and dependency by organizing fields and
table of a database. The main aim of Normalization is to add, delete or modify
field that can be made in a single table.

#### What are all the different normalizations?
The normal forms can be divided into 5 forms, and they are explained below -.

**First Normal Form (1NF):**

This should remove all the duplicate columns from the table. Creation of tables for the related data and identification of unique columns.

**Second Normal Form (2NF):**

Meeting all requirements of the first normal form. Placing the subsets of data in separate tables and Creation of relationships between the tables using primary keys.

**Third Normal Form (3NF):**

This should meet all requirements of 2NF. Removing the columns which are not dependent on primary key constraints.

**Fourth Normal Form (4NF):**

Meeting all the requirements of third normal form and it should not have multi- valued dependencies.

#### What is a View?
A view is a virtual table which consists of a subset of data contained in a table.
Views are not virtually present, and it takes less space to store.
View can have data of one or more tables combined, and it is depending on the relationship.

#### What is an Index?
An index is performance tuning method of allowing faster retrieval of
records from the table. An index creates an entry for each value
and it will be faster to retrieve data.

#### What are all the different types of indexes?
**Unique Index**

This indexing does not allow the field to have duplicate values if
the column is unique indexed. Unique index can be applied automatically
when primary key is defined.

**Clustered Index**

This type of index **reorders the physical order of the table** and search based
on the key values. Each table can have only one clustered index.

**Non-Clustered Index**

NonClustered Index **does not alter the physical order** of the table
and maintains logical order of data. Each table can have 999 non-clustered indexes.

[索引的类型，适用范围，创建，优化](https://www.cnblogs.com/AK2012/archive/2013/01/04/2844283.html)

#### How to create an index?
example
```sql
CREATE NONCLUSTERED INDEX IX_ProductVendor_VendorID   
    ON Purchasing.ProductVendor (BusinessEntityID);   
GO  
```
[Source](https://docs.microsoft.com/en-us/sql/relational-databases/indexes/create-nonclustered-indexes?view=sql-server-2017)
