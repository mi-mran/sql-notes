Compiled SQL Notes & Examples :shipit:
=======================================

A personal reference for SQL concepts and commands for times when I walk into a restaurant and forget which tables I can join.

## Spreadsheets VS Databases

| Differences   | Pros          | Cons        |
|:-------------:|:-------------:| :-----------:|
| Spreadsheets  | easy to learn, accessible, easy to modify | varying truth versions, easy to make editing mistakes, no audit trail |
| Databases     | used when scope is beyond single table, single repo used by multiple users, limit duplication, logical relations      |         not as easily accessible / learnable as spreadsheets |



---



## Relational VS Non-relational (NoSQL) DBs

| Differences        | Features      |
|:-------------:     |:-------------:|
| Relational         | table-like data structure, set of tables for related data, set of logic governing tables |
| Non-relational     | effective for unstructured data |



---



## Database Management System (DBMS)

Allows user to define, create, maintain and control access to database


- data integrity -> *maintains data consistency*
- concurrency -> *allows mutliple users to access data simultaneously*
- security -> *prevents unauthorised access*
- recovery -> *allows for DB restoration in the event of hardware / software failure*



---



## Query Functions

### SELECT

```sql
SELECT <columns>
FROM <table_name>
WHERE <filter_conditions>
```



### WHERE Conditions

Definition | Symbol
--- | ---
Equals | =
Not Equals | < or > or !=
Greater Than | > or >=
Less Than | < or <=
In | IN '...'
Not In | NOT IN '...'
Between Values | BETWEEN '...' and '...'
Not Between Values | NOT BETWEEN '...' and '...'
Is Empty | IS NULL
Is Not Empty | IS NOT NULL

- multiple `WHERE` criteria can be used using `AND` or `OR`



### ORDER BY

- order results by column, specifying order using `ASC` or `DESC`

```sql
SELECT <columns>
FROM <table_name>
WHERE <filter_conditions>
ORDER BY <column> <order_direction>
```



### DISTINCT 

- shows non-repeated values for specified column

```sql
SELECT DISTINCT <column>
FROM <table_name>
```



### LIMIT

- can be useful when results are sorted (or when observing small sample of table)

```sql
SELECT <columns>
FROM <table_name>
ORDER BY <column> <order_direction>
LIMIT <number_of_rows>
```



