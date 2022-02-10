---
title: "Introduction"
teaching: 0

objectives:
- "Introduction To SQL"
- "Build understanding on important keywords of SQL"

keypoints:
- "Introduction to SQL and its keywords like SELECT, FROM, AS, WHERE, DISTINCT, ORDER BY"
---

## INTRODUCTION TO SQL

SQL stands for Structured Query Language and is the standard language used in a
Relational Database Management System (RDBMS). SQL is used to communicated with the
database and perform necessary operations such as update existing data (or) retrieve data.


A database generally comprises of multiple tables and each table consists of multiple
records (rows) and attributes (columns). SQL helps perform operations on the tables of the
database.

![Intro_1](../fig/Intro_1.JPG)

### SELECT:

The SELECT statement is used to indicate what is required to be selected from the table.
To select columns from the table, mention the names of the columns after SELECT keyword. To
select all columns, indicate the asterisk (*) symbol after SELECT keyword.

Important Note – The SQL statement keywords are NOT case-sensitive and hence the keywords
select and SELECT are treated the same way.

Consider the below table called Customers which contains details about various customers. (Only
first five rows are shown)

![Intro_2](../fig/Intro_2.JPG)

| Syntax | Description |
| --- | --- |
| SELECT * FROM table_name | Will select all the columns from the table |
| SELECT column1, column2,... FROM table_name | Will select only the specified columns from the table |
| SELECT column1 AS new_name FROM table_name | Selects only the specified column but renames the column to the new_namewhile displaying the result |

Selecting all the columns

```sql
SELECT * FROM Customers
```
![Intro_3](../fig/Intro_3.JPG)

Selecting particular columns

```sql
SELECT CustomerName, City FROM Customers
```
![Intro_4](../fig/Intro_4.JPG)

Renaming columns for display
```sql
SELECT CustomerName AS Name, City FROM Customers
```
![Intro_5](../fig/Intro_5.JPG)

Result columns are displayed in the order specified
```sql
SELECT Country, ContactName, PostalCode, CustomerID FROM Customers
```
![Intro_6](../fig/Intro_6.JPG)

### WHERE:

The WHERE keyword is used to specify conditions. This keyword is used when you need to retrieve information matching certain conditions.

Syntax

```sql
SELECT columns FROM table_name WHERE condition
```

```sql
SELECT * FROM Customers WHERE Country="Germany"
```
![Intro_7](../fig/Intro_7.JPG)

### DISTINCT:

The DISTINCTkeyword  is  used  to  select  and  display  all  the  unique  values  under  the specified column. The keywords in SQL can be combined to get necessary results based on what kind of results which is required. For example, to identify all the different countries in the table, to identify the different departments where employees work in a employee table etc.


Syntax

```sql
SELECT DISTINCT column_name FROM table_name
```

```sql
SELECT DISTINCT Country FROM Customers
```
![Intro_8](../fig/Intro_8.JPG)


```sql
SELECT DISTINCT Country FROM Customers WHERE Country="USA"
```
![Intro_9](../fig/Intro_9.JPG)

### ORDER BY:

The ORDER BYkeyword is used to display the results in a particular order. You can specify the name of the column (or) a number indicating the column position based on which the results need to be ordered. By default, the results are ordered in ascending order but canbe changed to descending using DESCkeyword. Ordering can also be done based on more than one column.

Syntax

ASCENDING ORDER

```sql
SELECT column_name FROM table_name ORDER BY column_name/column_number
```

DESCENDING ORDER
```sql
SELECT column_name FROM table_name ORDER BY column_name/column_number DESC
```

FIRST COLUMN DESCENDING AND SECOND COLUMN ASCENDING
```sql
SELECT column_name FROM table_name ORDER BY column_1 DESC, column_2
```

FIRST COLUMN ASCCENDING AND SECOND COLUMN DESCENDING
```sql
SELECT column_name FROM table_name ORDER BY column_1, column_2 DESC
```

Examples:

```sql
SELECT CustomerID, CustomerName, ContactName, City FROM Customers ORDER BY CustomerName
```
![Intro_10](../fig/Intro_10.JPG)

```sql
SELECT CustomerID, CustomerName, ContactName, City FROM Customers ORDER BY CustomerName DESC
```
![Intro_11](../fig/Intro_11.JPG)

{% include links.md %}
