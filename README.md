Compiled SQL Notes & Examples :shipit:
=======================================

A personal reference for SQL concepts and commands for times when I walk into a restaurant and forget which tables I can join. (A work in progress)

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



## DB Integrity

1. Entity Integrity
    * Each row in a table represents a unique instance of an object / entity
    * Use primary keys to distinguish instances
    * Primary keys: cannot have null values & must have unique values

2. Domain Integrity
    * All columns have a pre-defined set of valid values
    * Columns must have fixed, known data type and length

3. Referential Integrity
    * Relations between tables must be correctly referenced
    * Value in one table that refers to value in another table must share domain
    * Enforced using foreign keys



---



## DB Modelling

Bottom Up (Normalisation) | Top Down (ER Modelling)
--- | ---
start with all fields in 1 table | create entity-relationship model
normalisation to split fields into separate tables | data & relationships represented graphically

### Rules of Modelling

Useful to maintain integrity of stored data by introducting constraints.

1. Relation names are distinct from all other relation names in the relational schema
2. 1 cell corresponds to 1 atomic value
3. Attributes in relations have distinct names
4. Values of an attribute are from the same domain
5. No duplicate tuples in a relation
6. Order of attributes does not have any significance
7. Order of tuples has no significance

### Normalisation

1. 1st Normal Form (1NF): domain only has atomic values (each row cannot contain more than 1 value)
2. 2nd Normal From (2NF): table is in 1NF and if there is a relation where primary key has multiple attributes, non-key attributes that are dependent on primary key should be separated
3. 3rd Normal Form (3NF): table is in 2NF and there should not be non-key attributes where a non-key attribute can be determined by another non-key attribute

### Relationships




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



### AGGREGATIONS

- `SUM` -> sums up non-null values of a column

```sql
SELECT SUM(<column>)
FROM <table_name>
```

- `AVG` -> returns average of non-null values of a column

```sql
SELECT AVG(<column>)
FROM <table_name>
```

- `MIN` -> returns smallest cell value

```sql
SELECT MIN(<column>)
FROM <table_name>
```

- `MAX` -> returns largest cell value

```sql
SELECT MAX(<column>)
FROM <table_name>
```

- `COUNT` -> returns number of non-null cells in a column

```sql
SELECT COUNT(<column>)
FROM <table_name>
```

> If you want to count all rows, use `COUNT(*)` or `COUNT(1)` instead



### FUNCTIONS (NON-CALCULATED)

- string functions

```sql
LENGTH, FORMAT, INSTR, LCASE, UCASE, LEFT, RIGHT, LOCATE, LTRIM, RTRIM, REPLACE, STRCOMP, SUBSTR
```

- date functions

```sql
MONTH, QUARTER, YEAR, DATEDIFF, DAYNAME, DAYOFWEEK, MONTHNAME
```

- data type

```sql
CAST, CONVERT
```



### ALIAS 

- temporarily shortens table name to make complex queries more manageable

```sql
SELECT <column_or_function> AS <alias_name>
FROM <table_name>
```

