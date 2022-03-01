---
title: "Joins"
teaching: 20


objectives:
- "Understanding the concepts of JOINS"
- "Data manipulation using Joins in SQL"
keypoints:
- "Familiarize the concepts of left join, right join, inner join, outer join and self join along with hands on examples"
---

## JOINS

A database generally comprises of multiple tables and a RDBMS comprises of tables which are related. When data is required to be extracted from two or more tables which are related to each other then we perform a join to combine the tables first and then extract the result.
![Joins_1](../fig/Joins__new_1.JPG)

Consider the below two tables which will be used for upcoming examples
![Joins_2](../fig/Joins__new_2.JPG)

![Joins_3](../fig/Joins__new_3.JPG)
### INNER JOIN:

The INNER  JOIN combines  tables  and  returns  the  records  only  when  there  is  an  exact match between the columns on which the join is performed.

#### Syntax:

```sql
SELECT columns FROM Table1 INNER JOIN Table2 ON Table1.column=Table2.column
```

#### Example:
```sql
SELECT Orders.OrderID, Customers.CustomerName
FROM Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID
```
![Joins_4](../fig/Joins__new_4.JPG)

### LEFT JOIN:

The LEFT JOIN combines tables and returns all the records from the left table. For records where there is no match in the right table it is displayed as a null Syntax

#### Syntax:

```sql
SELECT columns FROM Table1 LEFT JOIN Table2 ON Table1.column=Table2.column
```

#### Example:
```sql
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID
```
![Joins_5](../fig/Joins__new_5.JPG)

### RIGHT JOIN:

The RIGHT JOIN combines  tables  and  returns  all  the  records  from  the  right  table.  For records where there is no match in the left table it is displayed as a null

#### Syntax:

```sql
SELECT columns FROM Table1 RIGHT JOIN Table2 ON Table1.column=Table2.column
```

#### Example:
```sql
SELECT Orders.OrderID, Employees.LastName, Employees.FirstName
FROM Orders
RIGHT JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
```
![Joins_6](../fig/Joins__new_6.JPG)

### OUTER JOIN:

The OUTER JOIN combines tables and returns the records only when there is an exact match between the columns on which the join is performed.

#### Syntax:
```sql
SELECT columns FROM Table1 FULL OUTER JOIN Table2 ON Table1.column=Table2.column
```
![Joins_7](../fig/Joins__new_7.JPG)

### SELF JOIN:

A SELF-JOIN refers  to  a  condition  where  a  table  is  joined  with  itself.  We  do  not  use  a keyword for self-join but rather specify the name of the table twice (ach with a different alias) and then provide the joining condition in the WHERE clause.

#### Syntax:

```sql
SELECT columns FROM Table1 T1, Table2 T2 ON T1.column=T2.column
```

#### Example:

```sql
SELECT A.CustomerName AS CustomerName1, B.CustomerName AS CustomerName2, A.City
FROM Customers A, Customers B
WHERE A.CustomerID <> B.CustomerID
AND A.City = B.City
```
![Joins_8](../fig/Joins__new_8.JPG)

{% include links.md %}
