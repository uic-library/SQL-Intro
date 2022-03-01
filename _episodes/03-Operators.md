---
title: "Operators"
teaching: 20

objectives:
- "Understanding the concepts of Operators using SQL"
keypoints:
- "Familiarize with Arithmetic operations, Comparison operators and Logical Operators"
---

## OPERATORS

The  operators help  perform  operations on the  data  in  the table. They  can  be  used  to  perform arithmetic operations or filter based on certain conditions.

Consider the below table:

![Opt_1](../fig/opt_1.JPG)

### ARITHMETIC OPERATORS:

The arithmetic operators help perform arithmetic operations on the data in the table

![Opt_2](../fig/opt_2.JPG)

#### Example:

```sql
SELECT ProductID, Unit, Price, Price * Unit AS Total_sales, Price % Unit AS Modulo_result FROM Products
```
![Opt_3](../fig/opt_3.JPG)

### COMPARISON OPERATORS:

The  comparison  operators  are  used  to  filter  the  results  based  on  a  condition.  They  are generally passed in the WHERE clause and filters the result based on the condition provided.

![Opt_4](../fig/opt_4.JPG)

#### Syntax:

```sql
SELECT columns FROMv table_name WHERE condition <comparison_operator_of_choice> value
```

#### Examples:

```sql
SELECT ProductID, ProductName, Price FROM Products WHERE ProductID <= 15
```
![Opt_5](../fig/opt_5.JPG)

```sql
SELECT ProductID, ProductName, Price FROM Products WHERE Price = 18
```
![Opt_6](../fig/opt_6.JPG)

### LOGICAL OPERATORS:

SQL has three logical operators which can be used to specify more than one condition in the WHERE clause.

The three operators are:

* AND–Returns results when all the specified conditions are true
* OR–Returns results when at least one of the specified conditions are true
* NOT –Returns results when the opposite of conditions are true

#### Syntax:

```sql
SELECT columns FROM table_name WHERE condition1 AND/OR condition2
```

```sql
SELECT columns FROM table_namem WHERE NOTcondition
```

#### Examples:

```sql
SELECT CustomerName, Country, City, PostalCode
From Customers
Where Country = 'Brazil' AND City = 'São Paulo'
```
![Opt_7](../fig/opt_7.JPG)

```sql
SELECT CustomerName, Country, City, PostalCode
From Customers
Where City = 'Nantes' OR City = 'Paris'
```
![Opt_8](../fig/opt_8.JPG)

```sql
SELECT CustomerName, Country, City, PostalCode
From Customers
Where Not City = 'London'
```
![Opt_9](../fig/opt_9.JPG)

{% include links.md %}
